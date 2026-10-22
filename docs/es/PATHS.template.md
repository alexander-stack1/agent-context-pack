# PATHS.md — rutas canónicas (plantilla)

> Capa 2, carga por disparador. Fuente única de la ruta local de cada repo, vault y carpeta de activos.

**Regla:** ningún otro archivo repite una ruta local; los demás referencian este. Excepción: el `CLAUDE.md` de un repo puede declarar su propia ruta.
**Cuándo cargar:** tareas con rutas de repo, clones, worktrees, deploys o scripts con rutas embebidas. Antes de afirmar una ruta, nunca después.
**Nunca afirmar una ruta de memoria.** Ausente aquí = NO VERIFICADO: decirlo y preguntar.

## Repositorios de código
| Producto | Ruta local | Remoto | Rama | Rol |
|---|---|---|:-:|---|
| `[PRODUCT_A]` | `~/dev/[product-a]` | `[YOUR_GITHUB]/[product-a]` (privado) | `main` | ... |
| `[PRODUCT_B]` | `~/dev/[product-b]` | `VERIFICAR` | `VERIFICAR` | ... |

## Contexto, vaults y activos
| Qué | Ruta | Nota |
|---|---|---|
| Contexto canónico | `[CONTEXT_DIR]` | Mapa en [`MANIFEST.md`](MANIFEST.md) |
| Vault operativo | `[OPS_VAULT]` | El humano lee, el LLM escribe |
| Vault de dominio | `[DOMAIN_VAULT]` | Enrutamiento obligatorio en pedidos de dominio |
| Credenciales | `[CONTEXT_DIR]/credentials/` | Nunca abrir, citar ni espejar |
| Despachos | `~/dev/dispatches` | Un archivo por despacho |

## Excepciones nombradas a la regla de `~/dev`
| Ruta | Motivo | Decidido el |
|---|---|---|
| `~/[product-x]` | Fuera de carpetas sincronizadas; fuente de deploy | `[DATE]` |

## Rutas retiradas, no usar
| Ruta | Estado |
|---|---|
| `[OLD_PATH]` | Retirada el `[DATE]`. Sustituida por `[NEW_PATH]` |

*Al mover o renombrar una carpeta, actualizar solo este archivo y registrarlo en el changelog.*
