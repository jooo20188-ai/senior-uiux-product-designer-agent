# Scoring Rubric

The scoring system for every audit mode: expert judgment expressed as scores, bands, and one-line reasons.

## How to use

Scores appear in Mode 1 Quick Audit, Mode 2 Full Product Design Audit, and Mode 11 Final QA. Present them as a table, never as loose numbers in prose:

| Dimension | Score | Band | One-line reason |
|---|---|---|---|
| UX | 68 | Weak | Primary task takes 4 steps that could be 2. |
| Accessibility | 52 | Failing | Body text fails 4.5:1; two form inputs unlabeled. |
| Overall Readiness | 61 | Weak | Core flow works, but an unresolved Critical caps it. |

Rules for the table:
- Score every dimension you can assess. Mark the rest "Not scored" or "Provisional (limited input)".
- The one-line reason must point to something in the findings list. A score the reader cannot trace back to a finding is noise.
- Overall Readiness is a separate judgment, not the average of the other ten.

For partial assessments, keep the row and be explicit about the limit:

| Dimension | Score | Band | One-line reason |
|---|---|---|---|
| Interaction Design | Not scored | Not scored | No error, loading, or empty states were provided to review. |
| Mobile | Provisional (limited input) | Weak | Only a desktop view was shared; mobile inferred, low confidence. |

An honest "Not scored" is worth more than a confident guess. The reader can see exactly what the review could and could not reach, which is itself useful signal about the input.

## Scoring rules

These rules keep scores honest and keep them consistent with the findings list.

- Scores are expert judgment, not measurement. You are estimating how close a senior designer would call this to shippable, not computing a metric.
- Whole numbers only. No decimals. A 73.5 pretends to a precision that heuristic review does not have; round to a whole number and explain it in the reason.
- A Critical issue in a dimension caps that dimension at 74. You cannot call a dimension "good" while it contains something that blocks the task, breaks trust, or excludes users.
- Any unresolved Critical anywhere caps Overall Readiness at 74, regardless of how strong the other dimensions are.
- Dimensions you cannot judge from the input are marked "Not scored" (no relevant input) or "Provisional (limited input)" (partial input, low confidence). Never guess a number to fill the table.
- Scores must never contradict the findings list. If UX shows three High Impact findings, UX cannot score 85. When score and findings disagree, the findings win and the score changes.
- A score without a stated reason is invalid. Every row carries a one-line reason or it does not ship in the table.
- Bands are labels for score ranges, not extra opinions. Read the band off the score using the table below.
- Confidence is separate from the score. A low-confidence assessment can still produce a number; mark it Provisional and say so in the reason rather than lowering the score to signal uncertainty.
- Do not average your way to a number. Within a dimension, weight the issues users actually hit on the core flow over issues on rarely-seen screens.
- When in doubt between two adjacent scores, pick the lower one and state the reason. Optimism in a rubric costs the team a fix they will pay for later.

## Band meanings

| Band | Range | Meaning |
|---|---|---|
| Strong | 90-100 | Ship with confidence. Rare. Reserved for work with no known blocking or high-impact gaps. |
| Good with known gaps | 75-89 | Ship after the listed fixes. Solid foundation, specific issues named and addressable. |
| Weak | 60-74 | Fix the High Impact items before promoting or shipping. Usable but not yet defensible. |
| Failing | Below 60 | Likely blocking users or losing trust. Rework the substance before any polish. |

A score in the 60-74 band with a clean findings list still means "not yet". The band describes readiness to ship, not effort spent.

### Worked example: reading a score

Suppose a signup flow is clean and consistent but has one unlabeled input on the core form and body text at 3.9:1 contrast. The unlabeled input on a core flow is a Critical accessibility finding. That caps Accessibility at 74, and because it is unresolved it also caps Overall Readiness at 74, no matter how strong UI and Visual Hierarchy are. The table might then read: UI 86, Visual Hierarchy 84, Accessibility 58 (failing contrast plus an unlabeled core input), Overall Readiness 71 (sound elsewhere, but a Critical holds it down). Every number traces to a finding, and the caps are visible in the reasons. This is what "scores never contradict the findings" looks like in practice.

## UX

**What it measures:** Whether users can complete the primary task quickly, with minimal confusion, and without dead ends. This is task flow and clarity, not looks.

**Evidence to check:**
- The primary task and the number of steps it currently takes.
- Points where a first-time user would hesitate or guess.
- Dead ends, loops, or steps that exist for the system rather than the user.
- Whether the next action is obvious at each step.
- Recovery paths when a user makes a mistake.

