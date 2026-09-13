# Chillabus - Video Storyboard

Rough text storyboard for the hackathon video (see [../guidelines/video-outline.md](../guidelines/video-outline.md): 3-5 min, target 4:30, hard cap 5:00, YouTube unlisted).

Two tools split the work from this doc:
- **Claude Design** - per-scene graphic/text animation.
- **Claude + DaVinci MCP** - overall timeline assembly (cuts, transitions, VO sync).

Each scene lists: **Content** (what's on screen / narrated), **Claude Design** (animation to build), **Timeline** (DaVinci cut/sync note).

Screens referenced by name from [../ui-reference.md](../ui-reference.md)'s screen list - exact frames aren't final yet (Canva build in progress), so anything screen-specific is marked `[placeholder]` and gets swapped once those screens exist. Persona used throughout: **Arash** (see ui-reference.md).

---

## Scene 1 - Cold open: the load problem (0:00-0:20)

- **Content:** No screen yet, text/graphic only. VO opens on the problem: a student's week looks fine on a calendar but doesn't feel fine - mental, time, physical, social, errands are all separate piles nobody adds up. Name the five areas on screen as they're said.
- **Claude Design:** Five area labels animating in one at a time (mental -> time -> physical -> social -> errands), plain type, no icons yet.
- **Timeline:** VO track starts here. No screen cuts, just the animated text card. Runs to 0:20 flat.

## Scene 2 - Solution + the twist (0:20-0:50)

- **Content:** "Chillabus" name card. One line: it's a single honest capacity read across all five areas, and a voice-first assistant that acts on overload instead of just reporting it. State the twist directly - most apps track, this one intervenes.
- **Claude Design:** Capacity ring/number animating up from 0 to "90%" as the five areas merge into it.
- **Timeline:** Cut from the text-card scene into the first screen placeholder at the end of this beat, leading into Scene 3.

## Scene 3 - Demo: Home, capacity at a glance (0:50-1:20)

- **Content:** `[placeholder: Home screen - capacity hero + 5-area breakdown]`. VO: "This is Arash's week. He's at 90% - the app shows this the second he opens it." Point at the five-area bars underneath the hero number.
- **Claude Design:** Callout/highlight animation sweeping across the capacity number, then down to the five-area bars.
- **Timeline:** Hold on this single screen for the full 30s, VO paced to land on the hero number first, bars second.

## Scene 4 - Demo: quick flash pass (1:20-1:45)

- **Content:** Fast cuts through `[placeholder: Onboarding]` -> `[placeholder: Daily check-in]` -> `[placeholder: Quick-add]`. VO: "That number comes from a two-minute check-in and quick-add - this is how the load gets captured, not guessed." One short line per screen, no deep narration.
- **Claude Design:** One short text label per screen (e.g. "set your five areas", "how do you feel today", "add what's on your plate"), same transition style across all three so the montage reads as one beat.
- **Timeline:** Fast-cut montage, ~8s per screen, matched transition (e.g. consistent slide or crossfade) so it doesn't feel like three different edits.

## Scene 5 - Demo: proactive nudge -> voice assistant (1:45-2:30)

- **Content:** `[placeholder: Proactive overload nudge - "You're at 90% this week. Want me to lighten it?"]` -> `[placeholder: Voice assistant overlay, mic listening state]` -> Arash says "lighten my week" -> `[placeholder: assistant reply card]`. This is the demo's emotional core: the app notices before Arash does, and he can just talk to it.
- **Claude Design:** Mic listening-state animation (pulse/waveform), assistant reply card entrance animation.
- **Timeline:** Longest single beat in the demo (45s) - give it room. Sync VO tightly: nudge text appears exactly as VO reads it, mic animation starts exactly when Arash "speaks," reply card lands on the line after.

## Scene 6 - Demo: rebalance result + recovery (2:30-3:00)

- **Content:** `[placeholder: Rebalance result - lighter week, capacity read dropping]` then `[placeholder: Recovery suggestion card]`. VO: "Low-priority tasks get pushed back, the number drops, and it offers him something to actually recover with." No guilt framing anywhere in VO or on-screen copy.
- **Claude Design:** Capacity number animating down (90% -> lower value), task cards animating out/back, recovery card sliding in after.
- **Timeline:** Cut from the "before" capacity state to the "after" state, brief hold on the recovery card to close the demo loop.

## Scene 7 - Tech stack + build plan (3:00-3:40)

- **Content:** No app screens. VO + on-screen labels: React (Next.js) on Vercel for frontend, Clerk + Neon for auth/database, OpenAI for the assistant (Web Speech now, Realtime API as the upgrade path). Build-phase target: capacity visualiser, daily check-in, quick-add, voice input with text fallback, and one assistant tool loop (rebalance-my-week), deployed. Pulled directly from `../context/TRACKER.md` Architecture Decisions and `../context/OVERVIEW.md` Scope - no invented stack details.
- **Claude Design:** Simple stack diagram or stacked labels (frontend / auth+db / AI), no screen footage, no motion beyond entrance.
- **Timeline:** Static-card segment, lowest visual complexity in the video, let VO carry the pacing.

## Scene 8 - Impact + close (3:40-4:30)

- **Content:** What concretely changes for Arash: one honest number instead of five scattered worries, one step to act on overload instead of just another list to manage, no streaks or guilt anywhere in the app. Close on why this is worth building. End card: team name (per submission format - unlisted YouTube, titled with team name only).
- **Claude Design:** Closing text card animation, team/name end card.
- **Timeline:** Fade out on the last demo beat's energy, hold end card, then hard stop. Check total runtime lands at ~4:30 and stays under the 5:00 cap.

---

## Notes for whoever times this out

- Total target: 270s (4:30). Per-scene timings above are a starting split, not fixed - adjust once real VO is recorded and read at actual pace.
- `[placeholder]` tags mark anything waiting on the Canva screens (teammate's in-progress work per [../CLAUDE.md](../CLAUDE.md)) - swap in exact frame references once those exist, don't build new screens to fill this doc.
- No ideation process, mentor consultations, or idea evolution in the video - that's README territory per the outline's own note.
