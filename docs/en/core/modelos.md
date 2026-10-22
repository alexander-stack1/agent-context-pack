# modelos.md — model and effort matrix (single source)

> Template. Fill with exact IDs from each vendor's official docs and the check date. Never fill an ID from memory.

Roles: **ORQ** (orchestration and planning), **PES** (heavy reasoning), **EXE** (executor), **SIM** (search, triage, extraction).
Format: model | exact ID | default effort | max effort. Max only on human order or class C on the blacklist.

| Tool | ORQ | PES | EXE (specified / hard) | SIM |
|---|---|---|---|---|
| `[AGENT_CLI_A]` | `[MODEL_ORQ]` medium | `[MODEL_PES]` high | `[MODEL_EXE]` medium / high | `[MODEL_SIM]` low |
| `[AGENT_CLI_B]` | ... | ... | ... | ... |
| `[IDE_AGENT]` | ... | ... | ... | ... |

## S/M/C to model and effort

| Class | Decides and plans | Executes | Reviews | Subagent |
|---|---|---|---|---|
| S (two-way door, off blacklist) | The session itself | Inline; mechanical delegation to SIM low | None | Search/triage only |
| M (assertable bug or feature, TDD) | ORQ medium | EXE medium (high if tests fail twice) | Tests and lint; ORQ review | 1 EXE per module |
| C (blacklist, production, money, doubt) | ORQ high, plan and human approval | EXE high | PES high with clean context (adversarial) | EXE high, SIM low |

Rules: when in doubt, C. An `[S]` prefix does not beat the blacklist. The reviewer is never the model that wrote the code. Final domain writing stays with ORQ or PES, never SIM.
Models that require vendor-side data retention never receive client data.

## Sources
List the official URL for each ID and each effort parameter here.
