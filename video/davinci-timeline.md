# Chillabus - DaVinci Timeline Structure

Assembly spec for whoever (Claude + DaVinci MCP) builds the final cut in DaVinci Resolve. Sources: [claude-design-prompt.md](claude-design-prompt.md)'s 8 rendered scene clips, [vo-script.md](vo-script.md)'s narration once recorded, and optional music. Scene numbers and timing match [storyboard.md](storyboard.md) throughout - read that first if a scene reference here is unclear.

This doc assumes the `davinci-resolve` MCP server is connected. Tool names below (`mcp__davinci-resolve__*`) point at which tool does which job - check each tool's actual schema before calling it, this doc only says what needs to happen, not the exact call parameters.

---

## Project settings

- Timeline: 1920x1080, 30fps, 16:9 (standard YouTube upload).
- Target runtime: 4:30 (270s). Hard cap: 5:00, per [../guidelines/video-outline.md](../guidelines/video-outline.md).
- If Claude Design exports at a different resolution/frame rate, match the project settings to the source clips (`mcp__davinci-resolve__project_settings`) rather than forcing a conform.

## Track layout

| Track | Content |
| --- | --- |
| V1 | The 8 Claude Design scene clips, back to back, in storyboard order. |
| V2 | On-screen text/caption overlays, only if Claude Design ships them as separate transparent layers rather than baked into V1. Leave empty otherwise. |
| A1 | VO narration - one continuous track. |
| A2 | Background music bed (optional) - ducked well under VO, especially quiet through Scene 5's spoken lines. |

## Media pool setup

Import via `mcp__davinci-resolve__media_pool` / `media_pool_item`:

- 8 scene clips from Claude Design, named `scene1_coldopen`, `scene2_twist`, `scene3_home`, `scene4_flashpass`, `scene5_nudgevoice`, `scene6_rebalance`, `scene7_stack`, `scene8_close` (or whatever Claude Design actually names its exports - rename on import if they don't match, so the timeline build step below stays legible).
- VO recording (single file or 8 stitched clips matching `vo-script.md`'s scenes).
- Music bed, if used.

## Timeline build

Create one timeline (e.g. `chillabus_v1`) and place clips on V1 in order via `mcp__davinci-resolve__timeline` / `timeline_item`. Storyboard's rough split, as a starting point - **treat these timecodes as placeholders, not fixed cut points.** Once real clips and VO exist, each scene's actual length is whatever it renders/records to; shift subsequent scenes accordingly rather than trimming clips to force the numbers below.

| Scene | Rough in | Rough out | Duration | Source clip |
| --- | --- | --- | --- | --- |
| 1 - Cold open | 00:00 | 00:20 | 20s | scene1_coldopen |
| 2 - Solution + twist | 00:20 | 00:50 | 30s | scene2_twist |
| 3 - Home demo | 00:50 | 01:20 | 30s | scene3_home |
| 4 - Flash pass | 01:20 | 01:45 | 25s | scene4_flashpass |
| 5 - Nudge -> voice | 01:45 | 02:30 | 45s | scene5_nudgevoice |
| 6 - Rebalance + recovery | 02:30 | 03:00 | 30s | scene6_rebalance |
| 7 - Tech stack | 03:00 | 03:40 | 40s | scene7_stack |
| 8 - Impact + close | 03:40 | 04:30 | 50s | scene8_close |

## Transitions

Per `storyboard.md` / `claude-design-prompt.md`:

- Default: hard cut between scenes - this video doesn't need heavy transition work, the content carries it.
- Scene 4 only: matched transition style across its 3 internal sub-cuts (onboarding -> check-in -> quick-add) - this is defined inside the Scene 4 clip itself by Claude Design, not something to add in DaVinci.
- Scene 6: hard cut from the "before" (90%) to "after" (lower number) capacity state - no crossfade, the jump should read as sudden/effective.
- Scene 8 end: fade to black, then hold on the end card before stopping.

## Sync markers

Add via `mcp__davinci-resolve__timeline_markers` at:

- **0:00** - VO track start.
- **Scene 5 (four markers)** - nudge card entrance, mic tap, spoken line ("Lighten my week"), reply card entrance. These need frame-accurate VO sync per `claude-design-prompt.md`'s Scene 5 note - this is the tightest sync work in the whole edit, budget extra passes here.
- **Scene 6 cut point** - where capacity goes from 90% to the lower number.
- **Scene 8 end** - runtime checkpoint, confirm total duration before export.

## Audio

- A1: align VO under each scene using the scene boundaries above as a guide, not literal timestamps - VO pacing when actually recorded will drift a few seconds per scene versus the ~150wpm estimate in `vo-script.md`.
- A2 (if used): keep music under VO level throughout, drop further or mute during Scene 5's dialogue beats.

## Render

Via `mcp__davinci-resolve__render` / `render_presets`:

- Export 1080p, YouTube preset.
- Before exporting, check total timeline duration against the 5:00 hard cap - if the edit runs long, cut from Scene 4's flash pass or Scene 7's stack explanation first (per `storyboard.md`'s runtime note), not from Scene 5.

## Open items for whoever assembles this

- Timecodes above are placeholders from `storyboard.md`'s rough split - swap in actual clip durations once Claude Design renders the 8 scenes.
- VO recording doesn't exist yet - `vo-script.md` gives the script and target word counts, actual recorded pacing will shift scene boundaries.
- `[placeholder]` screen segments (Scenes 3, 4, 5, 6) depend on the teammate's Canva screens, still in progress per [../CLAUDE.md](../CLAUDE.md).
