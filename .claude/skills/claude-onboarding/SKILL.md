---
name: claude-onboarding
description: Audit any SaaS onboarding flow in 5 minutes. Use when the user provides a signup URL and wants a scored report identifying friction points, anti-patterns, and prioritized roadmap. Audits 60+ measurable signals across 11 categories grounded in canonical onboarding methodology (Wes Bush, Ramli John, Krystal Higgins, Reforge frameworks).
---

# claude-onboarding

🚧 **v1.0 build target: June 2026.** This SKILL.md is a placeholder.

## What this skill does

Audits a SaaS onboarding flow from a live URL and produces:

1. **Score (0-100)** based on 60+ measurable signals
2. **Top 5 friction points** with screenshots and severity ratings
3. **Prioritized roadmap** with impact/effort estimates
4. **Cited benchmarks** by SaaS category (B2B, B2C, prosumer, dev tools, enterprise)
5. **Pattern recommendations** drawn from elite SaaS teardowns

## Inputs

- **URL** (required): the SaaS signup or product landing URL
- **Test credentials** (optional): for navigating post-signup flows
- **SaaS category** (optional, will be inferred): B2B, B2C, prosumer, dev tools, enterprise, vertical
- **Comparison set** (optional, v1.1+): 1-3 competitor URLs to benchmark against

## Outputs

- Markdown report at `./onboarding-audit-{domain}-{date}.md`
- Screenshot directory at `./onboarding-audit-{domain}-{date}/screenshots/`
- Optional JSON output at `./onboarding-audit-{domain}-{date}.json` (for piping into dashboards)

## Methodology

The audit is grounded in:

- Wes Bush's ARC framework (Activate, Retain, Convert)
- Ramli John's EUREKA methodology + MVO (Minimum Viable Onboarding)
- Krystal Higgins's "onboarding is everywhere" surface area
- Reforge's activation = behavior that predicts retention principle
- Forrester + Nielsen Norman heuristics
- Octalysis (Yu-kai Chou) and Fogg Behavior Model where relevant

See [the companion bibliography](https://github.com/lusknchars/awesome-saas-onboarding) for full source attribution.

## Build status

This skill is in active development. Track progress on the [main repo README](../../../README.md).
