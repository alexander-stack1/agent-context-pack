# PATHS.md — canonical paths (template)

> Layer 2, loaded on trigger. Single source for the local path of every repo, vault and asset folder.

**Rule:** no other file repeats a local path; the rest reference this one. Exception: a repo's `CLAUDE.md` may state its own path.
**When to load:** tasks touching repo paths, clones, worktrees, deploys or scripts with embedded paths. Before stating a path, never after.
**Never state a path from memory.** Missing here = UNVERIFIED: say so and ask.

## Code repositories
| Product | Local path | Remote | Branch | Role |
|---|---|---|:-:|---|
| `[PRODUCT_A]` | `~/dev/[product-a]` | `[YOUR_GITHUB]/[product-a]` (private) | `main` | ... |
| `[PRODUCT_B]` | `~/dev/[product-b]` | `VERIFY` | `VERIFY` | ... |

## Context, vaults and assets
| What | Path | Note |
|---|---|---|
| Canonical context | `[CONTEXT_DIR]` | Map in [`MANIFEST.md`](MANIFEST.md) |
| Operational vault | `[OPS_VAULT]` | Human reads, LLM writes |
| Domain vault | `[DOMAIN_VAULT]` | Mandatory routing for domain prompts |
| Credentials | `[CONTEXT_DIR]/credentials/` | Never open, quote or mirror |
| Dispatches | `~/dev/dispatches` | One file per dispatch |

## Named exceptions to the `~/dev` rule
| Path | Reason | Decided on |
|---|---|---|
| `~/[product-x]` | Outside synced folders; deploy source | `[DATE]` |

## Retired paths, do not use
| Path | State |
|---|---|
| `[OLD_PATH]` | Retired on `[DATE]`. Replaced by `[NEW_PATH]` |

*When moving or renaming a folder, update only this file and log it in the changelog.*