| Band | Anchor |
|---|---|
| 90-100 | Primary task is obvious and short. Every step earns its place. First-time users do not hesitate. |
| 75-89 | Task completes reliably, but one or two steps add friction or need a second look. |
| 60-74 | Task completes, but the path is longer than it should be or a step reliably confuses users. |
| Below 60 | Users get lost, hit dead ends, or cannot tell what to do next on a core flow. |

## UI

**What it measures:** Whether the surface is clean, consistent, and legible: spacing, alignment, type, color use, and component polish at the pixel level.

**Evidence to check:**
- Spacing consistency against a 4 or 8px scale.
- Alignment across sections and within components.
- Type scale: are sizes and weights deliberate or accidental?
- Color use: purposeful, or decoration competing with content?
- Component consistency: do the same elements look the same everywhere?

| Band | Anchor |
|---|---|
| 90-100 | Consistent spacing scale, deliberate type ramp, aligned layout, components uniform across screens. |
| 75-89 | Mostly clean, with a few spacing or alignment inconsistencies that read as minor sloppiness. |
| 60-74 | Noticeable inconsistency in spacing, type, or color that makes the product feel unfinished. |
| Below 60 | Layout is misaligned or crowded; type and color feel arbitrary; components drift between screens. |

## Visual Hierarchy

**What it measures:** Whether the eye lands on the right thing first and moves in the intended order. One clear focal point per screen, supporting elements ranked beneath it.

**Evidence to check:**
- What pulls the eye first, and whether that is the intended priority.
- Whether the primary action stands apart from secondary actions.
- Contrast and size differences between heading levels.
- Whether multiple elements compete for the same attention rank.
- Use of whitespace to group and separate.

| Band | Anchor |
|---|---|
| 90-100 | One clear focal point; primary action is distinct; the eye moves in the intended order without effort. |
| 75-89 | Hierarchy mostly reads, but a secondary element occasionally competes with the primary one. |
| 60-74 | Several elements share the top rank; the primary action does not clearly win attention. |
| Below 60 | Everything is emphasized, so nothing is; the eye has no clear starting point. |

## Mobile

**What it measures:** Whether the experience works well on a phone as a first-class context, not a shrunk desktop layout. Touch, legibility, and reflow under real conditions.

**Evidence to check:**
- Body text size against the 16px mobile minimum.
- Touch targets against the 44px practical minimum.
- Reflow: does content stack cleanly or overflow and clip?
- Tap target spacing: are adjacent controls far enough apart to hit accurately?
- Fixed elements: do headers, banners, or keyboards cover content or actions?

| Band | Anchor |
|---|---|
| 90-100 | 16px+ body text, 44px+ targets, clean stacking, comfortable spacing, no clipped or covered content. |
| 75-89 | Works on mobile, but a few small targets or tight spacings make some taps imprecise. |
| 60-74 | Text below 16px in places, targets near the 24px floor, or reflow that forces horizontal scrolling. |
| Below 60 | Layout breaks on a phone: content clipped, targets too small to hit, or a core action unreachable. |

## Accessibility

**What it measures:** Whether the product meets a baseline of usability for people using assistive technology, keyboards, and low vision. Heuristic review, not a certified audit.

**Evidence to check:**
- Body text contrast against 4.5:1 and large text or UI components against 3:1.
- Visible keyboard focus on every interactive element.
- Form inputs with programmatic labels, not placeholder-only.
- Heading order: logical and sequential, not skipped for styling.
- Meaning conveyed by more than color alone.

| Band | Anchor |
|---|---|
| 90-100 | Passing contrast, visible focus, labeled forms, logical heading order, no color-only meaning. |
| 75-89 | Baseline mostly met; isolated issues such as one low-contrast label or a missing focus style. |
| 60-74 | Several heuristic failures: inconsistent focus, some unlabeled inputs, or borderline contrast. |
| Below 60 | Failing body-text contrast or unlabeled inputs on a core flow; keyboard users cannot proceed. |

## Trust and Credibility

**What it measures:** Whether the product earns enough confidence for the user to continue: clear identity, honest claims, real proof, and no manipulation.

**Evidence to check:**
- Is it clear who is behind the product and how to reach them?
- Are claims specific and honest, or vague and inflated?
- Is proof real and attributable, or generic filler?
- Are costs, terms, and commitments visible before the user commits?
- Any dark patterns: fake scarcity, forced continuity, hidden costs, confirm shaming.

| Band | Anchor |
|---|---|
| 90-100 | Clear identity, honest specific claims, real proof, transparent costs, no manipulative patterns. |
| 75-89 | Generally trustworthy, but one weak signal: thin proof, vague claim, or a hard-to-find contact path. |
| 60-74 | Trust gaps a cautious user would notice: unclear ownership, generic proof, or costs surfaced late. |
| Below 60 | Trust is broken or manipulated: hidden costs, fake urgency, unverifiable claims, or confirm shaming. |

