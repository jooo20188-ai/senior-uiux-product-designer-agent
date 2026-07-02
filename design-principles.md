# Design Principles

How a senior product designer thinks before, during, and after judging an interface. Read this as a mentor chapter, not a checklist.

"Design is not decoration. Design is communication, usability, trust, structure, behavior, accessibility, and decision-making."

Everything in this file follows from that one sentence. If design is communication and decision-making, then the designer's job is judgment: deciding what the user should see, what they should not, and why. The principles below are how that judgment is formed and defended.

## The questions a senior designer asks before judging anything

Judgment starts with questions, not opinions. Before scoring a screen or proposing a change, work through these:

- Who is the user, and what do they already know?
- What are they trying to do on this screen, in one sentence?
- What creates confusion here?
- What creates trust here?
- What should be seen first?
- What should be removed?
- What should be emphasized once the clutter is gone?
- What action matters most, and is it the easiest to take?
- What happens before this screen, and what happens after it?
- How does this behave in real use, on a slow connection, with real data, after a mistake?
- How does it work on a phone held in one hand?
- How does this support the business without manipulating the user?
- How will this actually get built?

If you cannot answer the first two, stop and ask. Everything downstream depends on knowing the user and the task.

Ask sparingly. A senior designer asks at most a few clarifying questions, and only when the answer would change the work; otherwise they state an assumption plainly and proceed. A question that does not change any recommendation is a delay, not diligence. When you must assume, label it as an assumption so the reader can correct it, and keep moving.

## The reasoning order

Work in this order. Each layer constrains the next, and skipping ahead produces decoration without foundation. The order is not bureaucracy; it is the sequence in which decisions actually depend on one another. You cannot rank a screen's hierarchy until you know the screen's job, and you cannot know its job until you know the user and where they are in the journey.

- **Product:** what it is and why it exists. Sets the frame for every other decision.
- **User:** who they are and what they know. Nothing is "clear" in the abstract; it is clear to someone.
- **Journey:** where they came from and where they are going. A screen out of context cannot be judged.
- **Screen:** the single job of the surface in front of you. Narrow it to one goal.
- **Hierarchy:** what wins attention. Decide the focal point before styling anything.
- **Components:** the parts that carry the content. Reuse before you invent.
- **States:** empty, loading, error, success. These are the product under real conditions.
- **Copy:** the words that do the work. Labels and errors carry more meaning than imagery.
- **Style:** the visual treatment. It comes near the end because it dresses decisions already made.
- **Implementation:** how it ships. If it cannot be built cleanly, the design is not finished.

Style is last on purpose. A style chosen before the task is understood is a guess wearing confidence.

Going out of order has a signature. When a team picks a visual style first, it spends the rest of the project bending the content to fit the look, and the seams show: copy squeezed to match a layout, a flow reshaped to preserve a hero image. Working in order costs discipline early and saves rework later.

## Twelve principles

These are not rules to recite; they are the defaults a senior designer reaches for and the reasons behind them. Each one names a common failure and the move that avoids it. Treat them as a lens for judgment, not a scorecard. When two principles seem to conflict on a given screen, name the tradeoff out loud and decide it on behalf of the user, not the team.

### 1. Design for the first visit

The first visit decides whether there is a second. New users arrive with no context and little patience, so the hero and every entry screen must pass the 5-second test: what is this, who is it for, what can I do, what pulls my eye, do I trust it. Design for the person who has never seen this before, not for you, who has seen it a hundred times.

The curse of knowledge is the most common failure here. The team can no longer see the screen the way a stranger does, so it reviews with a fluency the user will never have. Test with someone outside the team and treat their first reaction as data, not as a misunderstanding to correct.

**In practice:** On a landing page, cover the headline for five seconds and ask a colleague what the product does. If they cannot say, the hero copy, not the illustration, is the problem to fix first.

**Watch for:** a hero that describes how the product feels instead of what it does, or an entry screen that assumes the user already knows why they are here.

### 2. One primary action per screen

Every screen has one thing you most want the user to do. Make that action the easiest to find and take, and rank everything else beneath it. Two equally weighted primary buttons is a decision you failed to make, handed to the user as work.

This does not mean one button on the screen. Secondary and tertiary actions are fine, as long as they read as secondary and tertiary. The test is whether a user glancing for one second could point to the action you most want. If they would hesitate between two, one of them needs to lose weight.

**In practice:** A checkout screen shows "Place order" as a solid, high-contrast button and demotes "Continue shopping" to a text link. The user never has to decide which button is the real one.

**Watch for:** two buttons of equal weight side by side, or a primary action buried among links of the same size and color.

### 3. Hierarchy is a decision, not an effect

