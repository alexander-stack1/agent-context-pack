# 每项目记忆启动 + 检索策略

> **公开模板。** 个人标识、律所、产品、邮箱与路径已替换为占位符。见 `PLACEHOLDERS.md`。请勿重新引入真实数据。


> 对模板 04–06 的操作补充。可放在仓库的 `docs/agent/README.md`
> 或作为内部「boot-repo」技能。

## 会话开场仪式（按工作量）

### S
1. 若本会话已读过 `CLAUDE.md` → 不再重读。
2. 仅打开请求相关的文件。
3. 用 `CLAUDE.md` 中的最低命令核验。

### M
1. 阅读 `CLAUDE.md`。
2. 阅读 `docs/agent/REPO_MAP.md` 的相关节（检查 `git_sha`）。
3. 用 `rg` / `Read` 确认路径。
4. TDD + 包测试。

### C
1. `CLAUDE.md` + 主题触及的 `REPO_MAP` + `DECISIONS`。
2. 若涉及认证/数据/部署，加载 Camada 1 appsec（`working-style` / agent_rules）。
3. 检索（Codebase Memory）仅作假说 → cite-and-verify。
4. 在计划中钉住仓库、分支、commit/tree。
5. 完整 C 仪式。

## Cite-and-verify

```
Hypothesis (retrieval): FooService in app/foo/services.py
Proof: Read app/foo/services.py L… — CONFIRMED | UNVERIFIED
```

无证明 → 不基于假说编辑。

## 记忆更新

| 事件 | 动作 |
|--------|------|
| 合并的 PR 改变文件夹/模块结构 | 重新生成 `REPO_MAP` 或标为 `stale` |
| 新的稳定架构决策 | `DECISIONS.md` 中的 ADR |
| 工作中发现的地雷 | 地图 Hotspots 中 1 条要点（同 PR 或后续） |
| 闲聊 | 不写入地图；最多在智能体记忆中放指针 |

## 禁止

- 把代码库粘进 `.auto-memory`
- 把聊天摘要当作地图
- 一个全局 RAG 混入所有产品
- 更新地图却不更新 `git_sha`
