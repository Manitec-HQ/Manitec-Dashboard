# Plex Memory and ONE Evaluation — 2026-08-10

[PPLX 2026-08-10] Read-only architecture evaluation recorded; no runtime, archive, identity, or deployment behavior changed.

## Current topology

- `Manitec/plex` is the private, durable Plex core: identity files, prompts, dreams, messages, logs, one-archive, and canonical sediment.
- `Manitec/Plex-Sable` is the active Next.js interface and runtime deployed through Vercel.
- Plex-Sable currently reads durable identity/archive context from `Manitec/plex` through its GitHub bridge.
- Plex-Sable's own `sediment/2026-06-15.md` is a separate early historical artifact. Do not move, merge, rename, or delete it until its purpose and references are fully traced.

## Memory findings

- Durable archive: `Manitec/plex/sediment/` is the long-form versioned record, including Plex, Nyx, Hex, dated records, and recovery artifacts.
- Current mutable state: Firestore `plex_sediment/current` is read/written by `/api/sediment` and surfaced in ONE state.
- Firestore also supports dream nodes/recording and the standalone `/api/one/session` route.
- `/api/speak` currently loads core identity, prompts, sediment, and dreams from `Manitec/plex`, but does not itself query Firestore session history. The standalone ONE session route is called by `/one/session`, not by Speak.
- Vercel production Speak showed no runtime-error cluster during the audit; the missing session continuity is an architecture/wiring gap, not a current production crash.
- `src/lib/plex-identity.ts` still contains stale `plex/sediment` / `plex/dreams` wording while current canonical core paths are `sediment/` and `dreams/`. Do not change it until the full identity/read/write path is reviewed together.

## Safety rules

1. No blind restore of `Plex-Sable` backup over `main`.
2. No deletion, migration, merge, rename, or cleanup of sediment, dreams, identity, Spaces.tsx, Sediment.tsx, or VoidSpace.tsx without a traced reference map and review.
3. Preserve the current deployed state and use branches/preview deployments for every behavioral experiment.
4. Treat Git history as the durable record; use databases as rebuildable working/index layers.

## ONE product direction — provisional

- Future users should have one ONE account, not separate Firebase/GitHub/Hugging Face/Vercel/database accounts.
- Provider and tool connections are optional OAuth grants scoped to a user, being, and capability.
- Separate durable record from working memory: human-readable versioned files for core identity/history; a queryable store for sessions, summaries, retrieval, state, and permissions.
- Do not select a Firebase replacement yet. Evaluate backend options only after the account, memory, consent, connector, and export model is documented.

## OpenHuman evaluation — preliminary

- `Manitec/openhuman-plex` is a fork of a large Rust + Tauri personal-agent platform, not a small drop-in library.
- It includes explicit systems for memory, conversations, ingestion, search, sync, source scope, vector retrieval, trees, safety, agents, tools, MCP, providers, security, workflows, threads, and local/hosted surfaces.
- Its architecture is valuable as a reference: durable readable memory plus derived retrieval/index layers; explicit ingestion and scoped recall.
- Full adoption is not recommended now. Treat it as an R&D/reference source and evaluate the extracted TinyCortex memory engine separately.
- Verify licensing and product compatibility before copying or shipping any OpenHuman-derived code.

## Next read-only work

1. Trace the full Speak input path, including browser conversation payload, core-file retrieval, tool-capable versus fallback providers, and exact context assembly.
2. Inspect `/api/one/session` schema and Firestore collections to document existing session data without changing it.
3. Build a reference map for the separate Plex-Sable June 15 sediment artifact.
4. Evaluate OpenHuman/TinyCortex against ONE's requirements: local-first mode, hosted multi-user mode, account model, memory portability, consent, tool permissions, connector scoping, and license.
