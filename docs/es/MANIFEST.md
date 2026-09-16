# _MANIFEST.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Archivo de orientación de contexto, leído por Claude antes de cualquier tarea en esta carpeta.
> Última actualización: 13/09/2026 (vault Jurídico como segundo cerebro)

---

## Sobre esta carpeta

Esta es la carpeta de contexto canónico de [YOUR_NAME] ([YOUR_HANDLE]): [YOUR_ROLE], académico ([YOUR_UNIVERSITY]) y fundador de productos [YOUR_INDUSTRY]. La carpeta reúne la identidad de trabajo, la voz de las marcas, las reglas de colaboración, el estado de los proyectos y el vault de conocimiento.

The `[CONTEXT_DIR]/` folder (on the [SECONDARY_MACHINE]: `[CONTEXT_DIR]`) es la **única** fuente de contexto operacional canónico. Cualquier asistente, en cualquier máquina, debe leer exclusivamente los archivos de esta carpeta antes de iniciar tareas.

Hay dos vaults Obsidian, con roles distintos:

- **Context / `[YOUR_NAME]/`**: vault operacional (método Karpathy: el humano lee, el LLM escribe).
- **Legal**: segundo cerebro de dominio para todos los agentes: `[DOMAIN_VAULT]` (atajo `[DOMAIN_VAULT]` en el [SECONDARY_MACHINE]; ~4.5k notes: jurisprudencia, legislación, noticias, RAG, precedentes). No sustituye la Camada 1 de esta carpeta.

**Enrutamiento obligatorio:** en cualquier pedido relacionado con derecho, jurisprudencia, legislación, precedentes, doctrina, noticias jurídicas, RAG jurídico o investigación de dominio legal, **todas las IAs y agentes** deben consultar y apuntar al vault Jurídico (`[DOMAIN_VAULT]`) antes de inventar o improvisar. El `[YOUR_NAME]/` vault sigue solo para contexto operacional y el método Karpathy.

Flujo Karpathy en `[YOUR_NAME]/`:

1. Capturar en `raw/` (fechado).
2. Compilar en `wiki/<domain>/` (nota temática durable).
3. Consultar vía MOCs en `wiki/00-indices/`.
4. Mantener con revisiones periódicas (health check quincenal).

---

## CAMADA 1, Documentos canónicos
> Lee estos archivos PRIMERO, en cualquier sesión. Son la fuente de verdad actual.

| Archivo | Descripción | Frecuencia de actualización |
|---------|-----------|:------------------------:|
| `agent_rules.md` | Reglas universales para cualquier IA (puerta de entrada agnóstica) | Mensual |
| `senior-implementer-instructions.md` | Compilación operacional para implementador de código sénior (humano o agente): DoD, TDD, Postgres/Docker/K8s, seguridad, staged-write | Cuando cambie la ingeniería en los canónicos |
| `about-me.md` | Puntero de contexto: prioridades, reglas operacionales, método del vault | Mensual |
| `identity.md` | Quién es [YOUR_NAME], frentes profesionales, estilo académico, patrones anti-IA | Semestral |
| `stack.md` | Herramientas, MCPs, skills, plugins, LightRAG, pipeline RAG, subagentes | Semanal |
| `working-style.md` | Reglas de colaboración, protocolos de investigación e ingeniería, gobernanza de agentes, seguridad de aplicaciones para cualquier IA que audite código | Mensual |
| `templates-agent/` | Templates de memoria por repo (`CLAUDE.md`, `REPO_MAP`, `DECISIONS`, boot) + S/M/C reference; S/M/C canónico en working-style | Cuando cambie el boot de agente |
| `brand-voice.md` | Voz de las marcas, estilo de escritura académico y técnico largo canónico | Semestral |
| `ux-ui-INDEX.md` | Enrutamiento UX/UI (WEB vs MOBILE), R0 y color 60-30-10; cargar en tareas de interfaz | Continuo |
| `ux-ui-criteria.md` | Criterios MUST/MUST-NOT de UI (Norman/Krug/Yablonski/Refactoring UI/Johnson) + checklist | Continuo |
| `ux-ui-web-landing.md` | Subreglas y PASOS 0–14 para landing WEB | Continuo |
| `ux-ui-mobile.md` | Subreglas MOBILE (landing / app / chat) | Continuo |
| `ux-ui-REQUESTS.md` | Menú condensado: qué pedir (7 skills PT) al contratar/refactorizar UI | Continuo |
| `_PROJETOS-ATIVOS.md` | Estado actual y próximos pasos de cada frente | Semanal |
| `[YOUR_NAME]/wiki/00-indices/_HOME.md` | Panel de entrada del vault de conocimiento | Continuo |
| `[YOUR_NAME]/wiki/00-indices/open_questions.md` | Preguntas abiertas, incertidumbres y decisiones pendientes | Continuo |

