# Developer handoff

## Product intent
Keep this a replayable game with short prompts, not a compulsory quiz. Audience: young people learning about their first contracts, budgets and digital safety. Education details belong in optional help or teacher materials. The brand is an independent Telia Challenge concept, not an official partnership.

## Current state
- Three lifestyles with different starting budgets, savings goals and event pools.
- Social and work decisions unlock eligible follow-up events in later months.
- Random event counts include zero and never exceed six per month.
- Editable player names, clear costs, visual cash/happiness/win changes.
- Service switching/cancellation: exit and setup charges now, new billing next month.
- Blocked cards stop spending and savings transfers; scripted refunds notify the player.
- Seeded deterministic rewind preserves recorded events and choices.
- Classroom host/join uses Cloudflare D1 and room tokens.
- Simulated misleading AI recommendation with source verification; no external AI API.

## Source map
- app/engine.ts: pure state transitions, financial rules, events, seeded selection and replay.
- app/page.tsx: screen orchestration, local saves, classroom polling and dialogs.
- app/setup.tsx, phone.tsx, ending.tsx: setup, one-prompt gameplay and ending flow.
- app/services.tsx: contract change quotes and confirmation.
- app/education.tsx: teacher guidance, persona/problem and proposed Telia role.
- app/apartment.tsx, globals.css: illustration and responsive styling.
- app/api/classroom/route.ts and db/: classroom backend.
- tests/: engine, contracts, 72 lifestyle playthroughs and classroom API checks.

## Preserve
Do not spoil hidden scam outcomes before a choice. Disclose ordinary prices/terms before spending. Keep cheap and premium strategies viable. Do not add mandatory quizzes or force events into quiet months. Keep legacy saves compatible through normalizeGame. Existing migrations are immutable; add a new migration if the schema changes. Never commit .env, credentials, node_modules, local databases or build output.

## Verification and remaining work
Production build, TypeScript and automated engine/education/replayability suites passed for the current release. Latest visual browser QA was blocked by browser automation timeouts, so manually check phone and desktop layouts, setup through all six steps, choices, service changes and end screens. Classroom tests were verified in the earlier release; rerun against the local server before modifying that feature.

Next priorities: reliable three-minute demonstration, required persona/problem slide, mobile usability, then learner/teacher pilot evidence. The estimated challenge score of 39/50 is an informal assessment, not a real judge result.

## Hosting
The existing .openai/hosting.json points to the original private Sites project. It contains identifiers, not credentials. Local development works without its owner's account. Do not attempt to deploy to that project without owner access. Another host must support the Worker and D1 bindings; GitHub is source hosting, not a replacement for these runtime services.
