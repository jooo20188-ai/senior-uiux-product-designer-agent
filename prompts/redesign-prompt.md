# Redesign Direction Prompt

Purpose: turn a weak or dated screen into a clear, senior-level redesign direction.

## When to use
Use when a screen needs a fresh direction and you want structure, style, and copy you can hand to a builder.

## Provide with this prompt
- The current URL or screenshots, if a version exists
- The product, the target user, and the business goal
- What is working today that you want to keep

## Prompt
```
Act as a senior UI/UX product designer. Produce a redesign direction for the screen or product I describe.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- Business goal: {BUSINESS_GOAL}
- Primary action: {PRIMARY_ACTION}
- What I am giving you: {INPUT}

Output these sections in this exact order and numbering:
1. Product Goal
2. Target User
3. UX Strategy
4. Page or Screen Structure
5. Visual Design Direction
6. Modern UI Style Recommendation
7. Design System Foundation
8. Component List
9. Interaction States
10. Mobile Behavior
11. Accessibility Requirements
12. Suggested Copy
13. Universal AI Agent Implementation Brief
14. QA Checklist

Rules:
- Justify the style in sections 5 and 6 by product, audience, and trust context. Use restrained styles for healthcare, finance, legal, and government.
- Preserve what already works; name those elements and keep them.
- Section 12 must be actual copy the team can paste, not advice about copy.
- Every component in section 8 must list its required states in section 9 (default, hover, focus, active, disabled, loading, error, empty where relevant).
- Mobile and accessibility are always in scope.
- Label guesses with "Assumption:". Never invent analytics, research, or predicted numbers.
- Ask at most 3 clarifying questions, and only if they block the work.
```

## Expected output
A 14-section direction with UX strategy, screen structure, a justified style, a token foundation, a component and state list, real suggested copy, and an implementation brief.

## Tips
- Tell the reviewer which elements to keep so the redesign does not discard strengths.
- Give the business goal in one line; it shapes structure and copy.
- Ask for a low-fidelity structure first if you want to review layout before visuals.
