<img src="https://raw.githubusercontent.com/uic-logica/frontend/main/docs/screenshots/home-desktop.jpg" alt="The LOGICA @ UIC site: a warm painting of the Chicago skyline" width="100%">

# LOGICA @ UIC

**Latinx and underrepresented students in computing at the University of Illinois Chicago.** We run the club on software we build ourselves, in the open.

> [!IMPORTANT]
> **Software Teams are open.** Four teams, real products, shipped in the open. Pick the one you want to build and apply: **[logicauic.org/projects →](https://logicauic.org/projects)**

[**Live site**](https://logicauic.org) · [Projects](https://logicauic.org/projects) · [Roadmap](https://github.com/uic-logica/.github/blob/main/ROADMAP.md) · [How we work](https://github.com/uic-logica/.github/blob/main/CONTRIBUTING.md)

| 120 | 85 | 13 | 5 weeks |
|:--:|:--:|:--:|:--:|
| merged PRs | closed issues | members | from kickoff to a live site |

---

## For recruiters

**What we've shipped (Aug–Oct 2026):** a full club platform: public site, @uic.edu accounts, a member dashboard, an exec workspace (money, outreach, insights, applications, speakers, event editing), speaker intake with an availability calendar, and the V4 design across all of it, in light and dark.

**What we're building next (Fall 2026):** four products, one team each.

| | Product | The hard part |
|:--:|---|---|
| 🔵 | **Opportunity board** | Daily scrapers → a feed matched to class year → an application tracker |
| 🟠 | **Resume builder** | Members' own AI tailors a proven template through our MCP tools, so the club pays for no tokens |
| 🟢 | **Event replays in 3D** | Computer vision: phone video → Gaussian-splat scene in the browser, faces blurred |
| ⚪ | **Mock interviewer** | Interview practice for roles in the tracker, with feedback through your own AI (text first, voice later) |

**Demo days: TBD.** Teams haven't started; dates get set as they do. Each writeup, slides and retro land in [projects](https://github.com/uic-logica/.github/tree/main/projects) as the project ships.

Planned like Google, sized for students: OKRs, design docs and reviews, Friday releases, launch checklists, blameless retros. See [how we run projects](https://github.com/uic-logica/.github/blob/main/docs/how-we-run-projects/README.md).

**How the team runs.** Every change is public:

```mermaid
flowchart LR
  I[Issue] --> B[Branch] --> P[Pull request] --> C{CI} --> R[Review] --> M[Lead merges]
  D[Discord check-in<br/>every 2 days] -.-> I
  style M fill:#FECC15,color:#111
```

**Look at the work:**

| See | Where |
|---|---|
| A large feature, end to end | [frontend#140: V4 redesign of the public site](https://github.com/uic-logica/frontend/pull/140) |
| A UX pass driven by an audit of every screen | [frontend#142: things open where you click, stay linkable, load instantly](https://github.com/uic-logica/frontend/pull/142) |
| Backend + frontend shipped together | [backend#64](https://github.com/uic-logica/backend/pull/64) + [frontend#91](https://github.com/uic-logica/frontend/pull/91): Software Teams applications |
| How work is planned | [Roadmap](https://github.com/uic-logica/.github/blob/main/ROADMAP.md) · [project folders](https://github.com/uic-logica/.github/tree/main/projects) |
| How people are placed on teams | [Software Teams: Fall 2026](https://github.com/uic-logica/.github/blob/main/docs/guides/software-teams-fall-2026.md) |

**Stack:** Next.js 16 · TypeScript · Tailwind · Prisma 7 · Postgres (Supabase) · Auth.js · Vercel · Vitest · GitHub Actions

---

## For LOGICA members

1. **Apply to a Software Team:** [logicauic.org/projects](https://logicauic.org/projects) → Apply to a Software Team (sign up with your @uic.edu email).
2. **Read how we work:** [CONTRIBUTING](https://github.com/uic-logica/.github/blob/main/CONTRIBUTING.md): issue → branch → PR → review → merge.
3. **Find your team's work:** [project folders](https://github.com/uic-logica/.github/tree/main/projects) and issues labeled `team: …`.
4. **Set up locally:** [frontend](https://github.com/uic-logica/frontend#readme) · [backend](https://github.com/uic-logica/backend#readme) · [Claude Code skills](https://github.com/uic-logica/skills).

Contributions are **members only**.

| Repo | What |
|---|---|
| [frontend](https://github.com/uic-logica/frontend) | The site: public pages (including Projects), dashboard, exec workspace |
| [backend](https://github.com/uic-logica/backend) | API, auth, database |
| [.github](https://github.com/uic-logica/.github) | Roadmap, workflow, team pages, documents |
| [skills](https://github.com/uic-logica/skills) | Claude Code commands for our workflow |

---

**Join us:** [Discord](https://discord.gg/nRhY72ADNh) · [Instagram](https://www.instagram.com/logicaatuic/) · [LinkedIn](https://www.linkedin.com/company/logicaatuic/)

<sub>Owner: Nicolas Rufino · Last reviewed: Oct 15, 2026</sub>
