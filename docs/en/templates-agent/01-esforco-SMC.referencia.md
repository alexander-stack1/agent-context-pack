# Effort classification (S / M / C)

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.


> Suggested canonical template to paste into `working-style.md` (single source).
> Short mirrors: `agent_rules.md` and `senior-implementer-instructions.md`.
> Status: DRAFT — not applied to Camada 1 until explicit approval.

## Purpose

Match **engineering ceremony** to the change’s **risk and reversibility**.
Fail-closed, evidence, and blast radius **never** enter the S shortcut.

## Before planning

1. Classify the task as **S**, **M**, or **C**.
2. Declare on the **first line** of the response:
   `Effort: S|M|C — reason: … — paths: …`
3. If the user prefixes `[S]`, `[M]`, or `[C]`, that prefix wins, **except** blacklist (below): warn and ask for explicit confirmation to proceed as S.

## Definitions

### S — Simple (all must be true)

- Local, obvious change (typo, internal rename, copy, config with no new behavior).
- Few files (guidance: ≤ 3), same module or docs.
- *Two-way door*: easy to revert.
- Outside the path/theme blacklist.
- No new or changed public API contract.
- No authZ, RLS, OAuth, upload, rate limit, migration, deploy, secret, billing/payment, production.
- Unambiguous request (or `[S]`).

### M — Medium

- Bug or feature with assertable behavior.
- Scope limited to package/module.
- Does not touch production or blacklist without explicit mitigation.
- Partial failure of the S checklist, but no irreversibility.

### C — Complex (any one is enough)

- Touches blacklist (see below).
- Uncertain scope, multi-service, or public contract.
- Migration, deploy, production, money, staged-write on a real system.
- Security audit / request for “APPROVED”.
- Doubt in classification → **C**.

## Blacklist (forces C)

If the diff or investigation touches (path, symbol, or theme):

`auth`, `authorization`, `permission`, `rls`, `oauth`, `pkce`, auth `middleware`,
`migration`, `deploy`, `production`, `.env`, `secret`, `token`, `service_role`,
`billing`, `payment`, `stripe`, `upload`, `rate.?limit`, `firewall`

→ classify **C**. If the user asked for `[S]`, do **not** execute as S: explain and ask for confirmation to treat as C (or M with written mitigation).

## Ceremony by class

| Ritual | S | M | C |
|------|---|---|---|
| Reread full Camada 1 | No, if session already loaded and the task does not change rules | Yes if touching product code | Yes |
| Repo memory (`CLAUDE.md` / `REPO_MAP`) | Only if already in session; open the requested file | `CLAUDE.md` + map section | Contract + map + retrieval with cite-and-verify |
| Plan + approval | 1 line “I will X” and proceed if request is unambiguous | Short plan; wait if risk ≠ zero | Full plan + explicit approval |
| TDD 8 steps | N/A without behavior; else focal test | TDD + package/module tests | Full TDD |
| Full suite | No (path/package + lint/typecheck) | Package/module | Mandatory + fresh evidence |
| Mutation (“test bites”) | No | If there is a new test | Yes, if there is a new test |
| Multi-agent | Forbidden | Amplitude only | Adversarial review ok |
| Independent review / canary / smoke | No, unless requested | No, unless adjacent to prod | Per deploy/security |
| Staged-write + 2nd approval (money/prod) | N/A | N/A if draft only | Keep |
| Fail-closed / do not invent / no prod without order | **Always** | **Always** | **Always** |

## Audit line (mandatory on delivery)

```
Effort: M — reason: bug in X serializer; assertable behavior
Paths: app/foo/serializers.py, tests/test_foo.py
Verification: pytest tests/test_foo.py (GREEN) + ruff path
Repo: name @ short-sha — map: docs/agent/REPO_MAP.md (date)
```

## Examples

**S**
- Typo in README.
- Local variable rename without public API.
- Copy postgraduate material to a Drive folder.

**M**
- Fix serializer bug with a test.
- Read-only endpoint using existing auth.

**C**
- Any change in RLS / OAuth / migration / deploy.
- New authorization claim.
- Promotion to production.

## When in doubt

Treat as **C**. YAGNI governs the *scope* of the change, not the *proof*.
