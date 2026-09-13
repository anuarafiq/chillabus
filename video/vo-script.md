# Chillabus - VO Script

Third-person narrator. Matched to [storyboard.md](storyboard.md)'s scene timings at ~150 wpm (2.5 words/sec), so each block slots directly into its scene. Total: ~640 words / ~4:16 read time, leaving a little slack under the 4:30 target before the 5:00 hard cap.

Tone: calm, warm, direct - no guilt-mechanic language even when describing high load (per [../ui-reference.md](../ui-reference.md)'s tone guardrail).

---

## Scene 1 - Cold open (0:00-0:20, target ~50 words)

> On paper, this week looks fine. Classes. A job. A group project. Maybe plans with friends. But it doesn't feel fine, because nobody adds it up. Not the mental load, not the time, not the physical toll, the social energy, or the errands piling up quietly in the background.

**(49 words)**

## Scene 2 - Solution + twist (0:20-0:50, target ~75 words)

> That's what Chillabus is for. One honest number, pulled from five parts of your life - mental, time, physical, social, errands - so you see your real load at a glance. And here's the twist: it doesn't just show you the number and leave you to deal with it. It notices when you're overloaded, and it does something about it. That's Chillabus in one line: your load, understood, and acted on.

**(71 words)**

## Scene 3 - Demo: Home (0:50-1:20, target ~75 words)

> Here's Arash. Second-year, part-time job, a full course load. He opens the app and lands on Home - one hero number up top: ninety percent. Right under it, the five areas broken out, so he can see exactly where that number is coming from - mental and social running hottest this week. It's the first thing he sees, every time - no digging required. No spreadsheet, no guesswork.

**(70 words)**

## Scene 4 - Demo: flash pass (1:20-1:45, target ~62 words)

> That ninety percent doesn't come from nowhere. A quick onboarding sets his five areas. A daily check-in, just a few taps, asks how each one feels today. Quick-add captures a task the second it lands on his plate - what it is, how much effort, which area it belongs to. All of it feeds straight into that one number.

**(61 words)**

## Scene 5 - Demo: nudge -> voice assistant (1:45-2:30, target ~112 words)

> By Thursday, Chillabus notices before Arash does. A card appears on its own: "You're at ninety percent this week. Want me to lighten it?" No alarm, no red banner - just a straight, supportive question. Arash taps the mic and just says it out loud: "Lighten my week." That's it. No menus, no settings to hunt through. The assistant listens, thinks for a second, and replies right there on screen with a plan - which tasks move, and why. This is the moment the whole app is built around: the app catches the overload first, and Arash can act on it in one sentence, without opening a single tab.

**(113 words)**

## Scene 6 - Demo: rebalance + recovery (2:30-3:00, target ~75 words)

> The result: a lighter week. Two low-priority tasks get pushed back automatically, and the capacity number drops from ninety to a number that actually feels doable. Right after, a recovery suggestion shows up too - a walk, a nap, twenty minutes with a friend. Not a reward for finishing everything. Just a reminder that rest is part of managing the load, not something earned after it. That's the loop.

**(70 words)**

## Scene 7 - Tech stack + build plan (3:00-3:40, target ~100 words)

> Under the hood, it's a React app built with Next.js, deployed on Vercel. Clerk handles auth, Neon holds the data. The assistant runs on OpenAI, starting with the browser's built-in speech recognition, with a clear upgrade path to OpenAI's Realtime API if voice needs to get faster or more natural. In the three-week build phase, the target is the capacity visualiser, the daily check-in, quick-add, voice input with a text fallback, and one working assistant tool: rebalance-my-week, actually deployed and usable, not just a mockup.

**(92 words)**

## Scene 8 - Impact + close (3:40-4:30, target ~125 words)

> Here's what changes for Arash. Instead of five scattered worries - deadlines, chores, plans, energy, rest - he gets one honest read of his week, and one step to actually do something when it's too much. No streaks to keep. No broken chains, no red overdue pile-up, no guilt for having a hard week. Just a calmer way to see everything he's carrying, and a nudge to lighten it before it turns into burnout. Students don't need another app telling them what they missed. They need one that notices, speaks up, and helps them fix it - before the week wins. That's Chillabus, built for the Stress and Workload Manager track. Team CodeX.

**(114 words)**

---

## Notes

- "Ninety percent" is spoken to match the storyboard's placeholder capacity read - if the final demo screen uses a different number, update this script and the on-screen text together.
- Scene 5's nudge and assistant-reply lines are quoted VO copy - reuse them verbatim as the on-screen text in [claude-design-prompt.md](claude-design-prompt.md) so what's said and what's shown match exactly.
- Word counts are a pacing guide, not a hard rule - read it aloud once real recording starts and trim to whatever actually lands at ~4:30.
