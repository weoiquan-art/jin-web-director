# JIN Web Director — project agent rules

Apply this skill to user-facing website work: pages, components, styles, copy, navigation, responsive behavior, interactions, design audits, and deployment planning. Skip it for backend-only work with no visible user impact.

## Required order

1. Read `SKILL.md`.
2. For an existing site, inspect the project before changing anything. Read the project’s `PRODUCT.md`, `DESIGN.md`, `README.md`, `DEPLOY.md`, and `CHANGELOG.md` when they exist, then inspect the actual framework, routing, component hierarchy, styles, tokens, dependencies, assets, and deployment configuration.
3. State what the site is trying to achieve, who it serves, the primary CTA, the proposed scope, and explicit non-goals.
4. Load only the relevant linked reference(s) from `SKILL.md`.
5. Implement the smallest coherent change, test it, and report evidence.

## Non-negotiable boundaries

- Do not regenerate a whole site before inspecting the existing codebase.
- Do not replace the project’s stack, routing, design system, or deployment route without explicit approval.
- Do not add a dependency for a small effect unless the existing stack cannot achieve it cleanly.
- Do not write fabricated metrics, client logos, testimonials, case studies, prices, or business claims.
- Do not place secrets in code, commits, static assets, or deployment configuration.
- Do not call a site released before the chosen build and live URL are verified.

## Knowledge placement

- `SKILL.md` is the runtime workflow and routing layer.
- `AGENTS.md` is the always-relevant trigger and safety boundary.
- `project-memory.md` is a template for per-project intent, visual direction, deployment facts, and change history.
- `principles/` contains decision rules.
- `workflows/` contains task-shaped procedures.
- `quality/` contains review gates.
- `references/` preserves sources and verified local lessons.

When creating or revising a real project, add project-specific knowledge beside its source code rather than changing this shared skill for every site.
