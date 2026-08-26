# Roadmap

How we're building LOGICA @ UIC, step by step. Steps are numbered because each one depends on the step before it — you can't build member profiles before you have logins. The **Additions** list at the bottom has no order; pick any of those up whenever, they don't block or get blocked by anything.

Each step's tracking issues live in the repo that does the work — check `frontend` and `backend` issues labeled `roadmap` for the current state.

## Step 1 — Foundation
**Status: done.**
GitHub org, `frontend` + `backend` repos, branch protection, CI (lint + typecheck + build on every PR), issue/PR templates, roles (Member/Reviewer/Maintainer/Owner).

## Step 2 — Auth + roles
**Status: in progress — backend#1.**
Members sign in with their UIC (`.edu`) email — no third-party OAuth (no "Sign in with Google"), and no passwords. Passwordless instead: a one-time code emailed to them, and/or a passkey saved to their device once they've set one up. The backend stores three membership roles: `MEMBER`, `BOARD`, `EXEC_BOARD`. Role decides what a member can see and do everywhere else in the app.

- **Backend:** sign-in restricted to the UIC email domain, passwordless (one-time emailed code and/or WebAuthn passkey — no Google OAuth, no passwords), roles stored on the `User` model, database-backed sessions. The exact mechanism (code, passkey, or both) is the backend owner's call to make while building — see backend#1. The existing `auth.ts` was built on Google OAuth and needs reworking to match this.
- **Frontend:** nothing yet. Waits on a working session from the backend before any page can check "who's logged in, what's their role."

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
