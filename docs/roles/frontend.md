# Role: Frontend Developer

You own everything in the [`frontend`](https://github.com/uic-logica/frontend) repo — the site members and visitors actually see.

## What you'll build
- Pages: landing, team, feed, calendar/events, profiles, forms, spotlight, sponsor wall — see [ROADMAP.md](../../ROADMAP.md) for the order.
- All auth, data, and member-specific content comes from the backend API (`NEXT_PUBLIC_API_URL`). The backend is the source of truth — don't store real data client-side, don't fake an API response to unblock yourself, open a `backend` issue instead.
- Tailwind for styling.

## What good looks like
- `npm run lint` and `tsc --noEmit` pass locally before you open a PR — CI runs the same checks and blocks merge if they fail.
- Handle loading, empty, and error states, not just the happy path.
- Accessible by default: semantic HTML, labeled form inputs, keyboard-navigable. Use the `accessibility` label if you spot a gap.

## Where to start
1. [CONTRIBUTING.md](../../CONTRIBUTING.md) — branch, PR, review, merge workflow.
2. [ROADMAP.md](../../ROADMAP.md) — what step we're on, what depends on what.
3. [`frontend`'s README](https://github.com/uic-logica/frontend/blob/main/README.md) — local setup.
4. Install the [`skills`](https://github.com/uic-logica/skills) plugin — `/logica-pr`, `/logica-review`, `/logica-test`, `/logica-issue`, `/logica-lean` cover the steps in this doc as `/` commands.
5. Pick up an open issue on `frontend` labeled `roadmap` (or `enhancement`/`bug` for anything else).

## Who to ask
Reviews and merge decisions go through the repo's maintainers (CODEOWNERS). If a feature needs a backend endpoint that doesn't exist yet, file it on `backend` and pick up something else in the meantime.
