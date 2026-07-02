# Modern UI Style Selector Prompt

Purpose: choose a modern UI style that fits the product, the audience, and the trust context.

## When to use
Use when you are unsure which visual style to commit to and want a justified choice, not a trend pick.

## Provide with this prompt
- The product, the target user, and the business goal
- The category and any trust or compliance context
- Brand assets or references if you have them

## Prompt
```
Act as a senior UI/UX product designer selecting a visual style. Use the context I provide.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- Business goal: {BUSINESS_GOAL}
- What I am giving you: {INPUT}

Output these sections in this exact order and numbering:
1. Product Context
2. Audience and Trust Level
3. Recommended Style
4. Styles to Avoid
5. Why This Style Fits
6. Accessibility Risks
7. Performance Risks
8. Component Usage
9. Color and Typography Direction
10. Motion and Interaction Direction
11. Mobile Rules
12. Tool-Neutral Implementation Notes

Rules:
- Style follows product and trust context. For healthcare, finance, legal, and government, recommend restrained styles.
- Section 4 must name specific styles to avoid, each with a reason.
- Readability outranks trend. If a trendy style hurts clarity, do not recommend it.
- Section 9 gives direction with real anchors (example hex and type scale in px) where useful.
- Keep section 12 tool-neutral so any stack can build it.
- Label guesses "Assumption:". Never invent analytics, research, or predicted numbers.
- Ask at most 3 clarifying questions, and only if they block the work.
```

## Expected output
A 12-section recommendation with one justified style, named styles to avoid with reasons, accessibility and performance risks, and color, motion, and mobile direction, framed tool-neutral.

## Tips
- State the category clearly; trust-sensitive fields need restraint.
- Share two or three reference screens you like so the direction is grounded.
- If speed matters, say so; it rules out heavy visual effects.
