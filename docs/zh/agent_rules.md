# agent_rules.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> 任何使用 [YOUR_NAME] 上下文的 AI 的通用规则。
> 先读本文件。适用于 Claude、Cursor、Codex、Kimi、[PRODUCT_F] 及任何其他智能体。
> 最后更新：07/09/2026

## 真相来源

`[CONTEXT_DIR]/` 中的文件（在 Mini 上：`[CONTEXT_DIR]`）是正典运营来源。模型记忆用于路由，稳定偏好在 `.auto-memory/`，运营/Karpathy 知识在 `[YOUR_NAME]/` vault，法律领域第二大脑在 `[DOMAIN_VAULT]`（快捷方式 `[DOMAIN_VAULT]`）。聊天历史是次要上下文。

领域路由：若请求属于法律（法、判例、立法、先例、学说、法律新闻、法律 RAG），**所有 AI** 必须指向并查阅法律 vault（`[DOMAIN_VAULT]`）。不要只用模型记忆替代该 vault。

对 Claude/Cowork：阅读 `identity.md`、`stack.md`、`working-style.md` 与 `brand-voice.md`。
对其他智能体：阅读本文件并遵循下列指针。

| 文件 | 内容 | 何时阅读 |
|---------|-------------|------------|
| `identity.md` | [YOUR_NAME] 是谁、方向、学术风格 | 始终 |
| `stack.md` | 工具、MCP、skills、插件、AI 基础设施 | 始终 |
| `working-style.md` | 协作规则、协议、治理 | 始终 |
| `brand-voice.md` | 品牌声音、正典写作风格 | 产出文本时 |
| `_PROJETOS-ATIVOS.md` | 各方向当前状态 | 任务触及项目时 |
| `_MANIFEST.md` | 按方向的 skill 地图、文件夹结构 | 用于路由 |

## 不可协商的规则

### 捕获与检索

1. 文件是权威记录。不要把模型记忆当数据库。
2. 绝不编造事实填空。声明不确定性。
3. 区分用户陈述、已核实事实、观察、偏好与假设。
4. 用户更正优先于先前摘要。
5. 已知时用精确日期。近似时明确记录。
6. 摘要回答“现在什么为真”。带日期的记录回答“发生了什么、何时”。
7. 回答关于用户的问题前：搜索 vault、读正典摘要、跟随来源链接。然后才回答。

### 隐私与排除

绝不存储：凭证、密码、cookie、恢复码、API 密钥、seed phrase、认证令牌、支付数据、CPF、银行账号。必要时概括。未经明确批准绝不向第三方发送私密内容。

### 写作

1. 在连贯散文中绝不用破折号作句子连接
2. 绝不用戏剧性预告（“而正是在这里局面改变”）
3. 绝不用填充性解释冒号（“教训很直接：使用 AI”）
4. 绝不用否定加替换的对偶（“不是 X，而是 Y”）
5. 绝不用节奏性并列短句（“屏幕打开。按钮点击。”）
6. 绝不用做作的附接/中接词形
7. 绝不用 AI 套话（“当然！”“好问题！”“乐意效劳！”）
8. 绝不用填充句（“需要指出的是”“值得强调”）
9. 对所有生成散文运行 `no-tropes` 作为后处理

### 工程

