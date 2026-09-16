# stack.md

> **公开模板。** 个人标识、律所、产品、邮箱与路径已替换为占位符。见 `PLACEHOLDERS.md`。请勿重新引入真实数据。

> 工具、AI 基础设施与技术能力。变更频繁。
> 最近更新：28/07/2026

## 日常工具

- Obsidian（主库，经 iCloud 同步，位于 `[CONTEXT_DIR]/[YOUR_NAME]/`）
- Claude 与 Cowork（生产助手），含 70+ 本地技能与 20+ 插件
- [AGENT_TEAM]（[N] 名专业智能体，CTO → 经理 → 运营层级）
- [PRODUCT_F]（自有自动化：cron、LLM 网关、采集器）
- Ollama（Apple Silicon 本地模型：qwen2.5:7b、nomic-embed-text）与 OpenRouter（API 模型）
- Python 与 Node 做自动化，Postgres 与嵌入做 RAG
- Git 与 GitHub Actions 做版本与 CI
- Tailscale 远程访问机器
- PJe、邮箱与 WhatsApp 用于律所运营
- [PRODUCT_A]/[PRODUCT_B]（开发中的自有软件）
- [TOOL_MEDIA]（课程、视频与媒体的下载与整理）

## 已连接 MCP

| MCP | 用途 |
|-----|-----------|
| LightRAG | 本地知识图谱（[N] PDF，localhost:9621） |
| Context7 | 直接在上下文中获取最新库文档 |
| Codebase Memory | 代码库知识图谱（跨会话持久） |
| Perplexity | 带 AI 的网络调研 |
| xAI/Grok | 备选 LLM |
| PixelBrowse | 页面截图供 Claude 视觉阅读 |
| Google Calendar | 创建/列出/编辑事件 |
| Gmail | 搜索线程、创建草稿、标签 |
| Slack | 读频道、发消息、搜索、画布 |
| Notion | 创建/编辑页面、数据库、搜索 |
| Figma | 截图、设计上下文、code connect |
| Canva | 生成设计、编辑图像、模板 |
| Google Drive | 搜索/读取/创建文件 |
| Supabase | SQL、迁移、edge functions、分支 |
| Vercel | 部署、项目、日志、域名 |
| Gamma | 生成演示文稿 |
| Adobe Creative Cloud | 照片/视频编辑、模板、设计 |
| Fey (Financial) | 账户、交易、支出分析、预测 |
| Stripe/Invoicing | 创建并发送发票、列出交易 |
| Computer Use | 屏幕控制（鼠标、键盘、截图） |
| Claude in Chrome | 网页浏览、DOM、表单 |
| Mermaid | 校验并渲染图表 |
| Word (By Anthropic) | 创建/编辑 Word 文档 |
| PowerPoint (By Anthropic) | 创建/编辑演示文稿 |
| Microsoft Docs | 搜索并获取 Microsoft 文档 |

**Obsidian，核验说明（28/07/2026）：** 没有已连接的专用 Obsidian MCP。经 `ListConnectors`（「obsidian」为空）与 `SearchMcpRegistry`（公共目录无该名结果）确认。库 `[CONTEXT_DIR]/[YOUR_NAME]/` 已安装并启用 `obsidian-local-rest-api` 插件——这是专用 MCP 服务器的 Obsidian 侧前提——但客户端未配置指向该 API 的 MCP 服务器。实践中，今天对库的访问（读、创建、搜索笔记）经 Desktop Commander 与设备文件桥完成，而非专用 MCP。见技能 `desktop-commander:obsidian-vault`。

## 本地技能（70+）

按领域组织。完整路由见 `_MANIFEST.md`。

