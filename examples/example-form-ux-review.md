# Form UX Review: Oakline Renovations Quote Request

Mode: 1 Quick Audit scoped to a single form, plus a Mode 8 style copy set.
Input provided: Form field list and labels pasted as text, plus desktop and mobile screenshots.
Note: All products, people, and numbers in this example are fictional.

## 1 What I Reviewed

The quote-request form for Oakline Renovations, a home renovation contractor. I had the field list and labels as text and both a desktop and a mobile screenshot of the form. I did not see the pages leading to the form, the confirmation screen, or any live validation behavior, so findings about those are Provisional. This is a scoped audit of one form, not the whole site.

## 2 The Form as Given

The current form asks for nine fields, in this order.

1. Full name.
2. Email.
3. Phone.
4. Address.
5. Project type, a dropdown with 14 options.
6. Budget, a dropdown, required.
7. Project description, required, with a 500-character minimum.
8. How did you hear about us, required.
9. Preferred contractor, a dropdown.

## 3 Scores

Scoped to a single form. Dimensions the form cannot support are Not scored with a reason.

| Dimension | Score | Note |
| --- | --- | --- |
| UX | 46 | Front-loaded friction and a hostile description minimum. |
| Mobile | 44 | Placeholder-only labels and long dropdowns hurt small screens. |
| Accessibility | 48 | Placeholder-only labels fail once typing begins; capped by a Critical issue. |
| Conversion | 40 | Required budget and a 500-character minimum drive abandonment. |
| Trust and Credibility | 52 | No statement of what happens after submit. |
| Overall Readiness | 45 | Held at or below 74 by unresolved Critical issues. |
| Visual Hierarchy | Not scored | A single form does not show page-level hierarchy. |
| Design System | Not scored | One form cannot show tokens or component reuse. |
| Interaction Design | Not scored | No live validation or states were provided. |

Caps applied: the 500-character minimum and the placeholder-only mobile labels are Critical, holding their dimensions and Overall Readiness at or below 74.

## 4 Findings

Ordered by severity. All are Observed, since the field list and the desktop and mobile screenshots show each issue directly.

Finding 1

- Where: Project description field.
- What: A required 500-character minimum.
- Why it matters: Forcing 500 characters before any contact is hostile. A busy homeowner will abandon rather than write an essay just to ask for a quote, and this is the field most likely to end the session.
- Fix: Remove the minimum; keep the field optional and short.
- Severity: Critical. Confidence: Observed.

Finding 2

- Where: Mobile form labels.
- What: Fields use placeholder-only labels.
- Why it matters: Placeholders vanish once the user types, so the field loses its label. This fails for screen readers and for anyone who pauses mid-form and forgets what a field was for.
- Fix: Use visible labels above every field.
- Severity: Critical. Confidence: Observed.

Finding 3

- Where: Budget dropdown.
- What: Budget is required before any human contact.
- Why it matters: Asking budget up front creates negotiation anxiety and makes the visitor feel priced before they have spoken to anyone, so many leave rather than commit to a number.
- Fix: Remove budget from the form and raise it on the follow-up call.
- Severity: High Impact. Confidence: Observed.

Finding 4

- Where: Preferred contractor dropdown.
- What: The label is internal jargon a customer cannot answer.
- Why it matters: A new customer does not know the contractors by name, so the field creates doubt and forces a guess, which adds friction with no benefit to the user.
- Fix: Remove it and assign the contractor internally.
- Severity: High Impact. Confidence: Observed.

Finding 5

- Where: After submit.
- What: Nothing states what happens next.
- Why it matters: Without a promise of a reply, the user does not know if anyone will call or when, which lowers trust at the exact moment they are handing over their details.
- Fix: State the next step and timeframe near the button and on the success screen.
- Severity: High Impact. Confidence: Observed.

Finding 6

- Where: "How did you hear about us" field.
- What: Required.
- Why it matters: This serves the business, not the user, and adds friction to a task the user wants to finish quickly.
- Fix: Remove it, or make it optional and place it after submit.
- Severity: Medium Impact. Confidence: Observed.

## 5 The Form Reworked

Cut the form to what is needed to start a conversation. Move everything else to the follow-up call.

- Name.
- Contact method: one of email or phone, the user's choice.
- Address or postcode.
- Short project description, optional, no minimum.
- Optional photo upload, with a one-line note that photos help but are not required.

Moved to the follow-up call: budget, project type detail, preferred contractor, and how they heard about us. State clearly what happens after submit: "We reply within one business day with a call to schedule a free site visit."

## 6 Error and Helper Text Set

Microcopy for each remaining field. Error messages are written as fix instructions, not blame.

| Field | Label | Helper text | Error message |
| --- | --- | --- | --- |
| Name | Your name | So we know who to ask for. | Enter your name so we know who to ask for. |
| Contact method | Email or phone | Give us one, whichever you prefer. | Add an email or a phone number so we can reply. |
| Address or postcode | Project address or postcode | Helps us plan the site visit. | Enter the address or postcode for the work. |
| Project description | What you want done | A sentence is plenty. Optional. | No error; this field is optional. |
| Photo upload | Add a photo (optional) | A photo of the space helps us prepare. | That file did not upload; try a JPG or PNG under 10MB. |

## 7 What Already Works

- The form collects a real address, which a contractor genuinely needs to quote.
- Name, email, and phone are the right core fields to keep.
- An optional photo upload is a good idea and helps the contractor prepare.
- The labels are in plain language, apart from "Preferred contractor".

## 8 Verdict

The single most important fix is to remove the 500-character minimum on the description; it turns a simple quote request into an essay and will lose users at the last step. Next, give every field a visible label on mobile and drop the budget and preferred-contractor fields, then state clearly that Oakline replies within one business day. Watch quote-request completion after the change.
