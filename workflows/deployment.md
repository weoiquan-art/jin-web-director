# Deployment: source, build, hosting, and domain are different things

## The four layers

| Layer | Examples | Responsibility |
| --- | --- | --- |
| Source | `src`, `public`, `package.json`, lockfile, config, docs | editable, versioned project truth |
| Build | `npm install` → `npm run build` | produces deployable assets and exposes dependency/config errors |
| Deploy artifact | `dist/index.html`, assets, favicon | the generated output a static host serves |
| Live environment | provider URL, preview URL, custom domain | the visitor-visible release |

Changing a local source file does not update the live site. Downloading or editing an old deploy artifact is not a durable source change. Fix source, rebuild, then release through the defined route.

## Source of truth

- Use a Git repository as the normal source of truth for code and project memory.
- Keep hosting provider ownership separate from repository ownership. A provider is a deployment surface, not the only copy of the project.
- Keep domain registrar/ownership and renewal information separate from both source and host.
- Store deployment configuration in the repository. Store secret values only in the host’s environment-variable settings or another approved secret manager.

## Choose one primary release route

### Git-connected deploy

Use when the site will evolve and a stable URL should track reviewed commits.

1. Push the reviewed change to the connected repository/branch.
2. Let the host run the documented build command and publish directory.
3. Read the deploy result and visit the real URL.
4. Record commit/version and release evidence in `CHANGELOG.md`.

### Manual direct upload

Use for a quick static preview or a site intentionally maintained without Git-based auto-deploy.

1. Build locally.
2. Upload only the deploy artifact with `index.html` and assets at its first level.
3. Record the uploaded file name, date/version, generated URL, and verification result.

Do not silently mix these routes. If both exist, explicitly state which is production and which is a temporary preview.

## React + Vite baseline

For a typical React + Vite project, source lives in `src`/`public`, `npm run build` creates `dist`, and a static host should publish the built output. The project’s actual scripts and provider configuration are authoritative; inspect them rather than assuming exact filenames or host settings.

## Delivery and recovery

- A continuing developer needs the complete source project, not only `index.html` or a deployment ZIP.
- When delivering manually, keep a source package and a deploy package distinctly named with version/date. Source normally excludes `node_modules` and generated output; deploy contains the built output.
- Before release, verify the exact published URL, build stamp/version, key navigation, mobile behavior, and no accidental missing asset.
- When a live site looks stale, identify the chosen release route, the actual deployed commit/artifact, cache/service-worker behavior, and the provider’s build log before changing code.
- Treat an exit code or visual symptom as a clue, not a confirmed root cause. Preserve the full failing command/log and make the smallest validated correction first.
