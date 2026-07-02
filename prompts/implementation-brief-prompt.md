# Universal Implementation Brief Prompt

Purpose: produce a build-ready brief any coding agent, design agent, or developer can follow.

## When to use
Use when a design is decided and you need a precise, testable brief to hand off for the build.

## Provide with this prompt
- The product, the target user, and the screen or page goal
- The chosen style and any tokens already set
- Content, flows, and constraints the build must respect

## Prompt
```
Act as a senior UI/UX product designer writing a universal implementation brief. Use the context I provide.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- Business goal: {BUSINESS_GOAL}
- Primary action: {PRIMARY_ACTION}
- What I am giving you: {INPUT}

Output these sections in this exact order and numbering:
1. Project Goal
2. Target User
3. Screen or Page Goal
4. Design Style
5. Information Architecture
6. Section Order
7. Component Requirements
8. Design Tokens
9. Content Requirements
10. Interaction States
11. Responsive Rules
12. Accessibility Requirements
13. Performance Considerations
14. QA Checklist
15. Acceptance Criteria

Rules:
- Use concrete values, not adjectives. Give colors as hex, sizes and spacing in px, and exact breakpoints.
- Every component in section 7 must list its states in section 10 (default, hover, focus, active, disabled, loading, error, empty where relevant).
- Section 9 gives real content or exact copy, not notes about content.
- Accessibility is in scope: contrast at least 4.5 to 1 body and 3 to 1 large text and components, keyboard operable with visible focus, touch targets at least 44 by 44px.
- Section 15 acceptance criteria must be testable, each phrased so a reviewer can mark it pass or fail.
- Keep the brief tool-neutral so any coding agent, design agent, or developer can build from it.
- Label guesses "Assumption:". Never invent analytics, research, or predicted numbers.
- Ask at most 3 clarifying questions, and only if they block the work.
```

## Expected output
A 15-section brief with concrete tokens, components mapped to full states, real content, responsive and accessibility rules, and testable acceptance criteria, written for any builder.

## Tips
- Paste the final tokens so section 8 matches the design exactly.
- Write acceptance criteria as pass or fail checks; vague goals stall a build.
- List every state you expect so nothing ships in a default-only condition.
