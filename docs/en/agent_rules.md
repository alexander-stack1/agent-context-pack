# agent_rules.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Universal rules for any AI operating with [YOUR_NAME]'s context.
> Read this file FIRST. Works with Claude, Cursor, Codex, Kimi, [PRODUCT_F], and any other agent.
> Last updated: 07/09/2026

## Source of truth

Files in `[CONTEXT_DIR]/` (on the [SECONDARY_MACHINE]: `[CONTEXT_DIR]`) are the canonical operational source. Model memory is for routing, stable preferences live in `.auto-memory/`, operational/Karpathy knowledge lives in the `[YOUR_NAME]/` vault, and the legal domain second brain lives in `[DOMAIN_VAULT]` (shortcut `[DOMAIN_VAULT]`). Chat history is secondary context.

Domain routing: if the request is legal (law, case law, legislation, precedents, doctrine, legal news, legal RAG), **all AIs** must point to and consult the Legal vault (`[DOMAIN_VAULT]`). Do not use model memory alone in place of that vault.

For Claude/Cowork: read `identity.md`, `stack.md`, `working-style.md`, and `brand-voice.md`.
For other agents: read this file and follow the pointers below.

| File | Contents | When to read |
|---------|-------------|------------|
| `identity.md` | Who [YOUR_NAME] is, fronts, academic style | Always |
| `stack.md` | Tools, MCPs, skills, plugins, AI infra | Always |
| `working-style.md` | Collaboration rules, protocols, governance | Always |
| `brand-voice.md` | Brand voice, canonical writing style | When producing text |
| `_PROJETOS-ATIVOS.md` | Current status of fronts | When the task touches a project |
| `_MANIFEST.md` | Skill map by front, folder structure | For routing |

## Non-negotiable rules

### Capture and retrieval

1. Files are the authoritative record. Do not use model memory as a database.
2. Never invent facts to fill empty fields. Declare uncertainties.
3. Distinguish user reports, verified facts, observations, preferences, and hypotheses.
4. User corrections take priority over prior summaries.
5. Use exact dates when known. Explicitly record when approximate.
6. Summaries answer "what is true now". Dated records answer "what happened and when".
7. Before answering a question about the user: search the vault, read the canonical summary, follow source links. Only then answer.

### Privacy and exclusions

Never store: credentials, passwords, cookies, recovery codes, API keys, seed phrases, auth tokens, payment data, CPF, bank account numbers. Generalize when needed. Never send private content to third parties without explicit approval.

### Writing

1. Never use an em dash as a sentence connector in running prose
2. Never use dramatic foreshadowing ("and this is where the game changes")
3. Never use explanatory colon formulas ("the lesson is direct: use AI")
4. Never use negation-plus-substitution antithesis ("it is not X, but Y")
5. Never use rhythmic parataxis ("The screen opens. The button clicks.")
6. Never use artificial enclisis/mesoclisis
7. Never use AI filler language ("certainly!", "great question!", "gladly!")
8. Never use padding phrases ("it is important to note that", "it is worth highlighting")
9. Run `[SKILL_NO_TROPES]` as post-processing on all generated prose

### Engineering

