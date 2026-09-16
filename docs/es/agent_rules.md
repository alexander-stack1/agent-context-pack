# agent_rules.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Reglas universales para cualquier IA que opere con el contexto de [YOUR_NAME].
> Lee este archivo PRIMERO. Funciona con Claude, Cursor, Codex, Kimi, [PRODUCT_F] y cualquier otro agente.
> Última actualización: 07/09/2026

## Fuente de verdad

Los archivos en `[CONTEXT_DIR]/` (en el [SECONDARY_MACHINE]: `[CONTEXT_DIR]`) son la fuente canónica operacional. La memoria del modelo sirve para enrutar, las preferencias estables viven en `.auto-memory/`, el conocimiento operacional/Karpathy vive en el vault `[YOUR_NAME]/`, y el segundo cerebro jurídico de dominio vive en `[DOMAIN_VAULT]` (atajo `[DOMAIN_VAULT]`). El historial del chat es contexto secundario.

Enrutamiento de dominio: si el pedido es jurídico (derecho, jurisprudencia, legislación, precedentes, doctrina, noticias jurídicas, RAG jurídico), **todas las IAs** deben apuntar y consultar el vault Jurídico (`[DOMAIN_VAULT]`). No uses solo la memoria del modelo en lugar de ese vault.

Para Claude/Cowork: leer `identity.md`, `stack.md`, `working-style.md` y `brand-voice.md`.
Para otros agentes: leer este archivo y seguir los punteros abajo.

| Archivo | Contenido | Cuándo leer |
|---------|-------------|------------|
| `identity.md` | Quién es [YOUR_NAME], frentes, estilo académico | Siempre |
| `stack.md` | Herramientas, MCPs, skills, plugins, infra IA | Siempre |
| `working-style.md` | Reglas de colaboración, protocolos, gobernanza | Siempre |
| `brand-voice.md` | Voz de las marcas, estilo de escritura canónico | Al producir texto |
| `_PROJETOS-ATIVOS.md` | Estado actual de los frentes | Cuando la tarea toque un proyecto |
| `_MANIFEST.md` | Mapa de skills por frente, estructura de la carpeta | Para enrutamiento |

## Reglas innegociables

### Captura y recuperación

1. Los archivos son el registro autoritativo. No uses la memoria del modelo como base de datos.
2. Nunca inventes hechos para rellenar campos vacíos. Declara incertidumbres.
3. Distingue relatos del usuario, hechos verificados, observaciones, preferencias e hipótesis.
4. Las correcciones del usuario tienen prioridad sobre resúmenes previos.
5. Usa fechas exactas cuando se conozcan. Registra explícitamente cuando sean aproximadas.
6. Los resúmenes responden "qué es verdad ahora". Los registros fechados responden "qué pasó y cuándo".
7. Antes de responder una pregunta sobre el usuario: busca en el vault, lee el resumen canónico, sigue enlaces de fuente. Solo después responde.

### Privacidad y exclusiones

Nunca almacenes: credenciales, contraseñas, cookies, códigos de recuperación, claves de API, seed phrases, tokens de autenticación, datos de pago, CPF, número de cuenta bancaria. Generaliza cuando haga falta. Nunca envíes contenido privado a terceros sin aprobación explícita.

### Escritura

1. Nunca uses la raya como conector de frases en prosa corrida
2. Nunca uses anticipación dramática ("y aquí es donde cambia el juego")
3. Nunca uses dos puntos explicativos de relleno ("la lección es directa: usa IA")
4. Nunca uses antítesis de negación + sustitución ("no es X, sino Y")
5. Nunca uses parataxis rítmica ("La pantalla abre. El botón hace clic.")
6. Nunca uses enclisis/mesoclisis artificiales
7. Nunca uses lenguaje de IA ("¡ciertamente!", "¡excelente pregunta!", "¡con gusto!")
8. Nunca uses frases de relleno ("es importante señalar que", "cabe destacar")
9. Ejecuta `[SKILL_NO_TROPES]` como posprocesamiento en toda prosa generada

