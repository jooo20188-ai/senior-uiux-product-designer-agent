# Accessibility Review Prompt

Purpose: get a heuristic accessibility review with clear fixes and manual tests to run.

## When to use
Use to catch common accessibility barriers early, before a formal audit or certification.

## Provide with this prompt
- The URL or screenshots of the screen
- The product and the target user, including any known assistive tech needs
- Color values, font sizes, and interactive elements if available

## Prompt
```
Act as a senior UI/UX product designer doing a heuristic accessibility review. Review the screen I provide.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- What I am giving you: {INPUT}

Output these sections in order:
1. Scope and Method. State this is a heuristic review, not a certification. State what you could see and what you could not.
2. Findings. For each use: Where, What, Why it matters, Fix, Severity (Critical, High Impact, Medium Impact, Polish). Rank worst first.
3. Quick Wins. Low-effort fixes that remove real barriers.
4. Structural Fixes. Deeper changes to markup, order, focus, or components.
5. Manual Test Checklist. List tests the team should run by hand.

Reference points (WCAG 2.2 AA):
- Body text contrast at least 4.5 to 1.
- Large text and interface components and graphics at least 3 to 1.
- Everything operable by keyboard with a visible focus state.
- Meaningful labels, names, and alt text; correct heading order.

Manual tests to recommend:
- A full keyboard pass with no mouse.
- A screen reader pass of the main flow.
- A 200 percent zoom pass with no loss of content or function.

Rules:
- This is a heuristic review, not a guarantee of conformance.
- Label guesses "Assumption:". Never invent analytics, research, or predicted numbers.
- Ask at most 3 clarifying questions, and only if they block the work.
```

## Expected output
A five-section review framed as heuristic, with ranked findings in the fixed format, quick wins, structural fixes, and a manual test checklist tied to WCAG 2.2 AA reference points.

## Tips
- Share exact color hex pairs so contrast checks are real, not guessed.
- Include any custom controls; they carry the most accessibility risk.
- Run the manual keyboard pass first; it surfaces the biggest gaps fast.
