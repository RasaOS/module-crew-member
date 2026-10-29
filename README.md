# module-crew-member

**Version:** 0.1.0 · `rasa.module.crew.member` · public

The **member tier** of a galt crew, as a RasaOS module: the member tier of a galt crew (galt ADR 0042, 0050, 0052): member cards, each a role a lead hires (scout, auditor, builder, tester, reviewer and the rest), plus the engineering standard every writer builds to.

A crew has three tiers, each its own module: [`module-crew-manager`](https://github.com/RasaOS/module-crew-manager) → [`module-crew-lead`](https://github.com/RasaOS/module-crew-lead) → [`module-crew-member`](https://github.com/RasaOS/module-crew-member).

## The cards (`content/crew/members/`)

| Card | When | Source |
|---|---|---|
| `scout` | to map the ground first: the files, conventions, tests and traps a change touches | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `auditor` | first for every request: to read the code and the prior art and write the audit before anyone plans | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `builder` | to turn an item into working code in the shared worktree | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `tester` | to write and run the tests that show an item done | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `reviewer` | to read what landed for correctness, missed cases and risk | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `designer` | the request changes anything the person sees | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `architect` | the request crosses a package, system, data or contract boundary, or the plan calls it architectural | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `manager` | more than one request is open, or more than three members | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `security` | the request touches auth, roles, rules, secrets, personal data, uploads or a dependency | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `writer` | the request ends in a PR, a decision, or a doc the change makes stale | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `contracts` | the request touches a data model, a bus message, an API shape or a shared type | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `adversary` | every request the person did not mark trivial | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `devops` | the request touches rules, functions, hosting, CI, environment or a deploy | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `calculator` | the request needs a number worked out: it writes, runs and saves a script for every calculation | galt `router/src/crew/roles.ts` + bus-contract `CREW_BASE_ROLES` at `737a098` |
| `data-analyst` | the ask needs numbers worked out from data: a calculation, a comparison, a table of figures, a trend or a check of someone else's number | RasaOS/module-crew `content/crew/members/data-analyst.md` at `f6fea0d` |
| `medical-researcher` | the ask is a medical or health question to be researched: a condition, a treatment, a drug, a symptom, a test or what the evidence says | RasaOS/module-crew `content/crew/members/medical-researcher.md` at `f6fea0d` |
| `recruiting-analyst` | the ask is sports recruiting research: programs, rosters, requirements, timelines, contacts or what a player needs to do next | RasaOS/module-crew `content/crew/members/recruiting-analyst.md` at `f6fea0d` |
| `summarizer` | findings exist and need to become the deliverable the person asked for: a summary, a brief, a report, a comparison or a short answer | RasaOS/module-crew `content/crew/members/summarizer.md` at `f6fea0d` |
| `web-researcher` | the ask needs facts from the web: a lookup, a comparison, current information, a list of options with their sources | RasaOS/module-crew `content/crew/members/web-researcher.md` at `f6fea0d` |

A card is one markdown file: `key: value` header lines, a blank line, then the conduct (galt ADR 0052 D1, `tags:` from ADR 0054 D2). `{files}` and the like in a member body are filled by galt's member prompt.

## Using it

- **Install into a repo** (the brain layer): the cards land in `.claude/crew/members/`, where galt finds a repo's own cards.
- **Load into a session:** `.claude-plugin/plugin.json` makes the repo loadable (galt ADR 0064).
- **Source of truth today:** galt's in-code copies (`packages/router/src/crew/`) are what runs. This repo is a snapshot of them until galt reads its cards from here, with its code as the fallback.

## Changing a card

Change it here in a PR. `bin/check-cards` must be GREEN (`RASA_SCHEMA_DIR=~/rAI/rasa-os/schema bin/check-cards`). Bump the version: patch for wording, minor for a new card or header key. Until galt reads from here, mirror the change into galt's copy.
