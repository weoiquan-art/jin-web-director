# Redesign workflow: improve the existing site without erasing its context

## 1. Establish the baseline

Read project documents and use [codebase-inspection.md](codebase-inspection.md). Capture screenshots or a usable preview at relevant viewports. Identify what the existing implementation already proves: routes, components, content, design tokens, build route, and release history.

## 2. Diagnose the real problem

Classify the request before proposing a solution:

- product clarity: audience, promise, proof, or CTA is unclear;
- information architecture: order or grouping hides the decision path;
- visual hierarchy: type, spacing, contrast, crop, or component treatment is flat;
- responsive behavior: desktop decisions break on touch screens;
- interaction: motion competes with reading or fails to clarify state;
- technical quality: build, asset, accessibility, or performance issue.

Do not call for a full redesign before naming which category is failing and why.

## 3. Critique, then distill

Identify the five highest-leverage issues. Remove redundant decoration, repeated copy, card nesting, or animated noise before adding features. Preserve real product proof and confirmed brand decisions.

## 4. Plan a small sequence

Break the redesign into reviewable changes, for example:

1. hero hierarchy and primary CTA;
2. mobile hero and navigation;
3. evidence/project cards;
4. one narrative interaction;
5. accessibility and performance cleanup.

Each change should have an expected user-visible outcome and test plan. Avoid a giant AI-generated change that mixes copy, layout, routing, libraries, and deployment at once.

## 5. Implement and compare

Maintain component and token consistency. Recheck pages at target viewports, keyboard navigation, and reduced motion. Compare against the original requirement, not merely against the previous screenshot.

## 6. Handoff

Report the diagnosis, what was intentionally removed or preserved, test evidence, and remaining risks. Update project docs if the product direction or visual system changed.
