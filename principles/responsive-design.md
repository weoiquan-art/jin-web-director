# Responsive design: recompose, do not shrink

## Design behavior at the same time as layout

For every module, define desktop and mobile behavior while it is designed:

- reading order;
- navigation and CTA placement;
- image crop and aspect ratio;
- card stacking or horizontal scroll;
- type wrapping and content measure;
- sticky/scroll behavior;
- motion/reduced-motion behavior;
- empty, long-content, and missing-image states.

Do not wait until the desktop page is “finished” to add media queries.

## Reference viewport checks

| Viewport | Primary question |
| --- | --- |
| 375px | Is the one-column reading path clear, touchable, and free from forced horizontal scrolling? |
| 768px | Do intended two-column modules still have enough space, or should they remain single-column? |
| 1440px and wider | Does extra space improve composition and breathing room without expanding body copy into an unreadable measure? |

Use additional real device widths when the audience or analytics justify them. Do not treat these three checks as the only supported widths.

## Mobile baseline

- Keep primary touch targets comfortably reachable; aim for at least 44px where a control is directly touched.
- Use input text that does not trigger unwanted mobile zoom; 16px is a practical starting point for common mobile browsers.
- Guard against horizontal overflow caused by large media, long words, fixed widths, transforms, or grid children. Use `minmax(0, 1fr)` and sensible wrapping where needed.
- Choose image crops deliberately. Do not accept accidental face, product, or text clipping simply because the desktop ratio does not fit.
- Convert dense desktop rows into a readable sequence before hiding meaningful content.
- Avoid auto-advancing content on touch surfaces unless it has an accessible pause/stop control and is clearly useful.

## Responsive verification

At each target size, inspect:

1. heading wrapping and hierarchy;
2. CTA visibility and touch reach;
3. navigation, focus order, and menu state;
4. image crop, video ratio, and content order;
5. card stack, grid collapse, and horizontal scrolling;
6. sticky sections and animated regions;
7. long text, missing assets, and error states.

Responsive quality is not a screenshot exercise. Interact with the real page, then correct the design rules rather than patching random pixels.
