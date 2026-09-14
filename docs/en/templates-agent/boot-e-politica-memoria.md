# Per-project memory boot + retrieval policy

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.


> Operational complement to templates 04–06. May live in the repo's `docs/agent/README.md`
> or as an internal “boot-repo” skill.

## Session opening ritual (by effort)

### S
1. If `CLAUDE.md` was already read in this session → do not reread.
2. Open only the file(s) for the request.
3. Verify with the minimum command from `CLAUDE.md`.

### M
1. Read `CLAUDE.md`.
2. Read the relevant section of `docs/agent/REPO_MAP.md` (check `git_sha`).
3. Confirm paths with `rg` / `Read`.
4. TDD + package tests.

### C
1. `CLAUDE.md` + `REPO_MAP` + `DECISIONS` touched by the topic.
2. Camada 1 appsec (`working-style` / agent_rules) if auth/data/deploy.
3. Retrieval (Codebase Memory) only as hypothesis → cite-and-verify.
4. Pin repo, branch, commit/tree in the plan.
5. Full C ritual.

## Cite-and-verify

```
Hypothesis (retrieval): FooService in app/foo/services.py
Proof: Read app/foo/services.py L… — CONFIRMED | UNVERIFIED
```

Without proof → do not edit based on the hypothesis.

## Memory updates

| Event | Action |
|--------|------|
| Merged PR that changes folder/module structure | Regenerate `REPO_MAP` or mark `stale` |
| New stable architecture decision | ADR in `DECISIONS.md` |
| Landmine discovered during work | 1 bullet in map Hotspots (same PR or follow-up) |
| Casual conversation | Do not write to the map; at most a pointer in agent memory |

## Forbidden

- Paste codebase into `.auto-memory`
- Treat chat summary as the map
- One global RAG mixing all products
- Update the map without updating `git_sha`
