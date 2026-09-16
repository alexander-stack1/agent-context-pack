# _MANIFEST.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Arquivo de orientação de contexto, lido pelo Claude antes de qualquer tarefa nesta pasta.
> Última atualização: 13/09/2026 (vault Jurídico como segundo cérebro)

---

## Sobre esta pasta

Esta é a pasta de contexto canônico de [YOUR_NAME] ([YOUR_HANDLE]): [YOUR_ROLE], acadêmico ([YOUR_UNIVERSITY]) e fundador de produtos em [YOUR_INDUSTRY]. A pasta reúne a identidade de trabalho, a voz das marcas, as regras de colaboração, o estado dos projetos e o vault de conhecimento.

A pasta `[CONTEXT_DIR]/` (no [SECONDARY_MACHINE]: `[CONTEXT_DIR]`) é a **única** fonte de contexto operacional canônico. Qualquer assistente, em qualquer máquina, deve ler exclusivamente os arquivos desta pasta antes de iniciar tarefas.

Há dois vaults Obsidian, com papéis distintos:

- **Contexto / `[YOUR_NAME]/`**: vault operacional (método Karpathy: o humano lê, o LLM escreve).
- **Jurídico**: segundo cérebro de domínio para todos os agentes: `[DOMAIN_VAULT]` (atalho `[DOMAIN_VAULT]` no [SECONDARY_MACHINE]; ~4,5k notas: jurisprudência, legislação, notícias, RAG, precedentes). Não substitui a Camada 1 desta pasta.

**Roteamento obrigatório:** em qualquer pedido relacionado a direito, jurisprudência, legislação, precedentes, doutrina, notícias jurídicas, RAG jurídico ou pesquisa de domínio legal, **todas as IAs e agentes** devem consultar e apontar para o vault Jurídico (`[DOMAIN_VAULT]`) antes de inventar ou improvisar. O vault `[YOUR_NAME]/` continua só para contexto operacional e método Karpathy.

Fluxo Karpathy em `[YOUR_NAME]/`:

1. Capturar em `raw/` (datado).
2. Compilar em `wiki/<domínio>/` (nota temática durável).
3. Consultar via MOCs em `wiki/00-indices/`.
4. Manter com revisões periódicas (health check quinzenal).

---

## CAMADA 1, Documentos Canônicos
> Leia estes arquivos PRIMEIRO, em qualquer sessão. São a fonte da verdade atual.

| Arquivo | Descrição | Frequência de atualização |
|---------|-----------|:------------------------:|
| `agent_rules.md` | Regras universais para qualquer IA (porta de entrada agnóstica) | Mensal |
| `instrucoes-implementador-senior.md` | Compilação operacional para implementador de código sênior (humano ou agente): DoD, TDD, Postgres/Docker/K8s, segurança, staged-write | Quando mudar engenharia nos canônicos |
| `about-me.md` | Ponteiro de contexto: prioridades, regras operacionais, método vault | Mensal |
| `identity.md` | Quem [YOUR_NAME] é, frentes profissionais, estilo acadêmico, padrões anti-IA | Semestral |
| `stack.md` | Ferramentas, MCPs, skills, plugins, LightRAG, RAG pipeline, subagentes | Semanal |
| `working-style.md` | Regras de colaboração, protocolos de pesquisa e engenharia, governança de agentes, segurança de aplicações para qualquer IA que auditar código | Mensal |
| `templates-agent/` | Templates de memória por repo (`CLAUDE.md`, `REPO_MAP`, `DECISIONS`, boot) + referência S/M/C; canônico S/M/C em working-style | Quando mudar boot de agente |
| `brand-voice.md` | Voz das marcas, estilo de escrita acadêmico e técnico longo canônico | Semestral |
| `ux-ui-INDEX.md` | Roteamento UX/UI (WEB vs MOBILE), R0 e cor 60-30-10; carregar em tarefa de interface | Contínuo |
| `ux-ui-criteria.md` | Critérios MUST/MUST-NOT de UI (Norman/Krug/Yablonski/Refactoring UI/Johnson) + checklist | Contínuo |
| `ux-ui-web-landing.md` | Subregras e PASSOS 0–14 para landing WEB | Contínuo |
| `ux-ui-mobile.md` | Subregras MOBILE (landing / app / chat) | Contínuo |
| `ux-ui-PEDIDOS.md` | Cardápio condensado: o que pedir (7 skills PT) na contratação/refatoração de UI | Contínuo |
| `_PROJETOS-ATIVOS.md` | Estado atual e próximos passos de cada frente | Semanal |
| `[YOUR_NAME]/wiki/00-indices/_HOME.md` | Painel de entrada do vault de conhecimento | Contínuo |
| `[YOUR_NAME]/wiki/00-indices/open_questions.md` | Perguntas abertas, incertezas e decisões pendentes | Contínuo |

