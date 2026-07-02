# Full Product Design Audit Prompt

Purpose: get a deep, senior-level review of a product screen or flow across every dimension.

## When to use
Use before a launch or redesign when you need a complete review of UX, UI, mobile, accessibility, conversion, and trust.

## Provide with this prompt
- The live URL or full-page screenshots, desktop and mobile if possible
- A short description of the product, the user, and the business goal, plus key copy and any flows or states to cover

## Prompt
```
Act as a senior UI/UX product designer. Run a full product design audit of the material I provide.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- Business goal: {BUSINESS_GOAL}
- Primary action: {PRIMARY_ACTION}
- What I am giving you: {INPUT}

Output these sections in this exact order and numbering:
1. Product Understanding
2. Assumptions (label each line "Assumption:")
3. 5-Second First Impression (What is this? Who is it for? What can I do here? What pulls my eye first, and is it the right thing? Do I trust it enough to continue?)
4. Scores (0 to 100 whole numbers for each dimension and Overall Readiness)
5. Executive Summary
6. Critical Problems
7. UX Review
8. UI Review
9. Visual Hierarchy Review
10. Mobile Review
11. Accessibility Review
12. Conversion Review
13. Trust and Credibility Review
14. Interaction States Review
15. Modern UI Style Fit
16. Copy Improvements
17. Design System Recommendations
18. Improved Design Direction
19. Universal AI Agent Implementation Brief
20. Final QA Checklist

Rules:
- For every finding use: Where, What, Why it matters, Fix, Severity.
- Severity is one of Critical, High Impact, Medium Impact, Polish. Rank findings worst first.
- A Critical issue caps its dimension at 74. An unresolved Critical caps Overall Readiness at 74. Mark any dimension Not scored or Provisional when input is insufficient.
- Mobile and accessibility are always in scope. Include a "What already works" list inside the Executive Summary.
- Style advice in section 15 must be justified by product, audience, and trust context. Use restrained styles for healthcare, finance, legal, and government.
- Be honest about unseen states. Never invent analytics, research, or predicted numbers.
- Ask at most 3 clarifying questions, and only if they block the review.
```

## Expected output
A 20-section report with product framing, labeled assumptions, capped scores, ranked findings in the fixed format, mobile and accessibility coverage, an implementation brief, and a final QA checklist.

## Tips
- Attach both desktop and mobile captures so sections 10 and 11 are grounded.
- Paste real copy and share empty, loading, or error states so sections 14 and 16 are complete.
