# Teardown — {{PRODUCT_NAME}}

> Onboarding teardown · {{DATE}} · audited by `claude-onboarding`
> Source: {{URL}}

---

## TL;DR

**Overall score:** {{TOTAL_SCORE}}/100 — *{{CLASSIFICATION}}*

**This flow is optimized for:** `{{PRIMARY_PERSONA}}`
**This flow actively harms:** `{{HARMED_PERSONAS}}`

**One-line diagnosis:** {{ONE_LINE_DIAGNOSIS}}

**Top 3 leverage points (highest impact × lowest effort):**

1. {{LEVERAGE_1}}
2. {{LEVERAGE_2}}
3. {{LEVERAGE_3}}

---

## Score by category

| # | Category | Score | Verdict |
|---|---|---|---|
| 1 | Form Cognitive Load | {{C1_SCORE}}/100 | {{C1_VERDICT}} |
| 2 | Trust & Credibility | {{C2_SCORE}}/100 | {{C2_VERDICT}} |
| 3 | Microcopy & Voice | {{C3_SCORE}}/100 | {{C3_VERDICT}} |
| 4 | Friction & Dark Patterns | {{C4_SCORE}}/100 | {{C4_VERDICT}} |
| 5 | Visual Hierarchy & Attention | {{C5_SCORE}}/100 | {{C5_VERDICT}} |
| 6 | Motivation Triggers | {{C6_SCORE}}/100 | {{C6_VERDICT}} |
| 7 | Decision Support | {{C7_SCORE}}/100 | {{C7_VERDICT}} |
| 8 | Mobile & Touch | {{C8_SCORE}}/100 | {{C8_VERDICT}} |
| 9 | Accessibility | {{C9_SCORE}}/100 | {{C9_VERDICT}} |
| 10 | Performance & Polish | {{C10_SCORE}}/100 | {{C10_VERDICT}} |
| 11 | Psychological Hooks | {{C11_SCORE}}/100 | {{C11_VERDICT}} |

*Scoring: PASS = 1.0, WATCH = 0.5, FAIL = 0. Each category averages 10 signals.*

---

## Persona reading

For each persona, the experience of this flow:

### `PRG` Pragmatist — score {{PRG_SCORE}}/100
> {{PRG_NARRATIVE}}

**Critical wins for them:** {{PRG_WINS}}
**Critical losses for them:** {{PRG_LOSSES}}

### `SKP` Skeptic — score {{SKP_SCORE}}/100
> {{SKP_NARRATIVE}}

### `EXP` Explorer — score {{EXP_SCORE}}/100
> {{EXP_NARRATIVE}}

### `ANX` Anxious Newcomer — score {{ANX_SCORE}}/100
> {{ANX_NARRATIVE}}

### `MIG` Migrant — score {{MIG_SCORE}}/100
> {{MIG_NARRATIVE}}

### `BRW` Casual Browser — score {{BRW_SCORE}}/100
> {{BRW_NARRATIVE}}

---

## What this flow does well

For each strong category, narrate the pattern (2–4 sentences). Cite the principle.

### Pattern: {{PATTERN_NAME_1}}
{{PATTERN_DESC_1}}

*Principle:* {{PRINCIPLE_REF_1}}

### Pattern: {{PATTERN_NAME_2}}
{{PATTERN_DESC_2}}

*Principle:* {{PRINCIPLE_REF_2}}

(Repeat for as many strengths as warrant calling out — typically 3–5.)

---

## Top 5 friction points

### 1. {{FRICTION_1_TITLE}}
- **Signal:** {{SIGNAL_ID_1}} — {{SIGNAL_NAME_1}}
- **Verdict:** FAIL
- **Evidence:** {{EVIDENCE_1}} *(quote HTML or describe layout)*
- **Why it matters:** {{PRINCIPLE_1}} *(cite from methodology.md)*
- **Personas harmed:** {{PERSONAS_HARMED_1}}
- **Pattern reference:** {{BENCHMARK_REF_1}} *(cite from benchmarks.md)*
- **Fix:** {{FIX_1}}

