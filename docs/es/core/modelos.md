# modelos.md — matriz de modelos y esfuerzo (fuente única)

> Plantilla. Rellena con los IDs exactos de la documentación oficial de cada proveedor y la fecha de verificación. Nunca rellenar un ID de memoria.

Roles: **ORQ** (orquestación y planificación), **PES** (razonamiento pesado), **EXE** (ejecutor), **SIM** (búsqueda, triaje, extracción).
Formato: modelo | ID exacto | esfuerzo por defecto | esfuerzo máximo. Máximo solo por orden humana o clase C en blacklist.

| Herramienta | ORQ | PES | EXE (especificada / difícil) | SIM |
|---|---|---|---|---|
| `[AGENT_CLI_A]` | `[MODEL_ORQ]` medium | `[MODEL_PES]` high | `[MODEL_EXE]` medium / high | `[MODEL_SIM]` low |
| `[AGENT_CLI_B]` | ... | ... | ... | ... |
| `[IDE_AGENT]` | ... | ... | ... | ... |

## S/M/C a modelo y esfuerzo

| Clase | Decide y planifica | Ejecuta | Revisa | Subagente |
|---|---|---|---|---|
| S (two-way door, fuera de blacklist) | La propia sesión | Inline; delegación mecánica a SIM low | Nadie | Solo búsqueda/triaje |
| M (bug o feature verificable, TDD) | ORQ medium | EXE medium (high si el test falla 2 veces) | Tests y lint; revisión ORQ | 1 EXE por módulo |
| C (blacklist, producción, dinero, duda) | ORQ high, plan y aprobación humana | EXE high | PES high con contexto limpio (adversarial) | EXE high, SIM low |

Reglas: en duda, C. El prefijo `[S]` no vence a la blacklist. El revisor nunca es el modelo que escribió. La redacción final de dominio queda con ORQ o PES, nunca SIM.
Modelos que exigen retención de datos en el proveedor nunca reciben datos de cliente.

## Fuentes
Lista aquí la URL oficial de cada ID y de cada parámetro de esfuerzo.