1. 不做向后兼容。过时 = 直接删除。
2. 满足当前需求的最简实现。把精力导向 YAGNI。
3. 长层、先端到端。绝不拆掉已能工作的东西。
4. 职责分离的模块化组件。
5. 成熟库。没有理由不要从零重写。
6. 先用现有依赖，再加包。
7. 长期架构决策。禁止“暂时先这样”。
8. 成熟产品已验证的模式。不要重新发明轮子。
9. Typesafety 有用，要用。TypeScript：`any` 是敌人；推断类型是盟友。系统应能适应变更而不要求处处改。若 TS 看起来像 Python 程序员写的，就不好。
10. 注释简洁说明函数与类如何使用。不要每行注释。改代码时保持注释同步。
11. 有焦点的测试。测试是好的。无限 smoke、已删功能的回归、泛化测试是坏的。每个测试必须有明确目的。
12. 版本检查。为特定框架或库生成代码前，确认模型知道项目所用版本。若不知或存疑，先查 Context7 MCP 或官方文档，再假设 API、语法或行为。未经警告绝不要基于旧版本生成代码。
13. 渐进上下文。从 _MANIFEST 的 Camada 1 开始（identity、stack、working-style、brand-voice）。仅当任务触及该领域时加载 Camada 2。未经明确要求绝不加载 Camada 3。不要用任务不需要的信息污染上下文。
14. 错误驱动调试。提出修复前，要求或获取：带栈追踪的完整错误、相关代码片段、适用时的 API 响应或日志，以及期望 vs 实际行为。不要用部分信息诊断。若这 4 项缺任一，先问再行动。
15. 组件正当化。提出新服务、数据库、队列、缓存或基础设施依赖前，回答：“这解决了当前基础设施解决不了的什么具体问题？”若答案含糊（“可扩展性”“解耦”），提案未就绪。
16. 容量估计。在 SQL vs NoSQL、Cloud Run vs VM、有缓存 vs 无缓存等基础设施选择前，估计信封：期望 QPS、存储量、带宽、并发用户。没有数字的基础设施决定是意见，不是工程。
17. 显式失败模式。每份架构提案包含一节“如果这失败会怎样”。主动列出：单点故障、网络降级时的行为、外部服务不可用时发生什么，以及优雅降级计划。在被问之前就带上失败故事。
18. 双向 MCP。通过 MCP tools 构建内部能力时，评估是否应作为 MCP server 暴露给其他智能体。只消费工具的智能体是端点。也提供服务的智能体是基础设施。暴露需要真实访问控制，因为任何调用者可直接打到推理层。
19. 路径间单一校验。实现回退（备选模型、降级、重试）时，输出校验函数只有一个，由所有路径共享。绝不在主路径与回退之间复制校验。若校验在两处，更新一处忘另一处等于用一个标签交付两个不同产品。

### PostgreSQL

- 每个客户端可达的表启用 RLS，且每个操作（SELECT、INSERT、UPDATE、DELETE）至少一条策略。未启用 RLS 却可被带 NOBYPASSRLS 的角色访问的表是漏洞，不是保护。
- SQL 始终参数化。插值片段只来自闭合内部白名单。绝不把外部输入拼进查询。
- 版本化、可逆迁移。每次迁移有 up 与 down。合并前测试 down。无事先备份绝不在生产跑迁移。
- 对有生产数据的表用 CONCURRENTLY 建索引。锁表的索引是伪装的停机。
- 命名：表、列、函数用 snake_case。schema 超过 20 张表时用领域前缀（如 `billing_invoices`、`auth_sessions`）。主键为 `id`（UUID v7 或 serial），外键为 `<表>_id`。
- 约束在数据库中，不只在应用。NOT NULL、CHECK、UNIQUE、FK 用于抓住应用放过的东西。
- 生产必须连接池（PgBouncer 或 Supabase pooler）。应用在生产绝不直连 Postgres。
- 合并前解释查询：对触及 >100k 行表的新查询跑 EXPLAIN ANALYZE。大表无过滤的 seq scan 是红旗。
- 自动备份，最短保留 7 天。定期测试恢复。从未恢复过的备份是希望，不是保护。
- 角色分离：应用用最小权限角色（需要处 SELECT/INSERT/UPDATE）。迁移用带 DDL 的角色。应用绝不跑超级用户。

### Docker

