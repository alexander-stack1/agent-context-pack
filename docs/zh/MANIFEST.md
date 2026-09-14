# _MANIFEST.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> 上下文导向文件，Claude 在本文件夹任何任务前阅读。
> 最后更新：13/09/2026（法律 vault 作为第二大脑）

---

## 关于本文件夹

这是 [YOUR_NAME]（[YOUR_NAME]）的正典上下文文件夹：银行劳动法律师、学者（[YOUR_UNIVERSITY] 硕士、博士候选人）与 legaltech 产品创始人。文件夹汇集工作身份、品牌声音、协作规则、项目状态与知识 vault。

`[CONTEXT_DIR]/` 文件夹（在 Mini 上：`[CONTEXT_DIR]`）是正典运营上下文的**唯一**来源。任何助手、在任何机器上，开始任务前必须只阅读本文件夹中的文件。

有两个 Obsidian vault，角色不同：

- **上下文 / `[YOUR_NAME]/`**：运营 vault（Karpathy 方法：人读，LLM 写）。
- **法律**：所有智能体的领域第二大脑：`[DOMAIN_VAULT]`（Mini 上快捷方式 `[DOMAIN_VAULT]`；约 4.5k 笔记：判例、立法、新闻、RAG、先例）。它不替代本文件夹的 Camada 1。

**强制路由：** 任何与法、判例、立法、先例、学说、法律新闻、法律 RAG 或法律领域研究相关的请求，**所有 AI 与智能体**必须在编造或即兴之前查阅并指向法律 vault（`[DOMAIN_VAULT]`）。`[YOUR_NAME]/` vault 仍仅用于运营上下文与 Karpathy 方法。

Karpathy 流程在 `[YOUR_NAME]/`：

1. 在 `raw/` 捕获（带日期）。
2. 在 `wiki/<domain>/` 编译（耐久主题笔记）。
3. 通过 `wiki/00-indices/` 的 MOC 查阅。
4. 用定期审查维护（双周健康检查）。

---

## CAMADA 1，正典文档
> 任何会话中先读这些文件。它们是当前真相来源。

| 文件 | 说明 | 更新频率 |
|---------|-----------|:------------------------:|
| `agent_rules.md` | 任何 AI 的通用规则（无关工具的入口） | 每月 |
| `senior-implementer-instructions.md` | 高级代码实现者（人或智能体）的运营汇编：DoD、TDD、Postgres/Docker/K8s、安全、staged-write | 正典中的工程变更时 |
| `about-me.md` | 上下文指针：优先级、运营规则、vault 方法 | 每月 |
| `identity.md` | [YOUR_NAME] 是谁、专业方向、学术风格、反 AI 模式 | 每半年 |
| `stack.md` | 工具、MCP、skills、插件、LightRAG、RAG 流水线、子智能体 | 每周 |
| `working-style.md` | 协作规则、研究与工程协议、智能体治理、供审计代码的任何 AI 使用的应用安全 | 每月 |
| `templates-agent/` | 按仓库的记忆模板（`CLAUDE.md`、`REPO_MAP`、`DECISIONS`、boot）+ S/M/C 参考；正典 S/M/C 在 working-style | 智能体 boot 变更时 |
| `brand-voice.md` | 品牌声音、正典长篇学术与技术写作风格 | 每半年 |
| `ux-ui-INDEX.md` | UX/UI 路由（WEB vs MOBILE）、R0 与 60-30-10 色彩；界面任务时加载 | 持续 |
| `ux-ui-criteria.md` | UI MUST/MUST-NOT 标准（Norman/Krug/Yablonski/Refactoring UI/Johnson）+ 清单 | 持续 |
| `ux-ui-web-landing.md` | WEB landing 的子规则与步骤 0–14 | 持续 |
| `ux-ui-mobile.md` | MOBILE 子规则（landing / app / chat） | 持续 |
| `ux-ui-REQUESTS.md` | 精简菜单：招聘/重构 UI 时要请求什么（7 个 PT skills） | 持续 |
| `_PROJETOS-ATIVOS.md` | 各方向当前状态与下一步 | 每周 |
| `[YOUR_NAME]/wiki/00-indices/_HOME.md` | 知识 vault 入口面板 | 持续 |
| `[YOUR_NAME]/wiki/00-indices/open_questions.md` | 开放问题、不确定与待决事项 | 持续 |

