# modelos.md — 模型与推理强度矩阵（唯一来源）

> 模板。用各厂商官方文档中的确切 ID 和核对日期填写。绝不凭记忆填写 ID。

角色：**ORQ**（编排与规划）、**PES**（重推理）、**EXE**（执行者）、**SIM**（搜索、分诊、提取）。
格式：模型 | 确切 ID | 默认强度 | 最大强度。最大强度仅在人类指示或黑名单 C 级时使用。

| 工具 | ORQ | PES | EXE（明确 / 困难） | SIM |
|---|---|---|---|---|
| `[AGENT_CLI_A]` | `[MODEL_ORQ]` medium | `[MODEL_PES]` high | `[MODEL_EXE]` medium / high | `[MODEL_SIM]` low |
| `[AGENT_CLI_B]` | ... | ... | ... | ... |
| `[IDE_AGENT]` | ... | ... | ... | ... |

## S/M/C 对应模型与强度

| 级别 | 决策与规划 | 执行 | 审查 | 子代理 |
|---|---|---|---|---|
| S（可逆、不在黑名单） | 会话本身 | 内联；机械任务可交给 SIM low | 无 | 仅搜索/分诊 |
| M（可断言的 bug 或功能，TDD） | ORQ medium | EXE medium（测试失败两次则 high） | 测试与 lint；ORQ 审查 | 每模块 1 个 EXE |
| C（黑名单、生产、资金、存疑） | ORQ high，计划并经人类批准 | EXE high | PES high，干净上下文（对抗式） | EXE high、SIM low |

规则：有疑问选 C。`[S]` 前缀不能压过黑名单。审查者绝不是写代码的模型。最终领域写作由 ORQ 或 PES 负责，绝不交给 SIM。
要求厂商侧保留数据的模型绝不接收客户数据。

## 来源
在此列出每个 ID 和每个强度参数的官方 URL。