### Ingeniería

1. Sin compatibilidad hacia atrás. Obsoleto = borrar directo.
2. Implementación más simple que cumpla la necesidad actual. Canaliza energía en YAGNI.
3. Capas largas, end-to-end primero. Nunca desarmes lo que funciona.
4. Componentes modulares con separación de responsabilidades.
5. Bibliotecas maduras. Sin motivo, no reescribas desde cero.
6. Dependencias existentes primero, antes de añadir paquetes.
7. Decisiones de arquitectura de largo plazo. Sin "por ahora hazlo así".
8. Patrones validados de productos maduros. No reinventes la rueda.
9. Typesafety es útil; úsala. TypeScript: `any` es el enemigo; los tipos inferidos son aliados. Los sistemas deben adaptarse al cambio sin exigir ediciones en todos lados. Si el TS parece Python escrito por un pythonista, está mal.
10. Los comentarios describen de forma concisa cómo se usan funciones y clases. No comentes cada línea. Mantén comentarios en sync con el código al cambiar.
11. Tests enfocados. Los tests son buenos. Smoke infinito, regresión de features borradas y tests genéricos son malos. Cada test debe tener propósito claro.
12. Verificación de versión. Antes de generar código con framework o biblioteca específica, confirma que el modelo conoce la versión en uso. Si no, o hay duda, consulta Context7 MCP o la documentación oficial antes de asumir API, sintaxis o comportamiento. Nunca generes código basado en versión antigua sin avisar.
13. Contexto progresivo. Empieza por Camada 1 del _MANIFEST (identity, stack, working-style, brand-voice). Carga Camada 2 solo cuando la tarea toque ese dominio. Nunca cargues Camada 3 sin pedido explícito. No ensucies el contexto con información que la tarea no necesita.
14. Debugging guiado por error. Antes de proponer un fix, exige o busca: error completo con stack trace, código del tramo relevante, respuesta de API o log cuando aplique, y comportamiento esperado vs actual. No diagnostiques con información parcial. Si falta alguno de esos 4 elementos, pregunta antes de actuar.
15. Justificación de componente. Antes de proponer nuevo servicio, base, cola, caché o dependencia de infra, responde: "¿qué problema específico resuelve esto que la infra actual no resuelve?" Si la respuesta es vaga ("escalabilidad", "desacoplamiento"), la propuesta no está lista.
16. Estimación de capacidad. Antes de una decisión de infra que elija entre tecnologías (SQL vs NoSQL, Cloud Run vs VM, con caché vs sin), estima el sobre: QPS esperado, volumen de storage, bandwidth, usuarios concurrentes. Decisión de infra sin números es opinión, no ingeniería.
17. Modos de fallo explícitos. Toda propuesta de arquitectura incluye una sección "qué se rompe si esto falla". Lista de forma proactiva: punto único de fallo, comportamiento con red degradada, qué pasa si el servicio externo no está disponible, y el plan de degradación elegante. Trae la historia de fallo antes de que te la pidan.
18. MCP bidireccional. Al construir capacidad interna vía MCP tools, evalúa si debe exponerse como MCP server para otros agentes. Un agente que solo consume herramientas es un endpoint. Un agente que también sirve es infraestructura. La exposición exige control de acceso real porque cualquier caller puede golpear la capa de razonamiento directamente.
19. Validación única entre caminos. Al implementar fallback (modelo alternativo, degradación, retry), la función de validación del output es una sola, compartida por todos los caminos. Nunca dupliques validación entre camino primario y fallback. Si la validación vive en dos sitios, actualizar uno y olvidar el otro significa entregar dos productos distintos con una sola etiqueta.

### PostgreSQL

