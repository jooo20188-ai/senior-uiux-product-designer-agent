# Modern UI Style Selector: Fernwell

Mode: 9 Modern UI Style Selector
Input provided: Product description, audience, and brand adjectives ("calm, competent, human").
Note: All products, people, and numbers in this example are fictional.

## 1 Product Context

Fernwell is a telehealth service where adults 45 and older book video visits with clinicians. The primary job is simple and high-stakes: find the right clinician and book a video visit with confidence.

The task is clinical, not casual. It is usually done in daylight, at home, and sometimes when the person is unwell or worried. That context shapes every style choice: the interface must be legible, calm, and easy to trust on the first visit, because a person deciding about their health has no patience for a page that feels like marketing or a game.

## 2 Audience and Trust Level

The audience is adults 45 and older. In practice this means:

- Many prefer larger text and find small type genuinely hard to read.
- Many value clarity over flourish and read decoration as noise, not quality.
- Many are cautious about health information online and look for signs the service is real and competent.

Trust must be high, because the person is handing over health details and booking time with a clinician. The brand adjectives, calm, competent, human, all point the same way: away from spectacle and toward steadiness and legibility. A style that looks trendy but reads as cold or hard to use would actively lower trust for this group.

## 3 Recommended Style

Editorial Minimalism as the base, with soft depth accents. In practice:

- Calm light surfaces, with plenty of space around content.
- One desaturated green or blue accent, used sparingly for the primary action and key highlights.
- Generous type sizes, with an 18px body given the audience.
- High contrast throughout, so text and controls are easy to read.
- Depth limited to soft, quiet shadows on key cards to guide the eye, never heavy effects.

The result reads as a considered, human clinical space, not a marketing page. The soft depth is there only to help the eye find the appointment card and the primary action, not to decorate.

## 4 Styles to Avoid

- Glassmorphism-heavy treatments: blur and transparency reduce readability for older eyes and low-vision users, which is the opposite of what this audience needs.
- Neubrutalism: its harsh borders and loud contrast read as unserious in healthcare, where the tone should be calm and competent.
- Cyberpunk UI: neon on dark signals entertainment and gaming, not care, and undercuts trust for a clinical booking.
- Dark Premium SaaS: a dark interface is wrong for a daytime clinical booking task and for this audience, who benefit from bright, high-contrast, familiar surfaces.

## 5 Why This Style Fits

Editorial Minimalism serves all three brand adjectives directly.

- Calm comes from space and a single quiet accent, so nothing shouts.
- Competent comes from clear structure and legible type, which signals a service that has its act together.
- Human comes from real clinician photos, plain language, and generous sizing that respects the reader.

It also fits the job. A person choosing a clinician needs to compare a few options and decide without visual noise. High contrast and large type keep that easy for the target age group, and a quiet layout keeps the focus on the clinician and the time slot, which are the only things that matter at the moment of booking.

## 6 Accessibility Risks

Editorial Minimalism is low-risk, but two risks need control.

- The single accent must not become the only signal for status or action. Pair it with text and shape, so a color-blind user still understands state.
- Generous whitespace must not push key actions below the fold on small screens, which would hide the booking action from the users least likely to scroll.

Control both by keeping body text at 18px and 4.5:1 contrast, large text and UI components at 3:1, and confirming the primary action stays visible without scrolling. The soft depth accents must stay subtle enough not to lower contrast on the cards they sit under.

## 7 Performance Risks

This style is light by nature, which suits users who may be on older devices or slower home connections.

- Main risk: large clinician photos. Serve appropriately sized images and modern formats.
- Main risk: decorative motion. Keep it minimal, as covered in section 10.
- Keep shadows as simple CSS rather than heavy image assets, and avoid large background media.

A fast, quiet page also reinforces the calm, competent tone. For this audience, a page that loads slowly reads as unreliable, which is the opposite of the trust the service needs.

## 8 Component Usage

How the recommended style shapes each core component.

- Appointment card: a calm light surface with a soft shadow, large clear date and time, clinician name, and one primary action to confirm. The style keeps it uncluttered so the booking detail is unmistakable and the confirm action is the obvious next step.
- Clinician profile card: a real photo, name, credential, and a plain-language line on what they help with. The style favors legible type and honest presentation over badges or ratings theater, which matters when the reader is judging whether to trust a clinician.
- Time-slot picker: large, well-spaced tappable slots at 44px minimum, with the selected slot marked by color plus a check, not color alone. Generous spacing prevents mis-taps, which frustrate and can send the wrong booking.
- Pre-visit checklist: a simple high-contrast list with clear check states and 18px text, so a user can confirm they are ready for the visit without strain or doubt.

## 9 Color and Typography Direction

- Surface: a neutral light background with clear separation between sections.
- Text: a dark text color meeting 4.5:1 against the surface, used for all body copy.
- Accent: one desaturated green or blue as the single accent, reserved for the primary action and key highlights. Do not use the accent for body text.
- Type: a clear, readable sans with a defined scale, large headings, an 18px body, and a small size no lower than 16px for anything a user must read.

Prioritize legibility over character. For this audience, a plain, well-sized typeface that is easy to read beats a distinctive one that is not.

## 10 Motion and Interaction Direction

- Keep motion minimal and functional: gentle fades and short transitions that confirm an action, nothing decorative.
- Respect prefers-reduced-motion and drop non-essential animation when it is set.
- Never convey meaning through motion alone, since some users will not see it.

Interactions should feel steady and predictable. That supports the calm, competent tone and helps users who find motion distracting or who are unwell while booking.

## 11 Mobile Rules

- Single column throughout, so the eye follows one clear path.
- Body text at 18px, never smaller for critical content.
- Touch targets at least 44px, with clear spacing between time slots to prevent mis-taps.
- The primary action, booking, stays within thumb reach and visible without hunting.
- Keep whitespace generous but confirm it does not push the booking action off the first screen.
- Real photos should scale without pushing key detail out of view.

## 12 Tool-Neutral Implementation Notes

These notes work for any coding agent, design tool, or developer.

- Build on a light surface with one dark text token at 4.5:1 and one desaturated accent token reserved for primary actions.
- Set an 18px body and a legible type scale, with no critical text below 16px.
- Use soft, simple shadows for depth on cards only, kept as CSS rather than image assets.
- Standardize status to color plus text plus icon, never color alone.
- Meet 4.5:1 for body text, 3:1 for large text and UI components, and 44px touch targets.
- Respect prefers-reduced-motion and keep motion functional.
- Serve right-sized images and avoid heavy background media, so the page stays fast on older devices.

Ethics hold throughout: no fake urgency, no fake scarcity, and no invented testimonials. Where trust needs support, use honest proof such as real clinician credentials and clear next steps, never manufactured claims.
