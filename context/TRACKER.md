# Progress Tracker

Update this file after every meaningful implementation change.

## Current Phase

- Planning complete. UI prototype (Canva) next. No code yet.

## Current Goal

- Hand off to the team: README owner fills README from ideation.md; peer builds Canva screens from ui-reference.md.

## Completed

- Ideation and planning (2026-09-13): product shape, feature set, tech stack, open items.
- ideation.md (README staging), ui-reference.md (peer's screen reference).

## In Progress

- None (session ended at a handoff point).

## Next Up

- README owner fills sections 1, 2.1, 2.2, 4, 5 from ideation.md.
- Peer builds ~10 Canva screens + flow from ui-reference.md, links prototype in README section 3.
- Coding build phase (later): scaffold Next.js app, then the one tool loop (rebalance-my-week).

## Open Questions

- Target user is OPEN (persona "Arash" is a stand-in only).
- LLM token cost and free-tier limits (provider is OpenAI; team supplies keys).
- Web Speech reliability on iOS Safari (text fallback required).

## Architecture Decisions

- Next.js on Vercel, one repo for pages + agent (simplest for a small team, matches Vercel habits).
- Clerk + Neon over Supabase: better auth DX and Vercel-native, and Supabase's bundled realtime/storage buys nothing here (nudges are polling, no file uploads).
- OpenAI over Claude: chosen for the in-vendor speech-to-speech upgrade path (Realtime API) if voice grows past Web Speech.
- Agentic model: the tracker, balancer, and recovery nudge are assistant tool calls, not separate features.

## Session Notes

- This round is UI-only. Do not write app code or build screens.
- `context/` was created at the end of the ideation session for this handoff. SCHEMA.md, FLOW.md, PLAN.md were skipped: data model not firm yet, ui-reference.md already holds the flow, and the ideation.md build plan covers scope. Add them when their trigger is met.
