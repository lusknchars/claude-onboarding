# Rubric — 110 Onboarding Signals

Each signal: name, what to look for in HTML/CSS, scoring criteria, why it matters, which personas it affects.

**Scoring:** `PASS` (signal is well executed) / `WATCH` (acceptable but improvable) / `FAIL` (signal is broken or absent).

**Persona codes** (see `personas.md`): `PRG` Pragmatist · `SKP` Skeptic · `EXP` Explorer · `ANX` Anxious Newcomer · `MIG` Migrant · `BRW` Browser.

---

## Category 1 — Form Cognitive Load (10 signals)

Hick's Law: decision time scales logarithmically with options. Each field is a friction unit. Sweller's cognitive load theory: extraneous load kills task completion.

### S001 — Field count
- **Look for:** total visible `<input>` (excl. hidden) + `<select>` + `<textarea>` in signup form
- **PASS:** ≤4  ·  **WATCH:** 5–7  ·  **FAIL:** ≥8
- **Why:** every field doubles dropoff at the margin (Krug, *Don't Make Me Think*)
- **Hurts:** `PRG` `BRW` · **Helps:** `SKP` (only if fields earn trust)

### S002 — Required field ratio
- **Look for:** `required` attribute or `*` markers on labels
- **PASS:** only email + password required  ·  **WATCH:** +1 extra  ·  **FAIL:** ≥3 required beyond auth
- **Why:** forced fields = forced commitment before value (Bush, ARC framework)
- **Hurts:** `PRG` `EXP` `BRW`

### S003 — Field grouping & spacing
- **Look for:** logical grouping (auth fields together, profile fields together), white space between groups
- **PASS:** clear groups, ≥16px gap  ·  **WATCH:** flat list, no grouping  ·  **FAIL:** dense, no breathing room
- **Why:** chunking reduces working memory load (Miller, 7±2)

### S004 — Inline validation
- **Look for:** `pattern`, `aria-invalid`, JS validation hints in markup, error containers
- **PASS:** real-time hints + helpful copy  ·  **WATCH:** validation only on submit  ·  **FAIL:** no validation visible
- **Why:** late errors = redo cost (Norman, *Design of Everyday Things*)

### S005 — Password requirements visible upfront
- **Look for:** helper text near password field listing rules
- **PASS:** rules shown before typing  ·  **WATCH:** rules shown on focus  ·  **FAIL:** rules revealed only after rejection
- **Why:** retroactive failure violates predictability principle (Nielsen heuristic 1)

### S006 — Auto-focus on first field
- **Look for:** `autofocus` attribute on first input
- **PASS:** present on email/first field  ·  **FAIL:** absent
- **Why:** eliminates one click; respects user intent

### S007 — Smart defaults
- **Look for:** prefilled values (country from IP, timezone, locale), browser autofill compatibility (`autocomplete` attrs)
- **PASS:** ≥3 sensible defaults + autocomplete tokens  ·  **WATCH:** autocomplete only  ·  **FAIL:** none
- **Why:** default effect (Thaler & Sunstein, *Nudge*)

### S008 — Form depth
- **Look for:** single-page form vs multi-step wizard (look for `step` indicators, `nextStep` JS)
- **PASS:** single page if ≤6 fields, wizard if ≥7 with progress shown  ·  **FAIL:** multi-step for tiny forms (artificial complexity)
- **Why:** Zeigarnik effect rewards progress only if steps are meaningful (Higgins, *Better Onboarding*)

### S009 — Help text proximity
- **Look for:** `<small>`, `aria-describedby`, helper-class spans inside or directly below field
- **PASS:** within 8px of field  ·  **FAIL:** floating tooltip requiring hover
- **Why:** spatial association reduces cognitive shift (Gestalt proximity)

### S010 — Input type appropriateness
- **Look for:** `type="email"`, `type="tel"`, `type="number"`, `inputmode` attrs
- **PASS:** all fields use semantic types  ·  **FAIL:** all fields are `type="text"`
- **Why:** wrong keyboard on mobile = friction (touched in S071–S080 too)

---

## Category 2 — Trust & Credibility (10 signals)

Cialdini's *Influence*: social proof, authority, liking, scarcity (used ethically), commitment, reciprocity. Trust deficit kills signups before form is touched.

### S011 — Social proof on signup page
- **Look for:** "Join 50,000+ teams", customer count badges, user testimonials near form
- **PASS:** specific number + recent  ·  **WATCH:** vague ("trusted by thousands")  ·  **FAIL:** none
- **Why:** social proof is strongest when specific (Cialdini)
- **Helps:** `SKP` `ANX` `BRW`

### S012 — Customer logo strip
- **Look for:** `<img>` cluster of company logos near hero/form
- **PASS:** ≥5 recognizable logos  ·  **WATCH:** 3–4 logos  ·  **FAIL:** none or stock placeholders
- **Helps:** `SKP` `MIG`

### S013 — Privacy/security copy near form
- **Look for:** microcopy mentioning "we won't spam you", "encrypted", "GDPR-compliant" within form bounds
- **PASS:** specific reassurance  ·  **FAIL:** none
- **Helps:** `ANX` `SKP`

### S014 — HTTPS + security indicators
- **Look for:** `https://` URL, `Secure` headers, lock icons in copy
- **PASS:** HTTPS + visible mention  ·  **FAIL:** HTTP (instant disqualification)

### S015 — Compliance badges
- **Look for:** SOC2, ISO 27001, HIPAA, GDPR badges (often `<img>` with alt text)
- **PASS:** ≥2 badges relevant to product  ·  **WATCH:** privacy policy link only  ·  **FAIL:** nothing
- **Helps:** `SKP` `MIG` (B2B critical)

### S016 — Founder/team visibility
- **Look for:** "About" link, founder photos in footer, leadership page accessible
- **PASS:** ≤2 clicks to face + name  ·  **FAIL:** anonymous company

### S017 — Press / awards mention
- **Look for:** "As seen in" logos, "Featured by", award badges
- **PASS:** ≥2 reputable outlets  ·  **WATCH:** generic "featured"  ·  **FAIL:** none
- **Helps:** `SKP`

### S018 — Customer count / scale signal
- **Look for:** specific numbers — "10M users", "1B requests/day", "500 enterprise customers"
- **PASS:** specific + impressive  ·  **WATCH:** generic  ·  **FAIL:** absent
- **Why:** anchors perception of legitimacy (Cialdini authority)

### S019 — Pricing transparency before signup
- **Look for:** pricing page link in nav, free tier mentioned on landing
- **PASS:** pricing visible without signup  ·  **FAIL:** "talk to sales" only
- **Helps:** `PRG` `MIG` · **Hurts when hidden:** `SKP`

### S020 — Anti-pattern: manufactured scarcity
- **Look for:** countdown timers, "only X spots left" without basis
- **FAIL:** any artificial urgency  ·  **PASS:** no scarcity manipulation
- **Why:** dark pattern, erodes trust on detection (Brignull's pattern library)

---

## Category 3 — Microcopy & Voice (10 signals)

Sierra (*Badass*): users don't want to feel onboarded; they want to feel competent. Microcopy is where competence is granted or denied.

### S021 — CTA verb specificity
- **Look for:** primary button text
- **PASS:** outcome-specific ("Start your first design", "Get my free analysis")  ·  **WATCH:** generic ("Get started", "Sign up")  ·  **FAIL:** "Submit", "Continue", "OK"
- **Why:** specific verbs prime the brain for the next action (Sierra)

### S022 — Tone consistency
- **Look for:** does tone of hero match form labels match button match microcopy?
- **PASS:** consistent voice  ·  **FAIL:** marketing-formal in hero, casual in form, robotic in errors
- **Why:** dissonance breaks suspension of disbelief

### S023 — Jargon density
- **Look for:** acronyms, internal terminology, industry buzzwords on signup page
- **PASS:** ≤2 acronyms, all defined  ·  **WATCH:** 3–5  ·  **FAIL:** ≥6 unexplained
- **Hurts:** `ANX` `BRW` · **Helps:** `MIG` (signals expertise)

### S024 — Reading level
- **Look for:** copy complexity (estimate Flesch-Kincaid grade by sentence length + syllable count)
- **PASS:** grade 6–8  ·  **WATCH:** 9–12  ·  **FAIL:** ≥13
- **Why:** clarity scales with audience breadth (Krug)

### S025 — Error message tone
- **Look for:** error message templates in markup or visible states
- **PASS:** specific + actionable + warm ("That email's already in use — log in instead?")  ·  **FAIL:** "Invalid input"

### S026 — Empty form state copy
- **Look for:** placeholder text, empty container copy
- **PASS:** invitational ("What's your work email?")  ·  **FAIL:** label-as-placeholder ("Email")

### S027 — Confirmation copy warmth
- **Look for:** post-submit confirmation, "check your email" page
- **PASS:** human + specific ("We sent a magic link to lucas@example.com — usually arrives in 10 seconds")  ·  **FAIL:** "Email sent."

### S028 — Brand voice presence
- **Look for:** does the copy sound like *this* product or could it be on any signup page?
- **PASS:** distinctive personality  ·  **FAIL:** Mad Libs SaaS

### S029 — Pronoun choice (you/we ratio)
- **Look for:** count "you/your" vs "we/our" on signup page
- **PASS:** you-dominant (≥2:1)  ·  **FAIL:** we-dominant (company-centric copy)
- **Why:** *Building a StoryBrand* (Miller) — user is the hero

### S030 — Headline benefit clarity
- **Look for:** H1 above form
- **PASS:** outcome-stated ("Ship websites in 60 seconds")  ·  **WATCH:** feature-stated ("All-in-one platform")  ·  **FAIL:** brand-stated ("Welcome to Acme")

---

## Category 4 — Friction & Dark Patterns (10 signals)

Bush (*Product-Led Onboarding*): every roadblock not earning trust is taxing activation. Brignull's dark pattern taxonomy: the line between persuasion and manipulation.

### S031 — Required marketing consent
- **Look for:** unchecked-but-required marketing checkbox, hidden in TOS
- **PASS:** opt-in optional & unchecked  ·  **FAIL:** required to proceed
- **Why:** GDPR violation in EU; trust erosion globally

### S032 — Pre-checked subscription opt-ins
- **Look for:** `checked` attribute on marketing/newsletter checkbox
- **FAIL:** any pre-checked subscription  ·  **PASS:** opt-in unchecked or absent

### S033 — Forced phone number
- **Look for:** phone field marked required for free signup
- **PASS:** absent or optional  ·  **FAIL:** required for free tier
- **Hurts:** `BRW` `EXP` `ANX` (high friction; signals B2B sales pressure)

### S034 — Forced credit card on free tier
- **Look for:** "free trial" requiring card upfront
- **PASS:** truly free / no card  ·  **FAIL:** card required for trial called "free"
- **Why:** dark pattern; "free" implies no risk (Cialdini commitment)

### S035 — Confirmshaming
- **Look for:** dismissive opt-out copy ("No thanks, I don't want to save money")
- **FAIL:** any guilting language  ·  **PASS:** neutral opt-out

### S036 — Hidden cancellation/exit path
- **Look for:** can user back out of signup mid-flow?
- **PASS:** clear exit at every step  ·  **FAIL:** modal trap, hijacked back button
- **Why:** autonomy violation (Deci & Ryan SDT)

### S037 — Forced workspace/team setup before activation
- **Look for:** "name your workspace" gate before any product value
- **PASS:** workspace optional / inferred  ·  **WATCH:** required but defaulted  ·  **FAIL:** blocking step with no guidance
- **Hurts:** `BRW` `EXP` (friction before value)

### S038 — Forced email verification before any value
- **Look for:** can user see anything pre-verification?
- **PASS:** soft wall (preview while verification pending)  ·  **FAIL:** hard wall (nothing without verify)
- **Why:** "soft wall" pattern (Bush)

### S039 — Dismissal friction on tour/modals
- **Look for:** can user skip product tour, close modals, dismiss tooltips?
- **PASS:** visible "Skip" / X button  ·  **FAIL:** must complete

### S040 — Roadblock vs benevolent gate
- **Look for:** is each gate earning trust (verification) or extracting commitment (forced upgrade prompt)?
- **PASS:** every gate provides value or safety  ·  **FAIL:** gates serve company KPIs not user

---

## Category 5 — Visual Hierarchy & Attention (10 signals)

Norman, Krug. Attention is finite; design directs it or wastes it.

### S041 — Single primary CTA
- **Look for:** above-fold buttons; count "primary-styled" CTAs (filled, brand color)
- **PASS:** exactly one primary CTA  ·  **FAIL:** ≥2 primary buttons competing
- **Why:** Hick's Law on CTAs

### S042 — CTA color contrast
- **Look for:** primary button color vs background; estimate WCAG AA contrast (≥4.5:1 for text)
- **PASS:** meets AA  ·  **FAIL:** below 3:1
- **Hurts:** `ANX` (low confidence on next action)

### S043 — Form vs decoration weight
- **Look for:** is the signup form visually heavier than hero illustration / animation?
- **PASS:** form draws eye first  ·  **FAIL:** decoration dominates

### S044 — Above-fold form completeness
- **Look for:** is the entire form visible without scrolling on a 1366×768 viewport?
- **PASS:** entire form visible  ·  **WATCH:** form starts above fold, ends below  ·  **FAIL:** form fully below fold

### S045 — White space
- **Look for:** padding/margin around form, between sections
- **PASS:** generous spacing (≥24px between sections)  ·  **FAIL:** dense, cluttered

### S046 — Heading hierarchy
- **Look for:** semantic `<h1>`/`<h2>`/`<h3>` order
- **PASS:** one H1, logical descent  ·  **FAIL:** multiple H1s, skipped levels

### S047 — Animation purpose
- **Look for:** decorative animations, parallax, video backgrounds
- **PASS:** animation supports comprehension (e.g., shows product in use)  ·  **FAIL:** decoration that distracts from form
- **Hurts:** `PRG` `ANX`

### S048 — Eye-track readability
- **Look for:** does layout follow F-pattern (heading top-left, supporting copy left-aligned, CTA bottom-right or below copy)?
- **PASS:** standard F-pattern  ·  **FAIL:** chaotic or center-aligned long text

### S049 — Distraction count
- **Look for:** chat widgets auto-popping, exit-intent modals, sidebar promos, sticky banners
- **PASS:** signup page is distraction-light  ·  **FAIL:** ≥3 attention competitors

### S050 — Logo→CTA visual path
- **Look for:** distance and clarity from logo (top-left brand anchor) to primary CTA
- **PASS:** straight read down or to the right  ·  **FAIL:** CTA hidden or off-pattern

---

## Category 6 — Motivation Triggers (10 signals)

Fogg Behavior Model: B = MAP (Motivation × Ability × Prompt). Self-Determination Theory (Deci & Ryan): Autonomy + Competence + Relatedness drive intrinsic motivation. Without motivation, no friction reduction matters.

### S051 — Outcome promise specificity
- **Look for:** what will I have *done* after signup?
- **PASS:** concrete artifact ("Your first chart in 60 seconds")  ·  **FAIL:** abstract benefit ("Unlock your potential")
- **Why:** specificity primes mental simulation

### S052 — Time-to-value claim
- **Look for:** explicit time estimate ("set up in 2 minutes")
- **PASS:** specific time  ·  **FAIL:** vague ("get started fast")

### S053 — Autonomy signal (escape hatches)
- **Look for:** "skip", "explore on your own", "I'll set this up later" options
- **PASS:** visible alternative paths  ·  **FAIL:** linear forced flow
- **Why:** SDT autonomy
- **Helps:** `EXP` `MIG`

### S054 — Competence signal
- **Look for:** "you can" framing, pre-emptive reassurance ("no design experience needed")
- **PASS:** explicit  ·  **FAIL:** absent
- **Helps:** `ANX`

### S055 — Relatedness signal
- **Look for:** "join the community", Discord/Slack links, user count
- **PASS:** visible community signal  ·  **FAIL:** isolated experience
- **Helps:** `BRW` `ANX`

### S056 — Goal-gradient progress indicator
- **Look for:** "Step 1 of 3" or progress bar in multi-step flows
- **PASS:** present + accurate  ·  **FAIL:** absent in multi-step or misleading
- **Why:** goal-gradient hypothesis — motivation increases as goal nears (Hull, 1932)

### S057 — Personalization promise
- **Look for:** "tell us about yourself" → "we'll customize" framing
- **PASS:** explicit personalization payoff  ·  **WATCH:** asks but doesn't promise  ·  **FAIL:** asks without justification

### S058 — Reward preview
- **Look for:** screenshot/preview of what awaits after signup
- **PASS:** visible product preview  ·  **FAIL:** hero is generic illustration

### S059 — Action-outcome causality clarity
- **Look for:** does each step explain what completing it unlocks?
- **PASS:** clear cause-effect  ·  **FAIL:** opaque sequence

### S060 — Effort estimate transparency
- **Look for:** "this takes 30 seconds" vs no time framing
- **PASS:** transparent effort cost  ·  **FAIL:** opaque (user assumes worst)
- **Helps:** `PRG` `BRW`

---

## Category 7 — Decision Support (10 signals)

Iyengar's choice paralysis. Thaler & Sunstein nudge architecture. Without decision scaffolding, motivated users still bounce.

### S061 — Pricing tier comparison clarity
- **Look for:** pricing page (link from nav) — comparison table
- **PASS:** ≤4 tiers, clear differentiation  ·  **WATCH:** ≥5 tiers  ·  **FAIL:** dense matrix or hidden tiers

### S062 — Default selection
- **Look for:** "Most popular", "Recommended" badge on pricing
- **PASS:** clear default  ·  **FAIL:** equal weight (paradox of choice)
- **Why:** default effect (Thaler/Sunstein)

### S063 — Free tier prominence
- **Look for:** is free tier visible without scrolling on pricing?
- **PASS:** prominent  ·  **FAIL:** buried or absent

### S064 — No-credit-card-required signal
- **Look for:** copy near CTA: "no credit card required"
- **PASS:** explicit  ·  **FAIL:** ambiguous (user assumes card required)
- **Helps:** `BRW` `ANX` `SKP`

### S065 — Try-before-buy path
- **Look for:** demo, sandbox, playground link from landing
- **PASS:** zero-signup demo available  ·  **FAIL:** must signup to see anything
- **Helps:** `EXP` `MIG`

### S066 — FAQ proximity to decision
- **Look for:** FAQ section on landing or pricing page (above-fold or sticky)
- **PASS:** visible without leaving signup context  ·  **FAIL:** FAQ on separate page only
- **Helps:** `SKP`

### S067 — Use-case branching
- **Look for:** "for developers / for designers / for PMs" segmentation in nav or hero
- **PASS:** explicit segmentation with tailored landing  ·  **FAIL:** one-size-fits-all
- **Helps:** all personas via relevance

### S068 — Industry/role personalization
- **Look for:** post-signup or pre-signup question about role/industry
- **PASS:** asks, then customizes  ·  **WATCH:** asks, doesn't customize  ·  **FAIL:** absent

### S069 — Competitor comparison
- **Look for:** "vs Competitor X" page accessible from nav
- **PASS:** present + honest  ·  **WATCH:** present but biased  ·  **FAIL:** absent (forces user to research externally)
- **Helps:** `MIG` `SKP`

### S070 — Money-back / guarantee mention
- **Look for:** refund policy, "cancel anytime" copy near pricing
- **PASS:** explicit risk reduction  ·  **FAIL:** absent
- **Helps:** `ANX` `SKP`

---

## Category 8 — Mobile & Touch (10 signals)

≥60% of signup attempts originate on mobile across most categories. Mobile failure = market failure.

### S071 — Viewport meta correctness
- **Look for:** `<meta name="viewport" content="width=device-width, initial-scale=1">`
- **PASS:** correct  ·  **FAIL:** missing or wrong (e.g., `user-scalable=no`)

### S072 — Tap target size
- **Look for:** button/link sizes via CSS (height/padding); aim ≥44×44px (Apple HIG) or 48×48px (Google)
- **PASS:** ≥44px  ·  **FAIL:** ≤32px

### S073 — Tap target spacing
- **Look for:** margin between adjacent buttons
- **PASS:** ≥8px gap  ·  **FAIL:** adjacent / overlapping

### S074 — Input zoom prevention
- **Look for:** font-size ≥16px on inputs (iOS zooms in on smaller fonts)
- **PASS:** ≥16px  ·  **FAIL:** ≤14px

### S075 — Mobile-specific input types
- **Look for:** `inputmode="numeric"`, `inputmode="tel"`, `type="email"`
- **PASS:** all numeric/email/tel fields use semantic types  ·  **FAIL:** generic text

### S076 — Sticky CTA on mobile
- **Look for:** position:fixed or sticky CTA visible after scroll
- **PASS:** present  ·  **WATCH:** present but obscures content  ·  **FAIL:** absent on long landing

### S077 — Hamburger menu necessity
- **Look for:** hamburger menu on mobile
- **PASS:** present only when nav has ≥4 items  ·  **FAIL:** hamburger hiding 1–2 items
- **Why:** menu hides discoverability

### S078 — Modal dismissibility on mobile
- **Look for:** close X visible on small viewport, tap outside dismisses
- **PASS:** dismissible  ·  **FAIL:** trap

### S079 — Form scroll behavior on focus
- **Look for:** does focused input scroll into view above keyboard?
- **PASS:** field stays visible  ·  **FAIL:** keyboard covers field
- (Hard to assess via static HTML — flag as inferred)

### S080 — Mobile copy length adaptation
- **Look for:** hero copy too long for mobile (CSS media queries adjusting line breaks?)
- **PASS:** mobile-tuned copy  ·  **FAIL:** desktop-only writing

---

## Category 9 — Accessibility (10 signals)

WCAG 2.2 baseline. Inclusive design = reach. ~15% of users have a disability; far more have situational impairment.

### S081 — Alt text on images
- **Look for:** `alt` attributes on `<img>` tags (esp. logo, CTAs-as-image, illustrations)
- **PASS:** all decorative `alt=""`, all meaningful with descriptive alt  ·  **FAIL:** missing alts on key images

### S082 — ARIA labels on form fields
- **Look for:** `aria-label`, `aria-labelledby`, `aria-describedby` on inputs
- **PASS:** all labeled  ·  **FAIL:** unlabeled inputs

### S083 — Form label association
- **Look for:** `<label for="id">` matching `<input id="id">`
- **PASS:** all fields  ·  **FAIL:** placeholder-as-label only

### S084 — Heading hierarchy semantic
- **Look for:** logical H1→H2→H3 nesting, no skipped levels
- **PASS:** clean hierarchy  ·  **FAIL:** styled `<div>`s or skipped levels

### S085 — Color contrast (WCAG AA)
- **Look for:** body text vs background ≥4.5:1, large text ≥3:1
- **PASS:** AA met  ·  **FAIL:** below 3:1 anywhere on form

### S086 — Keyboard navigation
- **Look for:** `tabindex` placement, visible `:focus` styles in CSS
- **PASS:** logical tab order, visible focus ring  ·  **FAIL:** focus invisible or `outline:none` without replacement

### S087 — Skip-to-content link
- **Look for:** `<a href="#main">Skip to content</a>` (typically visually hidden until focus)
- **PASS:** present  ·  **WATCH:** absent on simple page  ·  **FAIL:** absent on complex page

### S088 — Form error announcement
- **Look for:** `aria-live="polite"` on error containers, `aria-invalid` on failed fields
- **PASS:** errors announced to screen readers  ·  **FAIL:** silent visual-only errors

### S089 — Language declaration
- **Look for:** `<html lang="en">` or appropriate
- **PASS:** correct lang  ·  **FAIL:** missing or wrong

### S090 — Reduced-motion respect
- **Look for:** CSS `@media (prefers-reduced-motion: reduce)` overrides
- **PASS:** present, animations disabled  ·  **WATCH:** absent but minimal animation  ·  **FAIL:** absent + heavy animation

---

## Category 10 — Performance & Polish (10 signals)

First impressions form in <50ms (Lindgaard et al., 2006). Every 100ms of latency cuts conversion (Akamai, Walmart, Amazon studies).

### S091 — Page weight
- **Look for:** total transferred bytes (HTML + critical CSS + above-fold images)
- **PASS:** ≤500KB  ·  **WATCH:** 500KB–2MB  ·  **FAIL:** ≥2MB

### S092 — Critical CSS inlined
- **Look for:** `<style>` tag in `<head>` with above-fold styles
- **PASS:** present  ·  **WATCH:** small external CSS only  ·  **FAIL:** large render-blocking CSS

### S093 — JS bundle count
- **Look for:** `<script>` tags (esp. blocking, non-async/defer)
- **PASS:** ≤3 scripts, all async/defer  ·  **WATCH:** 4–8  ·  **FAIL:** ≥9 or render-blocking

### S094 — Font loading strategy
- **Look for:** `font-display: swap`, preloaded fonts, system font stack
- **PASS:** swap or system  ·  **FAIL:** FOIT (invisible text while font loads)

### S095 — Image format
- **Look for:** WebP, AVIF, or `<picture>` with type fallbacks
- **PASS:** modern formats  ·  **WATCH:** PNG/JPG with reasonable sizing  ·  **FAIL:** uncompressed PNG/JPG

### S096 — Lazy loading on offscreen images
- **Look for:** `loading="lazy"` on below-fold `<img>`
- **PASS:** present below fold  ·  **FAIL:** all images eager

### S097 — Third-party script count
- **Look for:** scripts from non-primary domain (analytics, chat, A/B, marketing)
- **PASS:** ≤2  ·  **WATCH:** 3–5  ·  **FAIL:** ≥6
- **Why:** each third-party adds latency + privacy concern

### S098 — LCP element identifiability
- **Look for:** what's likely the largest contentful paint (hero image, headline)?
- **PASS:** identifiable + preloaded  ·  **FAIL:** ambiguous or large delayed asset

### S099 — Layout shift signals
- **Look for:** images/videos without explicit width/height, web fonts without size hints
- **PASS:** dimensions on all media  ·  **FAIL:** layout will shift on load

### S100 — Render-blocking resources
- **Look for:** synchronous `<script>` in `<head>` without async/defer; CSS without media queries
- **PASS:** none in head  ·  **WATCH:** 1–2  ·  **FAIL:** ≥3

---

## Category 11 — Psychological Hooks (10 signals)

Peak-End rule (Kahneman): people remember peaks and the end. Zeigarnik effect: incomplete tasks linger in memory. Variable rewards (Skinner): unpredictable payoff > predictable. Effective onboarding designs the *memory*, not just the experience.

### S101 — First-action triviality
- **Look for:** what's the literal first thing user does post-signup? (often inferred from product tours visible in marketing)
- **PASS:** ≤5 seconds, instant feedback ("name your project")  ·  **FAIL:** complex setup before any action
- **Why:** Fogg Tiny Habits — start absurdly small

### S102 — Progress / steps indicator
- **Look for:** "1 of 4", progress bar, dot indicators in multi-step flows
- **PASS:** present + meaningful  ·  **WATCH:** present but vague  ·  **FAIL:** absent in multi-step
- **Why:** Zeigarnik effect rewards visible progress

### S103 — Celebration / micro-rewards
- **Look for:** confetti, checkmarks, success animations referenced in JS or CSS classes
- **PASS:** present at key milestones  ·  **WATCH:** generic success message  ·  **FAIL:** silent transitions
- **Why:** dopamine reinforcement

### S104 — Personalized welcome
- **Look for:** dynamic insertion of name, company in post-signup copy (`{{firstName}}` patterns or similar)
- **PASS:** personalized copy detected  ·  **WATCH:** generic but warm  ·  **FAIL:** "Welcome user!"
- **Helps:** `ANX`

### S105 — Empty-state seeding
- **Look for:** sample content, demo project, "try this template" affordances
- **PASS:** rich seed content  ·  **WATCH:** templates available but unfeatured  ·  **FAIL:** literal blank slate
- **Why:** *Better Onboarding* (Higgins) — empty states are the most undervalued surface

### S106 — Time-to-aha estimate
- **Look for:** explicit "you'll see your first result in X minutes"
- **PASS:** specific  ·  **FAIL:** absent
- **Helps:** `PRG`

### S107 — Streak / continuity signal
- **Look for:** "Day 1 of your trial", retention nudges visible in copy
- **PASS:** soft retention scaffolding  ·  **WATCH:** trial countdown only  ·  **FAIL:** none

### S108 — Variable reward variety
- **Look for:** different empty states / different first-action prompts (suggests A/B or variability)
- **PASS:** evidence of varied paths  ·  **WATCH:** single path but well-designed  ·  **FAIL:** monotonous
- **Why:** Eyal *Hooked* — variable rewards build habit

### S109 — Peak moment design
- **Look for:** does the flow have *one* designed delightful surprise? (uncommon copy, motion easter egg, unexpected utility)
- **PASS:** identifiable  ·  **FAIL:** flat affect throughout
- **Why:** Kahneman peak-end — one peak > evenly competent flow

### S110 — End-of-onboarding closure
- **Look for:** clear "you're set up" moment + obvious next step
- **PASS:** explicit closure + next action  ·  **WATCH:** dumped into product  ·  **FAIL:** no end signal
- **Why:** Kahneman peak-end — the end disproportionately shapes recall

---

## Scoring summary

After auditing all 110 signals:

- **Category score** = (PASS count × 1.0 + WATCH count × 0.5) / 10 × 100
- **Total score** = average of 11 category scores (0–100)
- **Per-persona score** = weighted sum of signals tagged for that persona

Output the table in `templates/teardown.md`.
