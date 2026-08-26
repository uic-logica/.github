# Role: Backend Developer

You own everything in the [`backend`](https://github.com/uic-logica/backend) repo — auth, the database, and every API the frontend calls.

## What you'll build
- Prisma models for each feature as it comes online (profiles, feed, events, attendance, forms) — see [ROADMAP.md](../../ROADMAP.md) for the order.
- Next.js API routes (App Router route handlers only — this repo is headless, no pages).
- Passwordless auth restricted to the club's `.edu` email domain — no Google OAuth, no passwords; a one-time emailed code and/or a device passkey (WebAuthn) instead. Database sessions, role checks (`MEMBER` / `BOARD` / `EXEC_BOARD`) on anything that needs them. Exact mechanism is the backend owner's call — see backend#10.

## What good looks like
- `npm run lint` and `tsc --noEmit` pass locally before you open a PR — CI runs the same checks and blocks merge if they fail.
- Every schema change ships with a migration (`npx prisma migrate dev --name <feature>`) committed alongside it — never hand-edit the database.
- Role checks happen on the backend, not just hidden in the frontend UI. A member sending a raw request should never be able to do more than their role allows.
- Never commit real secrets. `.env.example` documents what's needed; real values go in `.env.local` (gitignored).

## Where to start
1. [CONTRIBUTING.md](../../CONTRIBUTING.md) — branch, PR, review, merge workflow.
2. [ROADMAP.md](../../ROADMAP.md) — what step we're on, what depends on what.
3. [`backend`'s README](https://github.com/uic-logica/backend/blob/main/README.md) — local setup, where things live in the codebase.
4. Install the [`skills`](https://github.com/uic-logica/skills) plugin — `/logica-pr`, `/logica-review`, `/logica-test`, `/logica-issue`, `/logica-lean` cover the steps in this doc as `/` commands.
5. Pick up an open issue on `backend` labeled `roadmap` (or `enhancement`/`bug` for anything else).

## Who to ask
Reviews and merge decisions go through the repo's maintainers (CODEOWNERS). Auth/schema questions: check with whoever's working `backend#10` (auth onboarding) first — most other features build on top of it.
