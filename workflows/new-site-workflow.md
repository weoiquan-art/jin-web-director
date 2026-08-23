# New-site workflow: eight directed phases

## Phase 1 — Product intent

Create or complete `PRODUCT.md`.

- audience and entry context;
- site type and product/brand surface;
- one-sentence promise;
- unique primary CTA;
- proof available now;
- success signal;
- scope exclusions and unknowns.

Do not design a hero before this is usable. If a project has more than one business idea, decide which one this release serves and put the others in a roadmap.

## Phase 2 — Information architecture

List the sections that lead a visitor from understanding to action. Start with content and evidence, not components. A typical list may include hero, proof, value, work/product, services, story, CTA, and footer, but remove or reorder any block that does not support the goal.

Deliverable: a section outline with the purpose of each section and the CTA it supports.

## Phase 3 — Visual direction

Create `DESIGN.md` before or alongside implementation.

- surface, brand traits, and anti-references;
- type roles, color roles, spacing rhythm, grid, content width, image treatment;
- visual-density, design-variance, and motion-intensity settings;
- desktop, mobile, and reduced-motion behavior.

Choose a small number of memorable visual anchors. Do not default to neon, blue-purple gradients, glass cards, glow borders, or giant headings merely because they look “technological.”

## Phase 4 — Interaction director

For each proposed motion moment, state its communicative job. Prioritize motion only when it clarifies hierarchy, process, feedback, spatial transition, or storytelling. Make a static version understandable first, then specify fallback and reduced-motion behavior.

## Phase 5 — Responsive design

Define desktop and mobile behavior for every major section. Validate at 375px, 768px, and desktop before calling the static layout complete. Reorder and simplify modules for small screens instead of shrinking them indiscriminately.

## Phase 6 — Implementation

- choose the simplest established stack that suits the project;
- use semantic HTML, accessible controls, and component boundaries that match the content model;
- reuse components and tokens rather than cloning markup;
- avoid unnecessary dependencies;
- keep secrets out of source and client bundles;
- keep generated build output separate from source.

## Phase 7 — QA

Use [quality/qa-checklist.md](../quality/qa-checklist.md). Inspect the real rendered site, not only generated code. Correct the highest-impact hierarchy, usability, or responsive problem before cosmetic polish.

## Phase 8 — Deployment

Create `DEPLOY.md`, choose one primary release route, run a production build, publish, verify the live URL, and record version/commit/known follow-up in `CHANGELOG.md`. See [deployment.md](deployment.md).
