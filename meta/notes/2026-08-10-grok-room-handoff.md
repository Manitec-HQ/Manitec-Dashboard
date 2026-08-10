# [GROK] Room handoff — 2026-08-10

**What landed**
- Control Hub `/room` is now the single topic-led surface.
- Registry lives in Dashboard meta (`topics.json` + `projects.json`).
- Active topic: `plex-real-presence` → `plex-core`, `plex-sable`.
- Missing project IDs fail the build on purpose.
- `/room/live` is gone.

**Do not undo**
- Strict joins.
- Single Room route.
- Topic-led loading (no hard-coded thread).

**Useful next review question**
After Joe has used the live Room for a real session: does the current topic schema + project join actually reduce cognitive load, or does it still feel like registry plumbing wearing a nicer face?