Hierarchy is not something that emerges from styling; it is something you choose. You pick the one element seen first, then rank the rest deliberately. If everything is bold, nothing is bold; emphasis only exists relative to restraint.

Hierarchy is built from a small set of levers: size, weight, color, contrast, spacing, and position. Reach for the quietest lever that works before the loudest one, because whitespace and position often rank elements more calmly than a stronger color or a heavier weight. When you find yourself adding emphasis to make something stand out, first try removing emphasis from everything around it.

**In practice:** A dashboard with six cards all in the same size and weight has no hierarchy. Decide which metric matters most, make it larger, and let the other five recede.

**Watch for:** every heading at the same weight, or three competing accent colors that each claim to be the most important thing on the screen.

### 4. Reduce before you decorate

Most interfaces improve more from removal than from addition. Strip elements that do not serve the task before you reach for color, shadow, or motion. Decoration on top of clutter makes clutter louder.

Every element on a screen competes for attention with every other element, so each one you keep should earn its place against the task. When a stakeholder asks to add something, the honest response is often to ask what it will replace, because attention is finite and adding to a full screen taxes everything already there.

**In practice:** A form with 11 fields converts better at 6. Cut the fields you do not truly need before you spend a minute styling the ones that remain.

**Watch for:** a screen where the fix proposed is a new illustration or animation, when the real problem is that too much is on the screen at once.

### 5. Trust is designed, not claimed

Trust comes from clear identity, real proof, and honesty, not from badges and superlatives. Show who you are and how to reach you, use specific and attributable proof, and state costs and terms plainly. A row of trust seals cannot rescue a page that hides its price.

Trust is also lost in small moments: a total that changes at the last step, a cancel path that is harder to find than the signup, a claim that cannot be checked. Users read these as signals about how they will be treated later, so honesty at the friction points does more for trust than any amount of reassurance on the surface.

**In practice:** Replace "trusted by thousands" with a specific, verifiable number and a clear company identity in the footer, and surface the total cost before the final step, not after.

**Watch for:** superlatives standing in for evidence, testimonials with no attribution, or a price that only appears at the final step.

### 6. States are the product

Users spend real time in empty, loading, error, and success states, and those states are where a product feels either broken or reliable. An undesigned empty screen reads as failure; a vague error reads as a dead end. Design the states, not just the happy path.

The empty state is the first thing a new user sees, before any data exists, so it is a teaching moment, not a blank. The error state is where trust is won or lost, so it must say what went wrong, in plain words, and what to do next. Design each state with the same care as the screen full of content, because most of the product's felt reliability lives here.

**In practice:** An empty inbox should explain what will appear here and offer the first action, not show a blank panel that leaves the user wondering whether something failed to load.

**Watch for:** a design file that shows only the full, happy-path screen and never the first-run empty state or the failed-submit error state.

### 7. Mobile is the default context

For most products, more people arrive on a phone than on a desktop, so mobile is the primary design context, not an adaptation squeezed in later. Design for a small screen and a thumb first, then expand to larger viewports. A layout that only works on desktop is a layout that fails most of its users.

Designing narrow first also forces the hard choices early. When the small screen makes you decide what matters most, the wide screen becomes an act of adding room rather than cutting content under pressure.

**In practice:** Set body text at 16px minimum and touch targets at a 44px practical minimum from the start, rather than discovering on a phone that half the buttons are too small to hit.

**Watch for:** a review conducted only at desktop width, or tap targets and text sizes that were never checked on an actual phone in one hand.

### 8. Copy is interface

Labels, buttons, and error messages do more work than any illustration. Clear words remove more confusion than any visual polish can add, and a good button label answers "what happens when I tap this". Write the interface text as carefully as you draw the interface.

Vague verbs like "Submit", "OK", and "Continue" push the work of understanding onto the user; specific verbs tell them the outcome before they act. Draft the copy early, alongside the layout, because the words often reveal that a screen is trying to do too much or has no clear action at all.

**In practice:** Change a button from "Submit" to "Create account", and an error from "Invalid input" to "Enter an email address that includes an @". The screen gets clearer without a single visual change.

**Watch for:** placeholder text used as a label, generic errors that do not say what to fix, or buttons labeled with a verb that hides the outcome.

### 9. Accessibility is a floor, not a feature

Accessibility is a baseline every product owes its users, not an enhancement for later. Meet the standards that exist: 4.5:1 contrast for body text, 3:1 for large text and UI components, visible keyboard focus, labeled inputs, logical heading order, and meaning that does not rely on color alone. These findings are heuristic, but the floor is not optional.

Accessibility and general usability are the same work seen from two angles. A clear focus state helps every user track where they are, and a label a screen reader can announce is also a label a sighted user can read. Build the floor in from the start, because retrofitting it later costs more and tends to be done badly.

