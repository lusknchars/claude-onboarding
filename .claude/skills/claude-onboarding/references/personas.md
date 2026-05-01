# Personas — The Six Archetypes

Same flow lands differently on different brains. This file defines the six personas the audit cross-references. Every signal in `rubric.md` carries persona codes; the report scores not just "is this good?" but "for whom is this good?"

These archetypes are derived from:

- **Bob Moesta — Forces of Progress** (push, pull, anxiety, habit)
- **Indi Young — Listening user research personas**
- **Cooper — *About Face* personas** (primary, secondary, served, anti)
- **Wes Bush — *Product-Led Onboarding* user types** (browser, evaluator, buyer)

Six is not arbitrary. Fewer over-generalizes; more becomes ungeneratable for a 5-min audit. Six covers the dominant motivation modes in tech product onboarding.

---

## `PRG` — The Pragmatist

> *"Show me value in 60 seconds or I leave."*

**Demographic correlate:** experienced developers, busy PMs, technical buyers under deadline.

**Motivation profile:**
- High motivation, low patience
- Will not read long copy
- Skips tours, ignores tooltips
- Reads like a vampire: scans, doesn't sip

**What they need:**
- Time-to-value claim that is true
- Skip everywhere
- Skeleton screens > spinners
- Code samples / actual product preview > marketing language

**What harms them:**
- Forced workspace setup before first action
- Multi-step wizards for simple goals
- "Tell us about yourself" surveys before any value
- Marketing modals between them and the product

**Signals that disproportionately serve them:** S006, S010, S021, S052, S060, S064, S065, S101.
**Signals that disproportionately harm them:** S001(high), S033, S034, S037, S047, S049.

---

## `SKP` — The Skeptic

> *"Prove this is real before I commit anything."*

**Demographic correlate:** enterprise evaluators, security-conscious buyers, burned-before users, due-diligence personas.

**Motivation profile:**
- Default state: distrust
- Reads pricing first, terms second, hero last
- Looks for press, customers, founder names, security posture
- Will leave at the first sign of dark pattern

**What they need:**
- Real customer logos (recognizable, not stock)
- Compliance badges, security mentions
- Pricing transparency
- Founder visibility — anonymous companies = scam signal
- Comparison page (and an honest one)

**What harms them:**
- Manufactured scarcity ("only 3 spots left!")
- Required credit card on "free trial"
- Hidden pricing
- Generic testimonials with stock photos

**Signals that disproportionately serve them:** S011, S012, S015–S019, S064, S066, S069, S070.
**Signals that disproportionately harm them:** S020, S031, S034, S035.

---

## `EXP` — The Explorer

> *"Let me poke around before deciding."*

**Demographic correlate:** designers, hobbyists, learners, evaluators with no immediate deadline.

**Motivation profile:**
- Curious-state motivation
- Wants to play, not commit
- Multiple tabs open, comparing options
- Reads docs / tries demos before signup

**What they need:**
- Sandbox / playground / demo without signup
- "Skip" affordances everywhere
- Optional fields that *feel* optional
- Visible escape paths

**What harms them:**
- Linear forced flow
- Required fields that don't earn their place
- Modal traps
- "You need to sign up to see this" walls

**Signals that disproportionately serve them:** S053, S063, S065, S067, S109.
**Signals that disproportionately harm them:** S036, S038, S039, S040.

---

## `ANX` — The Anxious Newcomer

> *"Tell me I won't break anything."*

**Demographic correlate:** non-technical users approaching technical products, first-time SaaS buyers, students.

**Motivation profile:**
- Higher motivation than average (they're choosing TO be there)
- High fear of "doing it wrong"
- Reads everything, including microcopy
- Sensitive to tone

**What they need:**
- Reassuring copy ("no design experience needed")
- Visible help / chat / docs
- Non-destructive defaults (undo, drafts, autosave)
- Personalized welcome
- Small first action with celebration

**What harms them:**
- Jargon, acronyms
- Cold confirmation copy ("Email sent.")
- Modal traps
- Time-to-value promises that feel impossibly fast (raises suspicion)

**Signals that disproportionately serve them:** S013, S023(low), S025, S027, S054, S055, S104.
**Signals that disproportionately harm them:** S023(high), S038, S042, S047.

---

## `MIG` — The Migrant

> *"I'm coming from a competitor. Skip the basics."*

**Demographic correlate:** power users switching tools, agency users onboarding new clients, advanced practitioners.

**Motivation profile:**
- Knows the category cold
- Frustrated by "what is X?" copy
- Wants import paths, API access, keyboard shortcuts
- Zero patience for tours

**What they need:**
- Migration path from competitor (named, with import tool)
- Comparison page
- API docs / CLI / dev features visible
- Power-user signals (keyboard shortcuts, advanced options)
- Use-case branching (developer/designer/PM)

**What harms them:**
- Beginner copy
- Forced tours
- Generic onboarding for everyone
- "What's a database?" framing

**Signals that disproportionately serve them:** S023(high — signals expertise), S063, S065, S067, S069.
**Signals that disproportionately harm them:** S039, S047 (forced tours kill them).

---

## `BRW` — The Casual Browser

> *"I'm just looking. Don't pressure me."*

**Demographic correlate:** discovery-phase users, link-followers from social media, students, the curious.

**Motivation profile:**
- Lowest motivation tier
- Highest leave probability
- Reads hero, maybe scrolls
- Will not give up email casually

**What they need:**
- No-signup demo path
- Free tier visibility without scrolling
- "No credit card required" copy
- Low-commitment first action
- Compelling hero that earns the scroll

**What harms them:**
- Email gate before any value
- Forced phone number
- Long forms
- Heavy marketing language

**Signals that disproportionately serve them:** S013, S063, S064, S065.
**Signals that disproportionately harm them:** S001(high), S033, S034, S038.

---

## How to use personas in the report

For each audit, after scoring all 110 signals:

1. For each persona, sum the WATCH/FAIL signals tagged for them
2. Identify the persona that **suffers most** in this flow
3. Identify the persona that this flow seems **optimized for**
4. Output a "for whom" reading that surfaces this asymmetry

Example output line:

> **This flow is optimized for `MIG`** (power-user defaults, jargon-rich copy, dense pricing) but **actively harms `ANX` and `BRW`** (no reassurance, jargon density 5×, no demo path before email gate). If 60% of your traffic is `BRW`, this flow is leaving 40%+ of activatable users on the table.

This is the differentiated insight — most audits never ask the "for whom" question.

---

## Persona distribution heuristic

When the user says "audit Linear's onboarding," they probably haven't told you *who their users are*. Without that, infer category-typical mix:

| Category | Likely mix |
|---|---|
| Developer tools | 50% MIG, 30% PRG, 10% SKP, 10% EXP |
| B2B SaaS | 30% SKP, 30% PRG, 20% MIG, 20% ANX |
| Design tools | 30% EXP, 25% MIG, 25% ANX, 20% PRG |
| Consumer / prosumer | 40% BRW, 30% ANX, 20% EXP, 10% PRG |
| Enterprise | 50% SKP, 30% MIG, 20% PRG |

If the user provides their actual mix, use it. Otherwise infer + state the assumption.
