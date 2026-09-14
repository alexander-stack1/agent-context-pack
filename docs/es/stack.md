# stack.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Ferramentas, infraestrutura de IA e capacidades técnicas. Muda con frequência.
> Última actualización: 28/07/2026

## Herramientas del día a día

- Obsidian (vault principal, sincronizado via iCloud, em `[CONTEXT_DIR]/[YOUR_NAME]/`)
- Claude e Cowork (assistente de producción), con 70+ skills locais e 20+ plugins
- Time de agentes Nexo (18 agentes especializados em hierarquia CTO → managers → operacionais)
- [PRODUCT_F] (automação propia: cron, gateway de LLM, coletores)
- Ollama (modelos locais em Apple Silicon: qwen2.5:7b, nomic-embed-text) e OpenRouter (modelos via API)
- Python e Node para automação, Postgres e embeddings para RAG
- Git e GitHub Actions para versionamento e CI
- Tailscale para acesso remoto às máquinas
- PJe, e-mail e WhatsApp na operação da banca
- [PRODUCT_A]/[PRODUCT_B] (software propio em desarrollo)
- OmniGet (download e organização de cursos, vídeos e mídia)

## MCPs conectados

| MCP | Finalidad |
|-----|-----------|
| LightRAG | Knowledge graph local (109 PDFs, localhost:9621) |
| Context7 | Documentação atualizada de bibliotecas direto no contexto |
| Codebase Memory | Grafo de conhecimento do codebase (persiste entre sessões) |
| Perplexity | Investigación web con IA |
| xAI/Grok | LLM alternativo |
| PixelBrowse | Screenshot de páginas para leitura visual pelo Claude |
| Google Calendar | Criar/listar/editar eventos |
| Gmail | Buscar threads, crear rascunhos, labels |
| Slack | Ler canais, enviar mensagens, buscar, canvas |
| Notion | Criar/editar páginas, databases, busca |
| Figma | Screenshots, design context, code connect |
| Canva | Gerar designs, editar imagens, templates |
| Google Drive | Buscar/ler/crear archivos |
| Supabase | SQL, migrations, edge functions, branches |
| Vercel | Deploy, projetos, logs, domínios |
| Gamma | Gerar apresentações |
| Adobe Creative Cloud | Edição de fotos/vídeo, templates, design |
| Fey (Financial) | Contas, transações, spending analysis, forecast |
| Stripe/Invoicing | Criar e enviar faturas, listar transações |
| Computer Use | Controle de pantalla (mouse, teclado, screenshots) |
| Claude in Chrome | Navegação web, DOM, forms |
| Mermaid | Validar e renderizar diagrapero |
| Word (By Anthropic) | Criar/editar documentos Word |
| PowerPoint (By Anthropic) | Criar/editar apresentações |
| Microsoft Docs | Busca e fetch de documentação Microsoft |

**Obsidian, nota de verificación (28/07/2026):** no existe um MCP dedicado ao Obsidian conectado. Confirmado vía `ListConnectors` (vazio para "obsidian") e `SearchMcpRegistry` (ningún resultado con esse nome no diretório público). O vault `[CONTEXT_DIR]/[YOUR_NAME]/` tem o plugin `obsidian-local-rest-api` instalado e ativo, pré-requisito do lado do Obsidian para um servidor MCP dedicado, pero ningún servidor MCP client-side está configurado apontando para essa API. En la práctica, hoy el acceso al vault (ler, crear, buscar notas) acontece via Desktop Commander e pela ponte de archivos do dispositivo, no por um MCP propio. Ver skill `desktop-commander:obsidian-vault`.

## Skills locales (70+)

Organizadas por dominio. Ver enrutamiento completo en `_MANIFEST.md`.

| Domínio | Qtd | Ejemplos principais |
|---------|:---:|---------------------|
| Trabalhista | 13 | advogado-trabalhista-bancario, especialista-recurso-revista, investigación-jurisprudencia |
| Desarrollo | 17 | tdd, diagnose, review, zoom-out, improve-codebase-architecture, commit-push-pr, archify |
| Google Cloud | 10 | cloud-run-basics, cloud-sql-basics, gcloud, gemini-agents-api, rag-engine-management, monitoring, logging, iam, waf-reliability, solution-architecture |
| Documentos | 9 | docx, pdf, pptx, xlsx, video-editing |
| Design | 7+ | Menú `ux-ui-REQUESTS.md`: planejar-interface, desenhar-landing, revisar-experiencia, refatorar-interface, polir-para-ship, provar-com-screenshot, redesenhar-[PRODUCT_A] (motors: gates + impeccable/frontend-design) |
| Obsidian | 4 | obsidian-cli, obsidian-markdown, obsidian-bases |
| Workflow | 10 | grill-with-docs, to-prd, to-issues, triage, handoff |
| Escrita | 6 | copy-marca-pessoal, edit-article, writing-beats, writing-shape |
| Utilitários | 9+ | [PRODUCT_C], product-partner, modo-conciso, defuddle |
| Estudo | 3+ | especialista-concursos, documento-estudo-abnt, revisor-academico |

## Plugins (20+)

Autodescubiertos por el sistema. Principales: Nexo Agents Team (18 agentes), Adobe for Creativity, Adspirer Ads, Legislação Brasileira, Marketing, Sales, Bright Data, Brand Voice, Engineering, Product Management, Operations, Finance, Searchfit SEO, Box, Wix, Figma, Desktop Commander, PDF Viewer.

## LightRAG (Knowledge Graph Local)

| Ítem | Valor |
|------|-------|
| Verson | 1.4.16 |
| LLM | Ollama qwen2.5:7b (local) |
| Embeddings | nomic-embed-text (local) |
| Documentos indexados | 109 PDFs (Biblioteca Dev) |
| MCP | lightrag_query, lightrag_insert, lightrag_health |
| URL | http://localhost:9621 |
| Privacidade | 100% local |

## RAG Pipeline (10 etapas, Zero Hallucination)

Arquitetura de referência para cualquier feature de IA que respdónde a partir de documentos:

1. Ingest + normalização (dedup, metadata, versioning)
2. Hybrid retrieval (BM25 + embeddings)
3. ANN + reranking (cross-encoder MiniLM/BGE)
4. Confidence scoring (quality, recency, authority, overlap)
5. Constrained generation (só do contexto, sin conhecimento externo)
6. Citation-backed responses (cada claim con fonte)
7. Confidence threshold (abaixo = "evidencia insuficiente")
8. Continuous evals (adversarial, recall, hallucination rate)
9. Caching + memory layer (Redis, TTL, invalidação)
10. Observability (trace IDs, token attribution, alertas)

Documentada nos skills do CTO e Solution Architect do Nexo.

## Gobernanza de agentes

Checklist de 9 bloques y orquestación multiagente documentados en `working-style.md` y en la memoria persistente de Claude (.auto-memory).

## Subagentes pessoais e tareas agendadas

| Skill | Frecuencia |
|-------|-----------|
| briefing-matinal | Todos los días 7h |
| code-review-continuo | Todos los días 20h |
| monitor-legislativo | Todos los lunes 8h |
| monitor-concursos | Todos los miércoles 8h |
| monitor-concorrentes | Día 1 de cada mes |
| estudo-adaptativo, revisao-espacada, deploy-guardian, refatoracao-sugerida, jurisprudencia-automatica, investigación-academica, coleta-decisoes | Bajo demanda |

---
*Actualizar siempre que instalar/remover MCPs, skills o plugins, o cambiar a infra. Registrar no `_CHANGELOG.md`.*