---

## CAMADA 2，领域
> 仅当任务明确触及该领域时加载。

### 知识（vault `[YOUR_NAME]/`）

| 路径 | 领域 | 何时加载 |
|---------|---------|----------------|
| `[YOUR_NAME]/wiki/00-indices/` | 按领域的 MOC 与索引 | 任何 vault 研究的起点 |
| `[YOUR_NAME]/wiki/direito-trabalho/` | 已编译劳动法内容 | 劳动法任务 |
| `[YOUR_NAME]/wiki/concursos/` | 检察院科目（[ORG_A]、[ORG_B]） | 考试学习 |
| `[YOUR_NAME]/wiki/[PRODUCT_A]/` | 产品、设计系统、功能 | [PRODUCT_A] 与 [PRODUCT_B] 任务 |
| `[YOUR_NAME]/wiki/tech/` | 技术、本地 AI、设计、编程 | 技术与自动化任务 |
| `ux-ui-*.md` (root) | 面向 UI 智能体的 WEB/MOBILE 标准与步骤 | 任何 UI、landing、app shell 或聊天 |
| `[YOUR_NAME]/raw/` | 带日期的原始捕获 | 编译新 wiki 笔记前 |
| `[YOUR_NAME]/Clippings/` | 已筛选的网页剪藏 | 查阅已保存材料 |

### 运营与资产

| 路径 | 领域 | 何时加载 |
|---------|---------|----------------|
| `ativos-[YOUR_FIRM]/` | [YOUR_FIRM] 信笺抬头与标志 | 生成事务所文书与文件 |
| `credenciais/` | 集成凭证 | 仅在需要访问的自动化任务（见 `_PARA-REVISAR.md`） |
| `appsec-rules.md` | 完整 fail-closed 手册（10 条规则 + 矩阵 + 已批准）；粘贴到 Claude AppSec Project | 审计、安全审查、auth/密钥/部署修复 |
| `documentos/` | 零散文档与项目状态 | 点查 |
| `Desktop/Negócio/Nexo [BRAND_KIT_DIR] /kit-nexo/` | Nexo Tecnologia 品牌包：标志、调色板、字体、头像、签名与各网络物料。规则见 `01-logotipo/logomarca.md` | 任何 Nexo 视觉物料 |

---

## CAMADA 3，归档（默认忽略）
> 除非 [YOUR_NAME] 明确要求，否则不要加载。

| 路径 | 内容 |
|---------|----------|
| `documentos/_arquivo/` | 旧状态与文档，保留作历史 |
| `changelog/` | Manifest/Changelog/Projects 的备份与旧版 |
| `[YOUR_NAME]/trash/` | 删除前隔离 |
| `*_v1`, `*_v2`, `*_old`, `*_backup` | 先前文件版本 |

---

## 按方向的 Skills
> 路由图。识别任务方向后，优先这些 skills。

### 银行劳动法（亲请求人）

| 任务 | Skill |
|--------|-------|
| 阅读新案件、文书摘要 | `resumo-processo` |
| 诉状、答辩、备忘录（一审） | `advogado-trabalhista-bancario` |
| 和解计算与提案 | `calculo-acordo-trabalhista` |
| 鉴定报告与计算 | `perito-trabalhista-bancario` |
| 质疑计算或报告 | `contador-trabalhista-impugnacao` |
| 再审上诉、embargos、agravo | `especialista-recurso-revista` |
| 对雇主上诉的反驳 | `contrarrazoes-trabalhistas` |
| 执行与清算 | `execucao-trabalhista` |
| 判例研究 | `pesquisa-jurisprudencia`, `jurisprudencia-stf-direitos-sociais` |
| 劳动程序学说（管辖、期限、无效、上诉、执行） | `martins-processo-trabalho` （Sergio Pinto Martins 书转换；私有仓库 `[YOUR_GITHUB]/martins-processo-trabalho`） |
| 核验法律或程序 | `legislacao-brasileira:verificar-legislacao` |

