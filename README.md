<p align="center">
  <img src="assets/git_skill_01post.png" alt="Claude Skills for </> On-boarding — by lusknchars" width="100%" />
</p>

# claude-onboarding

> Audit any SaaS onboarding flow in 5 minutes. 110 signals, 6 personas, 8 methodology lenses. Scored teardown with prioritized fixes and pattern references.

```
$ claude-onboarding audit https://your-saas.com

Onboarding Teardown — your-saas.com
─────────────────────────────────────────────

  Score  72 / 100        B-tier · Top 25% in B2B SaaS

  This flow is optimized for: MIG (Migrant)
  This flow actively harms:   ANX, BRW

  Form Cognitive Load    ▓▓▓▓▓▓▓▓░░    82
  Trust & Credibility    ▓▓▓▓▓▓▓▓▓░    91
  Microcopy & Voice      ▓▓▓▓▓▓░░░░    63
  Friction & Dark Pat.   ▓▓▓▓▓▓▓░░░    74
  Visual Hierarchy       ▓▓▓▓▓▓▓▓░░    80
  Motivation Triggers    ▓▓▓▓▓░░░░░    52
  Decision Support       ▓▓▓▓▓▓▓░░░    71
  Mobile & Touch         ▓▓▓▓▓▓▓▓░░    78
  Accessibility          ▓▓▓▓▓▓░░░░    65
  Performance & Polish   ▓▓▓▓▓▓▓▓▓░    88
  Psychological Hooks    ▓▓▓▓░░░░░░    44

  Top 3 leverage points (impact × effort)
    1. S105 Empty-state seeding — gallery > blank slate (Higgins)
    2. S041 Single primary CTA — 4 competing buttons (Hick's Law)
    3. S054 Competence signal — add "no design experience needed" (SDT)

  → onboarding-audit-your-saas-com-2026-04-30.md (full 110-signal table)
```

## What it does

