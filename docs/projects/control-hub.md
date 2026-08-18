# Manitec Control Hub

!!! success "Status: ✅ Live"
    Ops dashboard at [dash.manitec.pw](https://dash.manitec.pw).

## Overview

Joe’s private ops surface for the empire: deploys, health, activity, and the topic-led **Room**.

## Stack

- **Framework:** Next.js 15 (App Router)
- **Hosting:** Vercel
- **Auth:** Middleware password gate (`HUB_DASHBOARD_PASSWORD`)
- **Domain:** [dash.manitec.pw](https://dash.manitec.pw)
- **Repo:** `Manitec-HQ/Manitec-Control-Hub`

## Live surface

| Piece | Status |
|---|---|
| Password gate | ✅ Live |
| API routes (analytics, bot-health, firebase-status, firestore, github-activity, ping, redeploy, tasks, vercel-deploys) | ✅ Live |
| Topic-led `/room` | ✅ Live — loads `meta/topics.json` + `projects.json` |
| Active topic | `plex-real-presence` |
| `/room/live` | Retired (absorbed) |

## Open

- Wire `one-archive` read endpoint into the dashboard
- Data enrichment pass
- Use Room before inventing more systems

## Notes

Room is atmospheric but not yet a full work surface. Prefer real usage over new architecture.