1. No backward compatibility. Obsolete = delete directly.
2. Simplest implementation that meets the current need. Channel energy into YAGNI.
3. Long layers, end-to-end first. Never dismantle what works.
4. Modular components with separation of responsibilities.
5. Mature libraries. Without a reason, do not rewrite from scratch.
6. Existing dependencies first, before adding packages.
7. Long-term architecture decisions. No "for now do it this way".
8. Patterns validated in mature products. Do not reinvent the wheel.
9. Typesafety is useful; use it. TypeScript: `any` is the enemy; inferred types are allies. Systems must adapt to change without requiring edits everywhere. If the TS looks like Python written by a Pythonist, it is bad.
10. Comments concisely describe how functions and classes are used. Do not comment every line. Keep comments in sync with code when changing.
11. Focused tests. Tests are good. Infinite smoke tests, regression tests for deleted features, and generic tests are bad. Each test must have a clear purpose.
12. Version check. Before generating code for a specific framework or library, confirm the model knows the version in use. If not, or if doubtful, consult Context7 MCP or official docs before assuming API, syntax, or behavior. Never generate code based on an old version without warning.
13. Progressive context. Start with Camada 1 of _MANIFEST (identity, stack, working-style, brand-voice). Load Camada 2 only when the task touches that domain. Never load Camada 3 without an explicit ask. Do not pollute context with information the task does not need.
14. Error-driven debugging. Before proposing a fix, require or fetch: full error with stack trace, relevant code snippet, API response or log when applicable, and expected vs actual behavior. Do not diagnose with partial information. If any of these 4 elements is missing, ask before acting.
15. Component justification. Before proposing a new service, database, queue, cache, or infra dependency, answer: "what specific problem does this solve that current infra does not?" If the answer is vague ("scalability", "decoupling"), the proposal is not ready.
16. Capacity estimate. Before an infra decision that chooses among technologies (SQL vs NoSQL, Cloud Run vs VM, with cache vs without), estimate the envelope: expected QPS, storage volume, bandwidth, concurrent users. Infra decision without numbers is opinion, not engineering.
17. Explicit failure modes. Every architecture proposal includes a section "what breaks if this fails". Proactively list: single point of failure, behavior under degraded network, what happens if the external service is unavailable, and the graceful degradation plan. Bring the failure story before being asked.
18. Bidirectional MCP. When building internal capability via MCP tools, evaluate whether it should be exposed as an MCP server for other agents. An agent that only consumes tools is an endpoint. An agent that also serves is infrastructure. Exposure requires real access control because any caller can hit the reasoning layer directly.
19. Single validation across paths. When implementing fallback (alternate model, degradation, retry), the output validation function is one shared by all paths. Never duplicate validation between primary and fallback. If validation lives in two places, updating one and forgetting the other means shipping two different products under one label.

### PostgreSQL

- Every client-accessible table has RLS enabled and at least one policy per operation (SELECT, INSERT, UPDATE, DELETE). A table without RLS enabled that is reachable by a role with NOBYPASSRLS is a hole, not protection.
- SQL always parameterized. Interpolated fragments only from closed internal allowlists. Never concatenate external input into a query.
- Versioned, reversible migrations. Every migration has an up and a down. Test the down before merging. Never run a migration in production without a prior backup.
- Indexes created with CONCURRENTLY on tables with production data. An index that locks the table is downtime in disguise.
- Naming: snake_case for tables, columns, and functions. Domain prefix when the schema has more than 20 tables (e.g. `billing_invoices`, `auth_sessions`). Primary keys as `id` (UUID v7 or serial), foreign keys as `<table>_id`.
- Constraints in the database, not only in the application. NOT NULL, CHECK, UNIQUE, and FK exist to catch what the application lets through.
- Connection pooling mandatory in production (PgBouncer or Supabase connection pooler). The application never opens a direct connection to Postgres in production.
- Queries explained before merge: run EXPLAIN ANALYZE on new queries that touch tables with more than 100k rows. Seq scan on a large table without a filter is a red flag.
- Automatic backups with minimum 7-day retention. Test restore periodically. A backup that was never restored is hope, not protection.
- Separated roles: the application uses a role with minimal permissions (SELECT/INSERT/UPDATE where needed). Migrations use a role with DDL. Never run the application as superuser.

### Docker

