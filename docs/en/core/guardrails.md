# guardrails.md — hook-enforced locks

> Public template. Tune caps, paths and scripts in your private overlay.

Principle: a clear task runs to completion; the hook holds the red lines without asking. An internal guard error after parsing **blocks** (fail-closed).

## Hard block, no release
1. **Credentials:** reading `credentials/`, `.env*` (except `.env.example`, `.env.sample`, `.env.template`), `~/.ssh`, agent CLI auth files and test storageState.
2. **Secrets:** `printenv`, `env`, direct vault reads printed to the terminal, `echo` of secret variables. Secrets only via injection (`[VAULT_CLI] run ...`).
3. **Push:** force push (`--force`, `-f`, `--force-with-lease`, `+` refspec), push to `main`/`master`, deleting `main` or touching its protection. Pushing other branches is free.
4. **Commit:** never `--no-verify`. Hooks are part of the proof.
5. **Merge:** only via `scripts/merge-safe.sh` (green CI, reviewer approval pinned to head sha, squash with `--match-head-commit`, never `--admin`).
6. **Deploy:** only via `scripts/deploy-safe.sh` (known previous version, defined rollback, smoke test and automatic rollback on failure).
7. **Money:** production payment APIs only through a wrapper with per-operation and per-day caps (`config/limits.toml`); no refunds, webhooks, keys, accounts or transfers; log everything.
8. **Production data:** `DROP`, `TRUNCATE` or `DELETE` without `WHERE` outside local/test DBs; deleting databases, buckets or repos; remote migrations outside `scripts/migrate-prod.sh` (refuses destructive ones, snapshots first).
9. **Client data:** uploads (`scp`, remote `rsync`, `curl` upload, cloud CLIs, gist, upload MCPs) of paths listed in `config/client-data.txt`.
10. **Read-only subagent:** no Edit, Write, patch or writing shell.

## Block with temporary release (human terminal only)
11. External sends (email, chat, payments). Email and messages go as drafts.
12. Local destructive: `rm -rf` outside the current repo or `/tmp`; `reset --hard`, `clean -f`, `branch -D` on `main` or with unknown cwd.

## Warning only
13. S/M/C blacklist without declared `Effort: C` (ritual, not license); writes into synced folders (iCloud/Drive) or trash.
14. PostToolUse: warn when output looks like a secret.
15. Source-verification reminder on domain prompts.

## Local operation
- Dev servers bind to `127.0.0.1` only, never `0.0.0.0`. Admin panels closed to the internet.
- Before editing a canonical file or config: timestamped backup next to it, `file.bak-YYYYMMDD-HHMMSS-[REASON]`.
- Code lives outside synced folders, in `~/dev` by convention (named exceptions in `PATHS.md`).

## Logging and proof
- Every decision (allow, warn, deny, allow-approved) goes to `logs/harness.jsonl`, metadata only.
- `evals/` replays agent CLI payloads against the guard; `sync-harness --check` runs the evals.
- Reference implementation: one `guard-pretooluse` read by every CLI that supports hooks.

## File size
- Agent-authored file: up to ~5,000 tokens (≈ 20,000 bytes). Pre-commit hook measures staged files only.
- Excluded: lockfiles, generated code, binaries/assets, `@generated`/`DO NOT EDIT`, and `.agent-size-ignore` (with justification).
- Split by responsibility, never by line count; keep the public API via re-exports; run build, lint and tests.
