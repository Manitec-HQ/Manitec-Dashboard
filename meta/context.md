# Live Context

This file tracks the current working state of the Manitec ecosystem.

> Last touched: 2026-08-06 — audit Cycle 3 complete; collab live; ONE v1 live.

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

## Speak / Plex-Sable

- `/speak` restored on main `f8ef833` — identity + tools + LM Studio toggle.
- **Joe:** verify live Vercel deploy includes that SHA.
- Nav includes `/search` (meta claim otherwise was stale).

## Audit

- Cycles 1–3 documented in `meta/audit-2026-08-06.md`.
- Cycle 3 closed: speak fixed in git; ONE-browser repo not found (thread needs truth or close); deploy verify still Joe.

## Next work (ONE)

- Real model adapter behind `askBeing` (replace mock)
- first-run gaps: guide voice, memory choice, preview, handoff, Mani path
- Keep private aspect docs out of product defaults (`aspects/` → templates/examples)
