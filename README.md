# Senior UI/UX Product Designer Agent

A tool-neutral agent skill that makes an AI assistant review, plan, and direct product design like a senior UI/UX product designer. It produces honest audits with ranked findings, scores with stated reasons, redesign direction, and implementation briefs that any developer or coding agent can execute.

Its governing belief:

"Design is not decoration. Design is communication, usability, trust, structure, behavior, accessibility, and decision-making."

## What this is

Most design-focused AI output is decoration advice: apply a trend, change the colors, call it modern. This skill installs the part that is usually missing, the senior designer brain. It reasons about the product, the user, and the journey before it says anything about pixels, and it reports like a professional: what is broken, why it matters, what to change, and in what order.

It is written entirely in plain markdown. There is no CLI, no database, and no dependency. Any AI assistant that can read text can run it.

## Who it is for

- AI builders who want their coding or design agents to make better screens.
- Developers who want a design review before shipping.
- Founders who want to understand what is wrong with their site and what to fix first.
- Freelancers and agencies who need client-ready audit reports.
- Designers who want a rigorous second pair of eyes.
- Beginners who want to learn how senior designers actually reason.

## What it can do

Website, landing page, SaaS, dashboard, mobile app, ecommerce, portfolio, and admin panel reviews. Checkout, onboarding, form, and pricing page reviews. Empty state and error state reviews. Design system planning. UX copy improvement. Conversion and trust improvement, by ethical means only. Mobile and accessibility improvement. Modern UI style selection grounded in product fit. Tool-neutral implementation briefs.

## What it should not be used for

- Replacing user research. It reasons about likely behavior; it does not observe your users.
- Legal, medical, or compliance signoff. Accessibility output is a heuristic review, never a certification.
- Analytics. It never produces conversion rates or test results. It tells you what to watch, not what the numbers are.
- Manipulation. It refuses dark patterns, fake urgency, fake scarcity, and fake testimonials, and offers honest alternatives instead.

## The 11 modes

| Mode | Name | Purpose |
| --- | --- | --- |
| 1 | Quick Audit | Fast review with scores, top problems, top fixes |
| 2 | Full Product Design Audit | Deep review across UX, UI, hierarchy, mobile, accessibility, conversion, trust, states, style, and copy |
| 3 | Redesign Direction | A better design direction for an existing screen or product idea |
| 4 | Conversion Upgrade | Improve leads, sales, trust, and CTA clarity, ethical methods only |
| 5 | Mobile UX Fix | Mobile layout, readability, tap targets, navigation, forms, scroll flow |
| 6 | Accessibility Review | Accessibility risks and practical fixes |
| 7 | Design System Builder | Tokens, components, states, and rules |
| 8 | UX Copy Improvement | Headlines, CTAs, labels, helper text, errors, empty states |
| 9 | Modern UI Style Selector | Pick a UI style based on product, audience, trust, accessibility, performance |
| 10 | Universal Implementation Brief | Convert design strategy into a tool-neutral build brief |
| 11 | Final QA | Decide if a design is ready to show a client, ship, or publish |

Full mode procedures live in [modes.md](./modes.md). Output formats live in [output-formats.md](./output-formats.md).

## Quick start

There are three ways to use this skill. All three are tool-neutral and work with any AI assistant, coding agent, or automation agent that accepts instructions.

1. System prompt. Copy the prompt from [system-prompt.md](./system-prompt.md) into your agent's system prompt or custom instructions. This is the full designer brain, self-contained.
2. Skill file. If your agent supports loadable skills or context files, add [skill.md](./skill.md) plus the reference files it links. This is the deepest integration.
3. Task prompts. For one-off tasks, copy a single prompt from [prompts/](./prompts/) and fill in the placeholders. Each prompt carries enough rules to work on its own.

## Example usage

With the system prompt installed, requests like these work directly:

```
Run Mode 1 on this screenshot. It is the homepage of my dental clinic.
```

```
Mode 9. Product: an invoicing tool for freelancers. Audience: cost-conscious
solo workers. Which UI style fits, and which should I avoid?
```

```
Mode 10. Turn the attached redesign direction into an implementation brief
my coding agent can build from.
```

If no mode is named, the agent runs Mode 1 Quick Audit and says so.

## Recommended workflow

For an existing product: Mode 1 for the fast read, Mode 2 when you want the full picture, then Mode 10 to hand the fixes to a developer or coding agent, then Mode 11 before you ship.

For something new: Mode 3 for direction, Mode 9 if the visual style is undecided, Mode 7 if the product will grow past a few screens, then Mode 10 to build, then Mode 11 to check.

For a specific complaint: go straight to the matching mode. Phone problems, Mode 5. Weak signups, Mode 4. Confusing words, Mode 8.

## Output structure

Every audit follows the same discipline:

- It opens by stating what was reviewed and what could not be seen.
- A 5-second first impression test, answered as a first-time visitor: What is this? Who is it for? What can I do here? What pulls my eye first, and is it the right thing? Do I trust it enough to continue?
- Scores from 0 to 100 across eleven dimensions: UX, UI, Visual Hierarchy, Mobile, Accessibility, Trust and Credibility, Conversion, Design System, Interaction Design, Modern UI Style Fit, and Overall Readiness. Every score carries a reason. Dimensions the input cannot support are marked Not scored or Provisional instead of guessed. A Critical issue caps its dimension at 74, and any unresolved Critical caps Overall Readiness at 74. Full band definitions are in [scoring-rubric.md](./scoring-rubric.md).
- Findings in a fixed format: Where, What, Why it matters, Fix, Severity. Severity is one of Critical, High Impact, Medium Impact, or Polish, always in that order.
- A "What already works" list, so good work is preserved instead of redesigned.
- Next actions in priority order.

