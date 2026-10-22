# guardrails.md — 钩子强制锁

> 公开模板。在私有覆盖层中调整上限、路径和脚本。

原则：明确的任务执行到底；钩子守住红线而无需询问。解析后的守卫内部错误一律**拦截**（fail-closed）。

## 硬拦截，不可放行
1. **凭据：** 读取 `credentials/`、`.env*`（`.env.example`、`.env.sample`、`.env.template` 除外）、`~/.ssh`、代理 CLI 的认证文件和测试 storageState。
2. **密钥：** `printenv`、`env`、把保险库内容直接打印到终端、`echo` 密钥变量。密钥只能通过注入（`[VAULT_CLI] run ...`）。
3. **推送：** force push（`--force`、`-f`、`--force-with-lease`、带 `+` 的 refspec）、推送到 `main`/`master`、删除 `main` 或修改其保护。其他分支推送自由。
4. **提交：** 永不使用 `--no-verify`。钩子是证据的一部分。
5. **合并：** 只能通过 `scripts/merge-safe.sh`（CI 绿色、审查批准绑定 head sha、`--match-head-commit` squash、绝不 `--admin`）。
6. **部署：** 只能通过 `scripts/deploy-safe.sh`（已知上一版本、定义回滚、冒烟测试失败自动回滚）。
7. **资金：** 生产支付 API 只能经带单笔和每日上限的封装（`config/limits.toml`）；禁止退款、webhook、密钥、账户或转账；全部记录。
8. **生产数据：** 在本地/测试库之外执行 `DROP`、`TRUNCATE` 或无 `WHERE` 的 `DELETE`；删除数据库、存储桶或仓库；在 `scripts/migrate-prod.sh` 之外做远程迁移（拒绝破坏性迁移，先快照）。
9. **客户数据：** 上传（`scp`、远程 `rsync`、`curl` 上传、云 CLI、gist、上传类 MCP）`config/client-data.txt` 中列出的路径。
10. **只读子代理：** 无 Edit、Write、patch 或写入型 shell。

## 可临时放行的拦截（仅限人类终端）
11. 对外发送（邮件、聊天、支付）。邮件和消息走草稿。
12. 本地破坏性操作：当前仓库或 `/tmp` 之外的 `rm -rf`；在 `main` 或未知 cwd 下的 `reset --hard`、`clean -f`、`branch -D`。

## 仅警告
13. 命中 S/M/C 黑名单却未声明 `Effort: C`（仪式，不是许可）；写入同步文件夹（iCloud/Drive）或回收站。
14. PostToolUse：输出疑似包含密钥时警告。
15. 领域请求时提醒核验来源。

## 本地运行
- 开发服务器只绑定 `127.0.0.1`，绝不 `0.0.0.0`。管理面板不对互联网开放。
- 编辑规范文件或配置前：在旁边做带时间戳的备份 `file.bak-YYYYMMDD-HHMMSS-[REASON]`。
- 代码放在同步文件夹之外，按约定放在 `~/dev`（具名例外见 `PATHS.md`）。

## 记录与证明
- 每个决定（allow、警告、deny、allow-已批准）写入 `logs/harness.jsonl`，只记元数据。
- `evals/` 用代理 CLI 的载荷回放测试守卫；`sync-harness --check` 运行评测。
- 参考实现：所有支持钩子的 CLI 读取同一个 `guard-pretooluse`。

## 文件大小
- 代理编写的文件：最多约 5,000 token（≈ 20,000 字节）。pre-commit 钩子只检查已暂存文件。
- 排除：锁文件、生成代码、二进制/资产、`@generated`/`DO NOT EDIT`，以及 `.agent-size-ignore`（需注明理由）。
- 按职责拆分，绝不按行数；用重导出保持公共 API；运行构建、lint 和测试。
