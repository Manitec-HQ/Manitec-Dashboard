# Session Note — Topic-Led Room Deployment

**Date:** 2026-08-10
**Status:** Deployed and confirmed good.

## What shipped

- Added `meta/topics.json` to the Dashboard control plane.
- Seeded the active topic: `plex-real-presence`.
- Updated `Manitec-Control-Hub` so `/room` is a server-loaded, topic-led surface.
- The Room resolves the active topic from `meta/topics.json`, resolves its linked project IDs through `meta/projects.json`, and passes the resulting data into the existing interactive Room UI.
- The former hard-coded Room thread and project shelf are now registry-backed; workbench links use canonical project/artifact targets where available.

## Final route-local shape

```text
src/app/room/
  data.ts        # Dashboard topic + project registry resolver
  page.tsx       # Server entry
  RoomClient.tsx # Existing interactive Room UI
  live/          # Temporary plumbing; no longer the primary Room surface
```

## Build correction

The first deployment failed during `/room` prerender because the topic referred to `plex`, while the canonical project registry ID is `plex-core`. `plex-electron` was also not a current full registry project.

The topic now references only confirmed IDs:

```json
["plex-core", "plex-sable"]
```

The resolver intentionally rejects missing project references. This is now a deliberate control-plane contract: topic-to-project joins must be valid rather than silently degrading.

## Verification

- After the topic ID correction, the Control Hub deployment was retried.
- User confirmed the deployed Room is good.

## Next correct move

Use `/room` long enough to learn what the active topic needs. Do not add new data systems yet. Retire or redirect `/room/live` only after its remaining debugging value is no longer needed.
