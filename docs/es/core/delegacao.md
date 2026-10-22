# delegacao.md — roles y contrato

Roles: **orquestador** (decide, divide, revisa, integra, habla con el humano), **razonamiento pesado** (análisis profundo y revisión adversarial), **ejecutor** (implementa un artefacto), **simple** (búsqueda, triaje, extracción).

## Despacho
```
DESPACHO <id>
dueño: <un subagente>   modelo/esfuerzo: <x>   herramientas: <lista mínima>
objetivo: <1 frase>
artefacto: <1 ruta de salida>   (nada fuera de ella)
alcance: repo/rama/commit, archivos permitidos; fuera de alcance = NO VERIFICADO
prueba: <comando o criterio que el orquestador ejecutará o leerá>
prohibido: secretos, credentials/, push, correo, deploy, borrar
gate humano: <qué vuelve al humano antes de seguir>
presupuesto: <tiempo y tokens máximos>
entrega: resumen corto + evidencia (salida de comando, archivo:línea)
```

## Handoff estructurado (retorno)
```
HANDOFF <id>
hecho: <qué cambió, con rutas>
prueba: <salida de comando / archivo:línea>
no hecho / bloqueado: <motivo>
riesgos y NO VERIFICADO: <lista>
siguiente paso: <1 línea>
```

## Reglas del orquestador
1. Lee y contrasta toda salida con la prueba. 2. No reenvía secretos ni datos de cliente a quien no los necesita. 3. Los ejecutores no tienen herramientas de envío, push, deploy ni pago. 4. En C, revisor adversarial con contexto limpio y modelo distinto del ejecutor. 5. Un dueño por archivo, profundidad 1. 6. Lo registra. 7. Duda de clase se vuelve C.

## Cuándo delegar
Delegar: amplitud, lotes repetitivos, revisión independiente (siempre en C), exploración que contamina el contexto, trabajo paralelo con dueños distintos. Inline: clase S, un archivo, decisiones, redacción final de dominio, todo lo que dependa del contexto de la conversación.
