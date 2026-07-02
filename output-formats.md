# Output Formats

The canonical output structure for all 11 modes. Each mode below lists its exact sections in order, with a short note on what belongs in each. Modes and their reasoning procedures live in [modes.md](./modes.md).

## General Output Rules

- These formats are defaults. Keep the section names and their order.
- Put the verdict and scores early, never buried at the end.
- Order findings by severity, Critical first, using the [finding format](./skill.md#the-finding-format).
- Keep assumptions visible, each prefixed with "Assumption:".
- Include "What already works" in every audit mode, to guard against overdesign.
- Give no vague advice. Every fix names an element, an observable problem, and a specific change.
- Mark anything the input cannot support as Provisional or Not scored, never guessed.
- Close with next actions in priority order.

## How To Read These Formats

Each mode lists numbered sections. Use those exact names and that order so output stays predictable across reviews and easy to compare over time. When a section does not apply, keep the heading and write one honest line explaining why, for example "No trust gaps found on this screen" or "Not scored, the input did not include mobile". Do not silently drop a section, because a missing heading reads as an oversight rather than a decision.

Findings, wherever they appear, render in the [finding format](./skill.md#the-finding-format). A single finding looks like this:

- Where: the pricing section, Free and Pro cards.
- What: both cards use a filled button in the same color, so neither reads as the recommended choice.
- Why it matters: the visitor has to read all four cards to find the intended path, which slows the decision and lowers signups.
- Fix: keep the filled button on Pro only, switch Free to an outline button, and add one line under the Pro price naming who it is for.
- Severity: High Impact.
- Confidence: Observed.

Scores render as a short table so they scan in one pass:

| Dimension | Score | Note |
| --- | --- | --- |
| UX | 71 | Capped at 74 by a Critical navigation issue |
| Accessibility | Provisional | Only one state was visible |
| Mobile | Not scored | No mobile view provided |

The cap rules are easy to misapply, so make them visible in the notes column. Two worked cases:

- A dimension with a Critical issue cannot score above 74, even if everything else in that dimension is strong. If UI would otherwise be an 88 but a Critical contrast failure excludes users, it is capped at 74, and the note says why. Do not average the cap away.
- Any unresolved Critical issue anywhere caps Overall Readiness at 74. A product can have four dimensions in the 80s and still be capped at 74 overall while one Critical remains open. Once that Critical is fixed, the cap lifts.

Never write a decimal. A 62 and a 74 carry different meaning; a 62.5 carries none, because these are expert judgments, not measurements. When you have partial signal, write Provisional and name what you saw. When you have none, write Not scored and name what was missing.

## Mode 1: Quick Audit

1. What I Reviewed: the exact input and its limits, for example "one desktop screenshot, no flow".
2. 5-Second First Impression: the five canonical questions answered as a first-time visitor.
3. Scores: the dimensions you can judge, whole numbers, with Not scored where input is thin.
4. Top 5 Problems: the five highest-severity issues in the finding format.
5. Top 5 Fixes: five specific, buildable changes, ordered by impact.
6. What Already Works: the elements to keep, so they are not lost in a redesign.
7. Verdict: one or two lines naming the single most important fix.

## Fixed Formats

Four formats are fixed. Their section names and numbering do not change, because they are the contract other people and tools rely on: Mode 2 Full Product Design Audit, Mode 3 Redesign Direction, Mode 9 Modern UI Style Selector, and Mode 10 Universal Implementation Brief. You may leave a section brief or mark it Not scored, but keep the heading and its number in place.

## Mode 2: Full Product Design Audit

The section order runs from context to dimensions to direction to build: understand the product and state assumptions first, run the dimension reviews in the middle, then turn the findings into an improved direction, an implementation brief, and a QA checklist. Read top to bottom, it walks a stakeholder from what the product is to what to build next.

1. Product Understanding: what it is, who it serves, and the primary job.
2. Assumptions: every assumption made, each prefixed with "Assumption:".
3. 5-Second First Impression: the five canonical questions as a first-time visitor.
4. Scores: all 11 dimensions as whole numbers, with cap rules applied and Not scored where needed.
5. Executive Summary: the three or four things that matter most, in plain language.
6. Critical Problems: every Critical finding, repeated here so it cannot be missed.
7. UX Review: task flow, clarity, and the path to the primary action.
8. UI Review: spacing, alignment, type, color, and consistency.
9. Visual Hierarchy Review: whether the eye hits the right thing first, second, third.
10. Mobile Review: layout, readability, touch targets, and navigation on the small screen.
11. Accessibility Review: heuristic contrast, keyboard, focus, labels, and motion checks.
12. Conversion Review: offer clarity, friction, and honest trust signals.
13. Trust and Credibility Review: proof, transparency, and anything that raises doubt.
14. Interaction States Review: default, hover, focus, active, loading, empty, error, success, disabled.
15. Modern UI Style Fit: whether the current style suits the product and audience.
16. Copy Improvements: the highest-value rewrites, with a reason each.
17. Design System Recommendations: tokens, components, and rules to stabilize the product.
18. Improved Design Direction: the better direction in structure and reasoning, not just paint.
19. Universal AI Agent Implementation Brief: a tool-neutral brief a builder can execute.
20. Final QA Checklist: the checks to pass before this is ready to ship or publish.

## Mode 3: Redesign Direction

This format moves from strategy to structure to build, and it ends with a brief a developer can act on. State what the new direction fixes in the original, and name what you are removing, not only what you are adding.

1. Product Goal: the one outcome the redesign must serve.
2. Target User: who arrives and what they need to decide.
3. UX Strategy: the primary task and the shortest honest path to it.
4. Page or Screen Structure: the sections and their order, with a reason for the order.
5. Visual Design Direction: the look in concrete terms, tied to the product.
6. Modern UI Style Recommendation: the chosen style and why it fits, per [modern-ui-styles.md](./modern-ui-styles.md).
7. Design System Foundation: the tokens and rules the redesign rests on.
8. Component List: the components needed, and what is removed from the original.
9. Interaction States: the required states for each interactive element.
10. Mobile Behavior: how the structure and order adapt to the small screen.
11. Accessibility Requirements: contrast, keyboard, focus, target size, and motion rules.
12. Suggested Copy: headline, subhead, and primary CTA at minimum.
13. Universal AI Agent Implementation Brief: the tool-neutral build brief.
14. QA Checklist: the checks the redesign must pass before it ships.

## Mode 4: Conversion Upgrade

1. Offer and Primary Action: the single action the page should drive, stated plainly.
2. What I Reviewed and Assumptions: the input, its limits, and any labeled assumptions.
3. Friction Map: every point of effort, doubt, or confusion, in reading order.
4. Findings: conversion problems in the finding format, severity first, ethical framing only.
5. Copy Rewrites: offer and CTA copy improved for clarity and honesty, with reasons.
6. Trust Gaps: the objections nothing on the page answers, and the honest proof to fill them.
7. Prioritized Fix List: the fixes in order of impact and effort.
8. What to Watch After Changes: the behavior to observe after shipping, never a predicted number.

## Mode 5: Mobile UX Fix

1. Devices and Breakpoints Assumed: the assumed devices and breakpoints, labeled if not given.
2. What I Reviewed and Limits: the input and what it cannot show.
3. Mobile Findings: problems in the finding format, severity first, mobile only.
4. Layout and Section Order Changes: how the order should change for the thumb and small screen.
5. Readability and Touch Target Fixes: 16px minimum text, line length, and 44px targets.
6. Navigation and Sticky Action Guidance: reachability of the primary action and menu behavior.
7. Prioritized Fix List: the fixes in order of impact.

## Mode 6: Accessibility Review

1. Scope and Method: what was checked, and that this is a heuristic pass, not certification.
2. Findings: accessibility problems in the finding format, severity first.
3. Quick Wins: fixes that are fast and low-risk, such as contrast and label corrections.
4. Structural Fixes: deeper fixes to markup, focus order, or component behavior.
5. Manual Test Checklist: the full keyboard pass, screen reader pass, and 200 percent zoom to run.

## Mode 7: Design System Builder

The output is a foundation others build on, so it favors rules and defaults over one-off decisions. Name tokens by role, not value, and treat accessibility as a default rather than a later pass.

1. Product Context and Constraints: platform, brand, and any hard limits.
2. Design Tokens: color, type scale, spacing on a 4 or 8px scale, radius, and elevation.
3. Core Components and Required States: each component and the states it must ship.
4. Layout and Responsive Rules: breakpoints, grid, and spacing behavior.
5. Accessibility Defaults: the compliant defaults every component starts with.
6. Naming and Usage Rules: role-based names and when not to use a component.
7. Adoption Order: the sequence to roll out, highest leverage first.

## Mode 8: UX Copy Improvement

The rewrites table is the heart of this mode. Every row carries a reason, so each change reads as a decision rather than a preference, and the state text set closes the gaps that copy reviews usually skip.

1. Voice and Audience: the tone and reader, with assumptions labeled.
2. Rewrites: a table with columns Location, Current, Improved, and Why.
3. Microcopy Rules for This Product: specific rules for this product, not generic tips.
4. Error Empty Loading and Success Text Set: a complete set of state text, each naming cause and next action where relevant.

## Mode 9: Modern UI Style Selector

The recommendation is incomplete without the exclusions and the risks. Always fill Styles to Avoid with reasons, and always name the accessibility and performance costs of the chosen style, since every style carries some.

1. Product Context: what the product is and its primary job.
2. Audience and Trust Level: who it serves and how much trust it must project.
3. Recommended Style: the single chosen style, named clearly.
4. Styles to Avoid: the styles to skip for this product, each with a reason.
5. Why This Style Fits: the fit against audience, trust, and job.
6. Accessibility Risks: the style's risks and how to control them.
7. Performance Risks: the style's cost and how to control it.
8. Component Usage: how core components should look and behave in this style.
9. Color and Typography Direction: palette role and type direction, tied to legibility.
10. Motion and Interaction Direction: motion scope, respecting prefers-reduced-motion.
11. Mobile Rules: how the style holds up on the small screen.
12. Tool-Neutral Implementation Notes: build notes with no required tool.

## Mode 10: Universal Implementation Brief

1. Project Goal: the outcome the build serves.
2. Target User: who uses it and what they need.
3. Screen or Page Goal: the specific job of this view.
4. Design Style: the style and the reason for it.
5. Information Architecture: the content structure and grouping.
6. Section Order: the order of sections, top to bottom.
7. Component Requirements: the components and their behavior.
8. Design Tokens: color, type, spacing, radius, and elevation values.
9. Content Requirements: the copy and assets the build needs.
10. Interaction States: the required states for each interactive element.
11. Responsive Rules: breakpoints and how layout adapts.
12. Accessibility Requirements: contrast, keyboard, focus, target size, and motion rules.
13. Performance Considerations: weight, loading, and anything that risks speed.
14. QA Checklist: the checks the build must pass.
15. Acceptance Criteria: the checkable conditions that define done.

## Mode 11: Final QA

1. Verdict: exactly one of Ready to ship, Ready after listed fixes, or Not ready.
2. Blocking Issues: the Critical issues that gate the verdict, in the finding format.
3. Checklist Results: honest pass, fail, or not verified for each check.
4. Remaining Risks: the risks that remain even if the verdict is positive.
5. Suggested Order of Fixes: the order to resolve what is left, highest severity first.

## Filled Section Examples

Short skeletons showing the shape of a real response. They are illustrations of structure, not templates to copy verbatim, and they use no real product names or invented data.

Mode 11 verdict, written honestly:

> 1. Verdict: Ready after listed fixes.
> 2. Blocking Issues: one Critical. The primary button has no visible focus state, so keyboard users cannot see where they are. Fix before ship.
> 3. Checklist Results: contrast pass; keyboard reach fail; touch targets pass; error states not verified, no error view was provided.
> 4. Remaining Risks: the empty state for the results list was never shown, so first-run experience is unverified.
> 5. Suggested Order of Fixes: add the focus state, then supply and check the error and empty states.

Mode 9 exclusions, written with reasons:

> 4. Styles to Avoid: a heavily transparent, layered look, because the product shows dense financial tables where translucency lowers text contrast below 4.5:1. A motion-first style, because the audience opens this on older phones where heavy animation stutters and delays the primary task.

Mode 4 honest closing, with no predicted numbers:

> 8. What to Watch After Changes: whether visitors reach the signup form without scrolling back up, whether the new comparison line reduces time spent on the pricing section, and whether support questions about the plan difference drop. Watch these over a normal traffic period. Do not expect a specific lift; measure the actual change.

Mode 10 acceptance criteria, written as checkable conditions:

> 15. Acceptance Criteria:
> - [ ] Body text renders at 16px or larger on a 360px wide screen.
> - [ ] Every interactive element has a visible focus state and is reachable by keyboard.
> - [ ] Primary and secondary buttons each show default, hover, focus, active, and disabled states.
> - [ ] Text meets 4.5:1 contrast, and large text and UI components meet 3:1.
> - [ ] The page keeps its section order at every defined breakpoint.

A full Mode 1 response, end to end, so the whole shape is visible at once:

> 1. What I Reviewed: one desktop screenshot of a signup page. I cannot see hover, focus, loading, or error states, or the mobile view, so Interaction Design and Mobile are limited.
> 2. 5-Second First Impression: What is this? A tool for sending invoices. Who is it for? Unclear, the copy does not name the audience. What can I do here? Start a trial. What pulls my eye first? A large stock photo, not the form, which is the wrong target. Do I trust it? Partly, there is no proof near the action.
> 3. Scores: UX 68, UI 74, Visual Hierarchy 61, Trust and Credibility 60, Conversion 62. Mobile Not scored, no mobile view. Interaction Design Provisional, one state only.
> 4. Top 5 Problems: rendered in the finding format, Critical and High Impact first.
> 5. Top 5 Fixes: five specific changes, starting with the one that matters most.
> 6. What Already Works: the form asks for only an email and a password, which lowers effort. Spacing is consistent.
> 7. Verdict: usable but the hierarchy buries the primary task. The single most important fix is to demote the stock photo and make the form the first thing the eye meets.

A full Mode 8 rewrites table, showing the required columns:

| Location | Current | Improved | Why |
| --- | --- | --- | --- |
| Primary button | Submit | Start free trial | Names what happens next, not the mechanism |
| Empty state | No data | No invoices yet. Create your first one to get started. | States the situation and the next action |
| Error | Something went wrong | We could not save that. Check your connection and try again. | Names a likely cause and a concrete fix |
| Helper text | Enter details | Use the email where you want payment reminders sent | Tells the user why the field matters |

A Mode 4 friction map, written as observable friction points in reading order:

> 3. Friction Map:
> - The headline names a feature, not an outcome, so the visitor works to figure out the value.
> - The price is three scrolls down, so a cost-conscious buyer stalls before finding it.
> - The form asks for a company size that the trial does not need, adding an unnecessary field.
> - There is no proof near the button, so the final doubt goes unanswered at the moment of decision.

A Mode 6 accessibility pass, showing scope honesty and the split between quick and structural fixes:

> 1. Scope and Method: a heuristic review of one screen from markup and a screenshot. Not a certification. Confirm with the manual tests below.
> 2. Findings: rendered in the finding format, severity first. Critical: the icon-only close button has no accessible name. High Impact: the focus state is removed globally.
> 3. Quick Wins: add a text label to the close button; restore a visible focus ring; raise the helper text from about 3:1 to at least 4.5:1.
> 4. Structural Fixes: the modal does not trap or return focus, so keyboard users get lost. Rework the focus management.
> 5. Manual Test Checklist: run a full keyboard-only pass, a screen reader pass, and a 200 percent zoom pass before relying on these results.

A Mode 5 mobile fix, showing the mobile-only discipline and named numbers:

> 1. Devices and Breakpoints Assumed: Assumption: a 360px to 430px wide phone in portrait, since no device was named.
> 3. Mobile Findings: High Impact. The primary button sits at the top of a long page, so after scrolling the visitor loses it. Add a sticky bottom action bar. High Impact. Body text is around 13px, below the 16px mobile minimum, which forces zooming.
> 4. Layout and Section Order Changes: move the price above the feature list, because on a small screen the buyer decides on cost before reading features.
> 5. Readability and Touch Target Fixes: raise body text to 16px, and enlarge the icon buttons from about 32px to at least 44px.
> 6. Navigation and Sticky Action Guidance: keep the primary action reachable with one thumb at the bottom edge; collapse the top menu into a single clear control.

A Mode 10 brief skeleton, tool-neutral and buildable:

> 1. Project Goal: turn cold visitors into trial signups for an invoicing tool.
> 3. Screen or Page Goal: the signup page. Primary action is completing the trial form.
> 4. Design Style: a plain, trust-forward style with strong contrast, chosen because the product handles money.
> 6. Section Order: value headline, short form, one proof point, plan summary, footer.
> 8. Design Tokens: an action color for the single primary button, neutral grays for surfaces, a type scale with 16px base, spacing on an 8px scale.
> 10. Interaction States: the primary button ships default, hover, focus, active, loading, and disabled; the form ships inline error and success.
> 15. Acceptance Criteria: the checkable list a builder signs off against, as shown above.

## Length And Fit Guidance

Match output length to the input and the mode. A single screenshot does not justify a twenty-section audit padded with guesses; run Mode 1 and keep it tight. A full product with several screens and a stated goal earns Mode 2. When a mode's format has a section the input cannot support, keep the heading and write one honest line rather than inventing content to fill it.

Long output is not thorough output; ranked, specific, honest output is. A reader should be able to act on your review without asking a single follow-up question, and that is the standard every format here serves.
