# _MANIFEST.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Context orientation file, read by Claude before any task in this folder.
> Last updated: 13/09/2026 (Legal vault as second brain)

---

## About this folder

This is the canonical context folder of [YOUR_NAME] ([YOUR_NAME]): banking labor lawyer, academic (Master [YOUR_UNIVERSITY], doctoral candidate), and founder of legaltech products. The folder gathers work identity, brand voice, collaboration rules, project status, and the knowledge vault.

The `[CONTEXT_DIR]/` folder (on the Mini: `[CONTEXT_DIR]`) is the **only** source of canonical operational context. Any assistant, on any machine, must read exclusively the files in this folder before starting tasks.

There are two Obsidian vaults, with distinct roles:

- **Context / `[YOUR_NAME]/`**: operational vault (Karpathy method: the human reads, the LLM writes).
- **Legal**: domain second brain for all agents: `[DOMAIN_VAULT]` (shortcut `[DOMAIN_VAULT]` on the Mini; ~4.5k notes: case law, legislation, news, RAG, precedents). It does not replace Camada 1 of this folder.

**Mandatory routing:** on any request related to law, case law, legislation, precedents, doctrine, legal news, legal RAG, or legal domain research, **all AIs and agents** must consult and point to the Legal vault (`[DOMAIN_VAULT]`) before inventing or improvising. The `[YOUR_NAME]/` vault remains only for operational context and the Karpathy method.

Karpathy flow in `[YOUR_NAME]/`:

1. Capture in `raw/` (dated).
2. Compile in `wiki/<domain>/` (durable thematic note).
3. Consult via MOCs in `wiki/00-indices/`.
4. Maintain with periodic reviews (biweekly health check).

---

## CAMADA 1, Canonical Documents
> Read these files FIRST, in any session. They are the current source of truth.

| File | Description | Update frequency |
|---------|-----------|:------------------------:|
| `agent_rules.md` | Universal rules for any AI (agnostic entry door) | Monthly |
| `senior-implementer-instructions.md` | Operational compilation for senior code implementer (human or agent): DoD, TDD, Postgres/Docker/K8s, security, staged-write | When engineering in the canonicals changes |
| `about-me.md` | Context pointer: priorities, operational rules, vault method | Monthly |
| `identity.md` | Who [YOUR_NAME] is, professional fronts, academic style, anti-AI patterns | Semiannual |
| `stack.md` | Tools, MCPs, skills, plugins, LightRAG, RAG pipeline, subagents | Weekly |
| `working-style.md` | Collaboration rules, research and engineering protocols, agent governance, application security for any AI that audits code | Monthly |
| `templates-agent/` | Per-repo memory templates (`CLAUDE.md`, `REPO_MAP`, `DECISIONS`, boot) + S/M/C reference; canonical S/M/C in working-style | When agent boot changes |
| `brand-voice.md` | Brand voice, canonical long academic and technical writing style | Semiannual |
| `ux-ui-INDEX.md` | UX/UI routing (WEB vs MOBILE), R0 and 60-30-10 color; load on interface tasks | Continuous |
| `ux-ui-criteria.md` | UI MUST/MUST-NOT criteria (Norman/Krug/Yablonski/Refactoring UI/Johnson) + checklist | Continuous |
| `ux-ui-web-landing.md` | Sub-rules and STEPS 0–14 for WEB landing | Continuous |
| `ux-ui-mobile.md` | MOBILE sub-rules (landing / app / chat) | Continuous |
| `ux-ui-REQUESTS.md` | Condensed menu: what to ask (7 PT skills) when hiring/refactoring UI | Continuous |
| `_PROJETOS-ATIVOS.md` | Current state and next steps of each front | Weekly |
| `[YOUR_NAME]/wiki/00-indices/_HOME.md` | Knowledge vault entry panel | Continuous |
| `[YOUR_NAME]/wiki/00-indices/open_questions.md` | Open questions, uncertainties, and pending decisions | Continuous |

---

## CAMADA 2, Domains
> Load only when the task explicitly touches that domain.

### Knowledge (vault `[YOUR_NAME]/`)

| Path | Domain | When to load |
|---------|---------|----------------|
| `[YOUR_NAME]/wiki/00-indices/` | MOCs and indexes by domain | Starting point of any vault research |
| `[YOUR_NAME]/wiki/direito-trabalho/` | Compiled labor content | Labor Law tasks |
| `[YOUR_NAME]/wiki/concursos/` | Prosecution subjects ([ORG_A], [ORG_B]) | Exam study |
| `[YOUR_NAME]/wiki/[PRODUCT_A]/` | Product, design system, features | [PRODUCT_A] and [PRODUCT_B] tasks |
| `[YOUR_NAME]/wiki/tech/` | Tech, local AI, design, programming | Technical and automation tasks |
| `ux-ui-*.md` (root) | WEB/MOBILE criteria and steps for UI agents | Any UI, landing, app shell, or chat |
| `[YOUR_NAME]/raw/` | Dated raw capture | Before compiling a new wiki note |
| `[YOUR_NAME]/Clippings/` | Triaged web clippings | Consult saved material |

