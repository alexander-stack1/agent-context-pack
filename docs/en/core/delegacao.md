# delegacao.md — roles and contract

Roles: **orchestrator** (decides, splits, reviews, integrates, talks to the human), **heavy reasoning** (deep analysis and adversarial review), **executor** (implements one artifact), **simple** (search, triage, extraction).

## Dispatch
```
DISPATCH <id>
owner: <one subagent>   model/effort: <x>   tools: <minimal list>
goal: <1 sentence>
artifact: <1 output path>   (nothing outside it)
scope: repo/branch/commit, allowed files; out of scope = UNVERIFIED
proof: <command or criterion the orchestrator will run or read>
forbidden: secrets, credentials/, push, email, deploy, delete
human gate: <what goes back to the human before continuing>
budget: <max time and tokens>
delivery: short summary + evidence (command output, file:line)
```

## Structured handoff (return)
```
HANDOFF <id>
done: <what changed, with paths>
proof: <command output / file:line>
not done / blocked: <reason>
risks and UNVERIFIED: <list>
next step: <1 line>
```

## Orchestrator rules
1. Reads and checks every output against the proof. 2. Never forwards secrets or client data to anyone who does not need them. 3. Executors have no send, push, deploy or payment tools. 4. In C, adversarial reviewer with clean context and a different model from the executor. 5. One owner per file, depth 1. 6. Logs it. 7. Class doubt becomes C.

## When to delegate
Delegate: breadth, repetitive batches, independent review (always in C), context-polluting exploration, parallel work with distinct owners. Inline: class S, one file, decisions, final domain writing, anything that depends on conversation context.
