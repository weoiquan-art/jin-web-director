# Video-first film archive homepage

Use this reference when a supplied film is the homepage's primary experience and later films will continue as large vertical previews.

## Evidence boundary

This case comes from the 2026-09-28 JIN Motion homepage in [`video-web`](https://github.com/weoiquan-art/video-web). The supplied Hero source was a 15-second, 1280×720, 24 fps H.264/AAC character film. The static HTML, CSS and JavaScript passed source checks and an independent hosted preview published successfully. Cloudflare Pages deployment and physical-device review remained user-owned follow-up; do not present them as completed evidence.

## Product decision

- Treat the film as the product surface, not as decoration behind a generic landing page.
- Keep identity, film title, essential metadata and one viewing action in the first viewport.
- Preserve vertical document flow from the start when more films are planned. A single-screen reference with `overflow: hidden` is structurally incompatible with a growing archive.
- Keep retired website directions in explicit exclusions so a future agent does not blend them back into the current site.

## Place interface around the footage

Inspect representative frames before placing copy. Record where faces, hands, subtitles and high-contrast motion repeatedly appear. Put persistent copy in a stable safe region and use a directional overlay only where readability needs it.

Do not inherit centered text merely because a visual reference used it. A centered headline can cover the subject for most of a character-led clip. Re-evaluate `object-position`, title placement and overlay strength separately for desktop and mobile because `object-fit: cover` changes the visible composition.

## Playback contract

Use this baseline for decorative-autoplay Hero films:

- `autoplay muted loop playsinline` for the initial video;
- an explicit user gesture to unmute and start audible playback;
- a visible way to leave immersive viewing, plus Escape on desktop;
- a useful static information layer when autoplay fails;
- reduced-motion handling for interface animation without hiding the film or controls.

Keep video state in one function so the desktop control, mobile control and immersive CTA cannot disagree about whether sound is active.

## Typography and hierarchy

Changing the typeface is a system change, not a single CSS substitution. Define separate display and interface roles, load licensed web fonts through a durable route, and provide system fallbacks. Let the film provide most of the color; reserve typography and controls for hierarchy and action.

Metadata should describe the actual asset—duration, aspect ratio, frame rate and generation tool—rather than invented popularity or client proof.

## Repository and Cloudflare Pages handoff

For a no-build static site, keep `index.html`, CSS, JavaScript, project memory and provider headers at the publish root. Document the exact media path and verify that the binary exists before release; text source can look complete while the Hero still returns 404.

For a first small film, committing the original asset can be acceptable. As the archive grows, move versioned video assets to Cloudflare R2, Stream or another deliberate media origin instead of letting the source repository become the long-term video library. Record the chosen media origin and cache policy in `DEPLOY.md`.

Minimum post-deploy checks:

1. Hero loads on desktop and mobile.
2. Autoplay begins muted and loops.
3. Sound starts only after the user action.
4. Immersive mode has a working exit.
5. Mobile crop preserves the subject.
6. Scrolling reaches the next-film region.
7. The real production URL has no missing media or font requests.

## Reusable prevention rules

| Observed risk | Prevention rule |
| --- | --- |
| A visual reference dictates text placement without regard to the supplied footage. | Inspect several frames and place persistent UI around the film's attention zones. |
| A one-viewport prototype later needs more films. | Keep page scrolling enabled and make each film a repeatable full-scale section. |
| Desktop cover crop is accepted as mobile behavior. | Verify and tune `object-position` at mobile width from the real footage. |
| Autoplay audio is assumed to work. | Start muted and treat sound as an explicit user-controlled transition. |
| Source files are committed but the video binary is absent. | Verify the exact production media URL before calling the release complete. |
