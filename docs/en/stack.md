# stack.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Tools, AI infrastructure, and technical capabilities. Changes often.
> Last updated: 28/07/2026

## Day-to-day tools

- Obsidian (main vault, synced via iCloud, at `[CONTEXT_DIR]/[YOUR_NAME]/`)
- Claude and Cowork (production assistant), with 70+ local skills and 20+ plugins
- [AGENT_TEAM] (18 specialized agents in CTO → managers → operational hierarchy)
- [PRODUCT_F] (own automation: cron, LLM gateway, collectors)
- Ollama (local models on Apple Silicon: qwen2.5:7b, nomic-embed-text) and OpenRouter (API models)
- Python and Node for automation, Postgres and embeddings for RAG
- Git and GitHub Actions for versioning and CI
- Tailscale for remote access to machines
- PJe, email, and WhatsApp in firm operations
- [PRODUCT_A]/[PRODUCT_B] (own software under development)
- [TOOL_MEDIA] (download and organization of courses, videos, and media)

## Connected MCPs

| MCP | Purpose |
|-----|-----------|
| LightRAG | Local knowledge graph ([N] PDFs, localhost:9621) |
| Context7 | Up-to-date library documentation directly in context |
| Codebase Memory | Codebase knowledge graph (persists across sessions) |
| Perplexity | Web research with AI |
| xAI/Grok | Alternative LLM |
| PixelBrowse | Page screenshots for visual reading by Claude |
| Google Calendar | Create/list/edit events |
| Gmail | Search threads, create drafts, labels |
| Slack | Read channels, send messages, search, canvas |
| Notion | Create/edit pages, databases, search |
| Figma | Screenshots, design context, code connect |
| Canva | Generate designs, edit images, templates |
| Google Drive | Search/read/create files |
| Supabase | SQL, migrations, edge functions, branches |
| Vercel | Deploy, projects, logs, domains |
| Gamma | Generate presentations |
| Adobe Creative Cloud | Photo/video editing, templates, design |
| Fey (Financial) | Accounts, transactions, spending analysis, forecast |
| Stripe/Invoicing | Create and send invoices, list transactions |
| Computer Use | Screen control (mouse, keyboard, screenshots) |
| Claude in Chrome | Web browsing, DOM, forms |
| Mermaid | Validate and render diagrams |
| Word (By Anthropic) | Create/edit Word documents |
| PowerPoint (By Anthropic) | Create/edit presentations |
| Microsoft Docs | Search and fetch Microsoft documentation |

**Obsidian, verification note (28/07/2026):** there is no dedicated Obsidian MCP connected. Confirmed via `ListConnectors` (empty for "obsidian") and `SearchMcpRegistry` (no result with that name in the public directory). The vault `[CONTEXT_DIR]/[YOUR_NAME]/` has the `obsidian-local-rest-api` plugin installed and active, an Obsidian-side prerequisite for a dedicated MCP server, but no client-side MCP server is configured pointing at that API. In practice, today vault access (read, create, search notes) happens via Desktop Commander and the device file bridge, not via a dedicated MCP. See skill `desktop-commander:obsidian-vault`.

## Local skills (70+)

Organized by domain. See full routing in `_MANIFEST.md`.

| Domain | Qty | Main examples |
|---------|:---:|---------------------|
| Labor law | 13 | [SKILL_DOMAIN_DRAFTING], [SKILL_APPEALS], [SKILL_CASELAW_SEARCH] |
| Development | 17 | tdd, diagnose, review, zoom-out, improve-codebase-architecture, [SKILL_COMMIT_PR], archify |
| Google Cloud | 10 | cloud-run-basics, cloud-sql-basics, gcloud, gemini-agents-api, rag-engine-management, monitoring, logging, iam, waf-reliability, solution-architecture |
| Documents | 9 | docx, pdf, pptx, xlsx, video-editing |
| Design | 7+ | Menu `ux-ui-REQUESTS.md`: [SKILL_UI_PLAN], [SKILL_UI_LANDING], [SKILL_UI_REVIEW], [SKILL_UI_REFACTOR], [SKILL_UI_POLISH], [SKILL_UI_PROVE], [SKILL_UI_REDESIGN] (motors: gates + impeccable/frontend-design) |
| Obsidian | 4 | obsidian-cli, obsidian-markdown, obsidian-bases |
| Workflow | 10 | grill-with-docs, to-prd, to-issues, triage, handoff |
| Writing | 6 | [SKILL_BRAND_COPY], edit-article, writing-beats, writing-shape |
| Utilities | 9+ | [PRODUCT_C], product-partner, [SKILL_CONCISE_MODE], defuddle |
| Study | 3+ | [SKILL_EXAM_STUDY], [SKILL_STUDY_DOC], [SKILL_ACADEMIC_REVIEW] |

## Plugins (20+)

Auto-discovered by the system. Main ones: [AGENT_TEAM] ([N] agents), Adobe for Creativity, Adspirer Ads, Brazilian Legislation, Marketing, Sales, Bright Data, Brand Voice, Engineering, Product Management, Operations, Finance, Searchfit SEO, Box, Wix, Figma, Desktop Commander, PDF Viewer.

## LightRAG (Local Knowledge Graph)

| Item | Value |
|------|-------|
| Version | 1.4.16 |
| LLM | Ollama qwen2.5:7b (local) |
| Embeddings | nomic-embed-text (local) |
| Indexed documents | [N] PDFs (Dev Library) |
| MCP | lightrag_query, lightrag_insert, lightrag_health |
| URL | http://localhost:9621 |
| Privacy | 100% local |

## RAG Pipeline (10 stages, Zero Hallucination)

Reference architecture for any AI feature that answers from documents:

1. Ingest + normalization (dedup, metadata, versioning)
2. Hybrid retrieval (BM25 + embeddings)
3. ANN + reranking (cross-encoder MiniLM/BGE)
4. Confidence scoring (quality, recency, authority, overlap)
5. Constrained generation (from context only, no external knowledge)
6. Citation-backed responses (each claim with a source)
7. Confidence threshold (below = "insufficient evidence")
8. Continuous evals (adversarial, recall, hallucination rate)
9. Caching + memory layer (Redis, TTL, invalidation)
10. Observability (trace IDs, token attribution, alerts)

Documented in the CTO and Solution Architect skills of [AGENT_TEAM].

## Agent governance

9-block checklist and multi-agent orchestration documented in `working-style.md` and in Claude's persistent memory (.auto-memory).

## Personal subagents and scheduled tasks

| Skill | Frequency |
|-------|-----------|
| [TASK_MORNING_BRIEF] | Every day 7h |
| [TASK_NIGHTLY_REVIEW] | Every day 20h |
| [TASK_LAW_MONITOR] | Every Monday 8h |
| [TASK_EXAM_MONITOR] | Every Wednesday 8h |
| [TASK_COMPETITOR_MONITOR] | Day 1 of each month |
| [TASK_ON_DEMAND_A] … [TASK_ON_DEMAND_G] | On demand |

---
*Update whenever you install/remove MCPs, skills, or plugins, or change infra. Record in `_CHANGELOG.md`.*
