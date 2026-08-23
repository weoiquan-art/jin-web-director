# QA checklist: verify the website people actually use

Use the relevant parts of this list after every meaningful page or release. Check real rendered pages; code review alone is not sufficient.

## Visual

- [ ] The first viewport has a clear primary message and next step.
- [ ] Heading scale, line length, line height, alignment, and spacing create a readable hierarchy.
- [ ] Images have intentional crop/aspect behavior; important faces, objects, and text are not clipped.
- [ ] Component treatments are consistent and no unnecessary nested-card or decorative pattern has appeared.
- [ ] Empty, long, and missing-content states remain legible.

## UX and content

- [ ] Primary CTA is visible and appropriate; secondary actions do not compete.
- [ ] Navigation labels and page destinations match user expectations.
- [ ] Forms show labels, validation, errors, and success state where relevant.
- [ ] Content, figures, logos, testimonials, and claims are confirmed rather than invented.
- [ ] Links, controls, toggles, and media interactions were actually used in the preview.

## Responsive and accessibility

- [ ] 375px, 768px, and desktop layouts have been inspected for order, wrapping, crop, overflow, and reachability.
- [ ] Keyboard navigation, focus visibility, enter/escape behavior, and dialog/menu close paths work where relevant.
- [ ] Semantic structure, text alternatives, contrast, labels, and status communication are present.
- [ ] `prefers-reduced-motion` removes nonessential motion and preserves understanding.
- [ ] Browser zoom/reflow and long labels do not hide content or controls.

## Technical and release

- [ ] The appropriate install/lint/test/build commands passed, or known failures are reported exactly.
- [ ] Console errors, broken links, and missing media were checked.
- [ ] Images and fonts are sized/loaded deliberately; unnecessary dependencies and bundle cost were considered.
- [ ] Deployment configuration and the intended source/deploy route were checked.
- [ ] The published URL was opened after deployment and matches the expected version/build stamp.
- [ ] `CHANGELOG.md` / release notes include the user-visible change, verification, and known follow-up.