---

## CAMADA 2, Dominios
> Carga solo cuando la tarea toque explícitamente ese dominio.

### Conocimiento (vault `[YOUR_NAME]/`)

| Ruta | Dominio | Cuándo cargar |
|---------|---------|----------------|
| `[YOUR_NAME]/wiki/00-indices/` | MOCs e índices por dominio | Punto de partida de cualquier investigación en el vault |
| `[YOUR_NAME]/wiki/direito-trabalho/` | Contenido laboral compilado | Tareas de Derecho del Trabajo |
| `[YOUR_NAME]/wiki/concursos/` | Materias de procuraduría ([ORG_A], [ORG_B]) | Estudio para concursos |
| `[YOUR_NAME]/wiki/[PRODUCT_A]/` | Producto, design system, features | [PRODUCT_A] and [PRODUCT_B] tareas |
| `[YOUR_NAME]/wiki/tech/` | Tech, IA local, diseño, programación | Technical and tareas de automatización |
| `ux-ui-*.md` (root) | Criterios y pasos WEB/MOBILE para agentes de UI | Cualquier UI, landing, app shell o chat |
| `[YOUR_NAME]/raw/` | Captura bruta fechada | Antes de compilar una nota nueva en la wiki |
| `[YOUR_NAME]/Clippings/` | Recortes web triados | Consulta de material guardado |

### Operación y activos

| Ruta | Dominio | Cuándo cargar |
|---------|---------|----------------|
| `ativos-[YOUR_FIRM]/` | [YOUR_FIRM] papel membretado y logo | Generación de piezas y documentos del despacho |
| `credenciais/` | Credenciales de integración | Solo en tareas de automatización que exijan acceso (ver `_PARA-REVISAR.md`) |
| `appsec-rules.md` | Playbook fail-closed completo (10 reglas + matriz + APROBADO); pegar en Project Claude AppSec | Auditoría, review de seguridad, corrección auth/secrets/deploy |
| `documentos/` | Documentos sueltos y estado de proyectos | Consulta puntual |
| `[BRAND_KIT_DIR]/` | [YOUR_COMPANY] kit de marca: logo, paleta, tipografía, avatares, firmas y piezas por red. Reglas en `[BRAND_KIT_DIR]/logo-rules.md` | Cualquier pieza visual de [YOUR_COMPANY] |

---

## CAMADA 3, Archivo (Ignorar por defecto)
> NO cargues a menos que [YOUR_NAME] lo pida explícitamente.

| Ruta | Contenido |
|---------|----------|
| `documentos/_arquivo/` | Estados y documentos antiguos, mantenidos por historial |
| `changelog/` | Backups y versiones anteriores de Manifest/Changelog/Proyectos |
| `[YOUR_NAME]/trash/` | Cuarentena antes de eliminación |
| `*_v1`, `*_v2`, `*_old`, `*_backup` | Versiones anteriores de archivos |

---

## Skills por frente
> Mapa de enrutamiento. Al identificar el frente de la tarea, prefiere estas skills.

