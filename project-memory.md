# Project memory template

Copy the relevant sections into a website project root. Keep project facts here, rather than expecting a future agent to infer them from the code.

## PRODUCT.md

```md
# Product

- Audience:
- Site type: portfolio / marketing / course / local-business lead generation / product UI / other
- One-sentence promise: For [audience], this site helps them [action] by [proof].
- Primary CTA:
- Success signal:
- Confirmed proof and content:
- Explicit exclusions for this release:
- Unknowns or placeholders that must not be invented:
```

## DESIGN.md

```md
# Design direction

- Surface: brand/marketing or product/app
- Brand traits (three to five):
- Anti-references / patterns to avoid:
- Type roles: display / body / UI
- Color roles: background / text / primary action / accent / status
- Layout: content width, grid, spacing rhythm, radius, border/shadow rule
- Visual density (1–10):
- Design variance (1–10):
- Motion intensity (1–10):
- Image treatment and crop rules:
- Desktop behavior:
- Mobile behavior:
- Reduced-motion behavior:
- Accessibility commitments:
```

## DEPLOY.md

```md
# Deployment

- Source-of-truth repository and default branch:
- Framework and build command:
- Publish directory:
- Hosting provider and production URL:
- Preview route:
- Domain owner and renewal location:
- Environment variables: names only, never secret values
- Release trigger: Git push / manual upload / other
- Verification steps after release:
- Rollback method:
```

## CHANGELOG.md

```md
# Changelog

## YYYY-MM-DD — version or short commit
- User-facing change:
- Files / components changed:
- Build / test evidence:
- Live URL or preview:
- Known follow-up:
```

## Maintenance rule

Update these files whenever the product goal, visual system, deployment route, or version changes. A new agent should be able to understand the project without relying on a chat history.
