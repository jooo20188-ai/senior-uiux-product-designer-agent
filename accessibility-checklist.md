# Accessibility Review Checklist

Purpose: Check a screen or flow against WCAG 2.2 AA so people using keyboards, screen readers, magnification, or reduced motion can complete the core task.

How to use: Used by Mode 6 Accessibility Review and Mode 2 Full Audit (see [modes.md](./modes.md)). Each item is pass or fail. Mark N/A honestly when an item does not apply to the screen under review. Any unchecked item becomes a finding with a severity: Critical, High Impact, Medium Impact, or Polish.

## Contrast and color
- [ ] Body text meets 4.5:1 contrast against its background.
- [ ] Large text (24px, or 18.66px bold) meets 3:1 contrast.
- [ ] UI components, icons, and focus indicators meet 3:1 contrast against adjacent colors.
- [ ] No information is carried by color alone; a shape, icon, or text label repeats it.
- [ ] Placeholder text is not used as the field label.
- [ ] Error states combine an icon or text with color, not color by itself.
- [ ] Text over an image or gradient still meets its contrast target at every point.
- [ ] Link text is distinguishable from body text by more than color, such as underline.

## Typography and readability
- [ ] Body text is at least 16px on mobile.
- [ ] Line length stays within 45 to 75 characters.
- [ ] Line height for body text is about 1.5.
- [ ] Text is real text, not text baked into an image.
- [ ] Content zooms to 200 percent without loss of content or function.
- [ ] Text can reflow to a single column at 320px width without horizontal scroll.
- [ ] Spacing set by the user for line and letter spacing does not clip text.

## Keyboard
- [ ] Every interactive element is reachable and operable by keyboard.
- [ ] Tab order follows the visual and reading order.
- [ ] No keyboard trap holds focus inside any component.
- [ ] A skip link jumps past repeated navigation to main content.
- [ ] Custom widgets follow expected key patterns (arrow keys, Space, Enter).
- [ ] Escape closes overlays, menus, and dialogs.

## Focus
- [ ] A focus indicator is always visible on the focused element.
- [ ] The focus indicator meets 3:1 contrast against the background.
- [ ] The focused element is not fully hidden behind sticky headers or bars (WCAG 2.4.11).
- [ ] Opening a modal moves focus into it; closing returns focus to the trigger.

## Semantics and structure
- [ ] The page has exactly one h1.
- [ ] Headings follow a logical order with no skipped levels.
- [ ] Landmark regions (header, nav, main, footer) are present.
- [ ] Lists are marked up as lists.
- [ ] Buttons perform actions and links navigate; each is used correctly.
- [ ] Data tables use header cells tied to their rows and columns.

## Forms
- [ ] Every field has a visible label that stays visible after entry.
- [ ] Each label is programmatically associated with its field.
- [ ] Required fields are marked in text, not by color or an asterisk alone.
- [ ] Errors are named next to the field and repeated in a summary.
- [ ] Autocomplete attributes are set on name, email, address, and similar fields.
- [ ] No format is demanded without an explanation or example.

## Media and motion
- [ ] Alt text describes the purpose of each meaningful image.
- [ ] Decorative images are marked so screen readers skip them.
- [ ] Video has captions.
- [ ] Reduced motion is honored via prefers-reduced-motion.
- [ ] Nothing flashes more than three times per second.
- [ ] No audio autoplays.

## Screen reader basics
- [ ] Each page has a unique, descriptive title.
- [ ] Icon-only buttons have an accessible name.
- [ ] Status messages (saved, added to cart) are announced.
- [ ] Dynamic content updates are announced politely without stealing focus.
- [ ] The page language is set so pronunciation is correct.
- [ ] Link text makes sense out of context, not a bare "click here" or "read more".

## Manual tests to run
- [ ] Unplug the mouse and complete the core flow with keyboard only.
- [ ] Run a screen reader pass on the core flow.
- [ ] Zoom the browser to 200 percent and confirm nothing is lost.
- [ ] View the screen in grayscale to catch color-only meaning.
- [ ] Set a large system font on mobile and confirm layout holds.

## Common Critical failures
- [ ] Body text below 4.5:1 contrast, making core content hard to read.
- [ ] An interactive control that keyboard users cannot reach or operate.
- [ ] A keyboard trap that prevents leaving a widget or dialog.
- [ ] No visible focus indicator anywhere on the page.
- [ ] Form errors shown by color only, with no text or programmatic link.
- [ ] Images that convey key information with no alt text.
- [ ] Content that flashes more than three times per second.
