# Links point at logicauic.org

> **Owner:** [@nicolasrufino](https://github.com/nicolasrufino) · **Last reviewed:** Sep 30, 2026 · **Audience:** LOGICA members · **Type:** Change note
>
> **PRs:** .github (this PR) · frontend README

## Why

The site moved to **logicauic.org**, but the org profile, roadmap, guides and repo settings still linked the old Vercel address.

## What changes

| Where | Before | After |
|---|---|---|
| Org profile page, roadmap, contributing, Software Teams guide | `logicauic-logica5.vercel.app` | `logicauic.org` |
| frontend README | old link + "set SITE_URL before launch" | new link; SITE_URL now defaults to logicauic.org |
| GitHub org website, frontend repo website | empty / old link | `https://logicauic.org` |

## Not done

The old Vercel address still works (the backend allows both), so old bookmarks don't break.
