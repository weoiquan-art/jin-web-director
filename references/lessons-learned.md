# Verified lessons from JIN website work

These are local operating lessons derived from `JIN_网站搭建方法论_弯路与技巧复盘_v1.0.docx` and `網站搭建方法論.md`. They are not universal laws; they prevent known categories of failure.

## Project direction and content

| Observed lesson | Prevention rule |
| --- | --- |
| Multiple site concepts can be blended into one page before the primary job is frozen. | Start each release with one audience, one primary site task, one CTA, and explicit exclusions in `PRODUCT.md`. Move old direction into history rather than leaving it on the live page. |
| Effects can be added before visitors understand the offer. | Make the static hierarchy and real proof work before adding animation. |
| Public knowledge does not remove the value of a course/service. | Sell structure, saved trial-and-error, templates, real examples, support, and updates—not secrecy. |
| Local-business and course ideas have different purchase journeys. | For local business, prioritize verified service/contact/location information. For a course, validate interest and payment/fulfillment before building a complex platform. |

## Source, build, and deployment

| Observed lesson | Prevention rule |
| --- | --- |
| A Vite `index.html` or deploy artifact is not a complete development project. | Handoff the project root/source package with `src`, `public`, package manifest, lockfile, config, and project docs. |
| Source ZIP and deploy ZIP are easy to confuse. | Name and retain separate source and deploy packages; deploy output has `index.html` and assets at its first level. |
| Local changes do not automatically change the live site. | Record the primary deployment route, run the build, deploy intentionally, and open the real URL afterward. |
| Git-connected deploy and manual upload can be confused. | Choose one primary production route and document alternate previews clearly. |
| A temporary AI workspace or chat attachment is not durable project ownership. | Keep source-of-truth code in a local project and versioned Git repository; keep a change log and handoff package. |
| A generic build error code does not prove a root cause. | Preserve the exact failing command/log, classify facts versus hypothesis, then apply the smallest verified correction. |

## Responsive, media, and motion

| Observed lesson | Prevention rule |
| --- | --- |
| Desktop grids and auto-rotating galleries can become unusable on mobile. | Design mobile reading/order/touch behavior at the same time; use horizontal scroll or a simpler layout when it better fits. |
| Motion can interfere with inspection and touch. | Pause on hover/focus where relevant; provide reduced motion; do not auto-reorder mobile content without a reason. |
| Images can break layout or crop badly when their dimensions are uncontrolled. | Define aspect behavior and object position per meaningful image before visual polish. |

## Handoff and evidence

| Observed lesson | Prevention rule |
| --- | --- |
| A future agent cannot reliably reconstruct intent from HTML alone. | Maintain `PRODUCT.md`, `DESIGN.md`, `DEPLOY.md`, and `CHANGELOG.md` beside the project. |
| “It should work” is not release evidence. | Provide build output, verified URL, version/commit, known gaps, and deployment route in the handoff. |
| Third-party principles can be useful but may not fit the project exactly. | Attribute the source, translate it into JIN’s language, and only promote it to a rule after it helps a real project decision. |

## Evidence levels

### 2026-09-06 — Generated artwork and ink entrances

An attempted transparent raven cutout returned RGB with a baked checkerboard. It was rejected after inspecting the actual channels. The site instead uses the approved raster, a separate dark plate and a native SVG brush reveal. Mobile review also found I/N wrapping and the old signature escaping its crop; nowrap and source-proportioned cropping resolved them. See [brand-ink-entrance.md](brand-ink-entrance.md) for evidence boundaries and reusable checks. JIN's specific appearance and 2.04-second timing remain project preferences.

- **Confirmed:** observed in project files, conversations, build logs, release behavior, or explicit user decision.
- **Reusable rule:** a prevention rule extracted from repeated/clear local evidence.
- **Hypothesis:** a likely diagnosis awaiting source/log confirmation; never present it as proven fact.
- **Future route:** a proposed capability or business plan that must be revalidated before implementation.
