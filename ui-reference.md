# Chillabus - UI Reference (for the Canva screens)

> Reference, not a spec. Use it to keep the screens consistent with the product. Visual choices (exact palette, fonts, layout) are yours; this doc gives direction and the content each screen carries.

## What Chillabus is

A voice-first mobile web app that shows a student their whole load at a glance and helps them act before burnout. The home screen is a live capacity view across five areas: mental, time, physical, social, errands. An assistant, reached by voice with a text fallback, rebalances the week, pushes low-priority tasks back, and nudges the student toward rest.

Sample persona for placeholder content: **Arash, 20, second-year at MMU, works a part-time job.** Use one consistent person across the screens so it reads as a real account, not stock filler. (Target user is still being decided, so treat Arash as a stand-in.)

## Platform truth

Mobile-first web app, portrait phone frames. It should feel like an app you keep open on your phone, not a desktop dashboard shrunk down. Design at a phone width first.

## Tone

Playful and motivating, but calm underneath. The name is "Chillabus," so warmth and ease come first; the playfulness is in the voice and the small touches, not in pressure.

**Guardrail (important): no guilt mechanics.** No streaks, no broken-chain warnings, no "you missed a day" shame, no red overdue pile-ons. The user is already overloaded; the app should relieve pressure, never add it. When load is high, the tone stays supportive ("let's lighten this"), not alarming.

## Aesthetic direction

- Sit it next to friendly, calm mobile apps rather than dense productivity tools. Think soft and approachable, closer to a wellbeing app than a spreadsheet.
- The capacity read is the signature moment. Give it room and make it the thing the eye lands on first.
- Keep dense screens (task lists, this-week view) tidy; keep first-impression screens (home, nudges) spacious.

**NOT list (avoid looking like these):**

- A gritty productivity dashboard with tiny dense widgets
- A gamified habit app covered in flames, streak counters, and badges
- A clinical medical or mood-diary app
- Generic AI-slop: purple-to-blue gradients, neon glows, gradient text

## Screens

Around 10 core, plus 2 optional. Each note says what the screen carries and the one thing it must communicate.

1. **Splash / first-run** - brand moment, sets the calm tone. One thing: this app is friendly.
2. **Onboarding** - the student sets or weights the five areas and gets a short intro to talking by voice. One thing: "here are the five parts of your load."
3. **Home - Capacity at a glance (hero)** - the big capacity read ("You're at 90% this week") with the five-area breakdown below it. One thing: how full is my plate, right now.
4. **Daily check-in** - quick rating of how each of the five areas feels today. Light, a few taps. One thing: how am I feeling across my life, today.
5. **Quick-add** - add a task or commitment, set its effort, assign an area. One thing: capturing what is on my plate is fast.
6. **This week / task list** - what is coming up, grouped or sorted so overload is visible. One thing: what is actually on my plate this week.
7. **Voice assistant overlay** - a mic overlay over the current screen (not a full page), showing listening state and the assistant's reply as a card. A text input is visible as the fallback. One thing: I can just talk to it, and it answers here.
8. **Proactive overload nudge** - the assistant surfaces on its own when load is high: "You're at 90% this week. Want me to lighten it?" Supportive, not alarming. One thing: the app noticed before I did.
9. **Rebalance result** - the lighter week after the assistant acts: low-priority tasks pushed back, the capacity read dropping. One thing: it actually did something for me.
10. **Recovery suggestion** - a rest, downtime, or hangout card when the student is overloaded. One thing: recovery is part of managing load.
11. **(optional) Trends** - load or feeling over time, a gentle line, no guilt framing. One thing: my load has a shape over the weeks.
12. **(optional) Profile / settings** - account, area weights, voice on/off.

## User flow

```
Splash -> Onboarding -> Home (Capacity at a glance)
```

Home is the hub. From Home:

- **Check-in** and **Quick-add** feed the capacity read.
- **This week** shows the tasks behind the number.
- When load is high, a **Proactive nudge** appears and leads to the **Rebalance result**.
- **Recovery suggestion** is reachable from Home or from a nudge.
- The **Voice overlay** can be called from any screen.

The loop to demo: open app -> Home shows high capacity -> proactive nudge -> talk to the assistant by voice -> rebalance result shows a lighter week and a lower capacity read.