`claude-onboarding` is a [Claude Code](https://claude.com/claude-code) skill that:

1. Takes a SaaS signup URL (and optional test credentials)
2. Audits the public-facing flow — landing, signup form, pricing, post-signup if creds given
3. Scores **110 measurable signals** across **11 categories**
4. Cross-references against **6 user personas** to surface "for whom is this good?"
5. Cites **8 methodology lenses** grounded in canonical onboarding literature
6. Compares findings against **5 benchmark products** (Linear, Stripe, Notion, Figma, Vercel)
7. Outputs a markdown report with prioritized fixes — quick wins, mid-term, strategic

It mirrors what consultants like ProductLed sell as $2,000–$5,000 5-day audit sprints — in five minutes, reproducible across as many flows as you want to study.

## How to use

```bash
# In Claude Code
> audit https://linear.app onboarding

# With a comparison set
> audit https://linear.app vs https://height.app vs https://shortcut.com

# Quick mode (top 22 critical signals, 1-page summary)
> audit https://x.ai — diagnóstico rápido

# With test credentials for post-signup signals
> audit https://figma.com (test creds: foo@bar.com / pass123)
```

The skill activates on any of: *audit, score, teardown, review, benchmark, critique* + a SaaS URL.

## What it audits

**11 categories. 110 signals.**

| # | Category | Signals | What it measures |
|---|---|---|---|
| 1 | Form Cognitive Load | 10 | Field count, validation, autofocus, smart defaults — Hick + Sweller + Miller |
| 2 | Trust & Credibility | 10 | Social proof, compliance badges, founder visibility, pricing transparency — Cialdini |
| 3 | Microcopy & Voice | 10 | CTA specificity, jargon density, error tone, you/we ratio — Sierra + Krug |
| 4 | Friction & Dark Patterns | 10 | Forced fields, confirmshaming, hidden exits, gates — Bush + Brignull |
| 5 | Visual Hierarchy & Attention | 10 | Single CTA discipline, F-pattern, white space, distractions — Norman + Krug |
| 6 | Motivation Triggers | 10 | Outcome promise, time-to-value, autonomy/competence/relatedness — Fogg + SDT |
| 7 | Decision Support | 10 | Pricing clarity, default selection, free-tier prominence, FAQ proximity — Thaler + Iyengar |
| 8 | Mobile & Touch | 10 | Tap targets, viewport, input zoom, sticky CTA, modal dismissibility |
| 9 | Accessibility | 10 | WCAG 2.2 — alt text, ARIA, contrast, keyboard nav, reduced-motion |
| 10 | Performance & Polish | 10 | Page weight, JS bundles, font loading, lazy images, CLS — Lindgaard + Akamai |
| 11 | Psychological Hooks | 10 | First-action triviality, peak moment, empty-state seeding, end-of-onboarding closure — Kahneman + Higgins + Eyal |

## The 6 personas

Every signal carries persona codes. The audit asks not just *"is this good?"* but *"for whom?"*

| Code | Persona | What they need |
|---|---|---|
| `PRG` | Pragmatist | Time-to-value claim that's true, skip everywhere, no surveys |
| `SKP` | Skeptic | Customer logos, compliance badges, pricing transparency, founder visibility |
| `EXP` | Explorer | Sandbox without signup, "skip" affordances, optional fields that *feel* optional |
| `ANX` | Anxious Newcomer | Reassurance, warm copy, undo/drafts, small first action with celebration |
| `MIG` | Migrant | Migration paths, comparison pages, API docs, power-user signals |
| `BRW` | Casual Browser | No-signup demo, "no credit card required", low-commitment first action |

Persona archetypes derived from Bob Moesta's Forces of Progress, Indi Young's listening user research, Cooper's *About Face*, and Wes Bush's *Product-Led Onboarding* user types.

## Methodology

Eight lenses, each from a primary source. Every signal traces back to one:

1. **Cognitive Load** — Sweller, Miller, Hick
2. **Trust Architecture** — Cialdini's six principles
3. **Behavior Design** — Fogg's B = MAP
4. **Self-Determination Theory** — Deci & Ryan (autonomy, competence, relatedness)
5. **Memory & Peak-End** — Kahneman, Zeigarnik
6. **Choice Architecture** — Thaler & Sunstein, Iyengar
7. **Inclusive Design** — WCAG 2.2, Microsoft Inclusive Design
8. **Speed as Substance** — Lindgaard, Akamai/Walmart latency studies

Full source attribution → [`references/methodology.md`](.claude/skills/claude-onboarding/references/methodology.md).

Companion bibliography → [awesome-saas-onboarding](https://github.com/lusknchars/awesome-saas-onboarding).

## Benchmarks

The skill compares findings against five elite products. When something fails, the report points to what one of these does instead.

- **Linear** — keyboard-first, severe specific verbs, customer logos as identity
- **Stripe** — engineering-first onboarding, compliance as marketing, docs-as-product
- **Notion** — templates as activation, founder voice, empty-state-as-gallery
- **Figma** — multiplayer cursor as peak moment, hero-as-demo
- **Vercel** — single-CTA discipline, free-tier prominence, sub-second LCP

Pattern library → [`references/benchmarks.md`](.claude/skills/claude-onboarding/references/benchmarks.md).

## Status

**v0.1** — public-surface audit shipped. Audits landing + signup form + pricing + optional sandbox.

**v1.0 (target June 2026)** — adds authenticated walk-throughs (post-signup empty states, first-action timing, end-of-onboarding closure) via headless browser session.

**v1.1+** — multi-product comparison reports, JSON output for dashboards, language-detection for non-English flows.

## Install

```bash
# Option 1 — clone into your Claude Code skills directory
git clone https://github.com/lusknchars/claude-onboarding.git
cp -r claude-onboarding/.claude/skills/claude-onboarding ~/.claude/skills/

# Option 2 — use as project-scoped skill
git clone https://github.com/lusknchars/claude-onboarding.git
cd claude-onboarding
claude  # the .claude/skills/ folder is auto-discovered
```

Then in Claude Code: `> audit https://your-saas.com`

## Author

Built by [Lucas Oliveira](https://github.com/lusknchars).

## License

[MIT](LICENSE)
