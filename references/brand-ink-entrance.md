# Brand artwork to a short ink entrance
Date: 2026-09-06. Evidence: JIN Studio, static weoiquan-art.github.io source and local browser QA.

## When to use
A website uses generated brand art and a stroke-by-stroke entrance. This is a reference for that handoff, not a requirement to animate every website.

## Decisions grounded in this case
- Verify actual image channels before planning layers. A visible checkerboard is not evidence of alpha transparency. Our requested transparent cutout returned RGB with a baked checkerboard and was rejected.
- Assign separate jobs to illustration and animation. Preserve the approved artwork as the settled state. A generated unmarked dark plate plus a native SVG mask can provide a controlled drawing sequence; disclose any differences between the two images.
- To draw a letter, animate a mask along its path. Fading in the complete letter does not meet a request to draw it from a specified starting point.
- A white brush can use tapered geometry, bristle gaps and restrained edge texture. Review at its actual mobile display size; an overly clean vector curve can lose the requested ink character.
- Write one timeline with named timing responsibility, then test the visible order. Do not let decorative typography appear before the principal gesture has completed.
- Keep a static readable document, bounded image loading and an independent script-failure release. Test the missing-library, missing-image, missing-main-script and reduced-motion paths.
- When preserving an existing animation but changing the entrance order, retain its actual geometry and lifecycle behind a clearly labelled replay action. Stop frame loops when finished, hidden or interrupted.
- Judge responsive composition by actual viewport geometry. The observed mobile I/N wrapping was fixed with nowrap; signature cropping was tied to source-image aspect ratio.

## JIN-only decisions
JIN approved Studio positioning, the raven replacing J beside large I/N, white ink starting at the neck, and a quick dark-to-warm-white entrance. The implemented timeline lasts 2.04 seconds after the images are ready. These are project choices, not universal timing or aesthetic rules.

## Verification limits
Local browser checks cover desktop/mobile layouts, replay and fallback behavior. Reduced motion was simulated by a local-only matchMedia fixture, not a native OS preference override. Real-device frame rate and field Core Web Vitals were not measured. Source, workflow success, HTTP availability and visual review must be reported separately.

## Source
- [GSAP timeline](https://gsap.com/docs/v3/GSAP/Timeline/)
- [Website source](https://github.com/weoiquan-art/weoiquan-art.github.io)
- The project's DESIGN.md and QA.md contain the detailed implementation and evidence.
