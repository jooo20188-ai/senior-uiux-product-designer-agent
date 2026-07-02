# Quick Audit: Harbor Lane Dental Homepage

Mode: 1 Quick Audit
Input provided: One desktop homepage screenshot plus the page copy pasted as text.
Note: All products, people, and numbers in this example are fictional.

## 1 What I Reviewed

One desktop homepage screenshot at roughly 1440px wide, plus the full page copy as text. I did not see the mobile view, any inner pages, a booking flow, or any hover, focus, or loading states.

What the input can support:

- Judgments about layout, hierarchy, the hero, the visible actions, the services block, and the pasted copy.

What the input cannot support:

- Anything about interaction, keyboard use, real contrast values, page speed, or the pages a visitor reaches after the homepage.

Findings about interaction and about pages past the homepage are Provisional. Contrast is judged by eye from the screenshot and marked Likely, not Observed, because I did not run a checker. The screenshot shows a fixed layout, so I judged only what is visible above and just below the fold, plus the pasted copy. This is a fast read of one screen, not a full audit.

## 2 5-Second First Impression

Answered honestly as a first-time visitor who wants a dentist and is deciding in seconds whether to stay.

1. What is this? A dental practice. The hero photo and the word "Practice" signal healthcare, but the name Harbor Lane Dental sits small in the header, so it takes a beat to confirm. A visitor should not have to work to learn the name of the business.
2. Who is it for? Not stated. Nothing says new patients, families, emergencies, or a neighborhood. There is no location cue, so a local visitor cannot tell if this clinic is near them. It reads as generic and could be any practice anywhere.
3. What can I do here? Unclear. The only visible action is reading. There is no booking button and no obvious next step in the hero. To act at all, a visitor must find the small phone number in the header, which is easy to miss.
4. What pulls my eye first, and is it the right thing? The large stock photo of a smiling person and the headline "Welcome to Our Practice". That is the wrong thing. It carries no information and no action, so the strongest element on the page does the least work.
5. Do I trust it enough to continue? Not yet. No address, no hours, no dentist name, and a testimonial with no author. A cautious patient, and dental patients are often cautious, hesitates here and may check a competitor whose details are plain to see.

## 3 Scores

| Dimension | Score | Note |
| --- | --- | --- |
| UX | 58 | Primary action is missing from the hero; the path to book is unclear. |
| UI | 66 | Clean but generic; low-contrast body text hurts it. |
| Visual Hierarchy | 55 | The eye lands on a decorative photo, not on an action or proof. |
| Mobile | Not scored | No mobile view was provided. |
| Accessibility | 52 | Light-gray body text on white likely fails 4.5:1; not verified with a tool. |
| Trust and Credibility | 44 | No address, hours, dentist name, or attributed proof visible early. |
| Conversion | 41 | No booking CTA; phone number is tiny; no insurance or pricing help. |
| Design System | Not scored | A single static screenshot cannot show tokens or component reuse. |
| Interaction Design | Provisional (limited input) | No hover, focus, or loading states in a static image. |
| Modern UI Style Fit | 68 | The soft, clean style suits healthcare, but it is undifferentiated. |
| Overall Readiness | 60 | Capped by unresolved Critical issues; a real patient may leave without acting. |

Caps applied: the buried primary action is a Critical UX and Conversion issue, so both are held at or below 74, and Overall Readiness is held at or below 74 while that Critical issue is unresolved.

How to read these scores. Trust and Credibility and Conversion are the lowest because the page gives a cautious patient no reason to act and no early proof of who runs the clinic. UX and Visual Hierarchy sit in the low band because the strongest element, the hero photo, does the least work. UI and Modern UI Style Fit are higher because the underlying look is clean and calm; the problem is what the page says and does, not its paint. Mobile and Design System are Not scored because the input cannot support them, and Interaction Design is Provisional because a static screenshot shows no live states. None of these scores contradicts a finding; each low score maps to a problem listed below.

## 4 Top 5 Problems

Problem 1

