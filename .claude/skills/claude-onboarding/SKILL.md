---
name: claude-onboarding
description: Audit a SaaS onboarding flow from a public URL and produce a scored teardown (110 signals, 11 categories, 6 personas, 8 methodology lenses) with prioritized fixes. Use when the user asks to audit, score, teardown, review, benchmark, or critique a signup / activation / onboarding flow, or when given a SaaS URL with a verb like "evaluate", "analyze", or "diagnose" UX. Grounded in Bush, John, Higgins, Sierra, Cialdini, Kahneman, Fogg, Deci & Ryan, Thaler & Sunstein, WCAG 2.2.
---

# claude-onboarding

Onboarding teardown skill. Takes a public SaaS URL, returns a scored markdown report with prioritized fixes and pattern references.

> **Status:** v0.1 — public-surface audit (landing + signup form). Post-signup categories partially inferred from marketing assets. v1.0 (June 2026) adds authenticated walk-throughs.

## When to activate

Activate when the user provides a SaaS URL and asks any of:

- "Audit / score / teardown / review the onboarding of X"
- "What's wrong with X's signup?"
- "How does X's onboarding compare to Linear/Stripe/Notion?"
- "Run an onboarding audit on X"
- "Where's the friction in X's signup?"

If the URL is provided without a verb, ask once: *"Quer um teardown completo (110 sinais) ou um diagnóstico rápido (top 10 sinais críticos)?"* Then proceed.

## Inputs

| Input | Required | Default if absent |
|---|---|---|
| URL | yes | — |
| Test credentials | no | skip post-signup signals; mark as inferred |
| SaaS category | no | infer from landing copy + product type |
| Persona mix | no | use category heuristic from `references/personas.md` |
| Comparison set (1–3 competitor URLs) | no | use built-in benchmarks |
| Output mode (`full` / `quick`) | no | `full` |

**Quick mode:** score only the 22 highest-leverage signals (2 per category) and produce a 1-page summary. Use when user asks for "diagnóstico rápido" or has stated time pressure.

## Procedure

Follow these phases in order. Do not skip phases.

### Phase 1 — Gather

1. `WebFetch` the URL (`extract main HTML, signup CTAs, hero copy, pricing link`).
2. Follow the primary signup CTA. Fetch that page too.
3. If pricing page is linked from nav, fetch it.
4. If a demo/sandbox link exists (no signup), fetch it.
5. Inspect for: `<form>`, `<input>`, `<meta>`, `<script>`, `<link rel="stylesheet">`, customer logo `<img>` clusters, badge images, headline structure (`<h1>`–`<h3>`).
6. If user provided test credentials, attempt signup via `maestri-portal` skill. Capture screenshots at each step. *(If `maestri-portal` is unavailable, mark post-signup signals as inferred and continue.)*

### Phase 2 — Classify

1. **Category:** B2B, B2C, prosumer, dev tools, enterprise, vertical. State your inference and the evidence for it.
2. **Persona mix:** apply the heuristic table in `references/personas.md` unless the user supplied actuals. State the assumption.
3. **Comparison anchors:** pick 2–3 from the built-in five (Linear, Stripe, Notion, Figma, Vercel) most relevant to the audited product's category, OR the user-provided competitor URLs.

### Phase 3 — Score

Apply `references/rubric.md` — 110 signals across 11 categories. For each signal:

- Determine **PASS** / **WATCH** / **FAIL** strictly per the rubric criteria.
- Capture **evidence** — quote the HTML attribute, copy snippet, or describe layout in ≤1 sentence.
- If a signal can't be assessed (e.g., post-signup behavior without creds), mark **INFERRED** and explain the inference basis.

**Scoring math:**
- Category score = (PASS × 1.0 + WATCH × 0.5) / signals_in_category × 100
- Total score = average of 11 category scores
- Per-persona score = weighted sum of signals tagged for that persona (see persona codes in rubric)

### Phase 4 — Cross-reference personas

For each of the 6 personas (`PRG`, `SKP`, `EXP`, `ANX`, `MIG`, `BRW`):

