# Chillabus

## Overview

Chillabus is a voice-first mobile web app for uni students that shows their whole load at a glance and helps them act before burnout. The home screen is a live capacity view across five areas (mental, time, physical, social, errands) with a plain read like "You're at 90% this week." An agentic assistant, reached by voice with a text fallback, rebalances the week, pushes low-priority tasks back, and nudges the student toward rest. Built for the CodeNection 2026 hackathon, Stress & Workload Manager track.

## Goals

1. Give a student one honest read of how full their plate is, across five life areas.
2. Let the student act on overload in one step (talk to the assistant, get a lighter week), not just read a report.
3. Keep it something a stressed student would actually open on their phone: fast, calm, no guilt.

## Core User Flow

1. Student opens the app and lands on Home: capacity at a glance.
2. They do a quick daily check-in and quick-add any tasks or commitments.
3. Capacity updates. If load is high, the assistant surfaces a proactive nudge.
4. The student talks to the assistant by voice ("lighten my week").
5. The assistant runs a tool call and shows a rebalanced week with a lower capacity read.
6. Recovery suggestions (rest, downtime, a hangout) are offered when overloaded.

Full screen-by-screen detail lives in [ui-reference.md](../ui-reference.md).

## Features

### Load view

- Capacity visualiser across mental, time, physical, social, errands (the hero).
- Daily feeling check-in.
- Quick-add for tasks and commitments with effort and area.

### Agentic assistant

- Voice input with a text fallback, in a mic overlay.
- Proactive overload nudges.
- Tool calls: rebalance the week, push tasks back, suggest recovery, compute capacity.

## Scope

### In Scope

- UI prototype this round (Canva screens, ~10).
- Build phase: capacity visualiser, daily check-in, quick-add, voice input with text fallback, and one assistant tool loop (rebalance-my-week), deployed.

### Out of Scope

- Backend and data logic this round (UI-only).
- Build phase: stress trends over time, chaining several tools in one turn, calendar/timetable import.

## Success Criteria

1. A student can see one capacity read and the five-area breakdown on Home.
2. A student can add load via check-in and quick-add, and see capacity change.
3. A student can trigger the assistant to rebalance the week and see a lighter result.

## Open items

- Target user is still OPEN. Persona "Arash" is a sample-content stand-in only.