### Operations and assets

| Path | Domain | When to load |
|---------|---------|----------------|
| `ativos-[YOUR_FIRM]/` | [YOUR_FIRM] letterhead and logo | Generating firm filings and documents |
| `credenciais/` | Integration credentials | Only on automation tasks that require access (see `_PARA-REVISAR.md`) |
| `appsec-rules.md` | Full fail-closed playbook (10 rules + matrix + APPROVED); paste into Claude AppSec Project | Audit, security review, auth/secrets/deploy fix |
| `documentos/` | Loose documents and project status | Point consult |
| `Desktop/Negócio/Nexo [BRAND_KIT_DIR] /kit-nexo/` | Nexo Tecnologia brand kit: logo, palette, typography, avatars, signatures, and pieces by network. Rules in `01-logotipo/logomarca.md` | Any Nexo visual piece |

---

## CAMADA 3, Archive (Ignore by default)
> Do NOT load unless [YOUR_NAME] asks explicitly.

| Path | Contents |
|---------|----------|
| `documentos/_arquivo/` | Old status and documents, kept for history |
| `changelog/` | Backups and prior versions of Manifest/Changelog/Projects |
| `[YOUR_NAME]/trash/` | Quarantine before deletion |
| `*_v1`, `*_v2`, `*_old`, `*_backup` | Prior file versions |

---

## Skills by front
> Routing map. When you identify the task front, prefer these skills.

### Banking labor (pro-claimant)

| Task | Skill |
|--------|-------|
| Read new case, filing synthesis | `resumo-processo` |
| Petition, reply, memorials (1st instance) | `advogado-trabalhista-bancario` |
| Settlement calculation and proposal | `calculo-acordo-trabalhista` |
| Expert report and calculation | `perito-trabalhista-bancario` |
| Challenge calculation or report | `contador-trabalhista-impugnacao` |
| Review appeal, embargos, agravo | `especialista-recurso-revista` |
| Counter-arguments to employer appeal | `contrarrazoes-trabalhistas` |
| Enforcement and liquidation | `execucao-trabalhista` |
| Case-law research | `pesquisa-jurisprudencia`, `jurisprudencia-stf-direitos-sociais` |
| Labor procedure doctrine (competence, deadlines, nullities, appeals, enforcement) | `martins-processo-trabalho` (Sergio Pinto Martins book converted; private repo `[YOUR_GITHUB]/martins-processo-trabalho`) |
| Check law or procedure | `legislacao-brasileira:verificar-legislacao` |

### Academic ([YOUR_UNIVERSITY], doctorate)

| Task | Skill |
|--------|-------|
| Write or review article, thesis, chapter | `revisor-academico-juridico` |
| Doctrinal analysis and pre-project | `professor-trabalho-previdenciario-[YOUR_UNIVERSITY]` |
| ABNT study document | `documento-estudo-abnt` |
| STF judgment analysis | `analise-jurisprudencia-stf` |

### Legaltech and product

| Task | Skill |
|--------|-------|
| Legaltech market intelligence | `analise-mercado-juridico` |
| PRD from conversation | `gerar-prd` |
| Break plan into issues | `quebrar-em-issues` |
| Issue triage | `triagem` |
| Evaluate legal search or RAG relevance (score 0 to 3, precision, recall, golden set) | `avaliar-relevancia-jurisprudencia` |

### Development and automation

| Task | Skill |
|--------|-------|
| Team orchestration and architecture | `nexo-agents-team` (cto, backend, frontend, devops, dba, qa) |
| Senior implementer operational contract (DoD, TDD, infra, security) | `senior-implementer-instructions.md` (Camada 1) |
| Full code review | `especialista-revisao-codigo` |
| End-to-end system analysis | `analisador-sistema-ponta-a-ponta` |
| Commit, push, and PR | `commit-push-pr` |
| Interactive architecture diagrams | `archify` (architecture, workflow, sequence, data-flow, lifecycle) |
| TDD red-green-refactor | `tdd` |
| Disciplined debugging | `diagnose` |
| Module deepening | `improve-codebase-architecture` |
| Explain code in system context | `zoom-out` |
| Disposable prototype | `prototype` |
| Code review Standards + Spec | `review` |
| Refactor plan in tiny commits | `request-refactor-plan` |
| Cross-session context handoff | `handoff` |
| Grilling against domain model | `grill-with-docs` |
| SaaS competitive intelligence | `[PRODUCT_C]` |
| Product partner (idea to launch) | `product-partner` |

### Infrastructure and operations

| Task | Reference |
|--------|-----------|
| Architecture visualization (interactive HTML/SVG diagrams) | `archify` (5 types: architecture, workflow, sequence, data-flow, lifecycle) |
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
| Application security (OWASP, RLS, OAuth, deploy) | `working-style.md` "Application security" section (10 blocks) |

### Agent governance

| Task | Reference |
|--------|-----------|
| Checklist for production agents | Memory `agente-ia-producao` (9 blocks) |
| Multi-agent orchestration (Fable) | Memory `multi-agent-sessions` (coordinator pattern, threads, MCP routing) |
| Zero-hallucination RAG pipeline | CTO and Solution Architect skills (10 stages, mandatory confidence scoring) |