### [PRACTICE_AREA]

| Tarea | Skill |
|--------|-------|
| Leer proceso nuevo, síntesis de pieza | `[SKILL_CASE_SUMMARY]` |
| Petición, réplica, memoriales (1ª instancia) | `[SKILL_DOMAIN_DRAFTING]` |
| Cálculo y propuesta de acuerdo | `[SKILL_SETTLEMENT_CALC]` |
| Laudo y cálculo pericial | `[SKILL_EXPERT_REPORT]` |
| Impugnar cálculo o laudo | `[SKILL_CALC_CHALLENGE]` |
| Recurso de revista, embargos, agravo | `[SKILL_APPEALS]` |
| Contrarréplicas a recurso patronal | `[SKILL_COUNTER_APPEAL]` |
| Ejecución y liquidación | `[SKILL_ENFORCEMENT]` |
| Investigación de jurisprudencia | `[SKILL_CASELAW_SEARCH]`, `[SKILL_CASELAW_SEARCH_B]` |
| Doctrina de proceso del trabajo (competencia, plazos, nulidades, recursos, ejecución) | `[SKILL_DOMAIN_BOOK]` (libro de [BOOK_AUTHOR] convertido; repo privado `[YOUR_GITHUB]/[SKILL_DOMAIN_BOOK]`) |
| Verificar ley o tramitación | `[SKILL_LAW_CHECK]` |

### Académico ([YOUR_UNIVERSITY], doctorado)

| Tarea | Skill |
|--------|-------|
| Escribir o revisar artículo, tesis, capítulo | `[SKILL_ACADEMIC_REVIEW]` |
| Análisis doctrinal y anteproyecto | `[SKILL_ACADEMIC_ADVISOR]` |
| Documento de estudio en ABNT | `[SKILL_STUDY_DOC]` |
| Análisis de fallo del STF | `[SKILL_COURT_ANALYSIS]` |

### Legaltech y producto

| Tarea | Skill |
|--------|-------|
| Inteligencia de mercado legaltech | `[SKILL_MARKET_INTEL]` |
| PRD a partir de la conversación | `[SKILL_PRD]` |
| Romper plan en issues | `[SKILL_ISSUES]` |
| Triaje de issues | `[SKILL_TRIAGE]` |
| Evaluar relevancia de búsqueda o RAG jurídico (nota 0 a 3, precisión, recall, golden set) | `[SKILL_RETRIEVAL_EVAL]` |

### Desarrollo y automatización

| Tarea | Skill |
|--------|-------|
| Orquestación y arquitectura por equipo | `[AGENT_TEAM]` (cto, backend, frontend, devops, dba, qa) |
| Contrato operacional del implementador sénior (DoD, TDD, infra, seguridad) | `senior-implementer-instructions.md` (Camada 1) |
| Revisión de código completa | `[SKILL_CODE_REVIEW]` |
| Análisis de sistema de punta a punta | `[SKILL_E2E_ANALYSIS]` |
| Commit, push y PR | `[SKILL_COMMIT_PR]` |
| Diagramas de arquitectura interactivos | `archify` (architecture, workflow, sequence, data-flow, lifecycle) |
| TDD red-green-refactor | `tdd` |
| Debugging disciplinado | `diagnose` |
| Deepening de módulos | `improve-codebase-architecture` |
| Explicar código en el contexto del sistema | `zoom-out` |
| Prototipo descartable | `prototype` |
| Code review Standards + Spec | `review` |
| Plan de refactor en commits minúsculos | `request-refactor-plan` |
| Handoff de contexto entre sesiones | `handoff` |
| Grilling contra modelo de dominio | `grill-with-docs` |
| Inteligencia competitiva SaaS | `[PRODUCT_C]` |
| Socio de producto (idea al lanzamiento) | `product-partner` |

### Infraestructura y operaciones

