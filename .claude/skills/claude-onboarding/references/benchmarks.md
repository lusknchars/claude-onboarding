# Benchmarks — Pattern Library

Five elite products, one paragraph each per category they exemplify. Use as comparison anchors. When something in the audited product is mediocre, point to what one of these does instead. Always cite the example by name.

The five anchor products:

- **Linear** — issue tracking; cult of the keyboard; minimum viable luxury
- **Stripe** — payments; engineering-first onboarding; docs-as-product
- **Notion** — productivity; templates as activation; community-driven empty states
- **Figma** — design; the multiplayer wow; collaborative competence
- **Vercel** — hosting; deploy-as-onboarding; zero-config delight

Each was chosen because (a) the audit reader has likely seen it, (b) it represents a different opinionated bet on what activation means, (c) the patterns are reproducible.

---

## Form Cognitive Load

**Linear** — *Email-first, password-later.* The signup form asks for email only. Workspace creation is a separate, optional step inside the product. Field count = 1 above-fold. Compare this to most B2B SaaS that demand 5–7 fields up front.

**Stripe** — *Progressive disclosure.* Stripe's signup is email + password + name. Everything else (business info, bank, identity) is gated to the moment those fields are *needed* to unlock specific value. Friction earns its keep.

**Vercel** — *OAuth-first.* "Continue with GitHub" is the dominant CTA. The form is one button. For developers, this collapses signup to ≤2 seconds.

---

## Trust & Credibility

**Linear** — *Customer logos as identity.* Linear's homepage prominently shows OpenAI, Ramp, Cash App, Vercel. Recognition triggers are stacked. They don't list "trusted by 10,000 teams" — they show *which* teams.

**Stripe** — *Compliance as marketing.* Stripe leads with PCI-DSS, SOC2, HIPAA badges. For Skeptic personas in B2B, this clears 30 seconds of due diligence in one glance.

**Notion** — *Founder visibility.* Ivan Zhao's voice runs through the brand, in product copy and changelog. Notion never feels anonymous, which matters for trust in tools that store knowledge.

---

## Microcopy & Voice

**Linear** — *Severe, specific verbs.* "Build" not "Create". "Ship" not "Submit". The voice is calibrated to its audience (engineers who hate marketing speak).

**Notion** — *Conversational warmth.* Notion talks like a friend. "What would you like to call this page?" beats "Page name (required)." The voice does emotional labor.

**Vercel** — *Brevity as luxury.* Vercel's copy is famously sparse. The product speaks for itself; copy gets out of the way. Trade-off: Vercel can do this because their audience already knows what they need.

---

## Friction & Dark Patterns

**Stripe** — *Honest about what's gated.* When Stripe asks for bank info, it explicitly states "this is needed to receive payouts." Friction is contextualized. Compare to "tell us about your business" forms with no explanation.

**Linear** — *Defensive about pop-ups.* Linear has zero exit-intent modals, zero scarcity timers, zero forced upsells. The product's confidence is its marketing.

---

## Visual Hierarchy & Attention

**Vercel** — *Single CTA discipline.* Vercel's homepage above-fold has *one* primary CTA: "Start Deploying." Everything else is secondary. Hick's Law applied with intent.

**Figma** — *Hero proves the product.* Figma's homepage shows live multiplayer cursors moving on a real design. The hero IS the demo. No abstract illustration. The visual hierarchy serves the wow.

---

## Motivation Triggers

**Vercel** — *Time-to-value as identity.* "Deploy in 30 seconds" is true and measurable. The product's promise IS the time claim.

**Figma** — *Reward preview.* Signup prompts show a real design canvas with sample content already loaded. Motivation isn't a copy claim; it's a visible artifact already half-built.

**Linear** — *Power-user signaling.* Even on the marketing site, Linear shows command palette screenshots. This signals to MIG personas: "you'll be home here" before they even sign up.

---

## Decision Support

**Stripe** — *No pricing tier paralysis.* Stripe Standard is "2.9% + 30¢, no monthly fee." One number, one mental model. Custom enterprise is a different page. Choice paralysis avoided by separating B2C-easy from B2B-complex.

**Notion** — *Default tier highlighted.* "Plus" is marked as "Most popular" with a different border color. Default effect deployed deliberately.

**Vercel** — *Free tier prominence.* Hobby tier is the *first* tier on the pricing page, and "Free forever" is stated boldly. BRW persona is reassured before they read further.

---

## Mobile & Touch

**Stripe** — *Mobile parity.* Stripe's signup works as well on a phone as on desktop. No "please use desktop" warnings, no degraded mobile flow. Reach over feature-richness.

**Linear** — *Honest mobile limitation.* Linear's mobile app is read-only-first. They didn't try to cram desktop creation into mobile and fail; they shipped what mobile can excel at. Honest scope.

---

## Accessibility

**GitHub (honorable mention outside the five)** — *Skip-to-content link visible on focus.* Most products fail this; GitHub's skip link is a model. Keyboard navigation is first-class.

**Stripe** — *Screen-reader-friendly forms.* All form fields use proper labels, `aria-describedby` for help text, `aria-live` for errors. Compliance is built-in, not retrofitted.

---

## Performance & Polish

**Vercel** — *Sub-second LCP on marketing.* Vercel's own marketing site is fast because it's hosted on Vercel. The proof is the page itself. Performance as recursive demo.

**Linear** — *Instant perceived speed.* Linear's app uses optimistic updates everywhere. The user's action registers visually before the server confirms. This trades perfect consistency for perceived velocity.

---

## Psychological Hooks

**Notion** — *Empty state as gallery.* Notion's empty workspace shows template thumbnails. The blank slate is replaced with "look what's possible." Higgins's principle in operation.

**Figma** — *Multiplayer cursor as peak moment.* The first time another cursor moves on your screen is the peak moment. Figma engineered this to happen within the first session by suggesting collaborators early.

**Linear** — *Keyboard shortcut reveal.* When a user uses the mouse for an action that has a shortcut, Linear quietly shows the shortcut. The product teaches itself. Zeigarnik effect on competence.

**Stripe** — *Test mode as celebration.* When you make your first test charge, the dashboard celebrates with confetti. The reward is built into the activation event itself.

---

## How to use these in audits

When the audited product fails a category, structure the recommendation like this:

> **S041 (Single Primary CTA): FAIL.** The page has 4 primary-styled buttons competing.
> *Pattern reference:* Vercel's homepage commits to one CTA ("Start Deploying"); secondary actions are visually demoted. Recommendation: pick the highest-intent CTA and let the others recede.

This converts "you're doing it wrong" into "here's a known-good pattern to study." The audited team gets a concrete artifact to compare against, not abstract advice.

---

## Limitations of these benchmarks

These five are mostly developer / B2B SaaS skewed. For audits in other categories (consumer apps, fintech, e-commerce, healthcare), Claude should:

1. Use these as *baseline* for principles
2. Note when category-specific norms differ
3. Cite category-relevant exemplars from training knowledge if available

The principles transfer; the specific UI patterns may not.