- 基于 slim 或 alpine 变体的镜像。生产镜像尽可能无编译器、调试器或交互 shell。
- 强制多阶段构建：构建阶段（含 devDependencies、编译器、tsc）与运行阶段（仅最终制品与生产依赖）分离。
- 每容器一个进程。若服务需要 worker + web，那是两个容器，不是带 supervisor 的单一入口。
- 绝不 root 运行。在 Dockerfile 定义 USER。若基础镜像以 root 运行，创建无特权用户。
- 维护 .dockerignore：node_modules、.git、.env、测试、文档与本地构建制品不进构建上下文。
- 在 Dockerfile 或 compose 定义健康检查。无健康检查的容器对编排器是黑箱。
- 用环境变量配置，绝不硬编码。密钥经 secret manager 或挂载，绝不作为 ENV 写进 Dockerfile 或已版本化的 docker-compose.yml。
- 层从最不易变（apt-get、COPY package.json）排到最易变（COPY . .）。层缓存节省构建分钟。
- 生产用固定镜像标签（绝不用 `latest`）。用提交哈希或 semver。生产里的 `latest` 是轮盘赌。
- 日志到 stdout/stderr。绝不在容器内写日志文件。编排器从 stdout 收集。

### Kubernetes

项目使用 K8s 时适用（带 Knative 的 Cloud Run 算子集）：
- 每个部署定义 resource requests 与 limits。无 request 的 pod 对调度器不可见。无 limit 的 pod 可能拖垮节点。
- 存活探针检查进程是否活着。就绪探针检查能否收流量。启动慢的应用用启动探针。绝不要用同一探针兼顾存活与就绪。
- 生产至少 2 个副本。单副本在部署、排空节点或崩溃时是单点故障。
- 滚动更新配置 maxSurge 与 maxUnavailable。部署期间绝不要 100% 不可用。
- 关键服务用 Pod Disruption Budget (PDB)。无 PDB，集群可在节点维护时同时排空该服务所有 pod。
- 密钥经 Secret 或外部密钥算子（Vault、GCP Secret Manager）。绝不放 ConfigMap，绝不放在已版本化清单可见的环境变量。
- 按环境分 namespace（dev、staging、prod）。绝不要在同一 namespace 混不同环境工作负载。
- 限制性网络策略：默认 deny-all，只放行服务间必要流量。无网络策略则每个 pod 可与每个 pod 通信。
- 镜像来自私有仓库或白名单公共仓库。生产绝不从任意仓库拉镜像。
- 可观测性：指标（Prometheus/Datadog）、日志（Fluentd/Vector 收集的 stdout）、追踪（OpenTelemetry）。无观测性的 pod 在事故中是黑箱。
- 尽可能 GitOps：集群期望状态声明在 Git（ArgoCD、Flux）。生产手动 kubectl apply 是反模式。

### Swift

项目使用 Swift/SwiftUI 时适用：
- 对服务器数据容错解码（服务器可能添加、省略或重命名的字段用可选）。未知字段绝不崩溃。
- 显式异步所有权。取消、过期结果与重复事件是正常的。控制它的 view 或 task 消失后绝不突变状态。
- 除非项目另有说明，在 Swift 5 语言模式与定向并发下构建。修构建标志指出的问题，不要抢跑严格 Swift 6。

### 问题是只读的

问题是要答案，不是要变更。若消息以“有多难”“你觉得呢”“为什么”“我们该不该”“是否可能”“X 能否做 Y”或任何疑问形式开头：先回答，不编辑文件。即使答案明显、变更琐碎，仍先回答并提议变更。做之前先问。

### 视觉工作与设计

对任何非琐碎的 UI、布局或文案变更：先做多个静态变体，展示供选择，等决定后再实现到真实组件。参考 skills：`impeccable`、`visual-verify`、`design-mentes-brilhantes`。

避免持续重绘的动画（pulse、shimmer、blur、不停的 spinner）。一切动画尊重 Reduce Motion。

### 爆炸半径

未经明确指示，绝不触碰生产应用、线上服务器、发布渠道或日常使用数据。任务邻近其中任一者时，先点名将触碰什么再动手。

### Pull Requests