| Tarea | Referencia |
|--------|-----------|
| Visualización de arquitectura (diagramas interactivos HTML/SVG) | `archify` (5 types: architecture, workflow, sequence, data-flow, lifecycle) |
| Cloud Run (deploy, scaling, troubleshooting) | `cloud-run-basics` (Google) |
| Cloud SQL PostgreSQL | `cloud-sql-basics` (Google) |
| gcloud CLI | `gcloud` (Google) |
| Managed Agents API (multi-agent) | `gemini-agents-api` (Google) |
| RAG Engine Management | `agent-platform-rag-engine-management` (Google) |
| Cloud Monitoring (charts) | `cloud-monitoring-chart-generation` (Google) |
| Cloud Logging (LQL queries) | `cloud-logging-query-generation` (Google) |
| IAM troubleshooting | `iam-helper-for-troubleshooting` (Google) |
| Well-Architected Reliability | `google-cloud-waf-reliability` (Google) |
| Solution Architecture workflow | `google-cloud-solution-architecture` (Google) |
| PostgreSQL (RLS, migrations, indexing, naming, pooling) | `agent_rules.md` "PostgreSQL" section (10 rules) |
| Docker (multi-stage, health check, secrets, logs) | `agent_rules.md` "Docker" section (10 rules) |
| Kubernetes (probes, replicas, PDB, network policies, GitOps) | `agent_rules.md` "Kubernetes" section (11 rules) |
| Seguridad de aplicaciones (OWASP, RLS, OAuth, deploy) | `working-style.md` sección "Seguridad de aplicaciones" (10 bloques) |

### Gobernanza de agentes

| Tarea | Referencia |
|--------|-----------|
| Checklist para agentes en producción | Memory `agente-ia-producao` (9 blocks) |
| Orquestación multiagente (Fable) | Memory `multi-agent-sessions` (coordinator pattern, threads, MCP routing) |
| Pipeline RAG zero hallucination | Skills de CTO y Solution Architect (10 etapas, confidence scoring obligatorio) |

### Marca y contenido

| Tarea | Skill |
|--------|-------|
| Copy de [YOUR_HANDLE], [YOUR_FIRM] y productos | `[SKILL_BRAND_COPY]` |
| Logotipo, identidad visual y piezas gráficas | Sección "Flujo de diseño e identidad visual" en `working-style.md` |
| UI / landing / app / chat | `ux-ui-REQUESTS.md` → PT skills (`[SKILL_UI_PLAN]`, `[SKILL_UI_LANDING]`, `[SKILL_UI_REVIEW]`, `[SKILL_UI_REFACTOR]`, `[SKILL_UI_POLISH]`, `[SKILL_UI_PROVE]`, `[SKILL_UI_REDESIGN]`); motors: gates + impeccable |

### Conocimiento y productividad

| Tarea | Skill |
|--------|-------|
| Sintetizar tema o texto largo | `[SKILL_SYNTHESIZE]` |
| Modo de respuesta comprimido | `[SKILL_CONCISE_MODE]` |
| Estresar un plan con una entrevista | `[SKILL_INTERVIEW]`, `[SKILL_INTERVIEW_CTX]` |
| Operar el vault Obsidian | `obsidian-cli`, `obsidian-markdown`, `obsidian-bases` |
| Traducir documento a PT-BR | `[SKILL_TRANSLATE]` |
| Crear o ajustar una skill | `[SKILL_CREATE_SKILL]`, `skill-creator` |
| Convertir un libro (PDF, EPUB, DOCX, etc.) en skill de agente | `book-to-skill` (instalada en `~/.claude/skills/book-to-skill`, comando `/book-to-skill`) |

### Salida de documentos

| Formato | Skill |
|---------|-------|
| Word | `docx` |
| Excel | `xlsx` |
| Presentación | `pptx` |
| PDF | `pdf` |

---

## Templates del vault (`[YOUR_NAME]/templates/`)

