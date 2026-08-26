# Contributing to LOGICA @ UIC

## Workflow

1. Pick up (or file) an issue on the relevant repo's board — or use `/logica-issue` to file one in the right format.
2. Branch off `main`: `yourname/short-description` (e.g. `maria/feed-endpoint`).
3. Commit, push, open a PR against `main`. Fill out the PR template — link the issue. `/logica-pr` does steps 2-3 for you, including running lint/typecheck first.
4. CI (lint + typecheck) must pass.
5. A reviewer approves — `/logica-review` runs the same checklist a human reviewer would, catch issues before it's a human's turn. A maintainer merges.

Nobody pushes directly to `main` — even leads go through a PR. This isn't bureaucracy for its own sake, it's so a second person always looks at what's shipping to a site members and partners see.

## Claude Code skills

If you're using Claude Code, install the [`skills`](https://github.com/uic-logica/skills) plugin — it packages this workflow as `/` commands (`/logica-pr`, `/logica-review`, `/logica-test`, `/logica-issue`, `/logica-lean`) so you don't have to remember the steps above by hand. See that repo's README for install instructions.

## Roles

- **Member** — branch + PR. Default for everyone who joins.
- **Reviewer** — reviews and approves PRs in their area (frontend/backend/security).
- **Maintainer** — can merge approved PRs, owns a repo area.
- **Owner** — org admin.

## Local setup

See each repo's own README for its specific setup (`frontend`, `backend`).
