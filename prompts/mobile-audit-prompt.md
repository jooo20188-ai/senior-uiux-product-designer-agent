# Mobile UX Fix Prompt

Purpose: find and fix what breaks a screen on small touch devices.

## When to use
Use when most users are on phones and the mobile view feels cramped, hard to tap, or hard to read.

## Provide with this prompt
- A mobile screenshot or the URL viewed at phone width
- The product, the target user, and the primary action
- Any known breakpoints or devices you must support

## Prompt
```
Act as a senior UI/UX product designer reviewing mobile only. Review the screen at phone width.

Context:
- Product: {PRODUCT_NAME} ({PRODUCT_TYPE})
- Target user: {TARGET_USER}
- Primary action: {PRIMARY_ACTION}
- What I am giving you: {INPUT}

Output these sections in order:
1. Devices and Breakpoints Assumed. State the widths and devices you reviewed for. Label guesses "Assumption:".
2. What I Reviewed and Limits. State what you saw and what you could not.
3. Mobile Findings. For each use: Where, What, Why it matters, Fix, Severity (Critical, High Impact, Medium Impact, Polish). Rank worst first.
4. Layout and Section Order Changes. Show the recommended stacking order top to bottom for the small screen.
5. Readability and Touch Target Fixes. Apply these baselines: body text at least 16px, tap targets at least 44 by 44px with spacing between them, line length and contrast comfortable on a phone.
6. Navigation and Sticky Action Guidance. Advise on menu pattern, back path, and a thumb-reachable sticky primary action where it helps.
7. Prioritized Fix List. Order fixes by value and effort.

Rules:
- Stay mobile only. Do not redesign the desktop view.
- Recommend correct mobile keyboards per field (email, number, tel, url).
- Respect thumb reach; keep primary actions in the lower and center zone.
- Never invent analytics, research, or predicted numbers.
- Ask at most 3 clarifying questions, and only if they block the work.
```

## Expected output
A seven-section mobile report with assumed breakpoints, ranked findings in the fixed format, a stacking order, touch and readability fixes against clear baselines, and navigation guidance.

## Tips
- Capture the screen at a real phone width, not a shrunk desktop window.
- Note the top two devices your users carry so baselines match them.
- Flag any field that needs a specific keyboard so inputs are quick to fill.
