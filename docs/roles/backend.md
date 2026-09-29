# Role: Backend

> **Owner:** [@nicolasrufino](https://github.com/nicolasrufino) · **Last reviewed:** Sep 29, 2026 · **Audience:** Backend members · **Type:** Reference

You own auth, data and every API the frontend calls, in [`backend`](https://github.com/uic-logica/backend) (Next.js route handlers, Prisma, Postgres).

| Do | Don't |
|---|---|
| Check roles on the server for anything sensitive | Rely on the frontend hiding a button |
| Commit a migration with every schema change | Hand-edit the database |
| Keep secrets in `.env` (gitignored); document names in `.env.example` | Commit real values |
| Write a test for new validation or permission logic | Merge untested auth or money paths |

Sign-in today: passwords with @uic.edu sign-up; passwordless is archived in `archive/passwordless` and stays that way for now.
**Before a PR:** `npm run lint` · `npx tsc --noEmit` · `npm test`. Start with the [backend README](https://github.com/uic-logica/backend#readme).
