# Product design: purpose before interface

## Decide what the site is for

Before choosing a hero, visual style, component library, or animation, write a short product brief:

- Who is arriving on this site?
- Why did they come now?
- What single action matters most for this release?
- What proof makes that action believable?
- What must not be claimed, shown, or built yet?
- How will success be observed?

Use this sentence when scope is unclear:

> For **[audience]**, this site helps them **[action]** by showing **[credible proof]**.

If the sentence cannot be completed, do product clarification before visual design. A polished page with an undefined action is not a successful page.

## Classify the surface

| Surface | Typical JIN use | Primary design priority | Common failure |
| --- | --- | --- | --- |
| Brand / marketing | portfolio, course sales page, service page, local-business lead page | clarity, belief, a memorable but restrained brand impression | treating every section like a generic SaaS template |
| Product / app | course player, learner account, dashboard, form flow | predictable tasks, state clarity, legibility, resilient behavior | using marketing-page motion and decoration where utility should dominate |

A site may contain both surfaces, but each route or section should identify which one leads. Do not make an account settings screen behave like a portfolio hero.

## Information architecture follows the goal

Select, omit, and order sections based on the brief. The following are ingredients, not a mandatory landing-page order:

- Hero: what it is, who it is for, and the primary CTA.
- Trust or proof: real work, outcomes, credentials, process, quotes with permission, or specific evidence.
- Problem and value: the visitor’s situation and the relevant offer.
- Portfolio / product / curriculum: enough detail to evaluate fit.
- Services / delivery model / pricing context: only when it helps the decision.
- Case study or about: context that strengthens trust rather than repeats the hero.
- Final CTA and footer: the next step and essential contact/legal information.

For a portfolio, lead with work and a clear route to collaboration. For a course, lead with outcome, sample, structure, credibility, and a low-friction next step before building a complex members area. For a Google Maps or local-business site, prioritize real service area, offer, contact route, hours, and credible local proof over elaborate features.

## Product decision rules

- One page normally has one primary CTA. Secondary actions must not compete visually with it.
- The first viewport should answer identity, relevance, and the next action within a few seconds.
- Proof must be real and attributable. If proof is not available, use an explicit placeholder or reduce the claim.
- A new section earns its place by changing understanding or helping a decision. Delete repetition.
- Separate current release scope from future ideas. Put future memberships, payments, portals, or automation in a roadmap; do not imply they already exist.
- Capture decisions in the project’s `PRODUCT.md` before large work starts.

## Product review prompts

Before approving a major page change, ask:

1. Does a new visitor know what to do next?
2. Is the primary claim supported by something concrete?
3. Is the CTA appropriate to the visitor’s stage of trust?
4. What content could be removed without losing the decision path?
5. Are we optimizing a user journey, or merely decorating a page?
