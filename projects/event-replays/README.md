# 🟢 Event replays in 3D

**Label:** `team: event-replays` · **Priority:** next · **Lead:** Nicolas Rufino


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

## Timeline — Fall 2026

| Milestone | Date |
|---|---|
| Kickoff | Thu Oct 1 |
| Mini design sprint · session 1 (map + sketch) | Thu Oct 8 |
| Mini design sprint · session 2 (decide + prototype + test) | Thu Oct 15 |
| Design doc due | Sun Oct 25 |
| Design review | Tue Oct 27 |
| Spike (3D stack) | week of Oct 26 |
| Feature complete | Sun Nov 29 |
| Code freeze | Tue Dec 1 |
| **Demo day (showcase)** | **Thu Dec 3** |
| Retro | Sat Dec 5 |
| OKR grades | Fri Dec 11 |

## Artifacts

| File | What | Status |
|---|---|---|
| [okrs.md](okrs.md) | Objectives and key results, graded 0–1 | Due Tue Oct 6 |
| [design-doc.md](design-doc.md) | 1–3 page design doc | See timeline |
| [status/](status/) | Weekly snippet every Monday | From Mon Oct 12 |
| [launch-checklist.md](launch-checklist.md) | Must pass before the public release | Before the demo |
| [demos/](demos/) | Demo day writeup, slides, video | 2026-12-03 |
| [retro.md](retro.md) | Blameless retro and findings | After the demo |