---

## CAMADA 2, Domínios
> Carregue apenas quando a tarefa tocar explicitamente aquele domínio.

### Conhecimento (vault `[YOUR_NAME]/`)

| Caminho | Domínio | Quando carregar |
|---------|---------|----------------|
| `[YOUR_NAME]/wiki/00-indices/` | MOCs e índices por domínio | Ponto de partida de qualquer pesquisa no vault |
| `[YOUR_NAME]/wiki/direito-trabalho/` | Conteúdo trabalhista compilado | Tarefas de Direito do Trabalho |
| `[YOUR_NAME]/wiki/concursos/` | Matérias de procuradoria ([ORG_A], [ORG_B]) | Estudo para concursos |
| `[YOUR_NAME]/wiki/[PRODUCT_A]/` | Produto, design system, features | Tarefas do [PRODUCT_A] e [PRODUCT_B] |
| `[YOUR_NAME]/wiki/tech/` | Tech, IA local, design, programação | Tarefas técnicas e de automação |
| `ux-ui-*.md` (raiz) | Critérios e passos WEB/MOBILE para agentes de UI | Qualquer UI, landing, app shell ou chat |
| `[YOUR_NAME]/raw/` | Captura bruta datada | Antes de compilar nota nova na wiki |
| `[YOUR_NAME]/Clippings/` | Recortes web triados | Consulta de material salvo |

### Operação e ativos

| Caminho | Domínio | Quando carregar |
|---------|---------|----------------|
| `ativos-[YOUR_FIRM]/` | Papel timbrado e logo da [YOUR_FIRM] | Geração de peças e documentos da banca |
| `credenciais/` | Credenciais de integração | Apenas em tarefas de automação que exijam acesso (ver `_PARA-REVISAR.md`) |
| `appsec-rules.md` | Playbook fail-closed completo (10 regras + matriz + APROVADO); colar em Project Claude AppSec | Auditoria, review de segurança, correção auth/secrets/deploy |
| `documentos/` | Documentos avulsos e status de projetos | Consulta pontual |
| `[BRAND_KIT_DIR]/` | Kit de marca da [YOUR_COMPANY]: logotipo, paleta, tipografia, avatares, assinaturas e peças por rede. Regras em `[BRAND_KIT_DIR]/logo-rules.md` | Qualquer peça visual da [YOUR_COMPANY] |

---

## CAMADA 3, Arquivo (Ignorar por padrão)
> NÃO carregue a menos que [YOUR_NAME] peça explicitamente.

| Caminho | Conteúdo |
|---------|----------|
| `documentos/_arquivo/` | Status e documentos antigos, mantidos por histórico |
| `changelog/` | Backups e versões anteriores de Manifest/Changelog/Projetos |
| `[YOUR_NAME]/trash/` | Quarentena antes de exclusão |
| `*_v1`, `*_v2`, `*_old`, `*_backup` | Versões anteriores de arquivos |

---