- Images based on slim or alpine variants. Production image without compiler, debugger, or interactive shell when possible.
- Multi-stage build mandatory: build stage (with devDependencies, compiler, tsc) separated from runtime stage (final artifacts and production dependencies only).
- One process per container. If the service needs worker + web, those are two containers, not one entrypoint with a supervisor.
- Never run as root. Define USER in the Dockerfile. If the base image runs as root, create an unprivileged user.
- Maintain .dockerignore: node_modules, .git, .env, tests, docs, and local build artifacts stay out of the build context.
- Health check defined in the Dockerfile or compose. A container without a health check is a black box to the orchestrator.
- Environment variables for configuration, never hardcoded. Secrets via secret manager or mount, never as ENV in the Dockerfile or versioned docker-compose.yml.
- Layers ordered from least mutable (apt-get, COPY package.json) to most mutable (COPY . .). Layer cache saves minutes of build.
- Fixed image tag in production (never `latest`). Use commit hash or semver. `latest` in production is roulette.
- Logs to stdout/stderr. Never write logs to a file inside the container. The orchestrator collects from stdout.

### Kubernetes

Apply when the project uses K8s (Cloud Run with Knative counts as a subset):
- Every deployment with resource requests and limits defined. A pod without a request is invisible to the scheduler. A pod without a limit can take down the node.
- Liveness probe checks whether the process is alive. Readiness probe checks whether it can receive traffic. Startup probe for apps with slow boot. Never use the same probe for liveness and readiness.
- At least 2 replicas in production. One replica is a single point of failure during deploy, node drain, or crash.
- Rolling update with maxSurge and maxUnavailable configured. Never 100% unavailable during deploy.
- Pod Disruption Budget (PDB) for critical services. Without PDB, the cluster can drain all service pods at once during node maintenance.
- Secrets via Secret or external secret operator (Vault, GCP Secret Manager). Never in ConfigMap, never in an environment variable visible in the versioned manifest.
- Namespace per environment (dev, staging, prod). Never mix workloads from different environments in the same namespace.
- Restrictive network policies: deny-all as default, allow only necessary traffic between services. Without network policy, every pod talks to every pod.
- Images come from a private registry or allowlisted public registries. Never pull an image from an arbitrary registry in production.
- Observability: metrics (Prometheus/Datadog), logs (stdout collected by Fluentd/Vector), traces (OpenTelemetry). A pod without observability is a black box in an incident.
- GitOps when possible: desired cluster state declared in Git (ArgoCD, Flux). Manual kubectl apply in production is an anti-pattern.

### Swift

Apply when the project uses Swift/SwiftUI:
- Decode server data with tolerance (optionals for any field the server may add, omit, or rename). Never crash on unknown fields.
- Make asynchronous ownership explicit. Cancellation, stale results, and duplicate events are normal. Never mutate state after the controlling view or task has disappeared.
- Unless the project indicates otherwise, build in Swift 5 language mode with targeted concurrency. Fix what the build flags point to, without anticipating what strict Swift 6 would require.

### Questions are read-only

A question is a request for an answer, not a change. If the message opens with "how hard would it be", "what do you think", "why is this", "should we", "is it possible", "can X do Y", or any other interrogative form: answer first, without editing files. If the answer is obvious and the change trivial, still answer and offer the change. Ask before doing.

### Visual work and design

For any non-trivial UI, layout, or copy change: build several static variants first, present them for choice, and wait for the decision before implementing in the real component. Reference skills: `impeccable`, `visual-verify`, `[SKILL_DESIGN_A]`.

Avoid animations that continuously repaint (pulse, shimmer, blur, endless spinners). Every animation respects Reduce Motion.

### Blast radius

Never touch production apps, live servers, release channels, or daily-use data without explicit instruction. When the task is adjacent to any of them, name what will be touched before touching.

### Pull Requests

PRs follow `[SKILL_COMMIT_PR]` rules (draft by default, Conventional Commits). Additionally:
- Description opens with a minimal clear statement of the problem, then how it was solved
- Add at the end which model and harness made the changes
- When referencing an issue or PR, use a hyperlink
- When monitoring a PR: poll checks and comments newer than the last push. Verify each bot finding against source before acting. Fix real ones and dismiss false positives with written justification. Fix CI failures, distinguishing real breaks from known infra flakes. If nothing is new, stay quiet. Stop when review bots are green on the latest commit
- Merge only per the disposition given in the request (merge when green, or stop and report)