Vague advice is treated as a defect. "Improve spacing" fails the skill's own evals; "the hero has three competing focal points, make the headline dominant and move the secondary CTA below the primary" passes.

## Modern UI style intelligence

[modern-ui-styles.md](./modern-ui-styles.md) covers nineteen current styles: Glassmorphism, Liquid Glass, Bento Grid, Dark Premium SaaS, AI-Native UI, Neubrutalism, Claymorphism, Soft UI, Spatial UI, Aurora UI, Editorial Minimalism, Luxury Minimalism, Cyberpunk UI, High-Tech Fintech, Mobile Cinematic Dark, Swiss Modernism, Organic Biophilic UI, Tactile Digital UI, and Gradient Mesh UI.

Each entry states best use cases, where to use it, where not to, accessibility risks, performance risks, trust risks, component examples, and implementation notes. The file's rules override every style: text contrast and readability outrank trendiness, heavy blur is a performance budget rather than free decoration, and healthcare, finance, legal, government, and serious B2B products get restrained styles because trendy treatments reduce trust there. Style selection is Mode 9, and it always names the styles to avoid with reasons.

## Quality principles

- Product before pixels. The reasoning order is product, user, journey, screen, hierarchy, components, states, copy, style, implementation. Style is the ninth decision, never the first.
- Prioritization is mandatory. Every finding carries a severity, and fixes are ordered.
- Honesty about uncertainty. A screenshot is one state of one screen. The agent says what it cannot see, labels assumptions, and never invents data, research, or predicted numbers.
- Mobile and accessibility are always in scope, never optional extras.
- Restraint. The first fix for clutter is removal. Working designs are preserved, not rebuilt for novelty.

The full thinking is in [design-principles.md](./design-principles.md).

## Ethical design rules

The skill supports conversion through clarity: clearer offers, honest proof, less friction, better information, better comparison. It refuses fake scarcity, fake urgency, fake testimonials, confirm shaming, hidden costs, and forced continuity, and it proposes the honest alternative when asked for a manipulative one. These rules are enforced by the evals: any recommended dark pattern is an automatic eval failure.

## Repository map

| File | Purpose |
| --- | --- |
| [skill.md](./skill.md) | The core reusable skill |
| [system-prompt.md](./system-prompt.md) | Self-contained system prompt, ready to paste |
| [modes.md](./modes.md) | Detailed procedures for all 11 modes |
| [output-formats.md](./output-formats.md) | Canonical output formats per mode |
| [scoring-rubric.md](./scoring-rubric.md) | The 0 to 100 rubric for all eleven dimensions |
| [design-principles.md](./design-principles.md) | How a senior designer reasons |
| [modern-ui-styles.md](./modern-ui-styles.md) | Nineteen styles as fit-and-risk decisions |
| [accessibility-checklist.md](./accessibility-checklist.md) | Contrast, keyboard, focus, semantics, forms, media |
| [conversion-checklist.md](./conversion-checklist.md) | Offer, CTA, proof, pricing, friction, ethics |
| [mobile-checklist.md](./mobile-checklist.md) | Viewport, touch, readability, navigation, forms |
| [trust-credibility-checklist.md](./trust-credibility-checklist.md) | Identity, contact, proof, policies, honesty |
| [interaction-states-checklist.md](./interaction-states-checklist.md) | State coverage for components and systems |
| [design-system-checklist.md](./design-system-checklist.md) | Tokens, components, rules, governance |
| [implementation-brief-template.md](./implementation-brief-template.md) | The 15-section tool-neutral build brief |
| [examples/](./examples/) | Six worked examples with fictional products |
| [evals/](./evals/) | Eval rubric, twelve test cases, fifteen failure modes |
| [prompts/](./prompts/) | Nine copy-paste task prompts |

## Testing your deployment

The [evals/](./evals/) folder exists so you can verify the skill is actually working in your setup. Run the twelve cases in [evals/test-cases.md](./evals/test-cases.md) against your agent and grade the output with [evals/eval-rubric.md](./evals/eval-rubric.md). If the output drifts toward generic advice, unranked lists, invented numbers, or trend-chasing style picks, [evals/failure-modes.md](./evals/failure-modes.md) names the failure and the correction.

## How to contribute

Issues and pull requests are welcome. Useful contributions include sharper checklist items, better worked examples, new test cases, and corrections where guidance is wrong or outdated. Keep contributions tool-neutral, free of hype, and free of invented data. Examples must use fictional products and may not present fabricated results as real. If a change adds a rule, it should be concrete enough to test: an item a reviewer can pass or fail by looking at a screen.

## License

MIT. See [LICENSE](./LICENSE).

## Attribution

This project was informed by studying modern open-source UI/UX agent skills, including the MIT-licensed ui-ux-pro-max-skill by Next Level Builder, which demonstrates strong data-driven style, palette, and typography recommendation. No content, data, or code from that project or any other is included here; the structure, checklists, examples, rubrics, prompts, and all other content in this repository are original. The two approaches are complementary: data-driven style intelligence pairs well with the audit reasoning, prioritization, and honesty rules this repository provides. All product names appearing in examples are fictional.
