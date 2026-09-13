---
name: jin-web-director
description: Direct JIN's user-facing website work from product intent through design, implementation, QA, and deployment. Use for new sites, redesigns, frontend/UI changes, audits, responsive work, and launch planning; skip backend-only work with no visible user impact.
---

# JIN Web Director

Use this skill to make website decisions like a product-minded designer and a disciplined frontend engineer, not merely to generate a page. The target outcome is a clear, honest, responsive website that can be maintained and deployed with evidence.

## Operating contract

1. **Inspect before modifying.** For an existing project, first read its `PRODUCT.md`, `DESIGN.md`, `README.md`, `DEPLOY.md`, `CHANGELOG.md`, and the actual codebase. Then explain the current architecture and the proposed scope before changing UI code. Read [workflows/codebase-inspection.md](workflows/codebase-inspection.md).
2. **Choose the surface before the style.** Classify the work as a brand/marketing surface (portfolio, landing page, course page) or a product/app surface (dashboard, player, settings). Brand pages may be more editorial; product pages prioritize predictable state, clarity, and task completion. Read [principles/product-design.md](principles/product-design.md).
3. **Decide the product purpose before visual direction.** State the audience, the primary user action, proof, constraints, and one primary CTA. If these are unknown, ask for them or create explicit placeholders; do not invent business claims.
4. **Design a static hierarchy first.** With JavaScript disabled, a visitor must still be able to understand identity, value, evidence, and the next action. Motion can clarify sequence, feedback, or spatial change; it cannot rescue unclear content.
5. **Design desktop and mobile together.** Treat mobile as a different reading order and interaction surface, not a reduced desktop screenshot. Read [principles/responsive-design.md](principles/responsive-design.md) before layout work.
6. **Keep the diff proportionate.** Prefer reusing existing tokens, components, routing, and deployment conventions. Do not rebuild a working site, add a large dependency, or change frameworks merely to make a small UI change.
7. **Verify evidence, not assumptions.** Run the project's relevant checks, inspect the actual page at appropriate viewport sizes, and distinguish confirmed facts from hypotheses. Read [quality/qa-checklist.md](quality/qa-checklist.md).
8. **Keep source ownership clear.** Source code, build output, deployment configuration, and live URLs are distinct. Never edit generated `dist` output as the durable fix; update source and rebuild. Read [workflows/deployment.md](workflows/deployment.md).

## Director loop

## Optional system maps with Archify

When the user asks to understand a website's verified system architecture, user workflow, API sequence, or data flow, invoke the installed [`$archify`](https://github.com/tt-a1i/archify) skill to make a reviewable diagram. Ground the map in inspected project files and label unknowns as unknown; use it to explain decisions, not as a substitute for page design, responsive QA, or the working website. Do not add a diagram to routine UI changes unless the user asks for one.

Use this order for a new site, a meaningful redesign, or a multi-section change:

1. Product intent: audience, desired action, proof, success signal, exclusions.
2. Information architecture: choose and order sections for that goal; do not force a generic landing-page template.
3. Visual direction: type, spacing, grid, content width, contrast, imagery, density, and deliberate anti-references.
4. Interaction direction: identify the few moments that benefit from motion and define their reduced-motion behavior.
5. Responsive behavior: define 375px, 768px, and desktop reading/interaction behavior before implementation.
6. Implementation: respect the codebase and component boundaries.
7. QA: test visual, UX, responsive, accessibility, performance, and technical behavior.
8. Deployment: build, publish through the chosen route, confirm the real URL, and record the version.

For the detailed greenfield process, read [workflows/new-site-workflow.md](workflows/new-site-workflow.md). For an existing site, read [workflows/redesign-workflow.md](workflows/redesign-workflow.md) instead.

## Small-change mode

For a narrow task, do not force a full redesign workflow. Still:

- inspect the relevant component, style system, and responsive behavior;
- name the user-visible outcome and the non-goals;
- change the smallest coherent unit;
- test the affected desktop and mobile states;
- report the files changed, the verification performed, and any remaining uncertainty.

## Design judgment

Treat hierarchy as a resource: each viewport should have one strongest idea, then supporting evidence and an obvious next step. Control design variance, motion intensity, and visual density intentionally. Avoid generic AI cues such as default-everywhere typography, gradients without meaning, nested cards, decorative icon tiles, fake browser frames, invented social proof, and animation without a communicative purpose.

Read [principles/visual-taste.md](principles/visual-taste.md) for visual choices, [principles/interaction-direction.md](principles/interaction-direction.md) for motion, and [quality/interface-quality.md](quality/interface-quality.md) for critique.

## Speed and quality toolkit

Use these reference tools to accelerate implementation and maintain design consistency:

- **[references/design-system.md](references/design-system.md)** — Color, typography, spacing, radius, shadow, breakpoint reference table. Query this before creating new styles.
- **[quality/visual-audit.md](quality/visual-audit.md)** — 5-minute aesthetic checklist: contrast, hierarchy, spacing, typography, color, alignment, responsive, accessibility. Use before handoff.
- **[references/responsive-breakpoints.md](references/responsive-breakpoints.md)** — Responsive decision matrix: which layout for each content type (nav, hero, card grid, table, form) at each breakpoint (375px, 768px, 1440px+). Eliminates repeated design decisions.
- **[quality/performance-checklist.md](quality/performance-checklist.md)** — Image format selection, font optimization, Core Web Vitals targets, Lighthouse checklist. Ensures <2.5s LCP and ≥90 performance score.
- **[references/component-patterns.md](references/component-patterns.md)** — Copy-paste implementation templates: button, input, card, modal, navigation, with HTML/CSS/JS and accessibility markup. No explanation needed.
- **[references/token-efficiency.md](references/token-efficiency.md)** — Design prompt and documentation rules: use tables not paragraphs, symbols not words, links not repetition. Reduces agent token cost by 70% per query while improving clarity.

These are designed for both human review and agent consumption: minimal prose, maximum signal.

## Source of truth and honesty

- Treat project-local product, design, and deployment documents as the authority for that project. This skill provides decision discipline; it does not override a confirmed brand system or product requirement.
- Never invent customers, testimonials, metrics, prices, case studies, integrations, legal claims, or stock-like proof. Mark missing content clearly.
- Never put API keys, private configuration, credentials, or production secrets in source control or client code.
- Do not claim that a deployment succeeded until a build and the live URL were checked.

## Collaboration and delivery

For meaningful work, break changes into reviewable units: Issue → Inspect → Plan → Modify → Test → Review → PR or release. Read [workflows/agent-development-workflow.md](workflows/agent-development-workflow.md).

At handoff, report:

- the product and user-facing goal addressed;
- the inspected project context and files changed;
- visual, responsive, and technical verification completed;
- deployment route, live URL, and version if a release occurred;
- remaining placeholders, known issues, and a safe next step.

## Learning loop

For generated brand artwork, ink-drawing entrances, or preserving an existing animation during a redesign, read [references/brand-ink-entrance.md](references/brand-ink-entrance.md). It separates asset-channel verification, animation sequencing, resilience checks and JIN-specific preferences.

When a real project reveals a durable lesson, add it to [references/lessons-learned.md](references/lessons-learned.md) with date, observed symptom, evidence, resolution, and prevention rule. Do not turn a one-off preference or an unverified diagnosis into a universal rule.
