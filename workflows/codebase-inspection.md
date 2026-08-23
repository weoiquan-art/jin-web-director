# Codebase inspection: inspect first, modify second

Use this before any change to an existing site. The goal is to understand what already works and preserve useful structure.

## Inspect in this order

1. **Project root and documentation** — read `README.md`, `PRODUCT.md`, `DESIGN.md`, `DEPLOY.md`, `CHANGELOG.md`, and any repo-local `AGENTS.md`.
2. **Framework and commands** — identify the framework, package manager, scripts, runtime requirements, and how to start/build/test the project.
3. **Routing and entry points** — locate pages, layouts, route definitions, public entry files, and any client/server boundaries.
4. **Component hierarchy** — map major components, shared UI, content modules, and state ownership.
5. **Styling system** — identify CSS architecture, utility framework, modules, tokens, theme files, typography, and component variants.
6. **Assets and content** — find images, video, fonts, CMS/content files, data shape, alt-text conventions, and image optimization behavior.
7. **Dependencies** — distinguish existing necessary libraries from unused or legacy packages; do not add a replacement before understanding the current one.
8. **Responsive behavior** — locate breakpoints, responsive components, mobile navigation, layout shifts, and known overflow risks.
9. **Deployment configuration** — inspect hosting config, build command, output directory, environment-variable names, redirects, domains, and preview/release route.
10. **Current evidence** — run the smallest safe local command(s) needed to establish a baseline: tests, lint, build, and/or a visual preview.

## Report before modification

Reply with a concise inspection note containing:

- stack and package-manager command;
- route/page and component(s) relevant to the request;
- styling/tokens and responsive pattern already in use;
- deployment route and any constraints;
- confirmed facts versus unknowns;
- proposed change scope and explicit non-goals.

If the user’s request conflicts with a confirmed project convention, surface the tradeoff before changing it.

## Inspection does not mean analysis paralysis

For a one-line copy or color fix, inspect only the relevant context. For navigation, a component redesign, responsive work, or a deployment issue, inspect the full set above. The required depth follows change risk.
