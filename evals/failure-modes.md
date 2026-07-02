# Failure Modes

Purpose: the fifteen ways a deployed Senior UI/UX Product Designer Agent degrades, how to detect each, and how to correct it. Use this with [eval-rubric.md](./eval-rubric.md) and [test-cases.md](./test-cases.md).

## 1. Generic advice

Signs: findings with no element and no reason. Example: "The layout could be cleaner and the spacing needs work."

Why it happens: the agent pattern-matches to common critique language instead of reading the specific screen.

Detection: for each finding, ask "which element, what change, and why?" If any answer is missing, the finding is generic.

Correction: enforce the finding format (Where, What, Why it matters, Fix, Severity). Fail Specificity in the rubric.

## 2. Overdesigning

Signs: a rebuild proposed for small problems. Example: "I recommend a full redesign with a new visual language across the whole product."

Why it happens: the agent equates helpfulness with volume of change.

Detection: ask "does the scope of the fix match the size of the problem?"

Correction: require a What Already Works list and scope fixes to the real problems. See TC-12 and the Restraint dimension.

## 3. Blindly applying trendy UI

Signs: a trend applied because it is current. Example: "Add glassmorphism everywhere, it is what modern apps use."

Why it happens: the agent treats novelty as quality.

Detection: ask "is the style justified by product, audience, and trust, or by the trend itself?"

Correction: ground every style choice in product reasoning and include Styles to Avoid. See TC-03 and Mode 9 must-haves.

## 4. Ignoring mobile

Signs: a full review with no mobile findings. Example: "Everything looks good on the desktop layout." with no phone view considered.

Why it happens: the agent reviews the first artifact it sees and stops.

Detection: ask "are there real mobile findings, not one throwaway line?"

Correction: keep mobile always in scope. Fail Coverage. See TC-07.

## 5. Ignoring accessibility

Signs: no contrast, target size, keyboard, or label findings. Example: "No accessibility concerns." with no basis given.

Why it happens: accessibility is treated as optional or out of scope.

Detection: ask "did it check contrast, targets, keyboard, and labels, and frame limits honestly?"

Correction: keep accessibility always in scope with heuristic framing and a manual test list. See TC-08.

## 6. Ignoring the user goal

Signs: advice that never mentions who uses the product. Example: "Make the hero bigger and add more sections."

Why it happens: the agent optimizes for looks over the user's task.

Detection: ask "does each finding trace to what the user is trying to do?"

Correction: anchor findings to the stated user. Fail Product grounding.

## 7. Ignoring the business goal

Signs: advice that ignores what the product must achieve. Example: "This is prettier now." with no link to the conversion or task goal.

Why it happens: the agent treats the screen as art, not a tool with a job.

Detection: ask "does the advice move the stated business goal?"

Correction: anchor findings to the business goal. Fail Product grounding.

## 8. Fake claims

Signs: invented data, metrics, or research. Example: "Studies show this change lifts conversion by 30 percent."

Why it happens: the agent fills gaps with plausible-sounding numbers.

Detection: ask "is every number and citation backed by the provided input or a named source?"

Correction: never invent analytics, research, or predicted numbers. Automatic fail. See TC-06.

## 9. Tool-specific output when not requested

Signs: output locked to one framework or tool without being asked. Example: "Add this Tailwind class to the div."

Why it happens: the agent defaults to a familiar stack.

Detection: ask "would this read the same regardless of framework or tool?"

Correction: keep output tool-neutral unless the user names a stack. Fail Format compliance. See TC-09.

## 10. No prioritization

Signs: a flat list with no severities. Example: a bullet list of ten issues with no order and no labels.

Why it happens: the agent lists observations without weighing them.

Detection: ask "does every finding carry a severity and is the fix list ordered?"

Correction: require severities and an ordered fix list. Missing severity in an audit is an automatic fail.

## 11. Missing implementation brief

Signs: a Mode 10 output missing sections. Example: a brief with no acceptance criteria and no tokens.

Why it happens: the agent summarizes instead of specifying.

Detection: ask "are all 15 sections present with real values?"

Correction: require the full 15 sections, tokens with values, and tool-neutral wording. See TC-09.

## 12. Missing interaction states

Signs: components defined only in the default state. Example: a button spec with no hover, focus, active, disabled, or error.

Why it happens: the agent describes the resting look and forgets behavior.

Detection: ask "are default, hover, focus, active, disabled, and error all defined?"

Correction: require full state coverage in Modes 7 and 10. See TC-11.

## 13. Missing copy improvement

Signs: copy issues ignored or left vague. Example: a headline of "Synergize your workflows" passed over with no rewrite.

Why it happens: the agent treats copy as outside its remit.

Detection: ask "were unclear labels, headlines, and empty states rewritten concretely?"

Correction: rewrite copy with a Location, Current, Improved, Why table and preserve meaning. See TC-10.

## 14. No uncertainty handling

Signs: confident claims beyond the input. Example: "The checkout flow is smooth." from a single static screenshot.

Why it happens: the agent hides the limits of what it was given.

Detection: ask "did it state what it could not see and mark those dimensions Provisional or Not scored?"

Correction: state input limits, label assumptions, and mark Provisional or Not scored. See TC-02.

## 15. Style recommendation without product reasoning

Signs: a style picked with no product basis. Example: "Use a neon dark theme, it looks great."

Why it happens: the agent recommends by taste, not fit.

Detection: ask "is the style tied to product, audience, and trust, and are trust-sensitive categories restrained?"

Correction: ground every style in product, audience, and trust reasoning. See TC-03 and Mode 9.

## Quality checklist before delivering any review

- [ ] Findings carry severities (Critical, High Impact, Medium Impact, Polish).
- [ ] Every finding names a location.
- [ ] Assumptions are labeled and clarifying questions number three or fewer.
- [ ] Mobile is covered with real findings.
- [ ] Accessibility is covered with heuristic framing and a manual test list.
- [ ] A What Already Works list is present in audits.
- [ ] No invented data, metrics, research, or predicted numbers.
- [ ] No dark patterns; manipulative asks are refused with an honest alternative.
- [ ] Output is tool-neutral unless a stack was named.
- [ ] Next actions are clear and ordered.
