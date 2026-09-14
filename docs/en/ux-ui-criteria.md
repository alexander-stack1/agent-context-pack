# ux-ui-criteria.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Canonical technical guide for any AI that generates, reviews, or prototypes interface.
> Operational distillation (not a copy) of: Norman (*The Design of Everyday Things*), Krug (*Don't Make Me Think*), Yablonski (*Laws of UX* / lawsofux.com), Wathan & Schoger (*Refactoring UI*), Johnson (*Designing with the Mind in Mind*).
> Last updated: 07/09/2026
> Status: CAMADA 1 (load on every UI/UX, screen, prototype, design system, or front task).

---

## 0. How the AI must use this file

1. Read this file **before** proposing layout, UI copy, flow, component, or visual review.
2. Treat as **fail-closed**: if a MUST criterion cannot be met, declare `DOES NOT MEET` + reason; do not invent compliance.
3. On delivery, attach the filled **Closing checklist** (section 7). No checklist = incomplete delivery.
4. Do not reproduce full text from the works. Apply criteria. Cite the work only as origin of the criterion (e.g. "Norman: affordance").
5. On conflict between criteria, prefer this order: (1) clarity of the primary action, (2) reduced cognitive load, (3) visual hierarchy, (4) aesthetics.

**Prompt trigger (paste when asking for UI):**
`Follow [CONTEXT_DIR]/ux-ui-criteria.md rigorously. Deliver with the closing checklist filled. Fail-closed.`

---

## 1. Master principles (MUST)

### 1.1 Obvious action (Krug + Norman)
- The screen must answer in ≤3 mental seconds: **what is this**, **what can I do**, **where am I**.
- One **primary action** per screen (or per state). Secondaries visually subordinated.
- Controls must look like what they do (affordance). Current state must be perceptible (feedback).
- Natural control→effect mapping (e.g. gesture/button aligned with expected result).

### 1.2 Don't make the user think (Krug)
- Literal labels, not clever ones. Avoid internal jargon.
- Conventional navigation when a platform pattern exists (iOS HIG / web).
- Self-explanatory > instruction. If you need an on-screen manual, the flow failed.
- Happy path without distractions. Advanced options behind progressive disclosure.

### 1.3 Mental model and psychology (Johnson + Yablonski)
- Design for limited human perception and memory; not for the system model.
- Reduce simultaneous choices (Hick). Targets large enough for the context (Fitts).
- Consistency with what the user already knows (Jakob) **within the product and platform**.
- Group what is processed together (proximity / law of similarity).
- Avoid overload: chunks, hierarchy, fewer fields on the first step.

### 1.4 Hierarchy and visual craft (Refactoring UI)
- Hierarchy by **size, weight, color, and spacing**; not by decoration.
- Spacing on a consistent scale (e.g. 4/8). Align to an implicit grid.
- Readable text contrast (body vs background). Do not use light gray on light gray.
- Color with function: 1 brand color for emphasis; states (error/success/warning) distinct and not by color alone.
- Fewer borders; prefer space, subtle shadow, or differentiated background to separate.
- Density suited to context: mobile = less per screen; desktop can stack with breathing room.

### 1.5 Error, recovery, and trust (Norman + Johnson)
- Prevent error before correcting (constraints, safe defaults, confirmation only on destructive).
- Error message: what happened, why (in human language), how to fix now.
- Destructive actions: reversible when possible; otherwise explicit confirmation with named consequence.
- Loading and empty states are UI: never a dead screen without a next step.

---

## 2. MUST-NOT (forbidden on delivery)

- Generic placeholder as final copy ("Lorem", "Click here", "Learn more" without object).
- More than one visually tied CTA in the same region.
- Modal stacked on modal; alert that does not say what to do.
- Icon without label when meaning is not universal.
- Form asking for data the system already has or that can be optional later.
- Animation that delays the task or hides state.
- Dark pattern: false urgency, hidden opt-out, harmful pre-checked checkbox.
- Insufficient contrast; text over image without scrim.
- Invent usability metrics or "user tests" without evidence.

---

## 3. Criteria by delivery type

### 3.1 Wireframe / flow
- List screens and states (empty, loading, error, success, permission denied).
- Mark primary action and MVP minimum data.
- Make user decisions and drop-off points explicit.

### 3.2 High-fidelity UI / App Store solo
- Typography: at most 2 families; limited scale (e.g. 3–5 sizes).
- Reused components with same padding and radius.
- iOS safe areas; targets ≥ 44pt when tappable.
- Minimum accessibility: Dynamic Type when it fits; labels on controls; not information by color alone.

### 3.3 Interface copy
- Verb on the button = result ("Save PDF", not "OK").
- Screen title = task or object, not marketing.
- Error and empty microcopy written last, never omitted.

### 3.4 Review of an existing screen
- Report findings as: `FINDING` | `OK` | `UNVERIFIED` | `NOT APPLICABLE`.
- Each `FINDING` with: violated criterion (section of this guide), on-screen evidence, minimal fix.

---

## 4. Quick map: work → what to extract (without quoting text)

| Source | Use for |
|-------|----------|
| Norman | Affordance, signifiers, feedback, mapping, constraints, gulfs of execution/evaluation |
| Krug | Immediate clarity, happy path, obvious navigation, light usability tests |
| Yablonski / lawsofux.com | Hick, Fitts, Jakob, Miller, Prägnanz, aesthetic-usability, postel's, peak-end (apply sparingly) |
| Refactoring UI | Typographic hierarchy, spacing, color, depth, alignment, visual empty states |
| Johnson | Perception, attention, memory, recognition vs recall, cognitive load |

Free support site (does not replace the book): https://lawsofux.com/

---

## 5. Mandatory work order (generate UI)

1. **Job**: one sentence "user can X when Y".
2. **States**: full list before drawing.
3. **Structure**: hierarchy and primary action (no color).
4. **Craft**: typography, space, color, components.
5. **Copy**: final labels.
6. **Stress**: empty, error, offline, first open, return.
7. **Checklist** (section 7).

Do not jump to colors/style before steps 1–3.

---

## 6. Automatic rejection criteria for the delivery

The AI must **redo** (not deliver) if:
- Ambiguous primary action;
- Checklist missing or with blank MUST items;
- Placeholder copy;
- No error/empty state described;
- Contrast or touch target clearly insufficient in what was specified.

---

## 7. Closing checklist (mandatory in the response)

Copy and mark `YES` / `NO` / `N/A`. Every `NO` requires fix or `DOES NOT MEET` justification.

**Clarity**
- [ ] In 3s it is clear what the screen is and the main action
- [ ] One visible primary CTA; secondaries subordinated
- [ ] Literal labels; no internal jargon

**Interaction**
- [ ] Controls with adequate affordance/signifier
- [ ] Immediate feedback for actions (tap, submit, save)
- [ ] Destructive with confirmation or undo
- [ ] States: empty / loading / error / success described

**Cognition**
- [ ] Choices on the current step reduced to what is necessary
- [ ] Consistency with platform and product patterns
- [ ] Recognition > memorization (visible options, history, defaults)

**Visual**
- [ ] Clear typographic hierarchy (≤5 useful sizes)
- [ ] Spacing on a consistent scale
- [ ] Adequate text contrast
- [ ] Color with function; not aesthetics alone
- [ ] Adequate touch targets (mobile)

**Ethics / abuse**
- [ ] No dark pattern
- [ ] No fabricated urgency or guilt

**Meta**
- [ ] Screen job declared in one sentence
- [ ] Findings marked OK / FINDING / UNVERIFIED / NOT APPLICABLE when reviewing

---

## 8. Record in this context

- File: `[CONTEXT_DIR]/ux-ui-criteria.md`
- Include in `_MANIFEST.md` (Camada 1) at the next structural review.
- Optional: point from `working-style.md` in the design / product section.
- Solo apps and any UI bot must be instructed to load this file when the task is interface.

---
*Operational criteria for AI use. Does not replace reading the works. Do not redistribute PDFs of the works.*
