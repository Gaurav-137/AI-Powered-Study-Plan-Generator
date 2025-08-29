# AI‑Powered Study Plan Generator (Local‑First, No External AI)

A React + TypeScript web app that creates personalized study schedules from your exam dates, subjects, and daily availability. It prioritizes what to study and when, offers a drag‑and‑drop planner, and adapts when life happens — all without calling external AI APIs.

> Note: This README is intentionally high‑level to protect the unique implementation. I’m happy to walk through the deeper technical details during an interview.

---

## Why this exists
Students don’t need more to‑do lists — they need realistic, explainable plans that respect time constraints, energy levels, and upcoming exams. I built this to:
- Explore intelligent scheduling on the client side (privacy‑first).
- Blend learning science (spaced repetition, interleaving) with everyday planning.
- Showcase end‑to‑end product thinking: UX, algorithms, performance, and resilience.

---

## What it does (at a glance)
- Collects your subjects, exam dates, goals, and daily availability.
- Generates a study plan with time‑boxed sessions on a calendar/timeline.
- Lets you drag & drop blocks; the schedule adapts without breaking constraints.
- Explains “why this here” for each block (due dates, difficulty, reviews).
- Works offline; your data stays on your device by default.
- Optional exports (e.g., calendar) and “what‑if” scenarios (move an exam, lose a day).

---

## What makes it different
- Local‑first intelligence: No external AI APIs; the scheduling engine runs in the browser.
- Explainable decisions: Each block includes plain‑English reasoning for trust and accountability.
- Research‑backed planning: Spaced repetition, interleaving, breaks, and session caps.
- Resilient planning: Miss a session? The system gracefully reflows the affected window.
- Accessibility‑minded: Keyboard‑friendly DnD, color‑safe palette, focus mode timer.

---

## Live demo & screenshots
- Demo: [link here]
- 2‑min walkthrough video: [link here]
- Screenshots: [folder or embedded images]

> The demo runs with sample data by default. No personal data is required.

---

## How it works (high level)
- Inputs: Subjects, tasks, total effort, due dates, availability windows, preferences.
- Engine: A constraint‑aware scheduler computes a feasible plan, then improves it with small, time‑boxed refinements.
- UI: A fast calendar/timeline with drag‑and‑drop and a “Why this here?” explainer.
- Rescheduling: Localized re‑planning when you move or miss blocks, keeping the rest stable.
- Privacy: Data stored locally; offline‑ready. Optional encrypted sync can be toggled.

Simple architecture (high level):

UI (React) ⇄ Scheduler Worker (async) ⇄ Local Storage (IndexedDB)
↑
Plan Explainers


---

## Feature highlights
- Add exams, tasks, and effort; define availability and preferences.
- Smart session sizing with breaks and daily load limits.
- Prioritization that respects due dates, difficulty, and fairness across subjects.
- Review sessions spaced over time (adjusted by your feedback).
- Drag‑and‑drop editing with auto conflict resolution.
- Plan quality indicators and lightweight analytics.
- Calendar export and “what‑if” sandbox.

---

## Tech overview
- Frontend: React + TypeScript
- State & Data: Local storage (IndexedDB)
- Scheduling: Runs in a Web Worker for responsiveness
- UI: Accessible drag‑and‑drop planner, timeline/calendar views
- Testing: Unit + e2e; invariants to ensure no overlaps and deadline compliance
- PWA: Works offline; installable

> Libraries and deeper implementation specifics intentionally omitted here.

---

## Getting started (local)
- Requirements: Node 18+
- Setup:
  1. Clone the repo
  2. `npm install`
  3. `npm run dev`
- Open: http://localhost:3000 (or the port shown)

> A small seed dataset is included so you can generate a plan immediately.

---

## What I focused on
- Product thinking: Designing for explainability, recovery from misses, and realistic daily limits.
- Engineering: Deterministic, time‑bounded planning in a worker; smooth DnD with instant feedback.
- Learning science: Spaced repetition and interleaving surfaced directly in the UI.
- Privacy & performance: Local‑first data, measurable plan quality, and responsive interactions.

---

## Roadmap (selected)
- Deeper calendar integrations and notifications
- More robust “what‑if” scenarios
- Expanded accessibility testing
- Optional cloud backup with encryption
- Multi‑language and time zone enhancements

---

## Testing & quality (brief)
- Automated tests for core rules (no overlaps, within availability, due‑date respect)
- Scenario tests for rescheduling and missed sessions
- Visual/e2e checks for DnD and planner stability

---

## Privacy
- By default, data stays on your device. No external AI calls.
- Optional sync (if enabled) is encrypted.

---

## Notes for reviewers
- I’m happy to demo the scheduling heuristics, trade‑offs, and how explainability is built into the UI.
- The README is intentionally concise; deeper docs available upon request.

---

## License
Copyright (c) [Your Name]. All rights reserved.
This project is provided for personal portfolio review. No commercial use, redistribution, or derivative works without permission.

---