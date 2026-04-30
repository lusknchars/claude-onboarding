# claude-onboarding

> Audit any SaaS onboarding flow in 5 minutes. Get a scored report + prioritized roadmap.

🚧 **Status:** Coming June 2026. Watch the repo or follow [@lusknchars](https://github.com/lusknchars) for the launch.

## What it does

`claude-onboarding` is a [Claude Code](https://claude.com/claude-code) skill that:

1. Takes a SaaS signup URL (and optional test credentials)
2. Navigates the onboarding flow autonomously — signup form, email verification, post-signup screen, empty states, activation surface
3. Audits 60+ measurable signals across 11 categories (form friction, cognitive load, activation surfacing, anti-patterns, accessibility, performance)
4. Compares findings to industry benchmarks segmented by SaaS category
5. Outputs a scored report (0-100) + top friction points with screenshots + prioritized roadmap with citations

The skill replaces what consultants like ProductLed currently sell as a $2,000-$5,000 5-day audit sprint — but in 5 minutes, free, and reproducible across as many SaaS as you want to study.

## Quick start

```bash
# Install Claude Code (if you haven't)
npm install -g @anthropic-ai/claude-code

# Add the skill
# Coming June 2026 — instructions on launch
```

## What it audits

- **Signup form** — field count, social auth, validation, password UX, GDPR friction, CC requirement
- **Email verification** — magic link vs code, latency, soft vs hard wall
- **First screen post-signup** — primary CTA, progress indicator, time-to-orientation, personalization
- **Empty states** — copy quality, sample content seeding, "do this first" CTAs
- **Contextual help** — tooltips, inline vs modal, video embeds
- **Personalization** — role/use-case selectors, downstream branching, sample content matching
- **Activation event surfacing** — proximity to signup, visual prominence, time-to-first-value
- **Friction & anti-patterns** — forced invites, early upsell, mandatory phone, cookie-banner-blocking
- **Mobile responsiveness** — viewport handling, tap targets, font sizing
- **Accessibility** — WCAG 2.2 basics (alt text, contrast, keyboard nav, ARIA)
- **Performance** — LCP, TTI, payload size

## Built on top of

The methodology behind this skill draws from canonical onboarding literature:

- **Wes Bush** — *Product-Led Onboarding* (2021): ARC framework, value gap diagnostic
- **Ramli John** — *Product-Led Onboarding* (2022): EUREKA framework, Minimum Viable Onboarding (MVO)
- **Krystal Higgins** — *Better Onboarding* (2021): "Onboarding is everywhere" — empty states, contextual nudges, recovery flows
- **Bob Moesta** — *Demand-Side Sales 101* (2020): Forces of Progress as activation diagnostic
- **BJ Fogg** — *Tiny Habits* (2019): B = MAP (Motivation × Ability × Prompt)
- **Nir Eyal** — *Hooked* (2014): Trigger / Action / Variable Reward / Investment loop
- **Kathy Sierra** — *Badass: Making Users Awesome* (2015): the philosophical backbone
- **Reforge frameworks** — activation defined as behavior that predicts retention, not vanity completion

For the full bibliography, see [awesome-saas-onboarding](https://github.com/lusknchars/awesome-saas-onboarding).

## Sample output

🚧 *Sample report on a famous SaaS will be added before launch.*

## Roadmap

- **v1.0 (June 2026)** — Web onboarding audit (signup → activation), markdown report, 60+ measurable signals
- **v1.1 (July 2026)** — Comparative audit (against 3 user-specified competitors)
- **v1.2 (August 2026)** — Rewrite generation (corrected copy + suggested components)
- **v2.0 (Q4 2026)** — Lifecycle email audit (welcome series, activation drip)

## Adjacent skills (this family)

Skills that pair well with `claude-onboarding`:

- 🚧 [`claude-pricing`](https://github.com/lusknchars/claude-pricing) — audit your pricing page (July 2026)
- 🚧 [`claude-landing`](https://github.com/lusknchars/claude-landing) — audit your landing page (August 2026)
- 🚧 [`claude-changelog`](https://github.com/lusknchars/claude-changelog) — auto-generate changelogs (July 2026)

## Companion repository

- [awesome-saas-onboarding](https://github.com/lusknchars/awesome-saas-onboarding) — Curated bibliography, frameworks, tools, benchmarks, and elite SaaS teardowns. Read this first.

## Author

Built by [Lucas Oliveira](https://github.com/lusknchars). Reach out on [Twitter/X](https://twitter.com/) or [LinkedIn](https://linkedin.com/).

## License

[MIT](LICENSE) — use it, fork it, ship it.
