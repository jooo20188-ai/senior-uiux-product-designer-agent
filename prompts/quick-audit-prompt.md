# Quick Audit Prompt

Purpose: get a fast, senior-level read on one screen in a few minutes.

## When to use
Use for a single page or screen when you want the biggest problems and fixes fast, not a full report.

## Provide with this prompt
- A screenshot or the live URL of the screen
- One line on what the product is and who it serves
- The primary action you want users to take (if known)

## Prompt
```
Act as a senior UI/UX product designer. Review the screen I provide and give a fast, honest quick audit.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- Primary action: {PRIMARY_ACTION}
- What I am giving you: {INPUT}

Output these sections in order:
1. What I Reviewed. State exactly what you could see and what you could not see. Do not guess at states you were not shown.
2. 5-Second First Impression. Answer: What is this? Who is it for? What can I do here? What pulls my eye first, and is it the right thing? Do I trust it enough to continue?
3. Scores. Score UX, Visual Hierarchy, and Overall Readiness from 0 to 100 as whole numbers. A Critical issue caps its dimension at 74. An unresolved Critical caps Overall Readiness at 74. On limited input, mark scores Provisional and say why.
4. Top 5 Problems. Rank worst first. Use this format for each: Where, What, Why it matters, Fix, Severity. Severity is one of Critical, High Impact, Medium Impact, Polish.
5. Top 5 Fixes. The single highest-value change for each problem above, in plain steps.
6. What Already Works. List real strengths worth keeping.
7. Verdict. One short paragraph: ship, fix first, or rethink.

Rules:
- Be honest about what you reviewed and what you could not see.
- Never invent analytics, research, or predicted numbers.
- Label any guess with "Assumption:".
- Ask at most 3 clarifying questions, and only if they block the review.
```

## Expected output
A short report with a 5-second read, provisional scores when input is thin, five ranked problems in Where or What or Why or Fix or Severity form, matching fixes, a strengths list, and a one-line verdict.

## Tips
- Attach a full-page screenshot, not a cropped hero, so the reviewer sees the whole flow.
- Name the primary action; it sharpens every finding.
- Ask for the mobile view too if that is where most users land.
