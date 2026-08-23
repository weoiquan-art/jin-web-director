# Agent development workflow: small, reviewable changes

## Default loop

For a meaningful change, use:

> Issue → Inspect → Plan → Modify → Test → Review → PR or release

The Issue can be a GitHub issue, a taskboard item, or a concise task note. Its purpose is to isolate one outcome, not create bureaucracy.

## Scope examples

Prefer separate work items such as:

- Hero hierarchy;
- mobile hero and navigation;
- project-card behavior;
- a single scroll interaction;
- SEO metadata and share image;
- image and bundle performance;
- deployment troubleshooting.

Avoid “redesign the whole website” unless the product, information architecture, and technical base are all explicitly being replaced with user approval.

## Before modification

- inspect the current repository and relevant project memory;
- name the affected pages/components and the non-goals;
- propose the smallest viable approach;
- note whether content, design, responsiveness, accessibility, performance, or deployment verification is required.

## During modification

- preserve the project’s existing architecture where possible;
- use focused commits that describe real user-facing change;
- keep unrelated cleanup separate;
- do not commit credentials, raw production data, or generated build output unless the repository intentionally tracks it;
- link a PR or release note to evidence: screenshots, test/build result, and affected viewport states.

## Review gate

Before a PR or release, ask:

1. Is the product intent still clear?
2. Did the change create a new visual or interaction inconsistency?
3. Does mobile work as an intentionally designed surface?
4. Are keyboard, focus, reduced-motion, and error states covered where relevant?
5. Did the build and delivery route actually pass?
6. Is the diff small enough that someone else can review and reverse it?

## Knowledge governance

When a shipped decision is worth repeating, add it to the project’s documentation or to this Skill’s lessons file with evidence. If a rule is only a taste preference or an unverified guess, keep it as a preference/hypothesis instead of promoting it to a hard rule.
