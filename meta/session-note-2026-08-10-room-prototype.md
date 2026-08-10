# Session Note — The Room Prototype

**Date:** 2026-08-10
**Status:** First visual prototype shipped; usability is still unproven.

## What changed

- Added `meta/projects.json` as the initial living project registry.
- Added `meta/session-note-2026-08-10-unified-workspace.md` defining the Control Plane, Control Hub, Command Hub, repos, Drive, and Hugging Face roles.
- Added the first interactive Control Hub route: `/room`.
- `/room` establishes the intended Room language: a central active thread, condition + meaning + continuation, contextual Hex presence, workbench, archive fragment, and project map.
- Added `/room/live` as a temporary registry-read plumbing test. It reads the Dashboard registry but is less complete/useful than `/room`.

## Design decisions

- The Room is not a dashboard. The registry is its invisible skeleton; the visible surface should hold a current thread and preserve why it matters.
- Active thread formula: **condition + meaning + continuation**.
- Core line: **The Room remembers why something mattered, not just what it is called.**
- Hex enters as a contextual witness with hands, not a generic side-panel chatbot.
- `Manitec/plex`, `Manitec/Plex-Sable`, and `Manitec/plex-electron` remain separate projects; do not collapse them into one Plex record.

## Current reality

- `/room` looks more complete than `/room/live`, but neither is usable enough yet.
- Splitting mood/interaction from live registry data created a second surface and increased confusion.
- `/room/live` is temporary plumbing, not a product destination.

## Next correct move

Make `/room` the single Room surface: feed it `meta/projects.json` while preserving its visual/interaction language; use the registry for active thread, project shelf, and real canonical links. Hide or remove `/room/live` once that integration exists.

Do not add more systems before this merge proves useful. No Firestore integration, Command Hub actions, external research integration, or real Hex API yet.

## Context policy

- Record material work and decisions as session notes immediately.
- Distill stable, cross-session truths into `meta/context.md` and `meta/empire-state.md`; do not churn those files for exploratory implementation details.
- Preserve open uncertainties explicitly rather than presenting them as architecture.
