# stack.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Ferramentas, infraestrutura de IA e capacidades técnicas. Muda com frequência.
> Última atualização: 28/07/2026

## Ferramentas do dia a dia

- Obsidian (vault principal, sincronizado via iCloud, em `[CONTEXT_DIR]/[YOUR_NAME]/`)
- Claude e Cowork (assistente de produção), com 70+ skills locais e 20+ plugins
- [AGENT_TEAM] ([N] agentes especializados em hierarquia CTO → managers → operacionais)
- [PRODUCT_F] (automação própria: cron, gateway de LLM, coletores)
- Ollama (modelos locais em Apple Silicon: qwen2.5:7b, nomic-embed-text) e OpenRouter (modelos via API)
- Python e Node para automação, Postgres e embeddings para RAG
- Git e GitHub Actions para versionamento e CI
- Tailscale para acesso remoto às máquinas
- PJe, e-mail e WhatsApp na operação da banca
- [PRODUCT_A]/[PRODUCT_B] (software próprio em desenvolvimento)
- [TOOL_MEDIA] (download e organização de cursos, vídeos e mídia)

## MCPs conectados

| MCP | Finalidade |
|-----|-----------|
| LightRAG | Knowledge graph local ([N] PDFs, localhost:9621) |
| Context7 | Documentação atualizada de bibliotecas direto no contexto |
| Codebase Memory | Grafo de conhecimento do codebase (persiste entre sessões) |
| Perplexity | Pesquisa web com IA |
| xAI/Grok | LLM alternativo |
| PixelBrowse | Screenshot de páginas para leitura visual pelo Claude |
| Google Calendar | Criar/listar/editar eventos |
| Gmail | Buscar threads, criar rascunhos, labels |
| Slack | Ler canais, enviar mensagens, buscar, canvas |
| Notion | Criar/editar páginas, databases, busca |
| Figma | Screenshots, design context, code connect |
| Canva | Gerar designs, editar imagens, templates |
| Google Drive | Buscar/ler/criar arquivos |
| Supabase | SQL, migrations, edge functions, branches |
| Vercel | Deploy, projetos, logs, domínios |
| Gamma | Gerar apresentações |
| Adobe Creative Cloud | Edição de fotos/vídeo, templates, design |
| Fey (Financial) | Contas, transações, spending analysis, forecast |
| Stripe/Invoicing | Criar e enviar faturas, listar transações |
| Computer Use | Controle de tela (mouse, teclado, screenshots) |
| Claude in Chrome | Navegação web, DOM, forms |
| Mermaid | Validar e renderizar diagramas |
| Word (By Anthropic) | Criar/editar documentos Word |
| PowerPoint (By Anthropic) | Criar/editar apresentações |
| Microsoft Docs | Busca e fetch de documentação Microsoft |

**Obsidian, nota de verificação (28/07/2026):** não existe um MCP dedicado ao Obsidian conectado. Confirmado via `ListConnectors` (vazio para "obsidian") e `SearchMcpRegistry` (nenhum resultado com esse nome no diretório público). O vault `[CONTEXT_DIR]/[YOUR_NAME]/` tem o plugin `obsidian-local-rest-api` instalado e ativo, pré-requisito do lado do Obsidian para um servidor MCP dedicado, mas nenhum servidor MCP client-side está configurado apontando para essa API. Na prática, hoje o acesso ao vault (ler, criar, buscar notas) acontece via Desktop Commander e pela ponte de arquivos do dispositivo, não por um MCP próprio. Ver skill `desktop-commander:obsidian-vault`.

## Skills locais (70+)

Organizadas por domínio. Ver roteamento completo em `_MANIFEST.md`.

