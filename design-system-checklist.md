# Design System Checklist

Purpose: Check that a design system has the tokens, components, and rules a team needs to build consistent screens without one-off decisions.

How to use: Used by Mode 7 Design System Builder and Mode 2 Full Audit section 17 (see [modes.md](./modes.md)). Each item is pass or fail. Mark N/A honestly when an item does not apply to the system under review. Any unchecked item becomes a finding with a severity: Critical, High Impact, Medium Impact, or Polish.

## Color tokens
- [ ] Components use semantic names such as background, surface, text-primary, accent, and danger, not raw hue names.
- [ ] Light and dark values exist where dark mode is supported.
- [ ] Every text-on-surface pair passes its contrast requirement (4.5:1 body, 3:1 large).
- [ ] One accent color is reserved for primary actions only.
- [ ] Status colors for success, warning, and danger are defined and reused.
- [ ] No component introduces a color outside the token set.

## Typography tokens
- [ ] A named scale defines px values such as 12, 14, 16, 18, 20, 24, 30, 36, 48.
- [ ] Weights are limited to about three.
- [ ] Line heights are defined per size.
- [ ] One or two families are used, each with a declared fallback stack.
- [ ] Body size on mobile is at least 16px in the token set.
- [ ] Heading and body roles map to named scale steps, not arbitrary sizes.
- [ ] A maximum line length is defined to keep text within 45 to 75 characters.

## Spacing and layout tokens
- [ ] Spacing follows a 4 or 8px scale with named steps.
- [ ] Container widths and breakpoints are declared.
- [ ] Grid columns and gutters are declared.
- [ ] No one-off spacing values such as 13px or 27px appear in components.
- [ ] The same named step is used for equivalent gaps across components.
- [ ] A vertical rhythm step governs spacing between stacked blocks.

## Shape and elevation
- [ ] Radius steps are named and limited to about three plus a pill.
- [ ] Shadow levels are named and limited to about three.
- [ ] Border widths and colors are consistent.
- [ ] Elevation is used to signal layering, not decoration.
- [ ] The same radius is applied to related components, such as inputs and buttons.
- [ ] Focus outlines are defined as a token, not redrawn per component.

## Components
- [ ] Each core component exists once with variants, not near-duplicates: button, input, select, checkbox radio switch, card, modal, table, navigation, badge, alert, tabs, accordion, toast, empty state, skeleton.
- [ ] Each component defines its full state set.
- [ ] Each component documents when to use it and when not to.
- [ ] Component names are consistent between design files and code.
- [ ] Variants are true options of one component, not separate copies.
- [ ] Each component lists its required and optional properties.

## Rules
- [ ] Button hierarchy is defined: one primary per view, with secondary and tertiary specified.
- [ ] Icons come from one library at consistent sizes.
- [ ] Imagery rules are documented.
- [ ] A voice is defined for labels and error messages.
- [ ] Capitalization style for labels and headings is defined and applied.
- [ ] Date, time, and number formats are standardized.

## Responsive rules
- [ ] Each component's behavior at breakpoints is documented.
- [ ] Touch target adjustments on mobile meet the 44px practical minimum with 8px gaps.
- [ ] Density modes are defined if the system uses any.
- [ ] Tables have a defined behavior on narrow screens, such as stack or scroll.
- [ ] Navigation has a defined mobile pattern, not a shrunken desktop menu.

## Accessibility defaults
- [ ] Focus styles are built into components, not added per page.
- [ ] The input component API requires a label.
- [ ] Contrast requirements are baked into the color tokens.
- [ ] Interactive components ship with correct roles and states by default.
- [ ] Icon-only components require an accessible name through their API.
- [ ] Motion in components respects prefers-reduced-motion by default.

## Governance-lite
- [ ] Tokens live in one source of truth.
- [ ] Components are documented with do and do not examples.
- [ ] A rule for new components exists: reuse first, then extend, then create.
- [ ] Each component names an owner or maintainer.
- [ ] Deprecated components are marked with a recommended replacement.
- [ ] Design and code use the same token names so handoff stays aligned.

## Common Critical failures
- [ ] Components hardcode colors and spacing instead of using tokens.
- [ ] Token color pairs that fail contrast are shipped as defaults.
- [ ] Multiple near-duplicate versions of the same component exist.
- [ ] Components ship with no defined focus style.
- [ ] The spacing scale is ignored, producing one-off values across screens.
- [ ] No single source of truth, so tokens drift between files and tools.