### 学术（[YOUR_UNIVERSITY]，博士）

| 任务 | Skill |
|--------|-------|
| 撰写或审阅文章、论文、章节 | `revisor-academico-juridico` |
| 学说分析与预立项 | `professor-trabalho-previdenciario-[YOUR_UNIVERSITY]` |
| ABNT 学习文档 | `documento-estudo-abnt` |
| STF 判决分析 | `analise-jurisprudencia-stf` |

### Legaltech 与产品

| 任务 | Skill |
|--------|-------|
| Legaltech 市场情报 | `analise-mercado-juridico` |
| 从对话生成 PRD | `gerar-prd` |
| 将计划拆成 issues | `quebrar-em-issues` |
| Issue 分诊 | `triagem` |
| 评估法律检索或 RAG 相关性（0–3 分、精确率、召回、golden set） | `avaliar-relevancia-jurisprudencia` |

### 开发与自动化

| 任务 | Skill |
|--------|-------|
| 团队编排与架构 | `nexo-agents-team` (cto, backend, frontend, devops, dba, qa) |
| 高级实现者运营合同（DoD、TDD、基础设施、安全） | `senior-implementer-instructions.md` (Camada 1) |
| 完整代码审查 | `especialista-revisao-codigo` |
| 端到端系统分析 | `analisador-sistema-ponta-a-ponta` |
| Commit、push 与 PR | `commit-push-pr` |
| 交互式架构图 | `archify` (architecture, workflow, sequence, data-flow, lifecycle) |
| TDD red-green-refactor | `tdd` |
| 纪律化调试 | `diagnose` |
| 模块深化 | `improve-codebase-architecture` |
| 在系统上下文中解释代码 | `zoom-out` |
| 一次性原型 | `prototype` |
| Code review Standards + Spec | `review` |
| 以微小提交做重构计划 | `request-refactor-plan` |
| 跨会话上下文交接 | `handoff` |
| 对照领域模型拷问 | `grill-with-docs` |
| SaaS 竞争情报 | `[PRODUCT_C]` |
| 产品伙伴（从想法到发布） | `product-partner` |

### 基础设施与运维

| 任务 | 参考 |
|--------|-----------|
| 架构可视化（交互 HTML/SVG 图） | `archify` (5 types: architecture, workflow, sequence, data-flow, lifecycle) |
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
| 应用安全（OWASP、RLS、OAuth、部署） | `working-style.md` “应用安全”一节（10 块） |

### 智能体治理

| 任务 | 参考 |
|--------|-----------|
| 生产智能体清单 | Memory `agente-ia-producao` (9 blocks) |
| 多智能体编排（Fable） | Memory `multi-agent-sessions` (coordinator pattern, threads, MCP routing) |
| 零幻觉 RAG 流水线 | CTO 与 Solution Architect skills（10 阶段，强制置信评分） |

### 品牌与内容

| 任务 | Skill |
|--------|-------|
| [YOUR_HANDLE]、[YOUR_FIRM] 与产品的文案 | `copy-marca-pessoal` |
| 标志、视觉识别与平面物料 | `working-style.md` 中的“设计与视觉识别流程”一节 |
| UI / landing / app / chat | `ux-ui-REQUESTS.md` → PT skills (`planejar-interface`, `desenhar-landing`, `revisar-experiencia`, `refatorar-interface`, `polir-para-ship`, `provar-com-screenshot`, `redesenhar-[PRODUCT_A]`); motors: gates + impeccable |

### 知识与生产力

| 任务 | Skill |
|--------|-------|
| 综合主题或长文 | `sintetizador` |
| 压缩应答模式 | `modo-conciso` |
| 用访谈压测计划 | `entrevistar`, `entrevistar-com-contexto` |
| 操作 Obsidian vault | `obsidian-cli`, `obsidian-markdown`, `obsidian-bases` |
| 将文档译为 PT-BR | `tradutor-documentos` |
| 创建或调整 skill | `criar-skill`, `skill-creator` |
| 将书（PDF、EPUB、DOCX 等）转为智能体 skill | `book-to-skill` （安装于 `~/.claude/skills/book-to-skill`，命令 `/book-to-skill`） |

