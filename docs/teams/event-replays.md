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
