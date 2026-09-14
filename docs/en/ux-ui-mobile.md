# ux-ui-mobile.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> MOBILE sub-rules for responsive landing and app UI.
> Visual sources: mobile landing anatomy; mobile UX practices; mobile vs web contrast.
> Use with `ux-ui-criteria.md` + `ux-ui-INDEX.md`. Fail-closed.
> Updated: 07/09/2026

---

## When to apply

- Landing/marketing mobile breakpoint (≤768px), **or**
- Native app / PWA with tab navigation, **or**
- Chat/agent UI on phone.

If the task is a full landing: first `ux-ui-web-landing.md` (desktop), then **this file** for the mobile layout. Do not apply a 3-column grid on mobile.

---

## STEP 0 — MOBILE gate

1. Declare context: `landing-mobile` | `app-shell` | `chat-agent`.
2. Portrait-first. Landscape = bonus, not default.
3. Short attention: one task per screen; CTAs above the fold.
4. Color 60-30-10 (`ux-ui-INDEX.md`).
5. Touch targets ≥ 44×44 pt/px CSS.

---

## A. Mobile landing (same anatomy sections, different layout)

### STEP M1 — Mobile navbar

**Do**
- Logo on the left.
- Compact CTA (“Get Started” / primary action) visible.
- Hamburger on the right for remaining links (Solutions, Pricing, FAQs…).

**Sub-rules**
- M-NAV-1: No row of 6 text links at the top on mobile.
- M-NAV-2: Bar CTA = primary action (not “Menu”).
- M-NAV-3: Open menu = clear list + obvious close; no stacked modal.

### STEP M2 — Mobile hero (vertical stack)

Mandatory order (top to bottom):

1. Headline (`[result] — [objection]`)
2. Short subhead
3. **Primary CTA (CTV)** ← before the visual
4. Product visual

**Sub-rules**
- M-HERO-1: CTA above the visual (above the fold).
- M-HERO-2: One column; no text beside the mockup.
- M-HERO-3: Readable typography without zoom (body ≥ 16px).

### STEP M3 — Content sections

Use cases, pain, why, how, benefits, pricing, testimonials, CTV, FAQ, footer:

**Sub-rules**
- M-LAY-1: **Always 1 column**. Stacked cards.
- M-LAY-2: Pricing = stacked cards; “best” plan first or with clear badge.
- M-LAY-3: Testimonials = 1 visible card + swipe (gesture), not 5 photos side by side.
- M-LAY-4: Full-width FAQ accordion.
- M-LAY-5: Generous spacing between sections; the thumb needs breathing room.

### STEP M4 — Mobile landing checklist

- [ ] Hamburger + CTA in navbar
- [ ] Hero: headline → CTA → visual
- [ ] 1 column in all grid sections
- [ ] CTA above the fold
- [ ] Readable fonts; targets ≥ 44pt
- [ ] 60-30-10; accent only on CTA

---

## B. Mobile app (product shell)

### STEP M5 — App navigation

**Do**
- Prefer **bottom tab bar** (3–5 destinations) for main tasks.
- Hamburger only for secondary/settings, not for the core path.

**Sub-rules**
- M-APP-1: Tab destinations = frequent tasks; short labels + icon.
- M-APP-2: Active tab visually obvious.
- M-APP-3: Do not depend on hover.

### STEP M6 — Touch interaction

**Sub-rules**
- M-TOUCH-1: Tap / swipe / pinch; no hover-only affordance.
- M-TOUCH-2: Finger-friendly controls (≥ 44pt); spacing between targets.
- M-TOUCH-3: Discovered gestures with signifier (or avoid hidden gesture in MVP).

### STEP M7 — Content and attention

**Sub-rules**
- M-ATT-1: One primary action per screen.
- M-ATT-2: Minimize typing (defaults, picker, autocomplete, OCR/scan if it fits).
- M-ATT-3: Optimize for multiple sizes (safe area, notch, open keyboard).
- M-ATT-4: Short session: saved state; resume without redoing.

### STEP M8 — Mobile app checklist

- [ ] Bottom nav or justified platform pattern
- [ ] No hover dependency
- [ ] Targets ≥ 44pt; readable typography
- [ ] Minimal typing on the happy path
- [ ] States: empty / loading / error / offline
- [ ] Safe areas respected

---

## C. Chat / conversational agent (mobile)

### STEP M9 — Chat layout

**Do**
- Header: agent title + actions (search/profile) without stealing message area.
- History in bubbles (user vs agent) with clear contrast.
- Fixed bottom input: field + send; optional mic only if voice truly exists.

**Sub-rules**
- M-CHAT-1: Input always accessible (above the keyboard).
- M-CHAT-2: Long agent messages wrapped; inline CTAs only when they are the action.
- M-CHAT-3: Do not invent voice/mic if there is no implementation.

### STEP M10 — Chat checklist

- [ ] Distinguishable bubbles
- [ ] Stable bottom input
- [ ] Send with target ≥ 44pt
- [ ] Recoverable send error

---

## D. Quick MOBILE vs WEB table (do not confuse)

| Dimension | MOBILE | WEB |
|----------|--------|-----|
| Nav | Hamburger + CTA; or bottom tabs in app | Horizontal links + always-visible CTA |
| Layout | 1 column | 2–3 column grid |
| Interaction | Touch/gesture; no hover | Click + hover + keyboard |
| Orientation | Portrait-first | Wide landscape |
| Attention | Fast task | Longer exploration |
| Landing hero | CTA **before** visual | Visual may sit beside; CTA above the fold |

---

## Automatic rejection (mobile)

Redo if:
- 3-column grid on mobile;
- Hero CTA below the visual;
- Desktop links pinned at the top without hamburger;
- Target < 44pt without justification;
- Hover as the only signifier.