## Skills por frente
> Mapa de roteamento. Ao identificar a frente da tarefa, prefira estas skills.

### [PRACTICE_AREA]

| Tarefa | Skill |
|--------|-------|
| Ler processo novo, síntese de peça | `[SKILL_CASE_SUMMARY]` |
| Petição, réplica, memoriais (1º grau) | `[SKILL_DOMAIN_DRAFTING]` |
| Cálculo e proposta de acordo | `[SKILL_SETTLEMENT_CALC]` |
| Laudo e cálculo pericial | `[SKILL_EXPERT_REPORT]` |
| Impugnar cálculo ou laudo | `[SKILL_CALC_CHALLENGE]` |
| Recurso de revista, embargos, agravo | `[SKILL_APPEALS]` |
| Contrarrazões a recurso patronal | `[SKILL_COUNTER_APPEAL]` |
| Execução e liquidação | `[SKILL_ENFORCEMENT]` |
| Pesquisa de jurisprudência | `[SKILL_CASELAW_SEARCH]`, `[SKILL_CASELAW_SEARCH_B]` |
| Doutrina de processo do trabalho (competência, prazos, nulidades, recursos, execução) | `[SKILL_DOMAIN_BOOK]` (livro do [BOOK_AUTHOR] convertido; repo privado `[YOUR_GITHUB]/[SKILL_DOMAIN_BOOK]`) |
| Verificar lei ou tramitação | `[SKILL_LAW_CHECK]` |

### Acadêmico ([YOUR_UNIVERSITY], doutorado)

| Tarefa | Skill |
|--------|-------|
| Escrever ou revisar artigo, tese, capítulo | `[SKILL_ACADEMIC_REVIEW]` |
| Análise doutrinária e pré-projeto | `[SKILL_ACADEMIC_ADVISOR]` |
| Documento de estudo em ABNT | `[SKILL_STUDY_DOC]` |
| Análise de julgado do STF | `[SKILL_COURT_ANALYSIS]` |

### Legaltech e produto

| Tarefa | Skill |
|--------|-------|
| Inteligência de mercado legaltech | `[SKILL_MARKET_INTEL]` |
| PRD a partir da conversa | `[SKILL_PRD]` |
| Quebrar plano em issues | `[SKILL_ISSUES]` |
| Triagem de issues | `[SKILL_TRIAGE]` |
| Avaliar relevância de busca ou RAG jurídico (nota 0 a 3, precisão, recall, golden set) | `[SKILL_RETRIEVAL_EVAL]` |

### Desenvolvimento e automação

| Tarefa | Skill |
|--------|-------|
| Orquestração e arquitetura por time | `[AGENT_TEAM]` (cto, backend, frontend, devops, dba, qa) |
| Contrato operacional do implementador sênior (DoD, TDD, infra, segurança) | `instrucoes-implementador-senior.md` (Camada 1) |
| Revisão de código completa | `[SKILL_CODE_REVIEW]` |
| Análise de sistema ponta a ponta | `[SKILL_E2E_ANALYSIS]` |
| Commit, push e PR | `[SKILL_COMMIT_PR]` |
| Diagramas de arquitetura interativos | `archify` (architecture, workflow, sequence, data-flow, lifecycle) |
| TDD red-green-refactor | `tdd` |
| Debugging disciplinado | `diagnose` |
| Deepening de módulos | `improve-codebase-architecture` |
| Explicar código no contexto do sistema | `zoom-out` |
| Protótipo descartável | `prototype` |
| Code review Standards + Spec | `review` |
| Plano de refactor em commits minúsculos | `request-refactor-plan` |
| Handoff de contexto entre sessões | `handoff` |
| Grilling contra modelo de domínio | `grill-with-docs` |
| Inteligência competitiva SaaS | `[PRODUCT_C]` |
| Parceiro de produto (ideia ao lançamento) | `product-partner` |

### Infraestrutura e operações