1. Sum WATCH + FAIL for signals tagged to that persona.
2. Identify the **most-served persona** (lowest harm score).
3. Identify the **most-harmed persona** (highest harm score).
4. Write a 1–2 sentence narrative for each persona describing their experience of this flow.

This is the key differentiated insight. Most audits skip this. Don't.

### Phase 5 — Generate report

Use `templates/teardown.md` as the structural template. Fill every `{{PLACEHOLDER}}`. Sections, in order:

1. **TL;DR** — score, optimized-for / harms personas, one-line diagnosis, top 3 leverage points.
2. **Score by category** — 11-row table.
3. **Persona reading** — per-persona narrative.
4. **What this flow does well** — 3–5 patterns, each with principle citation.
5. **Top 5 friction points** — each with signal ID, evidence, principle (from `methodology.md`), personas harmed, pattern reference (from `benchmarks.md`), and concrete fix.
6. **Prioritized roadmap** — quick wins (≤1d eng, ≥5pt score gain) / mid-term (1–2 weeks) / strategic (≥1 month).
7. **Full signal table** — all 110 signals, status + 1-line evidence. Skip in quick mode.
8. **Limitations** — explicitly state inferred signals and what creds would unlock.
9. **Methodology footer** — pointer to `references/methodology.md`.

Save to `./onboarding-audit-{domain}-{YYYY-MM-DD}.md` in the user's current working directory.

### Phase 6 — Deliver

Output to chat:
1. The score and one-line diagnosis (the TL;DR essentials)
2. The 3 leverage points
3. Path to the full report
4. One follow-up offer: "Quer que eu compare com X (competitor) ou audite outra URL?"

Do not paste the full report into chat — point to the file. Reports are typically 800–2000 lines.

## Citation discipline

When referencing principles, use the short form from `methodology.md` final section:

- **Bush** — *Product-Led Onboarding*
- **Higgins** — *Better Onboarding*
- **Cialdini** — *Influence*
- **Kahneman** — *Thinking Fast and Slow* (peak-end)
- **Fogg** — *Tiny Habits* (B = MAP)
- **Deci & Ryan** — SDT
- **Thaler & Sunstein** — *Nudge*
- **Brignull** — dark pattern taxonomy
- **WCAG 2.2** — accessibility baseline

Every recommendation must trace to a named principle. No "I think" — only "Cialdini's social proof principle says X, this flow does Y, here's the gap."

## Pattern reference discipline

When something fails, point to a benchmark from `references/benchmarks.md`. Format:

> **S041 (Single Primary CTA): FAIL.** Page has 4 primary-styled buttons.
> *Pattern reference:* Vercel commits to one CTA ("Start Deploying"); secondary actions are visually demoted. Hick's Law applied with intent.
> *Fix:* Pick highest-intent CTA; demote others to text links or outline buttons.

This converts "wrong" into "here's a known-good pattern to study."

## Tone of the report

- Direct, evidence-led, never moralistic. The audited team is competent; you're surfacing what cognitive science predicts about *their users' brains*, not lecturing.
- No padding. If a category is strong, say so in 2 sentences and move on.
- No flattery, no "great work overall, but…" softeners. The leverage points carry the message.
- Portuguese or English to match the user's prompt language.

## What this skill does NOT do

- Crawl beyond signup + post-signup first screen (would require auth + headless browser session ≥ v1.0).
- Run real Lighthouse / Core Web Vitals (S091–S100 are static estimates).
- Validate mobile signals against real device behavior (CSS-only inference).
- Replace user research. Personas are archetypes; your specific users may differ.

State these limitations in every report. Honesty about scope is part of the skill's value.

## Files

- [`references/rubric.md`](references/rubric.md) — 110 signals, criteria, persona tags
- [`references/methodology.md`](references/methodology.md) — 8 lenses, principle-to-signal map
- [`references/personas.md`](references/personas.md) — 6 archetypes + category heuristics
- [`references/benchmarks.md`](references/benchmarks.md) — Linear / Stripe / Notion / Figma / Vercel pattern library
- [`templates/teardown.md`](templates/teardown.md) — output template
