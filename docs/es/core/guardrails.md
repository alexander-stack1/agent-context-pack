# guardrails.md — trabas por hook

> Plantilla pública. Ajusta topes, rutas y scripts en tu overlay privado.

Principio: una tarea clara llega hasta el final; el hook sostiene las líneas rojas sin pedir ok. Un error interno del guard tras el parse **bloquea** (fail-closed).

## Bloqueo duro, sin liberación
1. **Credenciales:** lectura de `credentials/`, `.env*` (salvo `.env.example`, `.env.sample`, `.env.template`), `~/.ssh`, archivos de auth de las CLIs de agente y storageState de pruebas.
2. **Secretos:** `printenv`, `env`, lectura directa del cofre impresa en terminal, `echo` de variables secretas. Secretos solo por inyección (`[VAULT_CLI] run ...`).
3. **Push:** force push (`--force`, `-f`, `--force-with-lease`, refspec con `+`), push a `main`/`master`, borrar `main` o tocar su protección. Push de otras ramas es libre.
4. **Commit:** nunca `--no-verify`. Los hooks son parte de la prueba.
5. **Merge:** solo por `scripts/merge-safe.sh` (CI verde, aprobación ligada al sha del head, squash con `--match-head-commit`, nunca `--admin`).
6. **Deploy:** solo por `scripts/deploy-safe.sh` (versión anterior conocida, rollback definido, smoke test y rollback automático si falla).
7. **Dinero:** APIs de pago en producción solo vía wrapper con tope por operación y por día (`config/limits.toml`); sin reembolsos, webhooks, claves, cuentas ni transferencias; log de todo.
8. **Datos de producción:** `DROP`, `TRUNCATE` o `DELETE` sin `WHERE` fuera de BD local/prueba; borrar bases, buckets o repos; migraciones remotas fuera de `scripts/migrate-prod.sh` (rechaza destructivas, snapshot antes).
9. **Datos de cliente:** subidas (`scp`, `rsync` remoto, `curl` upload, CLIs de nube, gist, MCPs de subida) de rutas listadas en `config/client-data.txt`.
10. **Subagente solo lectura:** sin Edit, Write, patch ni shell que escriba.

## Bloqueo con liberación temporal (solo en la terminal humana)
11. Envíos externos (correo, chat, pagos). Correo y mensajes van como borrador.
12. Destructivo local: `rm -rf` fuera del repo actual o `/tmp`; `reset --hard`, `clean -f`, `branch -D` en `main` o con cwd desconocido.

## Solo aviso
13. Blacklist S/M/C sin `Esfuerzo: C` declarado (rito, no licencia); escritura en carpetas sincronizadas (iCloud/Drive) o papelera.
14. PostToolUse: aviso cuando la salida parece contener un secreto.
15. Recordatorio de verificación de fuente en pedidos de dominio.

## Operación local
- Servidores de desarrollo solo en `127.0.0.1`, nunca `0.0.0.0`. Paneles administrativos cerrados a internet.
- Antes de editar un canónico o config: backup al lado con sello `archivo.bak-AAAAMMDD-HHMMSS-[REASON]`.
- Código fuera de carpetas sincronizadas, en `~/dev` por convención (excepciones nombradas en `PATHS.md`).

## Registro y prueba
- Cada decisión (allow, aviso, deny, allow-aprobado) va a `logs/harness.jsonl`, solo metadatos.
- `evals/` reproduce payloads de las CLIs contra el guard; `sync-harness --check` ejecuta los evals.
- Implementación de referencia: un único `guard-pretooluse` leído por todas las CLIs con hooks.

## Tamaño de archivo
- Archivo escrito por agente: hasta ~5.000 tokens (≈ 20.000 bytes). El hook pre-commit mide solo los staged.
- Excluidos: lockfiles, código generado, binarios/activos, `@generated`/`DO NOT EDIT`, y `.agent-size-ignore` (con justificación).
- Dividir por responsabilidad, nunca por número de líneas; preservar la API pública con reexport; ejecutar build, lint y tests.