- Toda tabla accesible por el cliente tiene RLS habilitado y al menos una política por operación (SELECT, INSERT, UPDATE, DELETE). Una tabla sin RLS habilitado accesible por un rol con NOBYPASSRLS es un agujero, no protección.
- SQL siempre parametrizado. Fragmentos interpolados solo de allowlists internas cerradas. Nunca concatenes input externo en una query.
- Migrations versionadas y reversibles. Toda migration tiene un up y un down. Prueba el down antes de mergear. Nunca ejecutes migration en producción sin backup previo.
- Índices creados con CONCURRENTLY en tablas con datos en producción. Un índice que bloquea la tabla es downtime disfrazado.
- Naming: snake_case para tablas, columnas y funciones. Prefijo de dominio cuando el schema tenga más de 20 tablas (p. ej. `billing_invoices`, `auth_sessions`). Claves primarias como `id` (UUID v7 o serial), foreign keys como `<tabla>_id`.
- Constraints en la base, no solo en la aplicación. NOT NULL, CHECK, UNIQUE y FK existen para atrapar lo que la aplicación deje pasar.
- Connection pooling obligatorio en producción (PgBouncer o pooler de Supabase). La aplicación nunca abre conexión directa a Postgres en producción.
- Queries explicadas antes de mergear: ejecuta EXPLAIN ANALYZE en queries nuevas que toquen tablas con más de 100k rows. Seq scan en tabla grande sin filtro es red flag.
- Backups automáticos con retención mínima de 7 días. Prueba restore periódicamente. Un backup que nunca se restauró es esperanza, no protección.
- Roles separadas: la aplicación usa rol con permisos mínimos (SELECT/INSERT/UPDATE donde haga falta). Las migrations usan rol con DDL. Nunca ejecutes la aplicación como superuser.

### Docker

- Imágenes basadas en variantes slim o alpine. Imagen de producción sin compilador, debugger o shell interactivo cuando sea posible.
- Multi-stage build obligatorio: stage de build (con devDependencies, compilador, tsc) separado del stage de runtime (solo artefactos finales y dependencias de producción).
- Un proceso por contenedor. Si el servicio necesita worker + web, son dos contenedores, no un entrypoint con supervisor.
- Nunca correr como root. Define USER en el Dockerfile. Si la imagen base corre como root, crea un usuario sin privilegios.
- Mantén .dockerignore: node_modules, .git, .env, tests, docs y artefactos de build local quedan fuera del contexto de build.
- Health check definido en el Dockerfile o en el compose. Un contenedor sin health check es una caja negra para el orquestador.
- Variables de entorno para configuración, nunca hardcodeadas. Secretos vía secret manager o mount, nunca como ENV en el Dockerfile o docker-compose.yml versionado.
- Layers ordenadas de lo menos mutable (apt-get, COPY package.json) a lo más mutable (COPY . .). La caché de layers ahorra minutos de build.
- Tag de imagen fija en producción (nunca `latest`). Usa hash del commit o semver. `latest` en producción es ruleta.
- Logs en stdout/stderr. Nunca escribas log a un archivo dentro del contenedor. El orquestador recoge de stdout.

### Kubernetes

