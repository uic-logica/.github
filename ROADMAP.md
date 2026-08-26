# Roadmap

How we're building LOGICA @ UIC, step by step. Steps are numbered because each one depends on the step before it — you can't build member profiles before you have logins. The **Additions** list at the bottom has no order; pick any of those up whenever, they don't block or get blocked by anything.

Each step's tracking issues live in the repo that does the work — check `frontend` and `backend` issues labeled `roadmap` for the current state.

**The step numbers here are not issue numbers.** A roadmap step describes a *feature* and usually spans both repos. Each repo works in its own order, tracked with its own prefix — `[FE n]` on `frontend`, `[BE n]` on `backend` — and every issue names the roadmap step it belongs to. The two sections below are those orders.

## Frontend page order

The frontend does not follow the step numbers below. It works **one page at a time, and the design is finished before any code is written**:

1. **Design** the page in Figma, [Pencil](https://pen.dev), or equivalent — a real, complete mockup grounded in the art/interaction reference doc and that page's content doc. Not a rough draft to polish in code.
2. **Share it** — a short `.md` in `frontend` with the link and a preview screenshot, PR'd, so it's reviewable without opening the design tool.
3. **Build it** — implement the page directly from that finished design.
4. **Then** start the next page.

See [`frontend`'s DESIGN.md](https://github.com/uic-logica/frontend/blob/main/DESIGN.md) for the visual direction and the motion/performance bar.

| # | Page | Issue | Roadmap step | Blocked by backend? |
|---|------|-------|--------------|---------------------|
| 0 | Art/interaction reference doc + a content doc per page | frontend#18, #19 | — | no |
| 1 | Landing page | frontend#7 | Additions | no |
| 2 | Team / roles page | frontend#8 | Additions | no |
| 3 | Sign-in screen + session/role check | frontend#1 | Step 2 | yes — backend#10 |
| 4 | Profile page | frontend#2 | Step 3 | yes — backend#2 |
| 5 | Feed page + composer | frontend#3 | Step 4 | yes — backend#3 |
| 6 | Calendar + event pages | frontend#4 | Step 5 | yes — backend#4 |
| 7 | Attendance check-in + history | frontend#5 | Step 6 | yes — backend#5 |
| 8 | Form renderer + the two forms | frontend#6 | Step 7 | yes — backend#6 |

The remaining Additions (member spotlight, company-visit info page, cybersecurity showcase, sponsor wall) slot into this order whenever someone claims one — same design-then-build sequence.

## Backend order

| # | Work | Issue | Roadmap step | Status |
|---|------|-------|--------------|--------|
| 1 | Foundation: scaffold, CI, branch protection | backend#7 | Step 1 | done |
| 2 | Passwordless auth + roles | backend#10, #11 | Step 2 | in progress |
| 3 | Profiles: read/update + involvement summary | backend#2 | Step 3 | |
| 4 | Feed: `Post` model + CRUD API | backend#3 | Step 4 | |
| 5 | Events: `Event` model, RSVP, shareable-link data | backend#4 | Step 5 | |
| 6 | Attendance: model + check-in endpoint | backend#5 | Step 6 | |
| 7 | Forms: `Form`/`FormField`/`Submission` + API | backend#6 | Step 7 | |

The frontend's first two pages need no backend, so backend#10 is not holding anyone up right now — build it properly rather than fast.

## Step 1 — Foundation
**Status: done.**
GitHub org, `frontend` + `backend` repos, branch protection, CI (lint + typecheck + build on every PR), issue/PR templates, roles (Member/Reviewer/Maintainer/Owner).

## Step 2 — Auth + roles
**Status: in progress — backend#10.**
Members sign in with their UIC (`.edu`) email — no third-party OAuth (no "Sign in with Google"), and no passwords. Passwordless instead: a one-time code emailed to them, and/or a passkey saved to their device once they've set one up. The backend stores three membership roles: `MEMBER`, `BOARD`, `EXEC_BOARD`. Role decides what a member can see and do everywhere else in the app.

- **Backend:** sign-in restricted to the UIC email domain, passwordless (one-time emailed code and/or WebAuthn passkey — no Google OAuth, no passwords), roles stored on the `User` model, database-backed sessions. The exact mechanism (code, passkey, or both) is the backend owner's call to make while building — see backend#10. The existing `auth.ts` was built on Google OAuth and needs reworking to match this.
- **Frontend:** the sign-in screen and the session/role check — `[FE 3]`, frontend#1. The screen gets designed whenever; the build waits on a working session from the backend before any page can check "who's logged in, what's their role." The frontend's first two pages (landing, team) don't need this, so it isn't blocking frontend work today.

Depends on: Step 1.

## Step 3 — Member profiles
Every member has a profile: name, major, grad year, bio, and a summary of their involvement (events attended, posts made, forms submitted). You can edit your own; you can view everyone else's.

- **Backend:** endpoint to read/update a profile; an "involvement" summary computed from the tables that come online in later steps.
- **Frontend:** profile page — editable self-view, read-only public view.

Depends on: Step 2 (needs a logged-in user).

## Step 4 — Feed / announcements
One place members land and see what's happening — announcements, upcoming events, spotlights. Board and Exec Board can post; everyone can read.

- **Backend:** `Post` model, CRUD API, posting restricted to `BOARD`/`EXEC_BOARD` by a server-side role check.
- **Frontend:** feed page, post composer for board members.

Depends on: Step 2 (role check needs auth).

## Step 5 — Calendar + events
Club calendar. Every event gets its own page with a shareable, embeddable link — so it can go out on Instagram, a group chat, anywhere off-site.

- **Backend:** `Event` model, RSVP, an endpoint that returns embeddable event data for the shareable link.
- **Frontend:** calendar view, individual event pages, RSVP button, "copy link" / embed snippet.

Depends on: Step 2.

## Step 6 — Attendance tracking
Track who actually showed up, not just who RSVP'd. Feeds the involvement summary on profiles (Step 3).

- **Backend:** `Attendance` model tied to `Event` + `User`, a check-in endpoint (code or QR based).
- **Frontend:** check-in flow for whoever's running the door, "my attendance history" on profile.

Depends on: Step 5 (needs events to check into), Step 3 (attendance feeds involvement).

## Step 7 — Forms system
A general-purpose form builder, used first for two concrete forms: startup-partner intake and company-visit signup. Built in-house, not Google Forms, so submissions live in our own database and tie back to member profiles and companies.

- **Backend:** generic `Form` / `FormField` / `Submission` models, submit + list endpoints.
- **Frontend:** a renderer that reads a form schema and draws the inputs, the two concrete forms built on top of it, a submissions view for board members.

Depends on: Step 2 (submissions tie to a logged-in member where relevant).

## Additions
These are suggestions, not a required list — a starting menu, not a mandate. No dependency order — start any of these whenever, they don't block the numbered steps and aren't blocked by them.

- Landing page (public homepage content and design)
- Team / roles page (who's on Exec Board / Board, photos + bios)
- Member spotlight (recurring feature on a member, shown on feed/landing)
- Company-visit info page (public info page; the signup form itself is Step 7)
- Cybersecurity showcase page (space for security-focused work/writeups)
- Sponsor / partner wall (logos + links for supporting companies)

### Got an idea that's not on this list?

That's genuinely welcome. LOGICA isn't meant to enforce one person's roadmap on everyone — it's a shared structure and vision to build under, and there's room for your own idea inside that. You don't need permission to start something different, just visibility: write a short `.md` file in [`additions/`](additions) explaining what you want to build and why, PR it in, and let the team know. That's it — see [`additions/README.md`](additions/README.md) for the exact steps.
