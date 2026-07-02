# Interaction States Checklist

Purpose: Check that every component defines the states users actually meet, and that hover, focus, loading, error, and empty states all behave.

How to use: Used by Mode 2 Full Audit section 14 and any component review (see [modes.md](./modes.md)). Each item is pass or fail. Mark N/A honestly when a state does not apply to a component. Any unchecked item becomes a finding with a severity: Critical, High Impact, Medium Impact, or Polish.

## State matrix
Mark each cell required, optional, or n/a for the component under review.

| Component | Default | Hover | Focus visible | Active | Disabled | Loading | Error | Success | Empty |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Button | req | req | req | req | opt | opt | n/a | n/a | n/a |
| Link | req | req | req | req | opt | n/a | n/a | n/a | n/a |
| Text input | req | opt | req | n/a | opt | opt | req | opt | n/a |
| Select | req | opt | req | n/a | opt | opt | req | opt | n/a |
| Checkbox and radio | req | opt | req | req | opt | n/a | req | n/a | n/a |
| Card as link | req | req | req | req | opt | n/a | n/a | n/a | n/a |
| Navigation item | req | req | req | req | opt | n/a | n/a | n/a | n/a |
| Modal | req | n/a | req | n/a | n/a | opt | opt | opt | n/a |
| Toast | req | opt | opt | n/a | n/a | n/a | req | req | n/a |
| Table row | req | opt | req | opt | opt | opt | opt | opt | req |
| Tab | req | req | req | req | opt | opt | n/a | n/a | n/a |
| Accordion | req | opt | req | req | opt | n/a | n/a | n/a | n/a |

## Buttons and links
- [ ] Hover changes appearance on pointer devices.
- [ ] Focus is visible for keyboard users.
- [ ] An active state acknowledges the press.
- [ ] A disabled state explains itself through nearby context, not a tooltip alone.
- [ ] A loading state disables double submit and shows progress in the button.
- [ ] Destructive actions require confirmation.
- [ ] The hover and focus states differ enough to tell pointer and keyboard apart.
- [ ] Button size and label do not shift between states, avoiding layout jump.
- [ ] A disabled control still reads as the same control, not as plain text.
- [ ] The loading state keeps the button width so surrounding layout stays put.

## Inputs and forms
- [ ] The focus state is distinct from the hover state.
- [ ] A filled field looks distinct from an empty one.
- [ ] Inline validation fires on blur for most fields, not on every keystroke.
- [ ] The error state names the problem and how to fix it.
- [ ] A success confirmation appears where the stakes justify it.
- [ ] Disabled and read-only are used correctly and not interchangeably.
- [ ] An error does not clear the value the user already typed.
- [ ] The character or selection limit is shown before the user hits it.

## System states
- [ ] Loading uses skeletons or spinners consistently, with copy for waits over about 2 seconds.
- [ ] Empty states explain what belongs here and offer the first action.
- [ ] Error states say what happened, what was saved, and what to do next.
- [ ] Success states confirm and point to the next step.
- [ ] Offline or failed-fetch conditions are handled visibly.
- [ ] A first-use empty state differs from a no-results-after-search state.
- [ ] A partial-error state shows which items failed and which succeeded.

## Motion
- [ ] Micro-interaction transitions run 150 to 300ms.
- [ ] Easing is consistent across similar transitions.
- [ ] Motion communicates cause and effect rather than decorating.
- [ ] Reduced motion removes nonessential animation via prefers-reduced-motion.
- [ ] Nothing important is conveyed by motion alone.
- [ ] A state change animates from its start point rather than snapping.
- [ ] Looping or parallax motion can be stopped or is disabled under reduced motion.

## Touch and keyboard parity
- [ ] Every hover-revealed control has a touch and keyboard path.
- [ ] Long-press and swipe actions have visible alternatives.
- [ ] Escape and outside-click close overlays consistently.
- [ ] Drag-and-drop has a click or keyboard alternative for the same result.
- [ ] Tooltips that carry needed information are also reachable by keyboard focus.

## Overlays and transient states
- [ ] Toasts stay long enough to read and can be dismissed by the user.
- [ ] Opening a modal traps focus inside it until it closes.
- [ ] A second overlay does not stack in a way that hides how to close the first.
- [ ] Closing any overlay returns focus to the control that opened it.

## Common Critical failures
- [ ] A control with no visible focus state, unusable by keyboard.
- [ ] A submit button with no loading state, allowing duplicate submissions.
- [ ] An error state that does not say what went wrong or how to recover.
- [ ] An empty state that looks like a broken or failed screen.
- [ ] A function available only on hover, with no touch or keyboard path.
- [ ] A destructive action that fires with no confirmation.
- [ ] An overlay that cannot be closed by Escape or an outside click.
