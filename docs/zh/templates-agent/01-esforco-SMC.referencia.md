# 工作量分类（S / M / C）

> **公开模板。** 个人标识、律所、产品、邮箱与路径已替换为占位符。见 `PLACEHOLDERS.md`。请勿重新引入真实数据。


> 建议粘贴进 `working-style.md` 的正典模板（单一来源）。
> 短镜像：`agent_rules.md` 与 `senior-implementer-instructions.md`。
> 状态：DRAFT — 未经明确批准前不应用于 Camada 1。

## 目的

使**工程仪式**匹配变更的**风险与可逆性**。
失败关闭、证据与爆炸半径**永不**进入 S 捷径。

## 规划之前

1. 将任务分类为 **S**、**M** 或 **C**。
2. 在响应**第一行**声明：
   `Effort: S|M|C — reason: … — paths: …`
3. 若用户前缀 `[S]`、`[M]` 或 `[C]`，该前缀胜出，**但**黑名单（见下）除外：警告并要求明确确认才能按 S 进行。

## 定义

### S — 简单（须全部为真）

- 局部、显见的变更（错字、内部重命名、文案、无新行为的配置）。
- 文件少（指导：≤ 3），同一模块或文档。
- *双向门*：易于回退。
- 在路径/主题黑名单之外。
- 无新的或变更的公共 API 契约。
- 无 authZ、RLS、OAuth、上传、限流、迁移、部署、密钥、计费/支付、生产。
- 请求无歧义（或 `[S]`）。

### M — 中等

- 有可断言行为的缺陷或功能。
- 范围限于包/模块。
- 不触碰生产或无书面缓解的黑名单。
- S 清单部分失败，但无可逆性问题。

### C — 复杂（任一即为足够）

- 触碰黑名单（见下）。
- 范围不确定、多服务或公共契约。
- 迁移、部署、生产、金钱、对真实系统的分阶段写入。
- 安全审计 / 要求「APPROVED」。
- 分类有疑 → **C**。

## 黑名单（强制 C）

若 diff 或调查触及（路径、符号或主题）：

`auth`、`authorization`、`permission`、`rls`、`oauth`、`pkce`、认证 `middleware`、
`migration`、`deploy`、`production`、`.env`、`secret`、`token`、`service_role`、
`billing`、`payment`、`stripe`、`upload`、`rate.?limit`、`firewall`

→ 分类为 **C**。若用户要求 `[S]`，**不要**按 S 执行：解释并请求确认按 C 处理（或带书面缓解的 M）。

## 按级别的仪式

| 仪式 | S | M | C |
|------|---|---|---|
| 重读完整 Camada 1 | 否，若会话已加载且任务不改规则 | 若触碰产品代码则是 | 是 |
| 仓库记忆（`CLAUDE.md` / `REPO_MAP`） | 仅若已在会话中；打开请求的文件 | `CLAUDE.md` + 地图节 | 契约 + 地图 + 带 cite-and-verify 的检索 |
| 计划 + 批准 | 一行「我将 X」；若请求无歧义则继续 | 短计划；风险 ≠ 零则等待 | 完整计划 + 明确批准 |
| TDD 8 步 | 无行为则 N/A；否则聚焦测试 | TDD + 包/模块测试 | 完整 TDD |
| 全量套件 | 否（路径/包 + lint/typecheck） | 包/模块 | 强制 + 新鲜证据 |
| 变异（「测试咬人」） | 否 | 若有新测试 | 若有新测试则是 |
| 多智能体 | 禁止 | 仅幅度大时 | 对抗性评审 OK |
| 独立评审 / 金丝雀 / 烟雾 | 否，除非要求 | 否，除非邻近生产 | 按部署/安全 |
| 分阶段写入 + 第 2 次批准（金钱/生产） | N/A | 若仅草稿则 N/A | 保留 |
| 失败关闭 / 不编造 / 无令不进生产 | **始终** | **始终** | **始终** |

## 审计行（交付强制）

```
Effort: M — reason: bug in X serializer; assertable behavior
Paths: app/foo/serializers.py, tests/test_foo.py
Verification: pytest tests/test_foo.py (GREEN) + ruff path
Repo: name @ short-sha — map: docs/agent/REPO_MAP.md (date)
```

## 示例

**S**
- README 错字。
- 无公共 API 的局部变量重命名。
- 把研究生材料复制到 Drive 文件夹。

**M**
- 用测试修序列化器缺陷。
- 使用既有认证的只读端点。

**C**
- RLS / OAuth / 迁移 / 部署上的任何变更。
- 新的授权声明。
- 晋级到生产。

## 有疑虑时

按 **C** 处理。YAGNI 管辖变更的*范围*，不管辖*证明*。
