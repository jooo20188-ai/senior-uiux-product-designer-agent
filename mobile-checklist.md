# Mobile UX Checklist

Purpose: Check that a screen works on a small touch device, with content that fits, targets that are easy to hit, and text that stays readable.

How to use: Used by Mode 5 Mobile UX Fix (see [modes.md](./modes.md)). Each item is pass or fail. Mark N/A honestly when an item does not apply to the screen under review. Any unchecked item becomes a finding with a severity: Critical, High Impact, Medium Impact, or Polish.

## Viewport and layout
- [ ] No horizontal scroll at 360px width.
- [ ] Content order still makes sense when the layout is linearized to one column.
- [ ] Cards stack in an intentional order, not a scrambled one.
- [ ] Safe-area insets are respected on notched devices.
- [ ] The viewport meta tag allows zoom; user scaling is not disabled.
- [ ] Layout holds in both portrait and landscape.

## Hero and first screen
- [ ] The headline and primary CTA are visible without scrolling on a common small viewport.
- [ ] Image crops keep the subject in frame.
- [ ] No full-height hero pushes all content below the fold without a cue to scroll.
- [ ] The headline wraps cleanly and is not cut off on the narrowest target.
- [ ] The CTA is full width or large enough to tap without precision.

## Readability
- [ ] Body text is at least 16px.
- [ ] Line length stays readable and does not run edge to edge.
- [ ] Headings scale down without wrapping into single-word lines.
- [ ] Contrast holds in bright light; avoid low-contrast gray text.
- [ ] Text has horizontal padding from the screen edge so it is not clipped.
- [ ] Tap-to-zoom is not needed to read any primary content.

## Touch
- [ ] Touch targets are at least 44px with 8px gaps (24px is the absolute WCAG 2.5.8 floor).
- [ ] The primary action sits in thumb reach at the screen bottom on tall screens.
- [ ] No function depends on hover.
- [ ] Swipe gestures have a visible alternative control.
- [ ] Adjacent links and buttons are spaced so the wrong one is not tapped.
- [ ] Small icon buttons have an invisible tap area that meets the minimum size.
- [ ] The tap area matches the visible control, with no dead zones around it.

## Navigation
- [ ] The menu is reachable and operable one-handed.
- [ ] The current location is visible.
- [ ] Back behavior is predictable and does not lose the user's place.
- [ ] Sticky elements together use no more than about 20 percent of viewport height.
- [ ] The menu toggle has a clear label or accessible name, not an icon alone.
- [ ] Closing the menu returns the user to the same scroll position.

## Forms on mobile
- [ ] Input types trigger the right keyboard, such as email, tel, and number.
- [ ] Labels sit above fields, not beside them.
- [ ] The layout is a single column.
- [ ] Error messages appear near the field without extra scrolling.
- [ ] Autofill works for name, email, and address.
- [ ] The submit button is not hidden behind the on-screen keyboard.
- [ ] The focused field scrolls into view above the keyboard.

## Media and performance awareness
- [ ] Images are sized for the viewport, not shipped at desktop weight.
- [ ] Video does not autoplay with sound.
- [ ] Heavy blur and shadow effects are tested on a mid-range device.
- [ ] Tap feedback appears within about 100ms.
- [ ] Images reserve their space so content does not jump as they load.
- [ ] A slow connection still shows readable content before media arrives.

## Scroll flow
- [ ] Section order matches the persuasion or task order.
- [ ] No scroll hijacking overrides the native scroll.
- [ ] A back-to-top or persistent action exists on long pages.
- [ ] Footer contact details are tappable as tel and mailto links.
- [ ] Momentum scrolling feels native and does not stutter.
- [ ] A sticky CTA does not cover content the user is trying to read.
- [ ] Pull-to-refresh, if present, does not fire during normal scrolling.

## Orientation and input
- [ ] Content is not locked to one orientation without a stated reason.
- [ ] Pinch-zoom is available on maps, images, and detailed content.
- [ ] Date and time pickers use the native mobile control where possible.
- [ ] Copy, paste, and select work in inputs without custom blocking.
- [ ] Modals and sheets can be dismissed with a visible close control.

## Common Critical failures
- [ ] Horizontal scroll at 360px that clips content or controls.
- [ ] Touch targets so small or crowded that taps miss consistently.
- [ ] Body text below 16px that forces pinch-zoom to read.
- [ ] A function available only on hover, unreachable by touch.
- [ ] Fixed bars that cover most of the viewport and hide content.
- [ ] Wrong input types that surface the wrong keyboard and block entry.
- [ ] Scroll hijacking that traps or disorients the user on a phone.