Aplicar cuando el proyecto use K8s (Cloud Run con Knative cuenta como subset):
- Todo deployment con resource requests y limits definidos. Un pod sin request es invisible para el scheduler. Un pod sin limit puede tumbar el node.
- Liveness probe verifica si el proceso está vivo. Readiness probe verifica si puede recibir tráfico. Startup probe para apps con boot lento. Nunca uses la misma probe para liveness y readiness.
- Al menos 2 réplicas en producción. Una réplica es single point of failure durante deploy, node drain o crash.
- Rolling update con maxSurge y maxUnavailable configurados. Nunca 100% unavailable durante deploy.
- Pod Disruption Budget (PDB) para servicios críticos. Sin PDB, el cluster puede drenar todos los pods del servicio a la vez durante mantenimiento de node.
- Secrets vía Secret o external secret operator (Vault, GCP Secret Manager). Nunca en ConfigMap, nunca en variable de entorno visible en el manifiesto versionado.
- Namespace por entorno (dev, staging, prod). Nunca mezcles workloads de entornos distintos en el mismo namespace.
- Network policies restrictivas: deny-all por defecto, liberar solo el tráfico necesario entre servicios. Sin network policy, todo pod habla con todo pod.
- Las imágenes vienen de registry privado o de registries públicos allowlisted. Nunca tires una imagen de un registry arbitrario en producción.
- Observabilidad: métricas (Prometheus/Datadog), logs (stdout recogido por Fluentd/Vector), traces (OpenTelemetry). Un pod sin observabilidad es black box en un incidente.
- GitOps cuando sea posible: estado deseado del cluster declarado en Git (ArgoCD, Flux). kubectl apply manual en producción es anti-pattern.

### Swift

Aplicar cuando el proyecto use Swift/SwiftUI:
- Decodifica datos del servidor con tolerancia (opcionales para cualquier campo que el servidor pueda añadir, omitir o renombrar). Nunca crashees por campos desconocidos.
- Haz el ownership asíncrono explícito. Cancelación, resultados obsoletos y eventos duplicados son normales. Nunca mutes estado después de que la view o task que lo controla haya desaparecido.
- Salvo indicación contraria del proyecto, construye en Swift 5 language mode con concurrency dirigida. Corrige lo que indiquen las build flags, sin anticipar lo que exigiría Swift 6 estricto.

### Las preguntas son read-only

Una pregunta es pedido de respuesta, no de cambio. Si el mensaje abre con "qué tan difícil sería", "qué opinas", "por qué esto", "debemos", "es posible", "¿X puede hacer Y?", o cualquier otra forma interrogativa: responde primero, sin editar archivos. Si la respuesta es obvia y el cambio trivial, aun así responde y ofrece el cambio. Pregunta antes de hacer.

### Trabajo visual y diseño

Para cualquier cambio no trivial de UI, layout o copy: construye varias variantes estáticas primero, preséntalas para elección y espera la decisión antes de implementar en el componente real. Skills de referencia: `impeccable`, `visual-verify`, `[SKILL_DESIGN_A]`.

Evita animaciones que repinten continuamente (pulse, shimmer, blur, spinners que no paran). Toda animación respeta Reduce Motion.

### Radio de impacto

Nunca toques apps de producción, servidores live, canales de release o datos de uso diario sin instrucción explícita. Cuando la tarea sea adyacente a cualquiera de ellos, nombra lo que vas a tocar antes de tocar.

### Pull Requests

Los PRs siguen las reglas de `[SKILL_COMMIT_PR]` (draft por defecto, Conventional Commits). Además:
- La descripción abre con descripción mínima y clara del problema, seguida de cómo se resolvió
- Añade al final qué modelo y harness hizo los cambios
- Al referenciar issue o PR, usa hyperlink
- Al monitorear PR: haz poll de checks y comentarios más recientes que el último push. Verifica cada hallazgo de bot contra el código fuente antes de actuar. Corrige los reales y descarta falsos positivos con justificación escrita. Corrige fallos de CI, distinguiendo breaks reales de flakes de infra conocidos. Si nada es nuevo, quédate en silencio. Para cuando los review bots estén verdes en el último commit
- Merge solo según la disposición dada en el pedido (merge when green, o parar y reportar)

### Ceremonia proporcional (S / M / C)

Antes del plan, clasifica el esfuerzo: **S** (simple), **M** (media), **C** (compleja).
Declara: `Esfuerzo: S|M|C — motivo: …`.

