# Design System Builder Prompt

Purpose: produce a small, usable design system with real token values and full component states.

## When to use
Use when a product needs consistent tokens, components, and rules that any framework can adopt.

## Provide with this prompt
- The product, the target user, and the brand or tone
- Existing colors, fonts, and spacing if any
- Any platform or brand constraints to respect

## Prompt
```
Act as a senior UI/UX product designer building a lightweight design system. Use the context I provide.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- What I am giving you: {INPUT}

Output these sections in order:
1. Product Context and Constraints. State the audience, tone, and any limits. For trust-sensitive categories like healthcare, finance, legal, and government, keep the system restrained.
2. Design Tokens. Give actual values: colors as hex, spacing and sizing in px, type scale in px with line heights, radii, and shadows. Use semantic names (for example color.text.primary, space.4), not raw color names.
3. Core Components and Required States. For each component list every state: default, hover, focus, active, disabled, loading, error, empty where relevant.
4. Layout and Responsive Rules. Grid, breakpoints, container widths, and spacing rhythm.
5. Accessibility Defaults. Contrast minimums (4.5 to 1 body, 3 to 1 large text and components), visible focus, and minimum touch target of 44 by 44px.
6. Naming and Usage Rules. How to name and when to use each token and component.
7. Adoption Order. The order to roll the system out.

Rules:
- Tokens must carry real values, not adjectives.
- Use semantic naming so tokens are portable.
- Every component must show its full set of states.
- No framework lock-in; keep it tool-neutral so any stack can implement it.
- Label guesses "Assumption:". Never invent analytics, research, or predicted numbers.
- Ask at most 3 clarifying questions, and only if they block the work.
```

## Expected output
A seven-section system with real token values, semantic names, components with full state sets, responsive and accessibility defaults, usage rules, and an adoption order, all framework-neutral.

## Tips
- Share any existing hex and font choices so the system extends them.
- Name your top five components first; the rest can follow the same patterns.
- Keep the palette small; it is easier to hold contrast and consistency.
