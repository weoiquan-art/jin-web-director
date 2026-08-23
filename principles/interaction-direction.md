# Interaction direction: motion must communicate

## Decide whether motion is needed

Before adding an animation, complete this sentence:

> This motion helps the visitor understand **[hierarchy / change / process / spatial relation / feedback]**.

If it cannot be completed, keep the information static. The default state of a marketing page is not “animated”; it is readable and responsive.

## Appropriate jobs for interaction

- reveal a sequence or a change in state;
- guide attention through a story or case study;
- clarify an input, transition, success, error, or loading state;
- show depth or spatial relation where it improves meaning;
- support a limited, chapter-like progression in a portfolio or campaign.

## Narrative scrolling, translated for practical sites

The Kage reference is useful as a lesson in chapter structure, depth, scene change, and progressive reveal. Translate that inspiration into web constraints:

- Use scroll-driven sections only when the content has a genuine sequence.
- Prefer a few memorable beats over full-page continuous spectacle.
- A sticky layout must earn the extra scroll distance by revealing a meaningful state or comparison.
- Layer media, copy, and foreground detail only when their depth communicates a relationship.
- Keep a complete static reading path. The content cannot depend on the animation finishing.

## Implementation guardrails

- Define start, end, and interruption behavior for each significant animation.
- Respect `prefers-reduced-motion`: remove loops, parallax, and nonessential transitions; reveal content immediately.
- Do not hijack scroll, block browser navigation, or make a user chase an unstable layout.
- Avoid autoplay motion that competes with reading or touch gestures. On mobile, prefer explicit interaction or simple horizontal scroll where appropriate.
- Animate compositor-friendly properties when possible and avoid layout thrash from repeated measurement or style changes during scroll.
- Test low-power/mobile behavior and reserve heavy visual effects for a clear business or narrative gain.

## Known JIN pattern: four-image sequence

When a visual gallery needs lightweight movement:

- desktop may use a slow, stable, non-layout-shifting sequence;
- hover and keyboard focus pause the sequence so the visitor can inspect;
- mobile uses intentional horizontal scroll with snap rather than automatic reordering;
- reduced-motion disables the loop and shows every image directly;
- image dimensions and crop behavior are fixed before animation is added.

## Review questions

1. What information becomes clearer because of this motion?
2. Does it work when reduced motion is enabled?
3. Does mobile keep control of scroll and touch?
4. Can the page still communicate if the animation fails or JavaScript is unavailable?
5. Is this the smallest interaction that creates the desired effect?
