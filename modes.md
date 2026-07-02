# Modes

The detailed operating guide for all 11 modes. Each mode names its purpose, its inputs, the reasoning procedure to follow, and the mistakes to avoid. Output structures live in [output-formats.md](./output-formats.md). Run one mode per request; if the user does not name a mode, run Mode 1 and say so. Every mode still obeys the [operating rules](./skill.md#operating-rules), the [finding format](./skill.md#the-finding-format), and the [honesty protocol](./skill.md#honesty-protocol).

## Mode 1: Quick Audit

Purpose: a fast, honest read of one screen or page with scores, top problems, and top fixes.

Use when: the user asks "is this good?" and gives a URL, screenshot, or short description.

Minimum inputs: one screen, page, or description of it.

Better with: the product's goal, the target user, and whether the view is desktop or mobile.

Process:

1. Name what the product is and who it serves in one or two lines.
2. Run the [5-second test](./skill.md#the-5-second-first-impression-test) as a first-time visitor.
3. Identify the primary task the screen should support.
4. Scan for the highest-severity issues first: broken tasks, trust breaks, exclusion.
5. Score the dimensions you can judge; mark the rest Not scored or Provisional.
6. Write the top 5 problems in the finding format, severity first.
7. Write the top 5 fixes as specific, buildable changes, then list what already works and give a one-line verdict.

Output: [Mode 1 format](./output-formats.md#mode-1-quick-audit).

Mode rules:

- Keep it to five problems and five fixes, and state the single most important fix explicitly. If everything matters, nothing is ranked.

Common mistakes:

- Listing twenty minor issues instead of the five that matter.
- Scoring dimensions the input cannot support.

## Mode 2: Full Product Design Audit

Purpose: a deep review across every design dimension, with scores, findings, and direction.

Use when: the user wants the complete breakdown, not a quick read.

Minimum inputs: one screen or page, plus the product goal.

Better with: multiple screens, the target user, mobile views, and any brand or copy context.

Process:

1. Establish product understanding: what it is, who it serves, the primary job.
2. Record assumptions with the "Assumption:" prefix.
3. Run the 5-second test.
4. Walk each dimension in order: UX, UI, hierarchy, mobile, accessibility, conversion, trust, interaction states, style fit, copy, design system.
5. Capture every problem in the finding format as you go.
6. Score all 11 dimensions, applying the cap rules from [scoring-rubric.md](./scoring-rubric.md).
7. Sort findings by severity and pull the Critical set into its own section.
8. Write the improved direction and a tool-neutral implementation brief, then the final QA checklist.

Output: [Mode 2 format](./output-formats.md#mode-2-full-product-design-audit).

Mode rules:

- Every dimension gets a verdict, even if it is "Not scored, insufficient input".
- The Critical Problems section repeats critical findings so they cannot be missed.
- Include "What already works" inside the executive summary or as its own note.

Common mistakes:

- Reviewing UI polish while skipping accessibility or mobile.
- Writing findings without the "Why it matters" line, which strips the ranking of meaning.

## Mode 3: Redesign Direction

Purpose: a better design direction for an existing screen or a product idea.

Use when: the user says "rebuild this", "how should this look instead", or describes an idea to design.

Minimum inputs: the current screen or a clear description of the product idea.

Better with: the goal, the target user, constraints, and any existing brand.

Process:

1. Restate the product goal and the target user in plain terms.
2. Define the UX strategy: the primary task and the shortest path to it.
3. Lay out the page or screen structure and section order.
4. Choose components for the job and cut the ones that do not serve it.
5. Select a UI style using the logic in [modern-ui-styles.md](./modern-ui-styles.md), and justify it.
6. Specify interaction states, mobile behavior, and accessibility requirements.
7. Draft the key copy: headline, subhead, primary CTA.
8. Produce a tool-neutral implementation brief and a QA checklist.

Output: [Mode 3 format](./output-formats.md#mode-3-redesign-direction).

Mode rules:

- Redesign the structure and reasoning, not just the paint. Justify why the new order beats the old one.
- Name what you are removing and why, not only what you are adding.

Common mistakes:

- Proposing a trend-driven look before defining the task.
- Redesigning without stating what problem in the original it solves.

## Mode 4: Conversion Upgrade

Purpose: improve leads, sales, trust, and CTA clarity using ethical methods only.

Use when: the user wants more signups or sales without manipulation.

Minimum inputs: the page and its intended offer or primary action.

Better with: the audience, the price, the competition, and known objections.

Process:

1. Identify the single primary action the page should drive. If there are two, pick the one that matters most.
2. Walk the page as a skeptical first-time visitor, top to bottom.
3. List the objections a real buyer would raise at each step.
4. Map each objection to the section that should answer it, and flag the ones nothing answers.
5. Build a friction map: every point where effort, doubt, or confusion slows the decision.
6. Rewrite the offer and CTA copy for clarity and honesty.
7. Identify trust gaps and propose honest proof to fill them.
8. Prioritize the fixes and describe what to watch after changes, never a predicted number.

Output: [Mode 4 format](./output-formats.md#mode-4-conversion-upgrade).

Mode rules:

- Ethical methods only. Refuse fake urgency, fake scarcity, and invented proof, and offer the honest alternative.
- Never predict a conversion lift. Describe what to observe instead.

Common mistakes:

- Adding a countdown or "only 2 left" without a real basis.
- Optimizing button color while the offer itself is unclear.

## Mode 5: Mobile UX Fix

Purpose: fix mobile layout, readability, tap targets, navigation, forms, and scroll flow.

Use when: the user complains about phone behavior specifically.

Minimum inputs: a mobile view or a description of the mobile experience.

Better with: the target devices, the breakpoints, and the primary mobile task.

Process:

1. State the devices and breakpoints assumed, and label them as assumptions if not given.
2. Identify the primary mobile task and whether it is reachable with one thumb.
3. Check readability: body text at 16px minimum, line length, and contrast.
4. Check touch targets against the 44px practical minimum, 24px absolute floor.
5. Review navigation, sticky actions, and whether the primary action stays in reach.
6. Review forms: input size, keyboard type, labels, and error placement.
7. Review section order and scroll flow for the small screen.
8. Prioritize the fixes by severity.

Output: [Mode 5 format](./output-formats.md#mode-5-mobile-ux-fix).

Mode rules:

- Never comment on desktop. This mode is mobile only.
- Treat a tap target under 44px that carries a primary action as at least High Impact.

Common mistakes:

- Shrinking desktop layout instead of rethinking order for the thumb.
- Ignoring the keyboard type on inputs, which slows every mobile form.

## Mode 6: Accessibility Review

Purpose: surface accessibility risks and practical fixes through a heuristic review.

Use when: the user asks about accessibility, keyboard use, or screen readers.

Minimum inputs: a screen, page, or component description.

Better with: markup or code context, and the intended interaction states.

Process:

1. State the scope and method, and that this is heuristic, not certification.
2. Check contrast against 4.5:1 for body text and 3:1 for large text and UI components.
3. Check that every interactive element is reachable and operable by keyboard, with a visible focus state.
4. Check text alternatives, labels, headings, and reading order.
5. Check target size, spacing, that color is not the only signal, and motion against prefers-reduced-motion.
6. Separate quick wins from structural fixes.
7. Hand off the manual test checklist: full keyboard pass, screen reader pass, 200 percent zoom.

Output: [Mode 6 format](./output-formats.md#mode-6-accessibility-review).

Mode rules:

- Never claim conformance or certification. This is a heuristic pass.
- Always recommend the three manual tests, because automated and visual checks miss real barriers.

Common mistakes:

- Reporting contrast only and calling accessibility handled.
- Treating a missing focus state as Polish when it blocks keyboard users.

## Mode 7: Design System Builder

Purpose: define tokens, components, states, and rules that keep a product consistent.

Use when: the user wants reusable foundations, not a one-off screen.

Minimum inputs: the product context and a sense of the components in use.

Better with: existing brand colors, type, a component list, and platform constraints.

Process:

1. Capture product context and constraints, including platform and brand.
2. Define tokens: color, type scale, spacing on a 4 or 8px scale, radius, elevation.
3. List core components and the states each must ship: default, hover, focus, active, loading, empty, error, success, disabled.
4. Set layout and responsive rules, including breakpoints and grid.
5. Set accessibility defaults so every component starts compliant.
6. Define naming and usage rules, including when not to use a component.
7. Order adoption so the highest-leverage tokens and components land first.

Output: [Mode 7 format](./output-formats.md#mode-7-design-system-builder).

Mode rules:

- Accessibility defaults are part of the system, not an afterthought bolted on later.
- Every component definition lists its required states, per [interaction-states-checklist.md](./interaction-states-checklist.md).

Common mistakes:

- Shipping color and type tokens but leaving component states undefined.
- Naming tokens by their value, such as "blue", instead of their role, such as "action".

## Mode 8: UX Copy Improvement

Purpose: improve headlines, CTAs, labels, helper text, errors, empty states, and onboarding text.

Use when: the user wants better words, not a layout change.

Minimum inputs: the current copy and where it appears.

Better with: the audience, the brand voice, and the task each string supports.

Process:

1. Establish the voice and audience, labeling assumptions if not given.
2. For each string, judge whether it states the value or the next action clearly.
3. Rewrite in a table: location, current, improved, and why.
4. Cut words that do not help the user decide or act.
5. Set microcopy rules specific to this product, not generic tips.
6. Provide a complete text set for error, empty, loading, and success states.

Output: [Mode 8 format](./output-formats.md#mode-8-ux-copy-improvement).

Mode rules:

- Every rewrite includes a "why", so the change is a decision, not a preference.
- Error text names the cause and the fix, never just "something went wrong".

Common mistakes:

- Making copy shorter but vaguer, losing the information the user needed.
- Rewriting the headline while leaving broken button and error text untouched.

## Mode 9: Modern UI Style Selector

Purpose: pick a UI style that fits the product, audience, trust needs, accessibility, and performance.

Use when: the user asks which visual style to use.

Minimum inputs: what the product is and who it is for.

Better with: the trust level required, performance constraints, and any brand.

Process:

1. Establish product context and the primary job.
2. Judge the audience and the trust level the product must project.
3. Recommend one style, drawing trade-offs from [modern-ui-styles.md](./modern-ui-styles.md).
4. Name the styles to avoid for this product, each with a reason.
5. Explain why the chosen style fits the audience, trust, and job.
6. Call out accessibility risks in the style and how to control them.
7. Call out performance risks and how to control them.
8. Give component, color, type, motion, and mobile direction, plus tool-neutral notes.

Output: [Mode 9 format](./output-formats.md#mode-9-modern-ui-style-selector).

Mode rules:

- Always name the styles to avoid, with reasons. A recommendation without exclusions is half an answer.
- Flag any style whose default look risks contrast or motion problems.

Common mistakes:

- Choosing a style for its screenshots rather than the product's trust needs.
- Recommending heavy motion or transparency for a product that needs speed and clarity.

## Mode 10: Universal Implementation Brief

Purpose: convert design strategy into a tool-neutral brief a developer or build agent can execute.

Use when: the user is handing a build request to a coding agent or engineer.

Minimum inputs: the design direction or an audit to build from.

Better with: confirmed tokens, content, and target platforms.

Process:

1. State the project goal, target user, and the goal of the specific screen or page.
2. Name the design style and the reason for it.
3. Define the information architecture and the section order.
4. Specify component requirements and required states.
5. Define design tokens: color, type, spacing, radius, elevation.
6. Define content requirements and responsive rules.
7. Set accessibility requirements and performance considerations.
8. Write the QA checklist and acceptance criteria the build must pass.

Output: [Mode 10 format](./output-formats.md#mode-10-universal-implementation-brief). A blank version lives in [implementation-brief-template.md](./implementation-brief-template.md).

Mode rules:

- Stay tool-neutral. Name tools only as interchangeable examples in a list of three or more.
- Acceptance criteria must be checkable, so a builder knows when the work is done.

Common mistakes:

- Writing goals but no acceptance criteria, leaving "done" undefined.
- Requiring a specific framework or tool the team may not use.

## Mode 11: Final QA

Purpose: decide whether a design is ready to show a client, ship, or publish.

Use when: the user asks "is this ready?"

Minimum inputs: the near-final screen or page.

Better with: the target platforms, the states, and any prior audit.

Process:

1. Review the primary task end to end for blockers.
2. Run the highest-severity checks: broken tasks, trust breaks, exclusion, missing states.
3. Confirm accessibility basics: contrast, keyboard reach, focus, target size.
4. Confirm mobile behavior and required interaction states.
5. Record checklist results honestly, including anything not verified.
6. List remaining risks and the order to fix them.
7. Give exactly one verdict.

Output: [Mode 11 format](./output-formats.md#mode-11-final-qa).

Mode rules:

- The verdict must be exactly one of: Ready to ship, Ready after listed fixes, or Not ready.
- Any unresolved Critical issue means the verdict cannot be "Ready to ship".

Common mistakes:

- Softening the verdict to avoid disappointing the user.
- Passing a design without checking the states that only appear during use.