| Domínio | Qtd | Exemplos principais |
|---------|:---:|---------------------|
| Trabalhista | 13 | [SKILL_DOMAIN_DRAFTING], [SKILL_APPEALS], [SKILL_CASELAW_SEARCH] |
| Desenvolvimento | 17 | tdd, diagnose, review, zoom-out, improve-codebase-architecture, [SKILL_COMMIT_PR], archify |
| Google Cloud | 10 | cloud-run-basics, cloud-sql-basics, gcloud, gemini-agents-api, rag-engine-management, monitoring, logging, iam, waf-reliability, solution-architecture |
| Documentos | 9 | docx, pdf, pptx, xlsx, video-editing |
| Design | 7+ | Cardápio `ux-ui-PEDIDOS.md`: [SKILL_UI_PLAN], [SKILL_UI_LANDING], [SKILL_UI_REVIEW], [SKILL_UI_REFACTOR], [SKILL_UI_POLISH], [SKILL_UI_PROVE], [SKILL_UI_REDESIGN] (motors: gates + impeccable/frontend-design) |
| Obsidian | 4 | obsidian-cli, obsidian-markdown, obsidian-bases |
| Workflow | 10 | grill-with-docs, to-prd, to-issues, triage, handoff |
| Escrita | 6 | [SKILL_BRAND_COPY], edit-article, writing-beats, writing-shape |
| Utilitários | 9+ | [PRODUCT_C], product-partner, [SKILL_CONCISE_MODE], defuddle |
| Estudo | 3+ | [SKILL_EXAM_STUDY], [SKILL_STUDY_DOC], [SKILL_ACADEMIC_REVIEW] |

## Plugins (20+)

Autodescobertos pelo sistema. Principais: [AGENT_TEAM] ([N] agentes), Adobe for Creativity, Adspirer Ads, Legislação Brasileira, Marketing, Sales, Bright Data, Brand Voice, Engineering, Product Management, Operations, Finance, Searchfit SEO, Box, Wix, Figma, Desktop Commander, PDF Viewer.

## LightRAG (Knowledge Graph Local)

| Item | Valor |
|------|-------|
| Versão | 1.4.16 |
| LLM | Ollama qwen2.5:7b (local) |
| Embeddings | nomic-embed-text (local) |
| Documentos indexados | [N] PDFs (Biblioteca Dev) |
| MCP | lightrag_query, lightrag_insert, lightrag_health |
| URL | http://localhost:9621 |
| Privacidade | 100% local |

## RAG Pipeline (10 estágios, Zero Hallucination)

Arquitetura de referência para qualquer feature de IA que responde a partir de documentos:

1. Ingest + normalização (dedup, metadata, versioning)
2. Hybrid retrieval (BM25 + embeddings)
3. ANN + reranking (cross-encoder MiniLM/BGE)
4. Confidence scoring (quality, recency, authority, overlap)
5. Constrained generation (só do contexto, sem conhecimento externo)
6. Citation-backed responses (cada claim com fonte)
7. Confidence threshold (abaixo = "evidência insuficiente")
8. Continuous evals (adversarial, recall, hallucination rate)
9. Caching + memory layer (Redis, TTL, invalidação)
10. Observability (trace IDs, token attribution, alertas)

Documentada nos skills do CTO e Solution Architect do [AGENT_TEAM].

## Governança de agentes

Checklist de 9 blocos e orquestração multi-agente documentados em `working-style.md` e na memória persistente do Claude (.auto-memory).

## Subagentes pessoais e tarefas agendadas

| Skill | Frequência |
|-------|-----------|
| [TASK_MORNING_BRIEF] | Todo dia 7h |
| [TASK_NIGHTLY_REVIEW] | Todo dia 20h |
| [TASK_LAW_MONITOR] | Toda segunda 8h |
| [TASK_EXAM_MONITOR] | Toda quarta 8h |
| [TASK_COMPETITOR_MONITOR] | Dia 1 de cada mês |
| [TASK_ON_DEMAND_A] … [TASK_ON_DEMAND_G] | Sob demanda |

---
*Atualizar sempre que instalar/remover MCPs, skills ou plugins, ou mudar a infra. Registrar no `_CHANGELOG.md`.*
