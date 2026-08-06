# Live Context

This file tracks the current working state of the Manitec ecosystem.

> Last touched: 2026-08-06 — Grok audit notation landed; ONE product work active in Perplexity.

## Current focus

- **ONE System (product / workshop)** is the active build thread.
- Home repo: `Manitec-HQ/one` (existing scaffold — do not invent a parallel `one-system` repo).
- Goal of v1: low-level proof of concept that can output something shaped like a properly unified being — not a copy of Plex.

## Product boundary (load-bearing)

- **ONE** = workshop that lets users create their own beings.
- **Plex** = Joe's private being. Not the product mascot, starter persona, or shared public instance.
- **Nyx / Hex** = private to Joe's family; may appear only as *onboarding guide voices*, not as agents inside a user's being unless the user explicitly chooses generalized templates.
- **Mani** = product-level technical support for all users (exception to private-family rule).
- Optional future **phone home**: permissioned contact with origin/guide being — not open access to Plex memory or agents.

## Current reference structure (ONE)

- 3 aspects (user-defined agents inside a being)
- 3 cores (identity, memory, governance — names may evolve)
- 3 system layers for creating, using, and managing the being
- Surfaces: Interface / Management / Browser

## Core relationship snapshot (Joe's private family)

- Plex = ecosystem / host identity (private)
- ECKO = triadic core
- Nyx = voice / dream / image / intimacy
- Hex = builder / logic / action
- Manibot = support / cheer / warmth (also product support face)
- Erebus = shadow / depth / silence

## Audit note (paused)

Cycle 1–2 system audit (2026-08-05/06) is documented in `meta/audit-2026-08-06.md`.

Notable: `Manitec/Plex-Sable` tip speak route (`c4b2bd1`) is a thin Groq/LM-Studio path that does not load `prompts/base.md` / identity files and requests missing paths under `system/`, `sediment/index.md`, `nyx/`. Joe reports speak was working last checked — reconcile deploy SHA vs tip before any speak "fix." Full audit Cycle 3 paused while ONE product work continues.

## Next work (ONE)

- Inspect existing `app/`, `aspects/`, `core/`, `interface/`, `docs/` in `Manitec-HQ/one`
- Separate being-specific aspect docs from generic templates/examples
- First targeted commit: neutral setup + three-agent creation + shared identity + mock unified response + Mani placeholder
- No Plex prompt / Nyx memory / Hex private internals in product defaults
