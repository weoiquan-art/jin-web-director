# Viscose JIN: site setup and browser verification

Date: 2026-09-25. Scope: the [Viscose JIN fork, draft PR #1](https://github.com/weoiquan-art/Viscose-JIN-fork/pull/1). This is a case study for adapting an interactive portfolio template when the project already has a WebGL scene and GSAP timeline. The [project QA record](https://github.com/weoiquan-art/Viscose-JIN-fork/blob/56782bba6719bb0e8fd3a1ca8c3542431286e92d/QA.md) is the source for checks and remaining limits; this reference does not certify a public release.

## Set up the work

1. Inspect the existing repository's `AGENTS.md`, README, license, build scripts, shaders, component boundaries and asset paths. Identify what must be preserved. In this case, retain the upstream MIT notice and the Viscose shader/GSAP interaction; remove unlicensed demo media and font use.
2. Set the audience, portfolio purpose, primary action and content scope in project-local `PRODUCT.md` and `DESIGN.md`. Obtain real artwork and contact destinations. Mark missing Sera costume views and the Facebook cover explicitly instead of filling them with invented images.
3. Keep the visible content, ring order, URL slugs and media paths in one project data map (`components/ring/projects.js` in this case). Use that map for the index, details and social/contact actions so changing one item does not silently change its meaning elsewhere.
4. Keep a readable HTML catalogue when JavaScript or WebGL is unavailable. Let reduced-motion visitors reach the content without waiting through an intro. Provide keyboard controls, focus return from media dialogs, direct links and history navigation; open external video links with `noopener noreferrer`.
5. Build and lint, then test the actual rendered site. A successful Next.js build cannot prove that a browser compiled the GLSL or that the entrance timeline finishes. Check console output, layout, media playback and close behavior, keyboard/touch/wheel input and unavailable-media fallbacks.

## The animation failure that changed the QA rule

Under local Chromium software WebGL, the opening animation moved much more slowly than expected although build and lint passed. Inspecting GSAP timeline state exposed ticker lag smoothing and a pause marker as relevant mechanisms. In the draft, `gsap.ticker.lagSmoothing(0)` is set for the scene and the prior behavior restored on cleanup; resuming removes the active pause before playing. Browser checks then observed the intro reach the first card. Treat this as a project-specific fix to verify against actual timing, not a rule to disable lag smoothing globally.

The draft QA covered Chromium at 360, 640, 1024 and 1512px; 1024px wheel interaction ran at device pixel ratio 0.5 to reduce software rendering load. It also checked deep-link refresh/history, reduced motion, no JS/WebGL catalogue, two local film dialogs, Escape and focus return. The [full QA record](https://github.com/weoiquan-art/Viscose-JIN-fork/blob/56782bba6719bb0e8fd3a1ca8c3542431286e92d/QA.md) still calls for physical-device visual review.

## Preview and release boundary

- Keep `npm run build`/lint, a GitHub commit or PR, a host preview URL and a production URL as separate evidence.
- A Vercel preview requires the actual Vercel project/deployment; running `npx vercel ai-gateway setup` configures an AI Gateway client and does not deploy this website.
- This case had local browser QA and a draft PR. As recorded in the project QA, Vercel preview and publication were still pending. Recheck the host's deployment log, exact commit, public URL and critical interactions before marking it released.

For assigning code implementation or diagnosis while keeping the site acceptance criteria intact, read [engineering-handoff.md](../workflows/engineering-handoff.md).