### 文档输出

| 格式 | Skill |
|---------|-------|
| Word | `docx` |
| Excel | `xlsx` |
| 演示文稿 | `pptx` |
| PDF | `pdf` |

---

## Vault 模板（`[YOUR_NAME]/templates/`）

| 模板 | 用途 |
|----------|-----|
| `template-daily.md` | 日记 |
| `template-raw.md` | 带日期的原始捕获 in `raw/` |
| `template-wiki.md` | `wiki/<domain>/` 中的耐久主题笔记 |

---

## 本文件夹操作规则

1. **任何任务前**，阅读 `about-me.md`（指针）、`identity.md`（身份）、`stack.md`（工具）与 `working-style.md`（规则）。
2. **长文**（预立项、文章、论文、意见书、备忘录、长篇文书）适用 `brand-voice.md` 的“长篇学术与技术写作风格（正典）”，交付前跑收尾清单。
3. 未经 [YOUR_NAME] 明确确认，**绝不删除文件**。
4. **模糊或待决事项**放入 `_PARA-REVISAR.md`。
5. **若文档日期不清**，标为 `VERIFY`。
6. **创建新文档时**，保存到正确文件夹并报告路径。
7. **文档版本**：使用 `_YYYY-MM-DD` 后缀。
8. **在 vault 中**引用其他笔记时，使用 wikilink `[[note-name]]`。
9. **每次结构变更**记录到 `_CHANGELOG.md`。

---

## 当前文件夹结构

```
📁 [CONTEXT_DIR]/
│
├── 📄 _MANIFEST.md            ← 本文件（导航图）
├── 📄 agent_rules.md          ← 任何 AI 的通用规则
├── 📄 senior-implementer-instructions.md ← 编码者的运营合同
├── 📄 about-me.md             ← 指针：优先级、规则、vault 方法
├── 📄 identity.md             ← 稳定职业身份
├── 📄 stack.md                ← 工具、MCP、skills、AI 基础设施
├── 📄 working-style.md        ← 协作与治理规则
├── 📄 brand-voice.md          ← 品牌声音
├── 📄 ux-ui-INDEX.md         ← UX WEB/MOBILE 路由 + 60-30-10
├── 📄 ux-ui-criteria.md      ← MUST/MUST-NOT + UI 清单
├── 📄 ux-ui-web-landing.md   ← WEB landing 步骤
├── 📄 ux-ui-mobile.md        ← MOBILE 步骤
├── 📄 ux-ui-REQUESTS.md      ← 菜单：要请求什么
├── 📄 _PROJETOS-ATIVOS.md     ← 方向状态
├── 📄 _PARA-REVISAR.md        ← 待决事项
├── 📄 _CHANGELOG.md           ← 变更历史
│
├── 📁 [YOUR_NAME]/                   ← 运营 Obsidian vault（Karpathy 方法）
│                                （法律第二大脑：快捷方式 [DOMAIN_VAULT]）
│   ├── 📁 raw/                ← 带日期原始捕获
│   ├── 📁 wiki/               ← 耐久主题笔记
│   │   ├── 00-indices/        ← 按领域 MOC
│   │   ├── concursos/         ← 检察院
│   │   ├── direito-trabalho/  ← 劳动法内容
│   │   ├── [PRODUCT_A]/         ← legaltech 产品
│   │   └── tech/              ← 技术、本地 AI、设计
│   ├── 📁 Clippings/          ← 已筛选网页剪藏
│   ├── 📁 templates/          ← 可复用模板
│   ├── 📁 reports/            ← 生成报告
│   ├── 📁 images/             ← 视觉附件
│   └── 📁 trash/              ← 隔离区
│
├── 📁 ativos-[YOUR_FIRM]/             ← 信笺抬头与标志
├── 📁 credenciais/            ← 集成凭证
└── 📁 documentos/             ← 零散文档
```

---
*每当文件夹结构变更或新增领域时更新本文件，并在 `_CHANGELOG.md` 记录变更。*
