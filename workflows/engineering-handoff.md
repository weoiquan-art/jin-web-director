# Hand off website engineering to `for-coding-`

Use this when JIN Web Director has identified a website's user goal, scope and checks, and a separate engineering skill would help with the code. Read the target project's own instructions first. [`weoiquan-art/for-coding-`](https://github.com/weoiquan-art/for-coding-) is the source repository; linking it does not install its skills or provide access to a running agent. Invoke a named skill only if the current agent has it available or its source has been supplied.

| Task state | Skill from `for-coding-` | What to hand over |
| --- | --- | --- |
| A scoped, approved change with a spec or task tickets | [`implement`](https://github.com/weoiquan-art/for-coding-/blob/main/skills/engineering/implement/SKILL.md) | Project path, user-visible outcome, precise components, exclusions and acceptance checks. This skill implements and commits; follow its own test/review instructions where its dependencies are available. |
| An observed bug or performance regression | [`diagnosing-bugs`](https://github.com/weoiquan-art/for-coding-/blob/main/skills/engineering/diagnosing-bugs/SKILL.md) | The exact symptom, repeatable action, browser/environment, baseline and a safe redacted artifact. It starts by building a tight pass/fail loop. |
| A requested review of existing code changes | [`code-review`](https://github.com/weoiquan-art/for-coding-/blob/main/skills/engineering/code-review/SKILL.md) | Fixed point (branch or commit), diff/PR, originating spec and repository standards. Check that its issue-tracker setup and parallel review capability are available. |
| A project too large to settle in one agent session | [`wayfinder`](https://github.com/weoiquan-art/for-coding-/blob/main/skills/engineering/wayfinder/SKILL.md) | Destination and issue tracker; it maps decision tickets before implementation. Do not use it for an ordinary component edit. |

Handoff note for a site task: `PRODUCT.md` goal and audience; actual assets and content gaps; `DESIGN.md` behavior and responsive states; affected code paths; exact acceptance and accessibility checks; existing test commands; deployment route. Keep credentials out of the note.

On return, use [site QA](../quality/qa-checklist.md) to check the rendered result and [deployment workflow](deployment.md) to distinguish code, build, preview and release. Attach the verified commit, environment, viewport/input coverage, known limits and any live URL to the project's QA/changelog. `for-coding-` supplies engineering process; JIN Web Director remains responsible for the site's content, visual intent and visitor-visible acceptance.
