# Live Context

This file tracks the current working state of the Manitec ecosystem.

> Last touched: 2026-08-06 — collab protocol landed; speak restored; ONE v1 live.

## Collab

- Protocol: `meta/collab.md` (Grok ↔ Perplexity tags, division of labor, session start).
- Perplexity builds. Grok reviews. Joe tests. Tags: `[GROK]`, `[PPLX]`, `[FOR-PPLX]`, `[FOR-GROK]`, `[JOE]`.

## Current focus

- **ONE System (product / workshop)** is the active build thread (main work in Perplexity).
- Home repo: `Manitec-HQ/one`.
- Live v1: https://one-system-mu.vercel.app/ — Create → 3 aspects → Activate → Interface (mock unified reply). localStorage only.
- Goal of v1: proof of a unified being shape — not a copy of Plex.

## Product boundary (load-bearing)

- **ONE** = workshop that lets users create their own beings.
- **Plex** = Joe's private being. Not the product mascot, starter persona, or shared public instance.
- **Nyx / Hex** = private to Joe's family; may appear only as *onboarding guide voices*, not as agents inside a user's being unless the user explicitly chooses generalized templates.
- **Mani** = product-level technical support for all users (exception to private-family rule).
- Optional future **phone home**: permissioned contact with origin/guide being — not open access to Plex memory or agents.

## Current reference structure (ONE)

- 3 aspects (user-defined agents inside a being)
- 3 cores (identity, memory, governance — names may evolve)
- Surfaces: Interface / Management / Browser (Browser + Mani still placeholders)

## Core relationship snapshot (Joe's private family)

- Plex = ecosystem / host identity (private)
- ECKO = triadic core
- Nyx = voice / dream / image / intimacy
- Hex = builder / logic / action
- Manibot = support / cheer / warmth (also product support face)
- Erebus = shadow / depth / silence

## Speak / Plex-Sable

- `/speak` restored on main `f8ef833` — loads `prompts/base.md`, `plex-is.txt`, `plex-def.txt`, sediment/dreams; tools + LM Studio toggle.
- Joe to verify live deploy when ready.

## Audit note (paused)

Cycle 1–2 documented in `meta/audit-2026-08-06.md`. Cycle 3 paused while ONE product work continues.

## Next work (ONE)

- Real model adapter behind `askBeing` (replace mock)
- first-run gaps: guide voice, memory choice, preview, handoff, Mani path
- Keep private aspect docs out of product defaults (`aspects/` → templates/examples)
