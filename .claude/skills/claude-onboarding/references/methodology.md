# Methodology — The Lenses

This file is Claude's mental model. Read it before scoring the rubric. Every signal in `rubric.md` traces back to one of the principles below.

The thesis is simple: **most onboarding gets graded by the wrong frame.** Designers grade aesthetics. PMs grade conversion. Engineers grade performance. None of them grade the user's brain.

This skill grades the user's brain. Eight lenses, each from a primary source.

---

## Lens 1 — Cognitive Load (Sweller, Miller, Hick)

The user has ≤7 chunks of working memory at any moment (Miller, 1956). Every field, button, and copy block consumes a chunk. *Extraneous* load (poor layout, jargon, redundant fields) crowds out *germane* load (understanding what the product does).

**Operational rule:** if you can remove a field, a step, a sentence, or a decision without losing the activation event — remove it.

- **Hick's Law:** decision time = log₂(N+1). Two CTAs is ≥40% slower than one.
- **Miller's 7±2:** chunk fields into groups; each group is one chunk.
- **Sweller's split-attention effect:** label and field must be visually adjacent.

Signals: S001–S010, S041–S050.

---

## Lens 2 — Trust Architecture (Cialdini)

Cialdini's six principles of persuasion, applied to signup:

| Principle | Signup application |
|---|---|
| **Social proof** | "Join 10,000 designers" |
| **Authority** | Press logos, founder credentials, compliance badges |
| **Liking** | Authentic founder voice, real photos, brand personality |
| **Reciprocity** | Free tier, free analysis, free trial without card |
| **Commitment** | Tiny first step (just email) → bigger commitment later |
| **Scarcity** | Time-limited bonuses *only when authentic* — fake scarcity backfires |

Trust is a stack of small confirmations. Break one and the rest don't compound.

Signals: S011–S020.

---

## Lens 3 — Behavior Design (Fogg)

**B = MAP** — Behavior happens when Motivation, Ability, and Prompt converge at the same moment.

For onboarding:
- **Motivation** = what they think they'll get (set by hero copy + outcome promise)
- **Ability** = how easy the next step is (set by field count, friction)
- **Prompt** = the CTA itself (specificity, contrast, position)

If completion drops, ask which of M/A/P is missing. Don't add to the wrong axis.

**Tiny Habits corollary:** make the first action absurdly small. If the user must "create a workspace, invite team, pick template" before doing anything, you've stacked three behaviors before any reward.

Signals: S051–S060, S101.

---

## Lens 4 — Self-Determination Theory (Deci & Ryan)

Intrinsic motivation has three nutrients:

1. **Autonomy** — the user feels in control. Forced linear flows starve this.
2. **Competence** — the user feels capable. Jargon and unhelpful errors starve this.
3. **Relatedness** — the user feels part of something. Isolated experiences starve this.

A flow that is fast and beautiful but autonomy-violating (modal trap, no skip) will *underperform* a slower flow with respect for user agency. SDT predicts long-term retention; cheap optimization tricks don't.

Signals: S036, S039, S053–S055.

---

## Lens 5 — Memory & Peak-End (Kahneman)

The user remembers two things: the **peak** and the **end**. Not the average. Not most steps. This is why competent-throughout flows underperform flows with one designed delight.

- **Peak:** ONE moment that exceeds expectation. Linear's command palette appearing. Stripe's CLI auto-detecting your project. Figma's first multiplayer cursor.
- **End:** the last impression colors recall of everything before. A bad final step poisons memory of a great middle.

**Zeigarnik effect:** an incomplete task occupies more cognitive real estate than a completed one. Visible progress bars exploit this.

Signals: S102, S103, S109, S110.

---

## Lens 6 — Choice Architecture (Thaler & Sunstein, Iyengar)

Users in choice paralysis don't choose — they leave.

- **Default effect:** the default is chosen 60–80% of the time regardless of value (Thaler/Sunstein, *Nudge*).
- **Choice paralysis:** ≥7 options reduces commitment by ~50% (Iyengar's jam study).
- **Decoy effect:** 3 tiers, with a deliberately weak middle, increases premium uptake.

Pricing pages, plan selectors, and onboarding "what kind of user are you?" gates all live or die by this lens.

Signals: S061–S070.

---

## Lens 7 — Inclusive Design (WCAG, Microsoft Inclusive Design)

Disability is rarely permanent. **Permanent** (one-armed user), **temporary** (broken arm), **situational** (holding a baby) — all benefit from the same accommodations. Designing for the edge serves the middle better.

Accessibility is not charity; it's reach. ~15% of users have a permanent disability. ~100% have situational ones daily.

Signals: S081–S090.

---

## Lens 8 — Speed as Substance (Akamai/Walmart, Lindgaard)

First impressions form in 50ms (Lindgaard et al., 2006). Trust is decided before content is read.

- 100ms latency = 1% conversion drop (Amazon)
- 1s latency = 7% conversion drop (Akamai)
- Pages over 2MB underperform 500KB pages by 2–3x in mobile signup (HTTPArchive correlation)

Speed isn't a separate concern from UX. It IS UX.

Signals: S091–S100.

---

## Persona Layer (cross-cutting)

Every signal above is mediated by *who* is reading it. The same friction destroys a Pragmatist and is invisible to a Migrant. Same warmth reassures an Anxious newcomer and bores a Skeptic.

See `personas.md` for the six archetypes and the cross-reference logic.

---

## Books / sources to cite by short reference

When generating reports, use these short references in citations:

- **Bush** — *Product-Led Onboarding* (ARC framework, value gap)
- **John** — *Product-Led Onboarding* (EUREKA, MVO)
- **Higgins** — *Better Onboarding* (onboarding surface area, empty states)
- **Sierra** — *Badass: Making Users Awesome* (competence not features)
- **Krug** — *Don't Make Me Think* (cognitive load, scannability)
- **Norman** — *Design of Everyday Things* (signifiers, feedback)
- **Eyal** — *Hooked* (variable rewards, trigger-action-reward-investment)
- **Cialdini** — *Influence* (six principles)
- **Kahneman** — *Thinking Fast and Slow* (peak-end, loss aversion)
- **Fogg** — *Tiny Habits* (B = MAP)
- **Deci & Ryan** — *Self-Determination Theory* (autonomy, competence, relatedness)
- **Thaler & Sunstein** — *Nudge* (choice architecture, defaults)
- **Iyengar** — *The Art of Choosing* (choice paralysis)
- **Miller** — *Building a StoryBrand* (user as hero)
- **Brignull** — *darkpatterns.org* (anti-pattern taxonomy)
- **Reforge** — activation = behavior that predicts retention
- **WCAG 2.2** — accessibility baseline
- **Lindgaard et al. (2006)** — 50ms first impression study
- **Akamai/Walmart studies** — latency-conversion correlations

---

## What to skip

When fielding pushback that the audit is "too academic," remember: every signal is operational and measurable. The lens is named so the reader can verify or argue with the principle, not to perform sophistication. If a citation isn't doing work, drop it.