| Template | Uso |
|----------|-----|
| `template-daily.md` | Nota diaria |
| `template-raw.md` | Captura bruta fechada in `raw/` |
| `template-wiki.md` | Nota temática durable en `wiki/<domain>/` |

---

## Reglas de operación de esta carpeta

1. **Antes de cualquier tarea**, lee `about-me.md` (puntero), `identity.md` (identidad), `stack.md` (herramientas), and `working-style.md` (reglas).
2. **En textos de largo aliento** (anteproyecto, artículo, tesis, dictamen, memorial, pieza extensa), aplica el "Estilo de escritura académico y técnico largo (canónico)" de `brand-voice.md` y ejecuta el checklist de cierre antes de entregar.
3. **Nunca borres archivos** sin confirmación explícita de [YOUR_NAME].
4. **Ítems ambiguos o pendientes de decisión** van a `_PARA-REVISAR.md`.
5. **Si la fecha de un documento no está clara**, marca como `VERIFY`.
6. **Al crear documentos nuevos**, guarda en la carpeta correcta e informa la ruta.
7. **Versiones de documento**: usa el sufijo `_AAAA-MM-DD`.
8. **En el vault**, al referenciar otra nota, usa wikilink `[[note-name]]`.
9. **Registra todo cambio estructural** de esta carpeta en `_CHANGELOG.md`.

---

## Estructura actual de la carpeta

```
📁 [CONTEXT_DIR]/
│
├── 📄 _MANIFEST.md            ← este archivo (mapa de navegación)
├── 📄 agent_rules.md          ← reglas universales para cualquier IA
├── 📄 senior-implementer-instructions.md ← contrato operacional para quien codifica
├── 📄 about-me.md             ← puntero: prioridades, reglas, método vault
├── 📄 identity.md             ← identidad profesional estable
├── 📄 stack.md                ← herramientas, MCPs, skills, infra IA
├── 📄 working-style.md        ← reglas de colaboración y gobernanza
├── 📄 brand-voice.md          ← voz de las marcas
├── 📄 ux-ui-INDEX.md         ← enrutamiento UX WEB/MOBILE + 60-30-10
├── 📄 ux-ui-criteria.md      ← MUST/MUST-NOT + checklist UI
├── 📄 ux-ui-web-landing.md   ← PASOS landing WEB
├── 📄 ux-ui-mobile.md        ← PASOS MOBILE
├── 📄 ux-ui-REQUESTS.md      ← menú: qué pedir
├── 📄 _PROJETOS-ATIVOS.md     ← estado de los frentes
├── 📄 _PARA-REVISAR.md        ← pendencias de decisión
├── 📄 _CHANGELOG.md           ← historial de cambios
│
├── 📁 [YOUR_NAME]/                   ← vault Obsidian operacional (método Karpathy)
│                                (legal second brain: atajo [DOMAIN_VAULT])
│   ├── 📁 raw/                ← captura bruta fechada
│   ├── 📁 wiki/               ← notas temáticas durables
│   │   ├── 00-indices/        ← MOCs por dominio
│   │   ├── concursos/         ← procuraduría
│   │   ├── direito-trabalho/  ← contenido laboral
│   │   ├── [PRODUCT_A]/         ← producto legaltech
│   │   └── tech/              ← tech, IA local, diseño
│   ├── 📁 Clippings/          ← recortes web triados
│   ├── 📁 templates/          ← templates reutilizables
│   ├── 📁 reports/            ← informes generados
│   ├── 📁 images/             ← anexos visuales
│   └── 📁 trash/              ← cuarentena
│
├── 📁 ativos-[YOUR_FIRM]/             ← papel membretado y logo
├── 📁 credenciais/            ← credenciales de integración
└── 📁 documentos/             ← documentos sueltos
```

---
*Actualiza este archivo siempre que la estructura de la carpeta cambie o se añadan nuevos dominios, y registra el cambio en `_CHANGELOG.md`.*