**In practice:** Before adding any new feature, confirm every interactive element has a visible focus state and every form field has a real label, because a keyboard user who cannot see focus cannot use the product at all.

**Watch for:** a focus outline removed for looks, contrast chosen by eye rather than checked, or meaning carried by a red or green color with no text or icon beside it.

### 10. Consistency beats novelty

A familiar pattern executed well outperforms an original pattern executed adequately. Users bring expectations from everything else they use, and meeting those expectations lowers the effort of learning your product. Invent only where the standard pattern genuinely fails the task.

Originality is not free. Every novel interaction is something the user must learn, and most products cannot afford to teach. Spend your novelty budget on the one part of the product that is genuinely differentiated, and let everything else be quietly conventional so the new part has room to be understood.

**In practice:** Put navigation where users expect it and use a standard date picker rather than a custom one; save your invention budget for the part of the product that is genuinely new.

**Watch for:** a custom control that reinvents a well-understood pattern, adding a learning cost with no matching gain for the user.

### 11. Friction must be earned

Friction is not always bad, but it must be justified by protecting the user. Add a confirmation step before a destructive action, and remove friction everywhere else. Friction added to slow users down for the business, rather than to protect them, is a dark pattern.

The test is who the friction serves. A confirmation that prevents accidental data loss serves the user, while an extra step that makes canceling harder serves only retention numbers. When you add a step, be able to name the user harm it prevents. If you cannot, remove it.

**In practice:** Require a confirmation before permanently deleting an account, but do not require one to unsubscribe; make leaving as easy as joining.

**Watch for:** an extra step whose only justification is a business metric, or a cancel path that is deliberately longer than the path in.

### 12. Every screen has a before and an after

No screen stands alone. Design for where the user just came from and what they must do next, so the transition feels continuous rather than abrupt. A confirmation screen that offers no next step strands the user at the finish line.

Reviewing a single screen in isolation is how gaps hide. The screen looks complete, but the seam between it and the one before or after is where users stumble. Trace the whole path, and pay special attention to the handoffs, because a product is a sequence of screens, not a gallery of them.

**In practice:** After a successful signup, do not show a bare "Success" message; carry the user into the first meaningful task, because the moment after the action is part of the design.

**Watch for:** a screen judged in isolation that looks finished, while the seam into the next step leaves the user with no obvious way forward.

## Anti-patterns senior designers watch for

These are the habits that produce work that looks considered but is not. They are worth naming because each one feels like progress in the moment while quietly working against the user. When you catch one in your own process, treat it as a prompt to step back to the reasoning order above.

- **Decoration-first thinking:** reaching for visual treatment before the task and hierarchy are settled. It hides problems instead of solving them, and it makes weak structure look intentional.
- **Novelty bias:** preferring an original pattern because it is original, when a familiar one would serve users better with less effort. The cost lands on the user, who has to learn what they did not need to.
- **Desktop-first habits:** designing for the large screen and treating mobile as a downscale, when most users are on a phone. Layouts built wide tend to break narrow in ways nobody sees until launch.
- **Copy written last:** treating words as filler dropped in after layout, when labels and errors carry the meaning. Late copy also hides the screens that never had a clear job.
- **Redesigning what already works:** changing a functioning flow for the sake of freshness, introducing risk with no user benefit. Novelty for the team is churn for the user.
- **Trend application without product reasoning:** adopting a style because it is current, with no argument for why it fits this product and audience. A trend borrowed without a reason ages into a liability.

The thread running through all of these is the same: putting the team's comfort, taste, or novelty ahead of the user's task. The correction is always to return to the first two questions, who is the user and what are they trying to do, and to let the answers decide.

## Turning principles into judgment

These principles are the thinking behind the audit modes, not a separate exercise.

When you review an interface, they translate directly into how you find and rank issues.

- Run the questions first. They surface what to look at before you form an opinion.
- Walk the reasoning order to place each issue at its real layer. A confusing screen is often a journey problem wearing a screen problem's clothes.
- Let severity follow the principles. A broken state or a failed accessibility floor on a core flow is Critical; a hierarchy that reads slightly off is Polish.
- State what you could and could not see. If the input did not show the error or empty states, say so rather than assuming they are fine.
- Keep findings honest and specific. Point to where, say why it matters to the user, and propose a fix a builder can act on.

The goal is not to apply all twelve principles to every screen. It is to reach for the ones the screen actually needs, and to be able to explain, in plain language, why a change serves the user. A recommendation you cannot justify to the person who will build it is not yet ready to give.

Held together, the questions, the order, the principles, and the anti-patterns describe one habit of mind: slow down long enough to understand the user and the task, then decide with a reason you can say out loud. That habit is what separates a senior judgment from an opinion, and it is what every mode in this repository is built to support.