- Where: Hero and header.
- What: The primary action is buried. The only way to act is a phone number in tiny header text; there is no booking or call button in the hero, and no online booking appears anywhere above the fold.
- Why it matters: For a single-location clinic the primary job is booking or calling. A visitor who is ready to book has nothing to click, so the page forces them to hunt for the small phone number or leave. Most will leave.
- Fix: Add a clear primary action in the hero, a "Book an appointment" button beside a tap-to-call link.
- Severity: Critical. Confidence: Observed.

Problem 2

- Where: Above the footer, and the header.
- What: No address, hours, or dentist name appears early; these sit only near the footer if at all.
- Why it matters: Local patients decide on location and hours first, before anything else. Missing them breaks trust and sends people to a competitor whose details are visible without scrolling.
- Fix: Show the address, today's hours, and the lead dentist's name near the top.
- Severity: High Impact. Confidence: Observed.

Problem 3

- Where: Testimonial carousel.
- What: Auto-rotating quotes with no attribution.
- Why it matters: Unattributed, moving praise reads as invented and lowers trust instead of building it, the opposite of what a testimonial is for.
- Fix: Use two or three static quotes with a real first name, last initial, and date.
- Severity: High Impact. Confidence: Observed.

Problem 4

- Where: Body copy site-wide.
- What: Light-gray text on white, likely below 4.5:1.
- Why it matters: Low contrast excludes low-vision and older users, a large share of dental patients, and makes the copy tiring to read for everyone.
- Fix: Darken body text to meet 4.5:1 and confirm with a checker.
- Severity: High Impact. Confidence: Likely.

Problem 5

- Where: Services area.
- What: Nine equal cards with no priority, and no pricing or insurance information anywhere on the page.
- Why it matters: Equal weight gives no entry point, so a visitor with a specific need must hunt, and a patient who wants to know if their insurance is accepted finds no answer, which is a common reason to call a different clinic.
- Fix: Lead with the top three services and group the rest, and add a short line on insurance accepted.
- Severity: Medium Impact. Confidence: Observed.

These five are ranked by how directly they block a patient from booking. The buried action is first because it stops the core task outright. The trust gaps and low contrast follow because they quietly turn away cautious and older patients. The services problem is last because it slows people rather than stopping them.

## 5 Top 5 Fixes

1. Put a primary action in the hero. Add a "Book an appointment" button beside a tap-to-call phone link, both visible without scrolling. This gives the ready patient a way to act on the first screen, which the page currently lacks.
2. Add a trust strip under the hero showing address, today's hours, and the lead dentist's name and credential. These are the details a local patient checks first, so they belong high on the page.
3. Replace the carousel with two or three static, attributed quotes, each with a first name, last initial, and date. Static, named proof reads as real; moving, anonymous praise reads as invented.
4. Raise body text contrast to at least 4.5:1 and confirm with a checker before publishing. This is a fast change that stops excluding low-vision and older patients.
5. Reorder services into three primary cards first, then a grouped list, and add a line on insurance accepted, so a visitor finds their need and answers the cost question fast.

## 6 What Already Works

- The name Harbor Lane Dental is specific and easy to remember, which helps a local patient recall it.
- The layout is uncluttered, with room to add the missing action and proof without a rebuild.
- The soft, clean visual tone is appropriate for a healthcare setting and reads as calm.
- The copy is calm and free of hype, a good base to build on.
- The single-column structure will adapt to mobile without a major rework once the missing pieces are added.
- Nothing on the page uses fake urgency or fake scarcity, so the fixes can add honest proof without undoing bad habits.

## 7 Verdict

The single most important fix is to give the hero a real primary action: a booking button and a tap-to-call link, visible without scrolling. Right now a ready patient cannot act, so the page fails its main job before trust or polish even matter. After that, add the address, hours, and dentist name so the page earns the trust a local clinic needs. These two changes together move the homepage from a brochure into a page that books patients. Watch appointment requests and calls after the change to see whether the new action is working.