### Brand and content

| Task | Skill |
|--------|-------|
| Copy for [YOUR_HANDLE], [YOUR_FIRM], and products | `copy-marca-pessoal` |
| Logo, visual identity, and graphic pieces | "Design and visual identity flow" section in `working-style.md` |
| UI / landing / app / chat | `ux-ui-REQUESTS.md` → PT skills (`planejar-interface`, `desenhar-landing`, `revisar-experiencia`, `refatorar-interface`, `polir-para-ship`, `provar-com-screenshot`, `redesenhar-[PRODUCT_A]`); motors: gates + impeccable |

### Knowledge and productivity

| Task | Skill |
|--------|-------|
| Synthesize theme or long text | `sintetizador` |
| Compressed response mode | `modo-conciso` |
| Stress a plan with an interview | `entrevistar`, `entrevistar-com-contexto` |
| Operate the Obsidian vault | `obsidian-cli`, `obsidian-markdown`, `obsidian-bases` |
| Translate document to PT-BR | `tradutor-documentos` |
| Create or adjust a skill | `criar-skill`, `skill-creator` |
| Convert a book (PDF, EPUB, DOCX, etc.) into an agent skill | `book-to-skill` (installed at `~/.claude/skills/book-to-skill`, command `/book-to-skill`) |

### Document output

| Format | Skill |
|---------|-------|
| Word | `docx` |
| Excel | `xlsx` |
| Presentation | `pptx` |
| PDF | `pdf` |

---

## Vault templates (`[YOUR_NAME]/templates/`)

| Template | Use |
|----------|-----|
| `template-daily.md` | Daily note |
| `template-raw.md` | Dated raw capture in `raw/` |
| `template-wiki.md` | Durable thematic note in `wiki/<domain>/` |

---

## Operating rules for this folder

1. **Before any task**, read `about-me.md` (pointer), `identity.md` (identity), `stack.md` (tools), and `working-style.md` (rules).
2. **On long-form texts** (pre-project, article, thesis, opinion, memorial, extended filing), apply the "Long academic and technical writing style (canonical)" from `brand-voice.md` and run the closing checklist before delivering.
3. **Never delete files** without explicit confirmation from [YOUR_NAME].
4. **Ambiguous or pending-decision items** go to `_PARA-REVISAR.md`.
5. **If a document date is unclear**, mark as `VERIFY`.
6. **When creating new documents**, save in the correct folder and report the path.
7. **Document versions**: use the `_YYYY-MM-DD` suffix.
8. **In the vault**, when referencing another note, use wikilink `[[note-name]]`.
9. **Record every structural change** to this folder in `_CHANGELOG.md`.

---

## Current folder structure

```
📁 [CONTEXT_DIR]/
│
├── 📄 _MANIFEST.md            ← this file (navigation map)
├── 📄 agent_rules.md          ← universal rules for any AI
├── 📄 senior-implementer-instructions.md ← operational contract for whoever codes
├── 📄 about-me.md             ← pointer: priorities, rules, vault method
├── 📄 identity.md             ← stable professional identity
├── 📄 stack.md                ← tools, MCPs, skills, AI infra
├── 📄 working-style.md        ← collaboration and governance rules
├── 📄 brand-voice.md          ← brand voice
├── 📄 ux-ui-INDEX.md         ← UX WEB/MOBILE routing + 60-30-10
├── 📄 ux-ui-criteria.md      ← MUST/MUST-NOT + UI checklist
├── 📄 ux-ui-web-landing.md   ← WEB landing STEPS
├── 📄 ux-ui-mobile.md        ← MOBILE STEPS
├── 📄 ux-ui-REQUESTS.md      ← menu: what to ask
├── 📄 _PROJETOS-ATIVOS.md     ← front status
├── 📄 _PARA-REVISAR.md        ← pending decisions
├── 📄 _CHANGELOG.md           ← change history
│
├── 📁 [YOUR_NAME]/                   ← operational Obsidian vault (Karpathy method)
│                                (legal second brain: shortcut [DOMAIN_VAULT])
│   ├── 📁 raw/                ← dated raw capture
│   ├── 📁 wiki/               ← durable thematic notes
│   │   ├── 00-indices/        ← MOCs by domain
│   │   ├── concursos/         ← prosecution
│   │   ├── direito-trabalho/  ← labor content
│   │   ├── [PRODUCT_A]/         ← legaltech product
│   │   └── tech/              ← tech, local AI, design
│   ├── 📁 Clippings/          ← triaged web clippings
│   ├── 📁 templates/          ← reusable templates
│   ├── 📁 reports/            ← generated reports
│   ├── 📁 images/             ← visual attachments
│   └── 📁 trash/              ← quarantine
│
├── 📁 ativos-[YOUR_FIRM]/             ← letterhead and logo
├── 📁 credenciais/            ← integration credentials
└── 📁 documentos/             ← loose documents
```

---
*Update this file whenever the folder structure changes or new domains are added, and record the change in `_CHANGELOG.md`.*
