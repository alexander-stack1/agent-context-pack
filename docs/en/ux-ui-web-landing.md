# ux-ui-web-landing.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> WEB (desktop) sub-rules for product / AI agent landing.
> Visual source: high-converting landing anatomy (navbar → footer).
> Use with `ux-ui-criteria.md` + `ux-ui-INDEX.md`. Fail-closed.
> Updated: 07/09/2026

---

## When to apply

Task = landing page, marketing site, pricing page, SaaS/agent home **on desktop/web viewport** (≥1024px as reference).

If mobile is also in scope: run this file for desktop **and** `ux-ui-mobile.md` for the mobile breakpoint. Do not mix rules in the same step.

---

## STEP 0 — Gate (mandatory)

Before any section:

1. Declare **job** in one sentence: "Visitor can X".
2. Declare the page **primary action** (only one).
3. Confirm Impeccable mode = **Persuade** (if marketing).
4. Apply **60-30-10** color (`ux-ui-INDEX.md` § Color).

Without complete STEP 0 → stop and ask for what is missing.

---

## STEP 1 — Navbar (WEB)

**Do**
- Logo on the left.
- Horizontal text links: Solutions, Benefits, How It Works, Integrations, FAQs, Pricing (only those that exist in the product; do not invent an empty section).
- Primary CTA always visible in the bar (button).

**Sub-rules**
- W-NAV-1: Literal labels; max 6–7 items.
- W-NAV-2: Navbar CTA = same primary action as the Hero (or entry to it).
- W-NAV-3: No hamburger on desktop ≥1024px.
- W-NAV-4: Hover states on links (web only).

**Do not**: complex menu, nested dropdown in MVP, secondary CTA tied with the primary.

**Verify**: CTA visible without scroll; clear labels in ≤1s.

---

## STEP 2 — Hero (WEB)

**Do**
- Headline in the pattern: `[Desired result] — [objection removed]`.
- Subhead: `action step + benefit promised by the headline`.
- Primary CTA: **Call-to-Value** = action verb + short benefit (e.g. "Start free — save 10h/week"). Do not use only "Learn more" / "OK".
- Large product visual (mockup or video) showing the outcome.

**Sub-rules**
- W-HERO-1: One headline; no empty slogan.
- W-HERO-2: CTA above the fold with the headline (desktop may place visual beside; CTA does not disappear below the fold).
- W-HERO-3: Objection in the headline must be real for the audience; if UNVERIFIED, mark it.
- W-HERO-4: Visual = product in use, not generic stock without context.

**Verify**: in 3s you can say what it is and what to click.

---

## STEP 3 — Social proof (logos)

**Do**: horizontal strip of logos / stats / badges.

**Sub-rules**
- W-PROOF-1: Only real logos/stats; otherwise `UNVERIFIED` or omit the section.
- W-PROOF-2: Do not invent clients.

---

## STEP 4 — Use cases (3 columns)

**Do**: 3 columns (icon + title + subhead). How the product fits distinct situations.

**Sub-rules**
- W-UC-1: 3-column grid on desktop.
- W-UC-2: Short, audience-focused; no feature dump.
- W-UC-3: Each column = a different job, not synonyms.

---

## STEP 5 — Pain points (3 columns)

**Do**: 3 pains with alert-tone icon + title + subhead; product as implicit resolution.

**Sub-rules**
- W-PAIN-1: 3-column grid.
- W-PAIN-2: User pains, not internal team complaints.
- W-PAIN-3: No exaggerated fear dark pattern.

---

## STEP 6 — Why us (3 columns)

**Do**: 3 clear differentiators (faster / easier / more trustworthy — only if true).

**Sub-rules**
- W-WHY-1: 3-column grid.
- W-WHY-2: Each item comparable to an obvious alternative; no empty superlative.

---

## STEP 7 — How it works (3–5 steps)

**Do**: numbered path with icons; 3 to 5 steps.

**Sub-rules**
- W-HOW-1: Linear order; one verb per step.
- W-HOW-2: No implementation jargon.

---

## STEP 8 — Benefits (2×2 grid)

**Do**: 3–4 benefits in a 2×2 grid (icon + text). Focus on “how it makes life easier”, not a specs list.

**Sub-rules**
- W-BEN-1: Desktop = 2 columns.
- W-BEN-2: Benefit ≠ feature; translate feature → outcome.

---

## STEP 9 — Pricing (3 cards)

**Do**: 3 plans with features + CTA per card. Highlight the recommended plan.

**Sub-rules**
- W-PRICE-1: Prices only if real; otherwise placeholder marked `EXAMPLE` / `UNVERIFIED`.
- W-PRICE-2: CTA per card aligned to primary action or upgrade.
- W-PRICE-3: One visually “best” card (border/badge), not three tied.

---

## STEP 10 — Testimonials

**Do**: carousel/strip with rating, real photo, quote, result.

**Sub-rules**
- W-TEST-1: No invented testimonial.
- W-TEST-2: Prefer concrete result over vague praise.

---

## STEP 11 — CTV block (Call-to-Value)

**Do**: high-contrast strip with action+benefit CTA.

**Sub-rules**
- W-CTV-1: Repeats the primary action; does not introduce a competing third CTA.
- W-CTV-2: Strong contrast (10% accent of the 60-30-10 rule).

---

## STEP 12 — FAQs

**Do**: accordions (price, setup, features, cancellation).

**Sub-rules**
- W-FAQ-1: Short answers that remove friction.
- W-FAQ-2: Do not hide price here if it is already in the Pricing section.

---

## STEP 13 — Footer

**Do**: links (Features, Pricing, Terms, Privacy, Contact), social, logo, trust badges if real.

**Sub-rules**
- W-FOOT-1: Minimum legal links if it is a real product.
- W-FOOT-2: No invented badge.

---

## STEP 14 — WEB checklist (attach on delivery)

Mark YES / NO / N/A:

- [ ] Section order 1→13 respected (nonexistent sections = N/A, do not invent)
- [ ] Navbar with always-visible CTA
- [ ] Hero: outcome—objection formula + CTV
- [ ] Use cases / pain / why in 3 columns
- [ ] Benefits in 2×2
- [ ] Pricing with highlighted plan + CTA per card
- [ ] 60-30-10 applied (accent only on CTAs/emphasis)
- [ ] Hover/focus on clickable controls
- [ ] No invented social proof
- [ ] `ux-ui-criteria.md` §7 checklist also filled

Any NO on a MUST item → redo before delivering.