| 领域 | 数量 | 主要示例 |
|---------|:---:|---------------------|
| 劳动法 | 13 | [SKILL_DOMAIN_DRAFTING]、[SKILL_APPEALS]、[SKILL_CASELAW_SEARCH] |
| 开发 | 17 | tdd、diagnose、review、zoom-out、improve-codebase-architecture、[SKILL_COMMIT_PR]、archify |
| Google Cloud | 10 | cloud-run-basics、cloud-sql-basics、gcloud、gemini-agents-api、rag-engine-management、monitoring、logging、iam、waf-reliability、solution-architecture |
| 文档 | 9 | docx、pdf、pptx、xlsx、video-editing |
| 设计 | 7+ | 菜单 `ux-ui-REQUESTS.md`：[SKILL_UI_PLAN]、[SKILL_UI_LANDING]、[SKILL_UI_REVIEW]、[SKILL_UI_REFACTOR]、[SKILL_UI_POLISH]、[SKILL_UI_PROVE]、[SKILL_UI_REDESIGN]（引擎：gates + impeccable/frontend-design） |
| Obsidian | 4 | obsidian-cli、obsidian-markdown、obsidian-bases |
| 工作流 | 10 | grill-with-docs、to-prd、to-issues、triage、handoff |
| 写作 | 6 | [SKILL_BRAND_COPY]、edit-article、writing-beats、writing-shape |
| 工具 | 9+ | [PRODUCT_C]、product-partner、[SKILL_CONCISE_MODE]、defuddle |
| 学习 | 3+ | [SKILL_EXAM_STUDY]、[SKILL_STUDY_DOC]、[SKILL_ACADEMIC_REVIEW] |

## 插件（20+）

由系统自动发现。主要有：[AGENT_TEAM]（[N] 智能体）、Adobe for Creativity、Adspirer Ads、Brazilian Legislation、Marketing、Sales、Bright Data、Brand Voice、Engineering、Product Management、Operations、Finance、Searchfit SEO、Box、Wix、Figma、Desktop Commander、PDF Viewer。

## LightRAG（本地知识图谱）

| 项 | 值 |
|------|-------|
| 版本 | 1.4.16 |
| LLM | Ollama qwen2.5:7b（本地） |
| 嵌入 | nomic-embed-text（本地） |
| 已索引文档 | [N] PDF（Dev Library） |
| MCP | lightrag_query、lightrag_insert、lightrag_health |
| URL | http://localhost:9621 |
| 隐私 | 100% 本地 |

## RAG 流水线（10 阶段，零幻觉）

任何从文档作答的 AI 功能的参考架构：

1. 摄入 + 规范化（去重、元数据、版本）
2. 混合检索（BM25 + 嵌入）
3. ANN + 重排序（交叉编码器 MiniLM/BGE）
4. 置信度评分（质量、时效、权威、重叠）
5. 受约束生成（仅来自上下文，无外部知识）
6. 带引用的回答（每条主张有来源）
7. 置信阈值（低于 =「证据不足」）
8. 持续评估（对抗、召回、幻觉率）
9. 缓存 + 记忆层（Redis、TTL、失效）
10. 可观测性（追踪 ID、token 归因、告警）

记录于 [AGENT_TEAM] 的 CTO 与 Solution Architect 技能中。

## 智能体治理

9 块清单与多智能体编排记录在 `working-style.md` 以及 Claude 的持久记忆（.auto-memory）中。

## 个人子智能体与定时任务

| 技能 | 频率 |
|-------|-----------|
| [TASK_MORNING_BRIEF] | 每天 7 时 |
| [TASK_NIGHTLY_REVIEW] | 每天 20 时 |
| [TASK_LAW_MONITOR] | 每周一 8 时 |
| [TASK_EXAM_MONITOR] | 每周三 8 时 |
| [TASK_COMPETITOR_MONITOR] | 每月 1 日 |
| [TASK_ON_DEMAND_A] … [TASK_ON_DEMAND_G] | 按需 |

---
*每当安装/移除 MCP、技能或插件，或变更基础设施时更新。记入 `_CHANGELOG.md`。*
