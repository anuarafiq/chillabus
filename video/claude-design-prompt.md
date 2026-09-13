# Claude Design Prompt - Chillabus Video Animation

Single brief for Claude Design covering all 8 scenes from [storyboard.md](storyboard.md), matched to the wording in [vo-script.md](vo-script.md). Generate as one consistent sequence, not 8 disconnected clips - same type, same motion language, same palette throughout.

---

## Shared style (apply to every scene)

- **Tone:** calm and warm, with a little playfulness in the motion timing - not corporate, not clinical. Sits closer to a friendly wellbeing app than a productivity dashboard (per [../ui-reference.md](../ui-reference.md)).
- **Avoid entirely:** gradient text, purple-to-blue gradients, neon glows, cyan-on-dark, cards nested in cards - the "AI slop" defaults called out in [../ui-reference.md](../ui-reference.md)'s NOT list.
- **Color:** OKLCH-based palette, soft and approachable, not saturated/neon. Light theme unless a specific scene calls for contrast (e.g. Scene 1's cold open can sit on a quieter, dimmer background before the app's own light UI appears in Scene 2 onward).
- **Motion:** smooth easing, no jarring pops or hard cuts within a single animation - things arrive gently, the way the product itself should feel to use.
- **Typography:** one clean type family throughout (no reflex fonts - Inter/Roboto - per house style), consistent weight/size scale across all 8 scenes so text doesn't feel like it's from different decks.
- **Screens:** wherever a scene references an actual app screen, treat it as `[placeholder]` - block out the layout and content described, don't invent details beyond what's specified. These get swapped for the real Canva screens once a teammate finishes them.

---

## Scene 1 - Cold open (0:00-0:20)

**On screen:** No app screen. Five words animate in, one at a time, plain type on a quiet background: "mental" -> "time" -> "physical" -> "social" -> "errands."

**Animate:** Each word fades/slides in and stays on screen as the next one joins it, so by the end all five are visible together, slightly scattered (not lined up in a neat row - visually represents "nobody's added this up yet"). No icons.

**On-screen text (verbatim from VO):** the five area words only - no other captions this scene.

## Scene 2 - Solution + twist (0:20-0:50)

**On screen:** "Chillabus" name/logotype, then a capacity ring or number counting up.

**Animate:** The five scattered words from Scene 1 animate together and merge into a single ring/number that counts up from 0% to 90%. Once it lands on 90%, hold briefly before cutting to Scene 3.

**On-screen text:** "Chillabus" (name card), then the number "90%" inside/beside the ring. No other captions - let the VO carry the twist line.

## Scene 3 - Demo: Home (0:50-1:20)

**On screen:** `[placeholder: Home screen]` - capacity hero number ("90%") at top, five-area breakdown bars below it.

**Animate:** A callout/highlight (soft glow ring or underline, not neon) sweeps onto the hero number first, holds, then sweeps down to the five-area bars as the VO mentions them.

**On-screen text:** None beyond what's native to the placeholder screen itself (the "90%" and area labels already on it).

## Scene 4 - Demo: flash pass (1:20-1:45)

**On screen:** Three placeholder screens in sequence - `[placeholder: Onboarding]`, `[placeholder: Daily check-in]`, `[placeholder: Quick-add]`.

**Animate:** Identical transition style between all three (e.g. a consistent horizontal slide or soft crossfade) so the montage reads as one beat, not three separate edits. Each screen gets one short label overlay as it appears.

**On-screen text (one line per screen, matched to VO):**
- Onboarding: "set your five areas"
- Daily check-in: "how do you feel today"
- Quick-add: "add what's on your plate"

## Scene 5 - Demo: nudge -> voice assistant (1:45-2:30)

**On screen:** `[placeholder: Proactive overload nudge card]` -> `[placeholder: Voice assistant overlay, mic]` -> `[placeholder: assistant reply card]`. This is the longest, most important beat - give the animation room to breathe.

**Animate:**
1. Nudge card slides/fades in on its own (nothing tapped it into existence - it should read as the app acting proactively).
2. Cut to mic overlay: a listening-state animation (soft pulse or waveform, not a harsh flashing indicator) while the quoted line is "spoken."
3. Reply card animates in after a brief thinking pause (a subtle loading indicator, not a spinner that reads as "broken/slow").

**On-screen text (verbatim from VO - keep quotes exact):**
- Nudge card: "You're at 90% this week. Want me to lighten it?"
- Spoken line (shown as a caption near the mic, not just narrated): "Lighten my week."
- Reply card: a short plan summary line, e.g. "Pushing back 2 low-priority tasks - here's your lighter week."

## Scene 6 - Demo: rebalance + recovery (2:30-3:00)

**On screen:** `[placeholder: Rebalance result]` then `[placeholder: Recovery suggestion card]`.

**Animate:** The capacity number animates down from 90% to a lower value (e.g. 65%) while one or two task cards visibly animate out/back (not deleted - "pushed back," so a soft slide-away, not a strikethrough or trash-can motion, to avoid any guilt/failure connotation). Recovery card slides in after, calm and inviting, not a reward/badge treatment.

**On-screen text:** the new capacity number, plus the recovery card's suggestion text, e.g. "Take a 20-minute walk" - keep it plain, no congratulatory language ("You did it!" etc. reads as guilt-mechanic adjacent - avoid).

## Scene 7 - Tech stack + build plan (3:00-3:40)

**On screen:** No app screens - a simple stack diagram or stacked label group.

**Animate:** Three groups entering in sequence, matched to VO pacing: Frontend (React / Next.js / Vercel) -> Data (Clerk / Neon) -> AI (OpenAI). Simple entrance only (fade or slide), no looping motion - this scene should read as the calmest, lowest-complexity visual in the sequence so the VO carries it.

**On-screen text:**
- "React + Next.js -> Vercel"
- "Clerk + Neon"
- "OpenAI (Web Speech -> Realtime API)"

## Scene 8 - Impact + close (3:40-4:30)

**On screen:** Closing text card, then an end card.

**Animate:** Closing line animates in cleanly (no confetti, no celebratory burst - keep it in the same calm register as the rest of the video). End card fades in last: team name, per the submission format (unlisted YouTube, titled with team name only).

**On-screen text:**
- Closing line: "One honest number. One step to lighten it."
- End card: "Chillabus - Team CodeX"

---

## Notes

- If the final Canva screens differ from what's blocked out here (exact capacity numbers, card copy), update this file and `vo-script.md` together so narration, on-screen text, and screens stay in sync.
- Scene 5 and Scene 6 carry the most motion complexity - if time is short, prioritize polish there over Scene 7's stack diagram.
