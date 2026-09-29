# Role: Frontend

> **Owner:** [@nicolasrufino](https://github.com/nicolasrufino) · **Last reviewed:** Sep 29, 2026 · **Audience:** Frontend members · **Type:** Reference

You build what members and visitors see, in [`frontend`](https://github.com/uic-logica/frontend) (Next.js, Tailwind).

| Do | Don't |
|---|---|
| Build from the night design: [`design/logica.pen`](https://github.com/uic-logica/frontend/tree/main/design) + DESIGN.md | Invent a new look for a page |
| Get all data from the backend through `/api` | Fake API responses to unblock yourself — open a backend issue |
| Handle loading, empty, error and signed-out states | Ship only the happy path |
| Label fields, keep keyboard access and focus rings | Remove accessibility to simplify |

**Before a PR:** `npm run lint` · `npx tsc --noEmit` · `npm test`. Start with the [frontend README](https://github.com/uic-logica/frontend#readme), then pick an issue labeled with your team.
