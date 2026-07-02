# Redesign Direction: Shiftline Landing Page

Mode: 3 Redesign Direction
Input provided: Current landing page copy pasted as text, plus the business goal.
Note: All products, people, and numbers in this example are fictional.

Shiftline is shift-scheduling software for independent restaurants. The stated goal is to book product demos. This direction rebuilds the page structure and reasoning around one skeptical, time-poor reader, not around a trend. The current copy was provided as text; no analytics, traffic, or conversion data was given, so nothing here predicts a number. Every recommendation is a design decision tied to the reader and the goal.

## 1 Product Goal

Book demos with independent restaurant owner-operators. Every section either moves the reader toward one demo action or removes a reason to hesitate. Success is watched as the demo-request completion rate after the change, never a predicted number.

## 2 Target User

A restaurant owner-operator checking a phone between services. In practice this reader is:

- Impatient, with a minute or two at most before the next table or delivery.
- Skeptical of software, having been sold tools that promised ease and did not deliver.
- Price-sensitive, running on thin margins and wary of another monthly bill.

They decide fast and leave faster. They want to know what it does, whether it fits a small team, and what it costs, in that order, before they will give up an email for a demo.

## 3 UX Strategy

The primary task is requesting a demo. The shortest honest path is:

- State the outcome in the hero and offer one demo action immediately.
- Answer the owner's real questions in order: does it work like my day, how hard is setup, what does it cost, why trust you.
- Keep each answer short enough to read between services, since that is when the reader arrives.
- Repeat the one primary action down the page so it is always in reach.

One primary action only. No competing CTAs, no newsletter box stealing attention, nothing that asks the reader to decide between two things at once. Every scroll should either build a reason to book or remove a reason to hesitate.

## 4 Page or Screen Structure

Ordered sections, each with a job.

1. Hero: state the outcome in the owner's terms and place one demo CTA. Job: earn the next scroll and offer the action immediately.
2. The problem in the owner's words: name the pain of paper schedules and last-minute text messages. Job: prove the page understands their day.
3. How it works in three steps: import staff, build the week, publish to phones. Job: show it is simple, not another system to learn.
4. Proof: two or three named quotes from independent operators and a plain logo row if real. Job: reduce risk with honest evidence.
5. Pricing transparency: show the plan and price, or a clear range and what sets it. Job: respect a price-sensitive reader who will not chase hidden numbers.
6. Objections: setup time, switching cost, support, and what happens to current schedules. Job: remove the last reasons to stall.
7. Final CTA: repeat the demo action with a one-line reminder of the outcome. Job: capture the reader who scrolled to the end.

## 5 Visual Design Direction

- Clean, light interface with generous spacing, so the page never feels dense or busy.
- A single warm accent used only for the primary action and key highlights, so the demo button is always the most obvious thing to click.
- Real photos of small restaurant teams and actual schedules, not stock boardrooms, so the page looks like it is made for this reader.
- Large, legible type that reads well on a phone held at arm's length in a busy room.

The look should feel calm and practical, like a tool that respects a busy person's time, not a pitch that wants their attention.

## 6 Modern UI Style Recommendation

Recommended: a restrained, clean light UI with one warm accent color. It reads as trustworthy and easy, which suits a skeptical operator on a small screen. Avoid Dark Premium SaaS: a dark, high-contrast look signals a product aimed at engineers and enterprises, not a restaurant owner between services, and it can feel cold for a hospitality audience. Avoid Glassmorphism: heavy blur and transparency reduce readability on a phone in a bright kitchen and add cost for no gain here. The job is clarity and speed, so the style stays quiet and legible.

## 7 Design System Foundation

- Color: one neutral surface family, one dark text color meeting 4.5:1 on the surface, and one warm accent reserved for the primary action. Do not use the accent for body text.
- Type: one readable sans family; a clear scale for H1, H2, body, and small; body at 16px minimum on mobile.
- Spacing: a 4 or 8px scale applied consistently.
- Radius and elevation: one small radius and one soft elevation for cards, used sparingly.

## 8 Component List

Needed: hero block with a single CTA button, three-step "how it works" row, proof card with attributed quote, pricing card, objection list as an accordion or plain list, and a repeated CTA block. Removed from the original: the secondary newsletter signup, the auto-rotating feature carousel, and the second competing CTA, all of which split attention from the demo action.

## 9 Interaction States

- Primary CTA button: default, hover, focus visible, active, and disabled while submitting.
- Demo form fields: default, focus, error with a specific message, and success confirmation.
- Accordion for objections: collapsed and expanded, with a visible focus ring.
- Loading state on submit, and a clear success state that states what happens next.

## 10 Mobile Behavior

Design mobile first, since the owner is on a phone. Single column throughout. Hero CTA sits within thumb reach, and a sticky bottom bar can repeat the demo action on scroll. The three steps stack vertically. Pricing stays fully visible, never hidden behind a tap. Tap targets are at least 44px and body text at least 16px.

## 11 Accessibility Requirements

- Body text contrast at least 4.5:1; large text and UI components at least 3:1.
- Every control reachable and operable by keyboard, with a visible focus state.
- Touch targets at least 44px on mobile.
- Form fields have real labels, not placeholder-only labels.
- Respect prefers-reduced-motion; no essential meaning conveyed by motion alone.

## 12 Suggested Copy

- Headline: "Build next week's schedule in minutes, not on a napkin."
- Subheadline: "Shiftline puts your staff schedule on everyone's phone, so you stop chasing shifts by text."
- Primary CTA: "Book a 15-minute demo".
- Section header, problem: "You are still scheduling on paper and group texts."
- Section header, how it works: "Set the week in three steps."
- Section header, pricing: "Simple pricing, shown up front."

## 13 Universal AI Agent Implementation Brief

Goal: build a mobile-first landing page that books demos for an independent restaurant audience. This brief works for any coding agent, design tool, or developer. Build the seven sections in the order above. Use one primary CTA, "Book a 15-minute demo", repeated in the hero and the final block, plus an optional sticky mobile bar. Apply the tokens in section 7: neutral surfaces, one dark text color at 4.5:1, one warm accent reserved for the primary action, 16px minimum body text, a 4 or 8px spacing scale. Remove the newsletter box, the carousel, and any second CTA. Implement the interaction and form states in section 9, including a submit loading state and a success state that names what happens next. Meet the accessibility requirements in section 11. No countdowns, no fake scarcity, no invented testimonials.

## 14 QA Checklist

- One primary action, "Book a 15-minute demo", with no competing CTA.
- Pricing is visible without a tap.
- Proof uses attributed quotes, with nothing invented.
- Mobile: single column, CTA in thumb reach, 16px body text, 44px targets.
- Contrast meets 4.5:1 for body and 3:1 for large text and components.
- Form fields have real labels; error and success states read clearly.
- Motion respects prefers-reduced-motion.
