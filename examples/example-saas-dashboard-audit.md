# Full Product Design Audit: Ledgerline

Mode: 2 Full Product Design Audit
Input provided: Three screenshots (dashboard home, invoice list, create-invoice modal) plus a one-paragraph product description.
Note: All products, people, and numbers in this example are fictional.

This example is condensed. A real Mode 2 audit expands each section with more findings, more copy, and per-screen detail.

## 1 Product Understanding

Ledgerline is an invoicing tool for freelancers. The described job is simple: send an invoice and get paid on time. The user is a solo worker, not an accountant, who wants to know who owes money and to chase it fast.

## 2 Assumptions

Assumption: The user opens Ledgerline mainly to check who has not paid and to send a new invoice.
Assumption: Most users have between five and forty active invoices, not hundreds.
Assumption: Mobile use happens, since freelancers work away from a desk, but no mobile view was given.

## 3 5-Second First Impression

1. What is this? An invoicing dashboard. Clear enough from the invoice list and totals.
2. Who is it for? A freelancer or small operator. The tone fits.
3. What can I do here? See numbers and, somewhere, make an invoice. The main action is not obvious at a glance.
4. What pulls my eye first, and is it the right thing? A large revenue chart. Wrong thing. The user's job is getting paid, not admiring a trend line.
5. Do I trust it enough to continue? Mostly. It looks functional, though the color-only status chips create quiet doubt about what is overdue.

## 4 Scores

| Dimension | Score | Note |
| --- | --- | --- |
| UX | 62 | The core job, chasing unpaid invoices, is below the fold. |
| UI | 71 | Tidy, but two solid blue buttons blur the action hierarchy. |
| Visual Hierarchy | 58 | The chart dominates; overdue totals are buried. |
| Mobile | Not scored | No mobile view was provided. |
| Accessibility | 54 | Status shown by color alone; capped by a Critical color-only issue. |
| Trust and Credibility | 74 | Adequate, no fake proof, but empty and error states unseen. |
| Conversion | 66 | The create-invoice modal front-loads friction with 11 fields. |
| Design System | 60 | Button roles and status chips are inconsistent across screens. |
| Interaction Design | Provisional (limited input) | Static screenshots; no hover, focus, or loading states shown. |
| Modern UI Style Fit | 72 | The clean, light style suits the tool and audience. |
| Overall Readiness | 63 | Held at or below 74 by unresolved Critical issues. |

Caps applied: color-only status is a Critical Accessibility issue, holding Accessibility at or below 74; unresolved Critical issues hold Overall Readiness at or below 74.

## 5 Executive Summary

Ledgerline works, but it leads with the wrong thing. The dashboard shows a revenue chart while the user's real job is to see who owes money and to act. Overdue invoices sit below the fold. The create-invoice modal shows 11 fields at once, including optional tax fields, which slows the most common task. Status chips rely on color alone, which fails for color-blind users. Fix the order, the modal, and the status signals, and this becomes a strong tool. What already works: the invoice list is scannable, the language is plain, and nothing uses fake urgency or invented proof.

## 6 Critical Problems

Where: Dashboard home. What: The overdue and unpaid totals are below the fold; a revenue chart leads. Why it matters: The primary job is getting paid, so the first thing a user needs is what is late and by how much. Fix: Lead with overdue and unpaid totals and a chase action; move the chart down. Severity: Critical. Confidence: Observed.

Where: Invoice list and modal. What: Paid and overdue are shown by color alone, green and red. Why it matters: Users who cannot distinguish red from green cannot tell paid from overdue, which is the core signal. Fix: Add a text label and an icon to each status chip. Severity: Critical. Confidence: Observed.

## 7 UX Review

The dashboard answers "how am I doing" before "who owes me", which reverses the user's priority. Getting to unpaid invoices takes a scroll or a click that should not be needed. The create-invoice modal mixes required and optional fields with no grouping, so the user reads all 11 to find the four that matter. Reorder the dashboard around the paid-or-not question and stage the modal so the common path is short.

## 8 UI Review

Spacing and type are consistent within each screen. The main flaw is button hierarchy: the primary action and a secondary action are both solid blue, so nothing signals which is the safe default. Give one solid primary and one quieter secondary. Status chips vary slightly in size between the list and the modal; standardize them.