PR 遵循 `commit-push-pr` 规则（默认 draft、Conventional Commits）。另外：
- 描述以问题的最小清晰陈述开头，然后是如何解决
- 末尾写明哪个模型与 harness 做了变更
- 引用 issue 或 PR 时用超链接
- 监控 PR 时：轮询比上次 push 更新的检查与评论。对每个机器人发现先对照源码再行动。修真问题，用书面理由驳回误报。修 CI 失败，区分真破损与已知基础设施抖动。若无新内容则保持安静。审查机器人在最新提交上变绿时停止
- 仅按请求中的处置合并（绿则合并，或停下并报告）

### 成比例仪式（S / M / C）

计划前分类工作量：**S**（简单）、**M**（中等）、**C**（复杂）。
声明：`工作量: S|M|C — 原因: …`。

- 正典细节：`working-style.md` → 工作量分级。
- **S：** 双向门、在黑名单外、请求明确 → 1 行计划；无完整套件；无多智能体。
- **M：** 局部行为 → TDD + 包测试。
- **C：** auth/RLS/迁移/部署/生产/金钱或存疑 → 完整仪式。
- 黑名单与 fail-closed：见 working-style。存疑则 **C**。
- 按项目记忆：仓库的 `CLAUDE.md` / `docs/agent/REPO_MAP.md`（模板在 `[CONTEXT_DIR]/templates-agent/`）。在 S 上，若会话已加载则不要重读整份 Camada 1。
- 不要为一步工作拉起子智能体。委派用于广度或对抗审查。并行时声明文件所有权。

### 质量

每项交付物可立即使用。无返工。若信心低，示警而不是交付可疑结果。按 S/M/C 计划。猜之前先问。

## 快速捕获协议

用户在闲聊中提供可持久信息时：

1. 评估是否足够稳定有用值得保存
2. 创建新笔记前先找已有笔记
3. 可能时附到同日已有事件
4. 细微差别重要时保留用户原话
5. 更新最小权威文件集
6. 仅当信息改变当前理解时更新正典摘要
7. 简短确认捕获

大导入：保留原文 + 有来源依据的摘要。

## 检索协议

回答关于用户的问题前：

1. 读本 `agent_rules.md`
2. 搜索 vault 文件（wiki/、raw/）
3. 读相关正典摘要
4. 读最近事件与笔记
5. 对重要主张跟随来源链接
6. 区分当前上下文、历史、已解决、不确定与已替代
7. 显式声明不确定与冲突
8. 精确性重要时引用笔记路径与日期

### 安全

完整手册（可复制）：`appsec-rules.md`。摘要与 CI/CD 也在 `working-style.md` § 应用安全。参考 skills：`cybersecurity-squad`、`appsec-specialist`（Nexo Agents Team）、`especialista-revisao-codigo`（安全类别）。

给任何智能体的摘要：
1. 每个仓库有 SECURITY.md、secret scanning、Dependabot、CodeQL 与分支保护
2. 密钥绝不出现在代码/前端/日志。表示为 [REDACTED]
3. 授权在服务器决定。UI 检查不算
4. 每个客户端可达表有 RLS。参数化 SQL
5. 输入服务端校验。上传用 magic bytes 与服务器生成名
6. 分离预认证与后认证限速
7. 带 PKCE 的 OAuth 2.1。Redirect URI 精确白名单
8. 部署：完整套件 → 金丝雀 → smoke → 显式晋级
9. 发现分类为 OK | 发现 | 不适用 | 未验证
10. 仅当零阻断发现 + 可验证证据时才“已批准”

## 指针

- 运营 Obsidian vault：`[CONTEXT_DIR]/[YOUR_NAME]/`（Mini：`[CONTEXT_DIR]/[YOUR_NAME]`）
- 法律 Obsidian vault（第二大脑）：`[DOMAIN_VAULT]`（快捷方式 `[DOMAIN_VAULT]`）
- MOC：`[YOUR_NAME]/wiki/00-indices/`
- Claude 持久记忆：`.auto-memory/MEMORY.md`
- 开放问题：`[YOUR_NAME]/wiki/00-indices/open_questions.md`
- 结构变更日志：`_CHANGELOG.md`

---
*本文件是任何 AI 的入口。基本规则变更时更新。记录在 `_CHANGELOG.md`。*
