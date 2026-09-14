# ux-ui-INDEX.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Canonical UX/UI index for agents. Routes WEB vs MOBILE and shared rules.
> Camada 1 / design. Updated: 07/09/2026

---

## Files (read in this order)

| Order | File | Role |
|---:|---------|------|
| 1 | `ux-ui-criteria.md` | MUST/MUST-NOT principles (Norman, Krug, Yablonski, Refactoring UI, Johnson) + checklist §7 |
| 2 | `ux-ui-INDEX.md` | This file: routing + 60-30-10 color |
| 3a | `ux-ui-web-landing.md` | Sub-rules and STEPS 0–14 for **WEB** landing |
| 3b | `ux-ui-mobile.md` | Sub-rules and STEPS for **MOBILE** (landing / app / chat) |

## Condensed request menu

Read **`ux-ui-REQUESTS.md`** to know what to ask for. PT skills: `planejar-interface`, `desenhar-landing`, `revisar-experiencia`, `refatorar-interface`, `polir-para-ship`, `provar-com-screenshot`, `redesenhar-[PRODUCT_A]`. They encapsulate these files + impeccable.

Grok Bot skill: [ux-ui-criteria](sand-workflow:ux-ui-criteria) (when installed in the fleet).
Complementary plugin (craft/polish): **impeccable** — only **after** the fail-closed criteria above.

---

## STEP R0 — Routing (agent’s first act)

Answer in one line before designing:

```
PLATFORM: web | mobile | both
SURFACE: landing | app-shell | chat | other
MODE: Persuade | Operate | Read | Experience
FILES: [list that will be read]
```

Rules:
- `landing` + `web` → criteria + INDEX + **web-landing**
- `landing` + `mobile` or `both` → criteria + INDEX + web-landing + **mobile** (section A)
- `app-shell` mobile → criteria + INDEX + **mobile** (section B)
- `chat` → criteria + INDEX + **mobile** (section C)
- Other Operate UI → criteria + INDEX; mobile vs web per mobile §D table

Without R0 → invalid delivery.

---

## Shared color — 60-30-10 rule (MUST)

| Slice | Role | Use |
|------:|------|-----|
| **60%** | Primary / background | Canvas (e.g. white or product neutral background) |
| **30%** | Secondary / text and support | Text, neutral icons, secondary surfaces |
| **10%** | Accent / CTA | Primary buttons, emphasis links, states that need attention |

**Sub-rules**
- C-1: Accent does **not** paint entire backgrounds or every decorative icon.
- C-2: Error/success/warning are separate semantics; do not spend the whole 10% accent on them if it conflicts with CTA.
- C-3: Text contrast (30%) on background (60%) must be readable; accent (10%) with contrast on the button background.
- C-4: When in doubt, reduce color, do not increase accent.

Declare on delivery:
```
60: [token/color]
30: [token/color]
10: [token/color] → used in: [listed CTAs]
```

---

## Agent execution order (summary)

1. **R0** (this file)
2. Read `ux-ui-criteria.md` (MUST/MUST-NOT)
3. Apply **60-30-10**
4. Follow numbered STEPS in `ux-ui-web-landing.md` and/or `ux-ui-mobile.md` **in order**; do not jump to visual craft before Hero/structure
5. Fill checklists of used files + criteria §7 checklist
6. Only then, if polish/bolder/typeset is requested: **impeccable** skill

---

## Short trigger (paste into the prompt)

```
Follow [CONTEXT_DIR]/ux-ui-INDEX.md (R0 + 60-30-10) and the web/mobile files that R0 indicates.
Also ux-ui-criteria.md. Deliver with checklists. Fail-closed. Do not invent social proof.
```

---

## Manifest integration

Include in Camada 1 (or Camada 2 tech/design) at the next structural review:
- `ux-ui-criteria.md`
- `ux-ui-INDEX.md`
- `ux-ui-web-landing.md`
- `ux-ui-mobile.md`

Copy to `[HOME]/Desktop/[CONTEXT_DIR]/` when the Mac is online (canonical iCloud source).

---
*Do not redistribute PDFs of the works. Operational criteria for AI.*