| Tarefa | Referência |
|--------|-----------|
| Visualização de arquitetura (diagramas interativos HTML/SVG) | `archify` (5 tipos: architecture, workflow, sequence, data-flow, lifecycle) |
| Cloud Run (deploy, scaling, troubleshooting) | `cloud-run-basics` (Google) |
| Cloud SQL PostgreSQL | `cloud-sql-basics` (Google) |
| gcloud CLI | `gcloud` (Google) |
| Managed Agents API (multi-agent) | `gemini-agents-api` (Google) |
| RAG Engine Management | `agent-platform-rag-engine-management` (Google) |
| Cloud Monitoring (gráficos) | `cloud-monitoring-chart-generation` (Google) |
| Cloud Logging (queries LQL) | `cloud-logging-query-generation` (Google) |
| IAM troubleshooting | `iam-helper-for-troubleshooting` (Google) |
| Well-Architected Reliability | `google-cloud-waf-reliability` (Google) |
| Solution Architecture workflow | `google-cloud-solution-architecture` (Google) |
| PostgreSQL (RLS, migrations, indexação, naming, pooling) | `agent_rules.md` seção "PostgreSQL" (10 regras) |
| Docker (multi-stage, health check, segredos, logs) | `agent_rules.md` seção "Docker" (10 regras) |
| Kubernetes (probes, réplicas, PDB, network policies, GitOps) | `agent_rules.md` seção "Kubernetes" (11 regras) |
| Segurança de aplicações (OWASP, RLS, OAuth, deploy) | `working-style.md` seção "Segurança de aplicações" (10 blocos) |

### Governança de agentes

| Tarefa | Referência |
|--------|-----------|
| Checklist para agentes em produção | Memória `agente-ia-producao` (9 blocos) |
| Orquestração multi-agente (Fable) | Memória `multi-agent-sessions` (coordinator pattern, threads, MCP routing) |
| RAG pipeline zero hallucination | CTO e Solution Architect skills (10 estágios, confidence scoring obrigatório) |

### Marca e conteúdo

| Tarefa | Skill |
|--------|-------|
| Copy de [YOUR_HANDLE], [YOUR_FIRM] e produtos | `[SKILL_BRAND_COPY]` |
| Logotipo, identidade visual e peças gráficas | Seção "Fluxo de design e identidade visual" em `working-style.md` |
| UI / landing / app / chat | `ux-ui-PEDIDOS.md` → skills PT (`[SKILL_UI_PLAN]`, `[SKILL_UI_LANDING]`, `[SKILL_UI_REVIEW]`, `[SKILL_UI_REFACTOR]`, `[SKILL_UI_POLISH]`, `[SKILL_UI_PROVE]`, `[SKILL_UI_REDESIGN]`); motors: gates + impeccable |

### Conhecimento e produtividade

| Tarefa | Skill |
|--------|-------|
| Sintetizar tema ou texto longo | `[SKILL_SYNTHESIZE]` |
| Modo de resposta comprimido | `[SKILL_CONCISE_MODE]` |
| Estressar plano com entrevista | `[SKILL_INTERVIEW]`, `[SKILL_INTERVIEW_CTX]` |
| Operar o vault Obsidian | `obsidian-cli`, `obsidian-markdown`, `obsidian-bases` |
| Traduzir documento para PT-BR | `[SKILL_TRANSLATE]` |
| Criar ou ajustar skill | `[SKILL_CREATE_SKILL]`, `skill-creator` |
| Converter livro (PDF, EPUB, DOCX etc.) em skill de agente | `book-to-skill` (instalada em `~/.claude/skills/book-to-skill`, comando `/book-to-skill`) |

### Saída de documentos

| Formato | Skill |
|---------|-------|
| Word | `docx` |
| Excel | `xlsx` |
| Apresentação | `pptx` |
| PDF | `pdf` |

---

## Templates do vault (`[YOUR_NAME]/templates/`)