## Conversion

**What it measures:** Whether the design supports the intended action ethically: clear value, one obvious next step, and no friction that is not earned. Ethical conversion only.

**Evidence to check:**
- Is the value proposition clear above the fold or at the entry point?
- Is there one primary action, and is it easy to find and take?
- Are form fields and steps reduced to what is genuinely needed?
- Do objections get answered near the point of decision?
- Any manipulation standing in for persuasion.

| Band | Anchor |
|---|---|
| 90-100 | Clear value, one obvious ethical primary action, minimal friction, objections answered in place. |
| 75-89 | Path to action works, but value could be sharper or one unnecessary field slows the commitment. |
| 60-74 | Value is unclear or the primary action competes with distractions; avoidable friction remains. |
| Below 60 | No clear action, buried value, excessive friction, or reliance on dark patterns to convert. |

## Design System

**What it measures:** Whether the product is built from a coherent, reusable set of tokens and components rather than one-off decisions. Consistency and scalability.

**Evidence to check:**
- Evidence of a spacing scale (4 or 8px) applied consistently.
- A defined type scale rather than arbitrary sizes.
- Color tokens with clear roles, not scattered hex values.
- Reused components versus repeated bespoke elements.
- Documented states and variants, or their absence.

| Band | Anchor |
|---|---|
| 90-100 | Coherent tokens for color, type, spacing, and radius; components reused with documented variants. |
| 75-89 | A system exists, but some values sit outside the scale or a few components are one-off. |
| 60-74 | Partial system: some tokens, many ad hoc values; components duplicated with small differences. |
| Below 60 | No discernible system; sizes, colors, and spacing are chosen per screen with no reuse. |

## Interaction Design

**What it measures:** Whether the product handles states and feedback well: empty, loading, error, and success are designed, and motion is purposeful and accessible.

**Evidence to check:**
- Are empty states designed, or blank and confusing?
- Loading states: is there feedback, or an unexplained wait?
- Error states: clear, specific, and recoverable?
- Success and confirmation: does the user know the action worked?
- Motion: purposeful, and does it respect prefers-reduced-motion?

| Band | Anchor |
|---|---|
| 90-100 | Empty, loading, error, and success states all designed; feedback is immediate; motion respects reduced-motion. |
| 75-89 | Core states handled, but one is thin: a generic error message or an undesigned empty state. |
| 60-74 | Several states missing or unclear; users wait or fail without adequate feedback. |
| Below 60 | States are absent: blank screens, silent failures, no confirmation that actions succeeded. |

## Modern UI Style Fit

**What it measures:** Whether the chosen visual style suits the product, audience, and content, and is executed consistently. Fit and coherence, not trend-chasing.

**Evidence to check:**
- Does the style match the audience and the product's purpose?
- Is one style applied coherently, or are several mixed?
- Does the style serve legibility and hierarchy, or fight them?
- Is the execution current without copying a trend for its own sake?
- Does the style hold up across the key screens?

| Band | Anchor |
|---|---|
| 90-100 | Style fits audience and content, applied coherently across screens, and supports legibility and hierarchy. |
| 75-89 | Style mostly fits, with minor inconsistency or one screen that drifts from the chosen direction. |
| 60-74 | Style is generic or mildly mismatched to the audience; execution is uneven across screens. |
| Below 60 | Style fights the content or the audience, mixes incompatible directions, or harms legibility. |

## Overall Readiness

**What it measures:** A single judgment, not an average: would a senior designer put their name on shipping this as it stands? It weighs the whole product, including how the dimensions interact.

**Evidence to check:**
- The state of the primary task end to end.
- Any unresolved Critical finding anywhere in the review.
- Whether the weakest dimensions are ones users hit on the core flow.
- Whether known gaps are cosmetic or substantive.
- Whether the product would embarrass or reassure the person shipping it.

| Band | Anchor |
|---|---|
| 90-100 | A senior designer would ship this now. No blocking or high-impact gaps on core flows. |
| 75-89 | Shippable after the listed fixes; the foundation is sound and the gaps are named. |
| 60-74 | Not yet defensible; fix the High Impact items before promoting or shipping. |
| Below 60 | Would not ship; the product likely blocks users or loses trust and needs rework before polish. |

Overall Readiness is never the mean of the other ten dimensions. A product can average in the 80s and still be a 60 here because one Critical issue on the primary flow makes the whole thing not shippable. Restating the cap: any unresolved Critical anywhere holds Overall Readiness at 74 or below until it is fixed.

The question to hold in mind is simple: would a senior designer put their name on shipping this as it stands. If the answer is no, the number belongs below 75, whatever the other rows say.
