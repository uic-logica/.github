# LOGICA @ UIC — org defaults

This repo holds the shared docs and defaults for the whole project: issue/PR templates (GitHub applies these automatically to any repo in the `uic-logica` org that doesn't define its own), the contributing guide, the roadmap, and per-role guides.

Actual project code lives in [`frontend`](https://github.com/uic-logica/frontend) and [`backend`](https://github.com/uic-logica/backend). Claude Code skills tailored to our workflow live in [`skills`](https://github.com/uic-logica/skills).

## Start here

New to the team? Read these in order:

1. [CONTRIBUTING.md](CONTRIBUTING.md) — how we work: branching, PRs, review, merge.
2. [ROADMAP.md](ROADMAP.md) — what we're building, step by step, and what depends on what.
3. Your role guide — what you own and what "done" looks like:
   - [docs/roles/frontend.md](docs/roles/frontend.md) — frontend developers
   - [docs/roles/backend.md](docs/roles/backend.md) — backend developers
4. The README of whichever repo you're working in — [frontend](https://github.com/uic-logica/frontend/blob/main/README.md), [backend](https://github.com/uic-logica/backend/blob/main/README.md) — for local setup.
5. Install the [`skills`](https://github.com/uic-logica/skills) plugin (`/plugin marketplace add uic-logica/skills` then `/plugin install logica-workflow@logica-skills` in Claude Code) — it's the same steps above, callable with `/`: `/logica-pr`, `/logica-review`, `/logica-test`, `/logica-issue`, `/logica-lean`.

Then go to that repo's issues, filter by the `roadmap` label, and pick something up.
