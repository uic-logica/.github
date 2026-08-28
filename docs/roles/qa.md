# Role: QA

You help make sure what ships actually works — testing pages and features after they're built, catching problems before members see them. No coding experience required to start.

## Right now, there's nothing to click-test yet
The frontend is still in the design phase — no page has been built yet (the landing page design itself isn't finished). So today's QA work isn't "test the site," it's **getting ready** so you can test the moment each page ships.

## What to do until pages start shipping
Pages unlock one at a time, in the [Frontend page order](../../ROADMAP.md#frontend-page-order) (landing, team/roles, sign-in, profile, feed, calendar, attendance, forms). For each page, before it's even built:

1. **Write a test checklist for that page.** What should happen on it, based on its content doc (`CONTENT.md` in the `frontend` repo) — what's on the page, what a visitor can do, what the empty state should look like.
2. **Ground it in the standing review checklist** already in [`frontend/AGENTS.md`](https://github.com/uic-logica/frontend/blob/main/AGENTS.md): loading state handled, empty state handled, error state handled, forms labeled and usable with just a keyboard.
3. One doc per page (or one doc, a section per page) — same pattern the content docs use. Your call which.

You can write the checklist as soon as a page's content doc exists — you don't need to wait for the design or the build.

## What QA does once a page ships (unlocks page by page)
- **Manual testing** against your checklist: try to break it — empty states, error states (bad login code, failed form submit), edge cases (very long bio, no photo), mobile, keyboard-only navigation, reduced-motion.
- **Reviewing PRs** with a QA eye — did they handle those states — not judging code style, that's the reviewers' job.
- **Writing bug reports** clear enough that whoever built it can reproduce and fix it without guessing.
- **Later, once you're comfortable:** turn the manual checks you keep repeating into actual automated tests, using whatever test runner is already configured in the repo — ask before adding a new one (see `AGENTS.md`'s testing section).

## Where to start
1. [CONTRIBUTING.md](../../CONTRIBUTING.md) — branch, PR, review workflow (same as everyone else).
2. [ROADMAP.md](../../ROADMAP.md) — the frontend page order, so you know what's next.
3. [`frontend`'s `AGENTS.md`](https://github.com/uic-logica/frontend/blob/main/AGENTS.md) — the checklist your testing is built on.
4. `frontend`'s `CONTENT.md` (once it covers a given page) — what that page is supposed to contain.

## Who to ask
Group chat if you're unsure what a page is supposed to do. Eduardo and LizBCa are your source for what's designed/built and when each page unlocks.
