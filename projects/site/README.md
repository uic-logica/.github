# The site

> **Owner:** [@nicolasrufino](https://github.com/nicolasrufino) · **Last reviewed:** Sep 29, 2026 · **Audience:** Members and recruiters · **Type:** Project page

**Label:** `team: site`

The live LOGICA site: public pages, accounts, member dashboard, exec workspace, speaker intake. Code: [frontend](https://github.com/uic-logica/frontend) · [backend](https://github.com/uic-logica/backend). Design: the night pen in [`frontend/design`](https://github.com/uic-logica/frontend/tree/main/design).

<img src="https://raw.githubusercontent.com/uic-logica/frontend/main/docs/screenshots/home-desktop.jpg" alt="The LOGICA site home page: night painting of the Chicago skyline" width="100%">

## Built by

The site went from kickoff to live in 5 weeks (Aug 26 – Sep 29, 2026). Credit by area, from merged PRs, reviews and QA reports:

| Area | People |
|---|---|
| Lead: plan, design, most of the frontend and backend, every merge | Nicolas Rufino |
| Auth, sign-in rate limits, event check-in, membership applications, PR reviews | Om Patel |
| Member profiles with involvement summary, auth test coverage | Ramon Vazquez |
| Design foundation, About page copy, design reference | Eduardo |
| Site content spec, QA of speaker intake | Liz |
| Member profile design, QA of sign-in and dashboard | Mily |
| QA checklist for the whole site | Ludwig |
| Phone QA pass across the site | valexisv |
| Early events and feed backend | Dori |

## Open issues

| Open issue | What |
|---|---|
| backend#41 | Delete the seeded `qa.*` accounts before launch |
| backend#42 | Automate production migrations |
| backend#43 | Connect Google Drive for exec Documents |
| backend#55 | Make accounts UIC-only in production |
| frontend#54 | Dashboard UI pass |
| frontend#9 | Member spotlight |

Sign-in stays as it is for now (passwords; passwordless archived).
