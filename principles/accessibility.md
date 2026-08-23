# Accessibility: the baseline for a usable interface

Accessibility is part of the design and implementation definition of done. It is not a final compliance layer.

## Build with semantic intent

- Use landmark elements (`header`, `nav`, `main`, `footer`) and heading levels that describe the information hierarchy.
- Use native buttons for actions and links for navigation. Do not turn generic containers into controls unless there is a justified accessible implementation.
- Associate form labels, help text, errors, and required state with the real input.
- Give meaningful images useful alternative text; mark purely decorative images as decorative.
- Use real lists, tables, and controls when the content is a list, comparison, or interaction.

## Keyboard and focus

- Every interactive item must be reachable and operable by keyboard.
- Keep a visible, intentional `:focus-visible` state. Do not remove focus indicators without a clear accessible replacement.
- Focus order must follow the visual/task order, including menus, dialogs, sticky panels, and mobile layouts.
- Dialogs, popovers, and menus need an explicit close path and sensible focus management.

## Readability and perception

- Do not rely on color alone to communicate status, errors, selection, or required fields.
- Check text and control contrast against their actual background states.
- Allow text enlargement and browser zoom without clipping controls or hiding content.
- Support reduced motion; avoid flashing, unnecessary auto-play, and motion that prevents reading.
- Provide captions/transcripts or equivalent information for meaningful audio/video where applicable.

## Test the actual interface

At a minimum, verify keyboard tab/shift-tab/enter/escape behavior, visible focus, form errors, mobile touch targets, zoom/reflow, and reduced-motion behavior. Use automated checks to find issues, but resolve them in the rendered page rather than treating a tool score as proof of usability.
