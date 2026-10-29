# Event replays in 3D

> **Owner:** [@nicolasrufino](https://github.com/nicolasrufino) · **Last reviewed:** Sep 29, 2026 · **Audience:** Members and recruiters · **Type:** Project page

**Label:** `team: event-replays` · **Priority:** next

Film an event on a phone; anyone can walk through it later on the event page. **Every face is blurred before anything is published.**

```mermaid
flowchart LR
  V[Phone video] --> F[Frames<br/>ffmpeg]
  F --> B[Blur faces]
  B --> P[Camera poses<br/>COLMAP]
  P --> G[3D scene<br/>Gaussian splat on rented GPU]
  G --> W[Viewer on /events/:id<br/>three.js]
  style B fill:#1BA673,color:#fff
```

| Milestone | Done when | Area |
|---|---|---|
| 1. Spike | One empty-room scene opens in the browser | CV |
| 2. Pipeline | Upload → GPU job → scene file stored with the event | Backend |
| 3. Viewer | Event page shows the scene, works on phones | Frontend |

**Camera rules:** no face matching, faces blurred, a sign at any event we capture.
**You learn:** computer vision, GPU jobs, 3D on the web.

## Timeline

**TBD.** The team hasn't started yet. Dates are set once people are placed and the team kicks off, and get added here as we move on.

## Artifacts

| File | What | Status |
|---|---|---|
| [okrs.md](okrs.md) | Objectives and key results, graded 0–1 | Due at kickoff |
| [design-doc.md](design-doc.md) | 1–3 page design doc | See timeline |
| [research.md](research.md) | Capture, formats, viewers, cost, privacy and v1 recommendation | Ready |
| [build-plan.md](build-plan.md) | Architecture, runbook, schedule, backlog, risks and tests | Ready |
| [status/](status/) | Weekly snippet every Monday | Once the team starts |
| [launch-checklist.md](launch-checklist.md) | Must pass before the public release | Before the demo |
| [demos/](demos/) | Demo day writeup, slides, video | TBD |
| [retro.md](retro.md) | Blameless retro and findings | After the demo |