## 9 Visual Hierarchy Review

The revenue chart is the largest, highest-contrast element, so the eye lands there first. That is decoration relative to the job. The overdue total, the thing a user came to see, is small and low. Promote overdue and unpaid to the top-left, the first place the eye lands, and demote the chart.

## 10 Mobile Review

Not scored. No mobile view was provided. Assumption: freelancers check invoices on a phone, so a mobile pass is needed before shipping, with attention to the modal, which will not fit 11 fields on a small screen.

## 11 Accessibility Review

Color-only status is the blocking issue, noted as Critical above. Beyond that, the two solid blue buttons may not differ enough in contrast to signal roles. Body text contrast was not measured from the screenshots and should be checked against 4.5:1. Focus states could not be seen and must be verified.

## 12 Conversion Review

For this tool, conversion means completing and sending an invoice. The modal works against that by showing 11 fields at once, including optional tax fields most users skip. The friction is front-loaded. Stage the modal so the user reaches "send" in a few clear steps and only meets tax fields if they need them.

## 13 Trust and Credibility Review

Nothing on screen fakes proof, which is correct. Trust risk sits in unseen states: a failed send or a payment error must explain the cause and the next step. Those states were not provided and must be designed before launch.

## 14 Interaction States Review

Provisional. Static screenshots cannot show hover, focus, active, loading, empty, error, success, or disabled. At minimum, define: an empty state for a new user with no invoices, a loading state for the list, a success state after sending, and an error state for a failed send that names cause and fix.

## 15 Modern UI Style Fit

The clean, light style fits an invoicing tool for freelancers. It reads as calm and functional. No change of style is needed; the work is in hierarchy and states, not paint.

## 16 Copy Improvements

- Dashboard heading: change "Overview" to "What needs attention", so the page names the job.
- Modal title: change "New invoice" to "Create invoice", matching the action word on the button.
- Status chip: add the words "Paid" and "Overdue" next to the color, not instead of it.

## 17 Design System Recommendations

- Button tokens: define action.primary as one solid style and action.secondary as one quiet style; forbid two solid buttons side by side.
- Status tokens: define status.paid and status.overdue as color plus label plus icon, never color alone.
- Spacing: confirm a 4 or 8px scale across screens; the modal spacing looks slightly off the grid.

## 18 Improved Design Direction

Rebuild the dashboard around the paying question. Top-left: overdue total and count with a chase action. Beside it: unpaid total and a create action. Below that: the invoice list, sorted overdue first. The revenue chart moves to the bottom or a separate view. Turn the create-invoice modal into a three-step flow: step one client and amount, step two line items, step three review and send, with tax fields disclosed only when the user marks the invoice taxable.

## 19 Universal AI Agent Implementation Brief

Goal: reorder the dashboard around getting paid, stage the invoice modal, and fix status signals. This brief works for any coding agent, design tool, or developer.

Dashboard: place overdue and unpaid totals first as two summary cards, top-left and top-right, each with a single action. Sort the invoice list overdue first. Move the revenue chart to the bottom of the page.
Modal: convert to three steps. Step one: client, amount, due date. Step two: line items. Step three: review and send. Show tax fields only after the user marks the invoice taxable, using progressive disclosure.
Buttons: apply role tokens. One solid primary per view; secondary actions use a quiet style. No two solid buttons adjacent.
Status: render each chip as color plus text label plus icon. Provide "Paid" and "Overdue" as the labels.
States to build: empty (no invoices yet), loading (list and send), success (invoice sent), error (send failed, name cause and next step).
Accessibility: body text at 4.5:1, UI components at 3:1, visible focus on every control, targets at 44px on touch.

## 20 Final QA Checklist

- Overdue and unpaid totals appear first, above the fold.
- Invoice list sorts overdue first.
- Create-invoice flow reaches "send" in three steps; tax fields hidden until needed.
- Every status chip shows color, text, and icon.
- One solid primary button per view; no adjacent solid buttons.
- Empty, loading, success, and error states exist and read clearly.
- Body text meets 4.5:1; components meet 3:1; focus is visible; targets are 44px on touch.
- Mobile view designed and reviewed before launch.
