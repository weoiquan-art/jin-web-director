# Visual taste: hierarchy, restraint, and intentional variation

## Use three design dials

Set these before visual implementation. They are project choices, not scores of quality.

| Dial | Low end | High end | JIN default guidance |
| --- | --- | --- | --- |
| Design variance | stable grid, conventional composition | asymmetry, overlap, editorial composition | portfolio can be medium; task-heavy UI should remain lower |
| Motion intensity | static, focus/hover feedback only | scroll scenes, layered transition, strong choreography | use low-to-medium by default; escalate only for a defined narrative reason |
| Visual density | generous space, few ideas per viewport | compact controls or data | portfolio/marketing stays low-to-medium; dashboard-like tools may be denser |

Record the dials and the reason in `DESIGN.md`. A design should feel deliberate even when it is quiet.

## Build hierarchy before decoration

Each viewport needs one clear strongest element. Then establish a supporting order:

1. primary message or task;
2. the proof or explanation that earns attention;
3. the CTA or next state;
4. tertiary detail only when the visitor needs it.

Use type scale, line length, weight, spacing, contrast, crop, and composition to create this order. Do not try to create hierarchy by making every heading huge, every card raised, or every word accented.

## Composition and typography

- Choose text widths for reading, not the maximum desktop width. Wide screens may support broad composition while body copy remains narrow.
- Establish display, body, and UI roles. A type system needs a reason for contrast; it does not need many fonts.
- Treat large type as composition: weight, line-height, measure, wrapping, and surrounding empty space decide whether it feels intentional.
- Use spacing as a rhythm. Related content sits together; a larger gap signals a conceptual change.
- Use cards only when a boundary, state, comparison, or interaction requires one. Do not wrap every paragraph in the same rounded container.
- Let images have an explicit role: evidence, narrative scene, product detail, or atmosphere. Set crops per image when needed so faces and meaningful objects are not accidentally cut.

## Anti-template audit

Treat these as prompts to inspect, not as a prohibited color or component list:

- default typography everywhere with no brand reason;
- decorative blue-purple gradients, glow, or glass layers without information purpose;
- cards inside cards, or a rounded-square icon tile above every section title;
- excessive small explanatory text that repeats the heading;
- a visual treatment applied uniformly to every section;
- fake browser/device frames when a real screenshot would communicate better;
- emojis used as a substitute for a coherent icon system;
- imaginary metrics, testimonials, client logos, or case studies.

If a pattern supports the actual brand, product, or content, it may be valid. The question is whether it earns attention.

## Critique sequence

Use this sequence during a design review:

1. **Critique:** identify hierarchy gaps, template cues, unclear product intent, and visual inconsistencies.
2. **Distill:** remove or quiet elements that do not improve comprehension or brand expression.
3. **Typeset / layout:** correct measure, grid, alignment, visual rhythm, contrast, and image treatment.
4. **Adapt / harden:** check mobile, long copy, empty states, keyboard access, slow media, and reduced motion.
5. **Polish:** adjust the final high-leverage details only after the structure works.

Do not respond to a hierarchy problem by adding more cards, gradients, small labels, or animation.
