# 🔵 Opportunity board

**Label:** `team: opportunity-board` · **Priority:** main focus · **Lead:** Nicolas Rufino

Every internship and new-grad role worth applying to, always current, filtered to what each member can actually get — plus a tracker for every application.

```mermaid
flowchart LR
  S1[Greenhouse / Lever / Ashby<br/>public job APIs] --> J[Daily scraper job]
  S2[Community lists<br/>e.g. SimplifyJobs] --> J
  S3[Partner roles<br/>from /partner] --> J
  J --> D[(Opportunity table<br/>deduped + tagged)]
  D --> F[Member feed<br/>by class year + interests]
  F --> T[Tracker<br/>Applied → OA → Interview → Offer]
  T --> R[Deadline reminders]
  style J fill:#2F6FD6,color:#fff
  style F fill:#2F6FD6,color:#fff
```

| Milestone | Done when | Area |
|---|---|---|
| 1. Spike | One scraper pulls one company's board into a local table, deduped | Backend |
| 2. Data model | `Opportunity` with tags (year, field, location, sponsorship, deadline) + migration | Backend |
| 3. Daily job | Scheduled job refreshes all sources; closed roles drop off | Backend |
| 4. Feed | Dashboard tab shows roles matched to the member's year | Frontend |
| 5. Tracker | Members move applications through stages; reminders fire before deadlines | Full-stack |

**Rules:** public APIs and lists only — no scraping sites whose terms forbid it (LinkedIn, Indeed, Handshake).
**You learn:** scraping, scheduled jobs, data pipelines, search.
