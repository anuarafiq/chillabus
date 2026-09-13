# Chillabus by CodeX

**Team:** Anuar Afiq, Siti Zafirah, Fawwaz 'Arash
**Problem Statement:** Stress & Workload Manager
**Video Presentation:** [Unlisted Youtube Link]
**Presentation Slides:** https://canva.link/wri1c2mi0025n60

## 1. Project Overview

**The Problem.**
Uni students carry load across many parts of life at once: coursework, part-time work, errands, friends, and their own physical and mental health. Burnout rarely comes from one big thing. It builds quietly while everything stacks up, and most students notice only after they are already running on empty. Without a clear view of how full their plate is, they keep saying yes and keep pushing back whatever feels less urgent.

Stakeholders: the student is the primary user. Peers, lecturers, and campus wellbeing services deal with the fallout when a student burns out.

Existing apps each cover one slice of this and miss the rest:

- **Notion and other to-do apps** store tasks well but stay passive. They never tell you that you are overloaded, and they never act for you.
- **Finch and other wellbeing apps** track mood and self-care but ignore actual academic workload, so how you feel never connects to what is due.
- **Calendar tools like Structured** show time blocks but not total load across life areas, and they never rebalance anything on your behalf.

**Our Solution.**
Chillabus is a voice-first mobile web app that shows a student their whole load at a glance and helps them act before burnout hits. The home screen is a live capacity view across five areas (mental, time, physical, social, errands) with a plain read like "You're at 90% this week." Behind it sits an agentic assistant you talk to by voice: it rebalances your week, pushes low-priority tasks back, and nudges you toward rest, all as tool calls it runs for you.

Feature set:

- Capacity visualiser across the five areas (the hero)
- Daily feeling check-in
- Quick-add for tasks and commitments
- Voice assistant with a text fallback
- Proactive overload nudges
- AI-driven load rebalancing
- Recovery suggestions (rest, downtime, a hangout)

---
## 2. Ideation & Process

### 2.1 Ideas We Considered

| Idea | Why it was kept or dropped |
| --- | --- |
| Capacity visualiser as the hero, five-area load at a glance **(Chosen)** | Answers the brief's core problem directly: students do not know how much they are carrying. Strongest single-glance value, and it anchors every other feature. |
| Agentic assistant that runs the other features as tool calls **(Chosen)** | Turns tracking into action. The brief asks the app to help rebalance, not just report. One assistant replaces four separate feature screens and becomes our main differentiator. |
| Voice-first with a text fallback **(Chosen)** | Lower friction for a stressed student on their phone, and it helps accessibility. The text fallback keeps demos safe where browser voice support is weak. |
| Hybrid input: daily check-in plus quick-add **(Chosen)** | The check-in captures how load feels; quick-add captures what is actually on the plate. Together they feed a believable capacity number. |
| Build the guideline feature list literally (visualiser, tracker, balancer, nudge as four parallel features) | Dropped as the main shape. Four side-by-side features read as a dashboard, not a helper. We folded them in as assistant tools instead. |
| Stress tracker as the core loop | Dropped as the hero. Too passive, and too close to existing wellbeing apps. Kept as a supporting daily check-in. |
| Calendar or timetable import as the main input | Dropped for this scope. Heavy to build and to fake convincingly, and not needed to prove the concept. Possible later. |
| Gamified streaks and daily-chain rewards | Dropped on purpose. Streak guilt piles more pressure on an already overloaded student, which works against the whole point of the app. |

### 2.2 Ideation Boards

![Ideation Board](assets/Ideation%20Board.png)


## 3. Design & Prototype

**UI Prototype:** https://canva.link/4kantpkx227qm7m

## 4. What Makes It Different

- **The assistant acts, it does not just store.** You talk to it and it runs tool calls: rebalance my week, push this back, suggest a break. To-do apps hold your tasks and wait; Chillabus does something about them.
- **Whole-life load in one number.** Capacity blends five areas into one honest read. Wellbeing apps track mood only; calendars track time only. Chillabus is the view that connects how you feel to what is actually due.
- **It pushes back for you.** The app watches for overload and offers a lighter week on its own, rather than waiting for you to notice and fix it yourself.
- **Anti-guilt by design.** Playful and motivating, but no streaks and no broken-chain shame. Guilt mechanics add load to the exact person we are trying to relieve, so we left them out on purpose. This is a deliberate stance, not a missing feature.

Comparison table:

| | Notion / to-do | Finch / wellbeing | Structured / calendar | Chillabus |
| --- | --- | --- | --- | --- |
| Whole-life load view | No | Partial (mood) | Partial (time) | Yes |
| Acts for you | No | No | No | Yes (agentic) |
| Voice-first | No | No | No | Yes |
| Anti-guilt design | n/a | Mixed | n/a | Yes |


## 5. Technical Architecture & Feasibility

**This round is UI-only.** The prototype is a Canva screen set, no backend or data logic yet. The stack below is the plan for the coding build phase.

- **Frontend and backend: Next.js (App Router) as a mobile-first PWA, hosted on Vercel.** One repo for pages, the API, and the assistant. Fast to build, installable on a phone, and Vercel gives us free hosting with HTTPS by default. Constraint: PWA install and background behaviour on iOS is limited.
- **Auth: Clerk.** Prebuilt, mobile-friendly sign-in components and a Vercel-native integration, so we spend build time on the product, not on auth plumbing. Constraint: a second vendor alongside the database, and free-tier active-user limits.
- **Database: Neon (serverless Postgres) with Drizzle ORM.** Typed queries and a generous free tier that suits serverless. Constraint: we wire the Clerk user id into Neon as a foreign key ourselves, since auth and data are separate vendors.
- **Assistant: OpenAI API with tool/function calling, run inside Next.js route handlers so the key stays server-side.** Tools map to the features: add or adjust a task, rebalance the week, suggest recovery, compute capacity. Constraint: token cost per assistant turn; we cap the loop. If voice grows past text, the in-vendor upgrade is the OpenAI Realtime API for speech-to-speech.
- **Voice: browser Web Speech API for speech-to-text, with a text fallback.** No server cost for the prototype. Constraint and known risk: `SpeechRecognition` support is inconsistent on iOS Safari, so the text fallback is required, not optional. Server-side transcription (Deepgram or Whisper) is the upgrade if voice must be reliable in a loud demo hall.
- **Proactive nudges: polling or on-open checks.** The app recomputes capacity when opened or on a timer. Zero extra infrastructure, and enough to demo the assistant acting.

**System architecture diagram**

![System Architechture Diagram](assets/System%20Architecture%20Diagram.png)


**Build plan and scope**
The build phase ships concentrates on a narrow, functional app loop deployed live on Vercel.

- Five area capacity visualizer rendering dynamic score calculations.
- Daily check-in module updating area weights.
- Quick-add task dialogue supporting effort rating and area tagging.
- Voice input modal pairing Web Speech recognition with text fallback.
- End-to-end agentic tool loop.

Out of scope for the build phase: Historical stress analytics, multi-tool chained conversational loops and third-party calendar or Learning Management System (LMS) timetable synchronization.