### 2. {{FRICTION_2_TITLE}}
- **Signal:** {{SIGNAL_ID_2}} — {{SIGNAL_NAME_2}}
- **Verdict:** FAIL
- **Evidence:** {{EVIDENCE_2}}
- **Why it matters:** {{PRINCIPLE_2}}
- **Personas harmed:** {{PERSONAS_HARMED_2}}
- **Pattern reference:** {{BENCHMARK_REF_2}}
- **Fix:** {{FIX_2}}

### 3. {{FRICTION_3_TITLE}}
*(same structure)*

### 4. {{FRICTION_4_TITLE}}
*(same structure)*

### 5. {{FRICTION_5_TITLE}}
*(same structure)*

---

## Prioritized roadmap

Three buckets by impact × effort. Recommend in order.

### Quick wins (≤1 day eng, ≥5 point score gain)
- {{QUICK_WIN_1}}
- {{QUICK_WIN_2}}
- {{QUICK_WIN_3}}

### Mid-term (1–2 weeks)
- {{MID_TERM_1}}
- {{MID_TERM_2}}

### Strategic (≥1 month, requires product-level decisions)
- {{STRATEGIC_1}}
- {{STRATEGIC_2}}

---

## Full signal table (110)

For each signal, status + 1-line evidence. Compact for skim, complete for audit.

### Category 1 — Form Cognitive Load

| ID | Signal | Status | Evidence |
|---|---|---|---|
| S001 | Field count | {{S001}} | {{S001_EV}} |
| S002 | Required field ratio | {{S002}} | {{S002_EV}} |
| S003 | Field grouping & spacing | {{S003}} | {{S003_EV}} |
| S004 | Inline validation | {{S004}} | {{S004_EV}} |
| S005 | Password requirements visible | {{S005}} | {{S005_EV}} |
| S006 | Auto-focus on first field | {{S006}} | {{S006_EV}} |
| S007 | Smart defaults | {{S007}} | {{S007_EV}} |
| S008 | Form depth | {{S008}} | {{S008_EV}} |
| S009 | Help text proximity | {{S009}} | {{S009_EV}} |
| S010 | Input type appropriateness | {{S010}} | {{S010_EV}} |

### Category 2 — Trust & Credibility

| ID | Signal | Status | Evidence |
|---|---|---|---|
| S011 | Social proof on signup | {{S011}} | {{S011_EV}} |
| S012 | Customer logo strip | {{S012}} | {{S012_EV}} |
| S013 | Privacy/security copy near form | {{S013}} | {{S013_EV}} |
| S014 | HTTPS + security indicators | {{S014}} | {{S014_EV}} |
| S015 | Compliance badges | {{S015}} | {{S015_EV}} |
| S016 | Founder/team visibility | {{S016}} | {{S016_EV}} |
| S017 | Press / awards mention | {{S017}} | {{S017_EV}} |
| S018 | Customer count / scale signal | {{S018}} | {{S018_EV}} |
| S019 | Pricing transparency before signup | {{S019}} | {{S019_EV}} |
| S020 | Anti-pattern: scarcity | {{S020}} | {{S020_EV}} |

*(Continue for all 11 categories — S021 through S110 follow the same table format.)*

---

## Limitations of this audit

- v0.1 audits only the **public-facing surface** (signup form + landing). Categories that require post-signup navigation are partially covered:
  - Empty states (S105) — inferred from marketing screenshots when available
  - Personalized welcome (S104) — inferred from JS template strings
  - End-of-onboarding closure (S110) — speculative

- Performance signals (S091–S100) are static estimates; for accurate Core Web Vitals, run Lighthouse separately and re-score.

- Mobile signals (S071–S080) are validated against responsive CSS but not against real device behavior.

- Personas are heuristic archetypes, not your specific user research. Override the persona mix if you have real data.

---

## Methodology

This teardown applies 8 lenses across 11 categories and 110 signals, scored against 6 user personas. Methodology grounded in:

Wes Bush · Ramli John · Krystal Higgins · Kathy Sierra · Don Norman · Steve Krug · Robert Cialdini · Daniel Kahneman · BJ Fogg · Edward Deci & Richard Ryan · Daniel Thaler & Cass Sunstein · Sheena Iyengar · Donald Miller · Harry Brignull · WCAG 2.2 · Reforge.

See `references/methodology.md` for the full lens-to-principle mapping.

---

*Generated by [claude-onboarding](https://github.com/lusknchars/claude-onboarding) · v0.1*
