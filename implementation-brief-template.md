# Implementation Brief Template

The reusable template behind Mode 10 Universal Implementation Brief. It converts design strategy into a brief any coding agent, design agent, or developer can execute without seeing the original conversation.

The standard to hold: if a competent builder cannot start work from this brief alone, the brief is incomplete. Fill every section, or mark it "Not applicable" with a reason.

## How to fill it in

- Use concrete values, not adjectives. "16px, weight 600, color token text-primary", not "nice bold heading".
- Every component lists its states. A component without states is half specified.
- Every requirement is testable. If a QA person cannot check it pass or fail, rewrite it until they can.
- Keep it tool-neutral. Name a stack only if the project already requires one; otherwise describe outcomes, not products.

## 1 Project Goal

State what the project is and the single outcome it must achieve.

```
Project: [name]
Goal: [one sentence: what success looks like for this work]
Scope: [what is in, what is explicitly out]
```

## 2 Target User

Describe who will use this and what they already know, because "clear" always means clear to someone.

```
Primary user: [who they are]
Context of use: [device, setting, urgency, expertise]
What they know coming in: [assumptions about prior knowledge]
```

## 3 Screen or Page Goal

Name the single job of the screen or page this brief covers.

```
Screen: [name]
Primary job: [the one thing a user must be able to do here]
Primary action: [the single most important action on this screen]
```

## 4 Design Style

Specify the visual direction in concrete terms, and why it fits this product and audience.

```
Style direction: [named direction, applied coherently]
Why it fits: [one line tying style to user and content]
Reference boundaries: [what to avoid so the style stays consistent]
```

## 5 Information Architecture

List the content and its structure, so the builder knows what exists before deciding order.

```
Content inventory: [every distinct block of content on this screen]
Grouping: [how blocks relate and cluster]
Priority: [rank of blocks by importance to the user]
```

## 6 Section Order

Give the top-to-bottom order of sections, reflecting the priority set above.

```
1. [section]
2. [section]
3. [section]
...
```

## 7 Component Requirements

List every component the screen needs. Use a table so nothing is left implicit.

| Component | Purpose | Content | States | Behavior | Accessibility notes |
|---|---|---|---|---|---|
| [name] | [why it exists] | [what it holds] | [state set] | [what it does on interaction] | [labels, focus, roles] |
| Primary button | Triggers the primary action | Label text | default, hover, focus, active, disabled, loading | Submits form; disables while loading | Real label, 3:1 contrast, visible focus |
| Text input | Collects one value | Label, placeholder, help text | default, focus, disabled, error | Validates on blur; shows inline error | Programmatic label, error tied to field |

## 8 Design Tokens

Define the tokens the build must use. Replace placeholders with real values.

**Color**

| Token | Value | Role |
|---|---|---|
| color-bg | #FFFFFF | Page background |
| color-surface | #F5F5F5 | Card and panel background |
| color-text-primary | #1A1A1A | Body and heading text |
| color-text-muted | #5A5A5A | Secondary text, meets 4.5:1 |
| color-accent | #2B5FFF | Primary action, links |
| color-danger | #C0341C | Errors, destructive actions |

**Type scale (px)**

| Token | Size | Weight | Use |
|---|---|---|---|
| text-xs | 12 | 400 | Captions, meta |
| text-sm | 14 | 400 | Secondary body |
| text-base | 16 | 400 | Body, mobile minimum |
| text-lg | 20 | 600 | Subheadings |
| text-xl | 28 | 700 | Section headings |
| text-2xl | 36 | 700 | Page title |

**Spacing scale (4 or 8px)**

| Token | Value |
|---|---|
| space-1 | 4 |
| space-2 | 8 |
| space-3 | 16 |
| space-4 | 24 |
| space-5 | 32 |
| space-6 | 48 |

**Radius and shadow**

| Token | Value |
|---|---|
| radius-sm | 4px |
| radius-md | 8px |
| radius-lg | 16px |
| shadow-1 | subtle: low blur, low opacity |
| shadow-2 | raised: medium blur for menus and modals |

## 9 Content Requirements

Specify the real words, not placeholders, wherever they are known.

```
Headline: [exact text]
Body copy: [exact text or source]
Button labels: [exact text; describe what happens on click]
Error messages: [exact, specific, recoverable wording]
Empty state text: [what it says and the first action it offers]
```

## 10 Interaction States

List the required state set for interactive elements. Include every state that applies to each component.

- default
- hover
- focus visible
- active
- disabled
- loading
- error
- success
- empty (where the component can be empty)

For each interactive component, confirm which states apply and describe what each looks like and does.

## 11 Responsive Rules

Give behavior at each breakpoint. These defaults are reasonable and adjustable to the project.

| Breakpoint | Width | Layout intent |
|---|---|---|
| Mobile | 360 | Single column, 16px+ body, 44px+ targets, stacked sections |
| Tablet | 768 | Two columns where content allows; navigation may expand |
| Laptop | 1024 | Multi-column layout; sidebar or wider content area |
| Desktop | 1440 | Max content width set; generous whitespace, no line over 75 characters |

```
Reflow rules: [how sections stack and reorder]
Line length: [keep 45 to 75 characters at all widths]
Touch versus pointer: [target sizes and hover behavior per input type]
```

## 12 Accessibility Requirements

State the accessibility floor as testable requirements. These are heuristic until verified with real assistive technology.

- [ ] Body text meets 4.5:1 contrast; large text and UI components meet 3:1 (WCAG 2.2 AA).
- [ ] Every interactive element has a visible focus state.
- [ ] Every form input has a programmatic label, not a placeholder alone.
- [ ] Heading order is logical and sequential.
- [ ] No meaning is conveyed by color alone.
- [ ] Touch targets meet a 44px practical minimum, 24px absolute floor.
- [ ] Motion respects prefers-reduced-motion.

## 13 Performance Considerations

Name the performance targets and constraints the build must respect.

```
Load target: [what must be usable, and how fast]
Asset budget: [image sizes, font loading strategy]
Perceived performance: [loading and skeleton states to avoid blank waits]
```

## 14 QA Checklist

List the checks a reviewer runs before calling the work done.

- [ ] Primary action is present, obvious, and works.
- [ ] All component states render correctly, including error and empty.
- [ ] Layout holds at 360, 768, 1024, and 1440.
- [ ] Contrast, focus, labels, and heading order pass a heuristic accessibility pass.
- [ ] Copy matches the content requirements exactly.
- [ ] No horizontal scroll on mobile; no clipped or covered content.

## 15 Acceptance Criteria

Write acceptance criteria as testable checkboxes, phrased the way a QA person would verify them.

- [ ] Form submits with keyboard only, and the error summary receives focus on failed submit.
- [ ] On a 360px viewport, all touch targets are at least 44px and no content requires horizontal scrolling.
- [ ] Body text contrast measures at least 4.5:1 against its background on every screen in scope.
- [ ] Every interactive element shows a visible focus indicator when tabbed to.

## Developer and AI agent notes

Hand this brief to any builder as the single source of truth. A human developer works through the sections in order; a coding or design agent can treat each section as a scoped instruction and each acceptance criterion as a test to satisfy. Keep the brief tool-neutral: it describes required outcomes, token values, states, and criteria, and leaves the choice of framework, component library, or design file format to the builder. If the builder asks a question the brief does not answer, that gap is a defect in the brief; add the answer here so the next builder does not have to ask.
