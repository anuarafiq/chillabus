# Chillabus - project notes

CodeNection 2026 hackathon entry, Stress & Workload Manager track (team CodeX: Anuar Afiq, Siti Zafirah, Fawwaz 'Arash).

Team split, respect it:
- `README.md` is filled by a teammate from [ideation.md](ideation.md). Do not edit README unless asked.
- The UI screens and flow are built by a peer in Canva from [ui-reference.md](ui-reference.md). Do not build screens.
- The current phase is UI-only. Do not write app code until the build phase starts.
- `guidelines/` holds the hackathon rules and format (video length, screen count, deployable). Reference, not project content. Do not re-import it.

## Project Context

Read these files in order before implementing or making any architectural decision. Only read files that exist, not every project has all of them:

1. `context/OVERVIEW.md` - product definition, goals, features, and scope. Always read.
2. `context/ARCHITECTURE.md` - system structure, boundaries, storage model, and invariants. Always read.
3. `context/SCHEMA.md` - database tables, relationships, ERD, RLS policies. Read if present (projects with a real database).
4. `context/FLOW.md` - screen-by-screen flow, user journeys, button actions, success/error states. Read if present (projects with several screens). Until it exists, [ui-reference.md](ui-reference.md) holds the flow.
5. `context/PLAN.md` - build order, dependencies, acceptance criteria per unit. Read if present (multi-unit builds).
6. `context/TRACKER.md` - current phase, completed work, open questions, next steps. Always read, read last, it reflects the current state on top of the plan above.

`context/CHECKLIST.md` is not part of normal session start. Read it only when the user asks to prepare for launch or deploy.

Update `context/TRACKER.md` after each meaningful implementation change. If a unit in `PLAN.md` is completed, mark it done in TRACKER.md, not by editing PLAN.md's acceptance criteria checkboxes.

If implementation changes the architecture, scope, schema, or flow documented in the context files, update the relevant file before continuing. Keep ARCHITECTURE.md's Storage Model and SCHEMA.md in sync, don't let them contradict each other.
