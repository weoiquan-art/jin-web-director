# Performance: preserve the visitor’s attention and device budget

## Set a budget before adding effects

An animation, font, video, image, or library must earn its cost. Define what it contributes to product understanding or the brand experience, then choose the lightest implementation that reaches that goal.

## Media rules

- Use the smallest useful image dimensions and modern formats supported by the project’s existing pipeline.
- Give images intrinsic dimensions or an aspect-ratio strategy so loading does not shift layout.
- Avoid loading decorative video or large assets before content necessary for the first decision is available.
- Use responsive image sources and lazy loading where they do not delay meaningful first-view content.
- Treat hero media as a critical design decision: optimize it deliberately rather than blindly lazy-loading it.

## Motion and JavaScript

- Prefer CSS or the project’s existing animation tool for simple transitions.
- Avoid adding a large library for one reveal, carousel, or parallax effect.
- Animate properties that do not repeatedly recalculate layout where possible.
- Stop unnecessary loops when they are off-screen, paused by the user, or reduced-motion is active.
- Test motion on a mobile-sized viewport; a desktop smoothness result is not enough.

## Fonts and third parties

- Use only the weights/styles needed for the visual system.
- Avoid third-party embeds, trackers, and widgets that do not serve the product goal.
- Document any required external script and provide graceful degradation if it is unavailable.

## Verification

Use the project’s available diagnostics and browser evidence to inspect load behavior, layout shift, heavy assets, console/network failures, and bundle changes. Record the before/after decision when a performance-sensitive change adds visible value. Do not optimize a metric while breaking reading order, accessibility, or content integrity.