### Proportional ceremony (S / M / C)

Before the plan, classify effort: **S** (simple), **M** (medium), **C** (complex).
Declare: `Effort: S|M|C — reason: …`.

- Canonical detail: `working-style.md` → Effort classification.
- **S:** two-way door, outside blacklist, unambiguous request → 1-line plan; no full suite; no multi-agent.
- **M:** local behavior → TDD + package tests.
- **C:** auth/RLS/migration/deploy/prod/money or doubt → full ritual.
- Blacklist and fail-closed: see working-style. When in doubt, **C**.
- Per-project memory: repo `CLAUDE.md` / `docs/agent/REPO_MAP.md` (templates in `[CONTEXT_DIR]/templates-agent/`). On S, do not reread full Camada 1 if the session already loaded it.
- Do not spawn subagents for one-step work. Delegation is for amplitude or adversarial review. In parallel, declare file ownership.

### Quality

Every deliverable ready for immediate use. No rework. If confidence is low, signal instead of delivering something doubtful. Plan per S/M/C. Ask before guessing.

## Quick capture protocol

When the user provides durable information in casual conversation:

1. Assess whether it is stable and useful enough to save
2. Search for an existing note before creating a new one
3. Attach to an existing same-day event when possible
4. Preserve the user's words when nuance matters
5. Update the smallest set of authoritative files
6. Update the canonical summary only if the information changes current understanding
7. Confirm the capture briefly

For large imports: preserve original + source-grounded summary.

## Retrieval protocol

Before answering a question about the user:

1. Read this `agent_rules.md`
2. Search vault files (wiki/, raw/)
3. Read the relevant canonical summary
4. Read the most recent events and notes
5. Follow source links for consequential claims
6. Distinguish current context, history, resolved, uncertain, and superseded
7. Declare uncertainties and conflicts explicitly
8. Cite note paths and dates when precision matters

### Security

Full playbook (copyable): `appsec-rules.md`. Summary and CI/CD also in `working-style.md` § Application security. Reference skills: `[SKILL_SECURITY_SQUAD]`, `[AGENT_TEAM]:appsec`, `[SKILL_CODE_REVIEW]` (security category).

Summary for any agent:
1. Every repository with SECURITY.md, secret scanning, Dependabot, CodeQL, and branch protection
2. Secrets never in code/frontend/log. Represent as [REDACTED]
3. Authorization decided on the server. UI checks do not count
4. RLS on every client-accessible table. Parameterized SQL
5. Inputs validated server-side. Uploads with magic bytes and server-generated names
6. Separate pre-auth and post-auth rate limits
7. OAuth 2.1 with PKCE. Redirect URIs with exact allowlist
8. Deploy with full suite → canary → smoke → explicit promotion
9. Findings classified as OK | FINDING | NOT APPLICABLE | UNVERIFIED
10. Only "APPROVED" if zero blocking findings + verifiable evidence

## Pointers

- Operational Obsidian vault: `[CONTEXT_DIR]/[YOUR_NAME]/` ([SECONDARY_MACHINE]: `[CONTEXT_DIR]/[YOUR_NAME]`)
- Legal Obsidian vault (second brain): `[DOMAIN_VAULT]` (shortcut `[DOMAIN_VAULT]`)
- MOCs: `[YOUR_NAME]/wiki/00-indices/`
- Claude persistent memory: `.auto-memory/MEMORY.md`
- Open questions: `[YOUR_NAME]/wiki/00-indices/open_questions.md`
- Structural changelog: `_CHANGELOG.md`

---
*This file is the entry door for any AI. Update when fundamental rules change. Record in `_CHANGELOG.md`.*