- Detalle canónico: `working-style.md` → Clasificación de esfuerzo.
- **S:** two-way door, fuera de la blacklist, pedido inequívoco → plan de 1 línea; sin suite integral; sin multiagente.
- **M:** comportamiento local → TDD + tests del paquete.
- **C:** auth/RLS/migration/deploy/prod/money o duda → rito completo.
- Blacklist y fail-closed: ver working-style. En duda, **C**.
- Memoria por proyecto: `CLAUDE.md` / `docs/agent/REPO_MAP.md` del repo (templates en `[CONTEXT_DIR]/templates-agent/`). En S, no releas la Camada 1 entera si la sesión ya la cargó.
- No dispares subagentes para trabajo de un paso. La delegación es para amplitud o revisión adversarial. En paralelo, declara ownership de archivos.

### Calidad

Cada entregable listo para uso inmediato. Sin retrabajo. Si la confianza es baja, señaliza en lugar de entregar algo dudoso. Plan según S/M/C. Pregunta antes de adivinar.

## Protocolo de captura rápida

Cuando el usuario aporte información durable en conversación casual:

1. Evalúa si es estable y útil como para guardarla
2. Busca la nota existente antes de crear una nueva
3. Anexa a un evento existente del mismo día cuando sea posible
4. Preserva las palabras del usuario cuando la matiz importe
5. Actualiza el menor conjunto de archivos autoritativos
6. Actualiza el resumen canónico solo si la información cambia el entendimiento actual
7. Confirma la captura brevemente

Para importaciones grandes: preservar original + resumen fundamentado en la fuente.

## Protocolo de recuperación

Antes de responder una pregunta sobre el usuario:

1. Leer este `agent_rules.md`
2. Buscar en los archivos del vault (wiki/, raw/)
3. Leer el resumen canónico relevante
4. Leer eventos y notas más recientes
5. Seguir enlaces de fuente para afirmaciones consecuentes
6. Distinguir contexto actual, histórico, resuelto, incierto y sustituido
7. Declarar incertidumbres y conflictos explícitamente
8. Citar rutas de notas y fechas cuando la precisión importe

### Seguridad

Playbook completo (copiable): `appsec-rules.md`. Resumen y CI/CD también en `working-style.md` § Seguridad de aplicaciones. Skills de referencia: `[SKILL_SECURITY_SQUAD]`, `[AGENT_TEAM]:appsec`, `[SKILL_CODE_REVIEW]` (categoría seguridad).

Resumen para cualquier agente:
1. Todo repositorio con SECURITY.md, secret scanning, Dependabot, CodeQL y branch protection
2. Secretos nunca en código/frontend/log. Representar como [REDACTED]
3. Autorización decidida en el servidor. Checks de interfaz no cuentan
4. RLS en toda tabla accesible por el cliente. SQL parametrizado
5. Inputs validados server-side. Uploads con magic bytes y nombre generado por el servidor
6. Rate limit separado pre-auth y post-auth
7. OAuth 2.1 con PKCE. Redirect URIs con allowlist exacta
8. Deploy con suite integral → canario → smoke → promoción explícita
9. Hallazgos clasificados como OK | HALLAZGO | NO APLICABLE | NO VERIFICADO
10. Solo "APROBADO" si cero hallazgos bloqueantes + evidencia verificable

## Punteros

- Vault Obsidian operacional: `[CONTEXT_DIR]/[YOUR_NAME]/` ([SECONDARY_MACHINE]: `[CONTEXT_DIR]/[YOUR_NAME]`)
- Vault Obsidian Jurídico (segundo cerebro): `[DOMAIN_VAULT]` (atajo `[DOMAIN_VAULT]`)
- MOCs: `[YOUR_NAME]/wiki/00-indices/`
- Memoria persistente Claude: `.auto-memory/MEMORY.md`
- Preguntas abiertas: `[YOUR_NAME]/wiki/00-indices/open_questions.md`
- Changelog estructural: `_CHANGELOG.md`

---
*Este archivo es la puerta de entrada para cualquier IA. Actualiza cuando cambien reglas fundamentales. Registra en `_CHANGELOG.md`.*