| Template | Uso |
|----------|-----|
| `template-daily.md` | Nota diária |
| `template-raw.md` | Captura bruta datada em `raw/` |
| `template-wiki.md` | Nota temática durável em `wiki/<domínio>/` |

---

## Regras de operação desta pasta

1. **Antes de qualquer tarefa**, leia `about-me.md` (ponteiro), `identity.md` (identidade), `stack.md` (ferramentas) e `working-style.md` (regras).
2. **Em textos de fôlego** (pré-projeto, artigo, tese, parecer, memorial, peça extensa), aplicar o "Estilo de escrita acadêmico e técnico longo (canônico)" do `brand-voice.md` e rodar o checklist de fechamento antes de entregar.
3. **Nunca delete arquivos** sem confirmação explícita de [YOUR_NAME].
4. **Itens ambíguos ou pendentes de decisão** vão para `_PARA-REVISAR.md`.
5. **Se a data de um documento não estiver clara**, marque como `VERIFICAR`.
6. **Ao criar novos documentos**, salve na pasta correta e informe o caminho.
7. **Versões de documento**: use o sufixo `_AAAA-MM-DD`.
8. **No vault**, ao referenciar outra nota, use wikilink `[[nome-da-nota]]`.
9. **Registre toda alteração estrutural** desta pasta no `_CHANGELOG.md`.

---

## Estrutura atual da pasta

```
📁 [CONTEXT_DIR]/
│
├── 📄 _MANIFEST.md            ← este arquivo (mapa de navegação)
├── 📄 agent_rules.md          ← regras universais para qualquer IA
├── 📄 instrucoes-implementador-senior.md ← contrato operacional para quem codifica
├── 📄 about-me.md             ← ponteiro: prioridades, regras, método vault
├── 📄 identity.md             ← identidade profissional estável
├── 📄 stack.md                ← ferramentas, MCPs, skills, infra IA
├── 📄 working-style.md        ← regras de colaboração e governança
├── 📄 brand-voice.md          ← voz das marcas
├── 📄 ux-ui-INDEX.md         ← roteamento UX WEB/MOBILE + 60-30-10
├── 📄 ux-ui-criteria.md      ← MUST/MUST-NOT + checklist UI
├── 📄 ux-ui-web-landing.md   ← PASSOS landing WEB
├── 📄 ux-ui-mobile.md        ← PASSOS MOBILE
├── 📄 ux-ui-PEDIDOS.md       ← cardápio: o que pedir
├── 📄 _PROJETOS-ATIVOS.md     ← estado das frentes
├── 📄 _PARA-REVISAR.md        ← pendências de decisão
├── 📄 _CHANGELOG.md           ← histórico de alterações
│
├── 📁 [YOUR_NAME]/                   ← vault Obsidian operacional (método Karpathy)
│                                (segundo cérebro jurídico: atalho [DOMAIN_VAULT])
│   ├── 📁 raw/                ← captura bruta datada
│   ├── 📁 wiki/               ← notas temáticas duráveis
│   │   ├── 00-indices/        ← MOCs por domínio
│   │   ├── concursos/         ← procuradoria
│   │   ├── direito-trabalho/  ← conteúdo trabalhista
│   │   ├── [PRODUCT_A]/         ← produto legaltech
│   │   └── tech/              ← tech, IA local, design
│   ├── 📁 Clippings/          ← recortes web triados
│   ├── 📁 templates/          ← templates reusáveis
│   ├── 📁 reports/            ← relatórios gerados
│   ├── 📁 images/             ← anexos visuais
│   └── 📁 trash/              ← quarentena
│
├── 📁 ativos-[YOUR_FIRM]/             ← papel timbrado e logo
├── 📁 credenciais/            ← credenciais de integração
└── 📁 documentos/             ← documentos avulsos
```

---
*Atualize este arquivo sempre que a estrutura da pasta mudar ou novos domínios forem adicionados, e registre a mudança no `_CHANGELOG.md`.*
