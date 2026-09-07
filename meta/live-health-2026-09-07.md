# Live Bot Health Checkpoint — 2026-09-07

> Source: Joe's manual chat tests plus Vercel runtime logs.
> Status: point-in-time evidence; not a complete production-health audit.

## Purpose

Record the observed state of the live bot surfaces before any repair, migration, consolidation, or architectural change. This supports the current Plex mapping objective: preserve and understand existing systems first, then make minimal, reversible repairs.

## Manual test results

| Surface | Joe's test result | Current interpretation |
|---|---|---|
| HexBot | Worked | Preserve as the working behavioral/reference system; no repair proposed yet. |
| NyxBot | Failed | `/api/nyx-chat` returned HTTP 500 twice; root cause not yet surfaced by Vercel beyond a Node deprecation warning. |
| ManiBot | Failed | Vercel identifies two unavailable/decommissioned model calls in `/api/chat`. |
| Plex-Sable | Failed | Vercel identifies a Firestore document-size limit failure in `/api/speak`. |

## Vercel evidence

### Plex-Sable

- Project: `plex-sable` (`Manitec/Plex-Sable`).
- Route: `POST /api/speak`.
- Observed at: `2026-09-07T10:09:19Z`.
- HTTP status: `500`.
- Root error: Firestore rejected a write to `plex_sessions/joe` because the document was `1,048,636` bytes, above Firestore's `1,048,576`-byte maximum.
- The route logged successful context construction before the failed persistence attempt: `basePromptChars: 3041`, `plexContextChars: 2483`, `historyChars: 313`, `fullPromptChars: 5568`, `toolCount: 0`, mode `relational`.
- Error cluster first observed: `2026-08-31T14:27:07Z`; last observed: `2026-09-07T10:09:19Z`.

### NyxBot

- Project: `nyxbot` (`Ecko-7/nyxbot`).
- Route: `POST /api/nyx-chat`.
- Observed at: `2026-09-07T09:56:18Z` and `2026-09-07T09:56:55Z`.
- HTTP status: `500` both times.
- Vercel surfaced `(node:4) [DEP0169] DeprecationWarning` for `url.parse()`; this is a maintenance warning, not yet a proven root cause of the 500s.
- No Firebase document-limit error was returned in the retrieved Nyx logs.

### ManiBot

- Project: `mani_bot` (`Manitec-HQ/manibot`).
- Route: `/api/chat`.
- Vercel errors during Joe's test window:
  - `meta-llama/llama-4-scout-17b-16e-instruct` does not exist or is inaccessible at Groq (`404`, `model_not_found`).
  - `deepseek-r1-distill-llama-70b` is decommissioned at Groq (`400`, `model_decommissioned`).
- Both are non-retryable model-selection failures in the current route path.

## Working hypothesis boundaries

- The evidence does not establish that Firestore as a whole is storage- or quota-exhausted.
- It does establish that one Plex-Sable Firestore document is oversized and cannot accept further writes.
- Nyx failure is confirmed, but its root cause remains unresolved.
- Mani failure is directly attributable to stale model identifiers in the observed requests.
- HexBot worked in the manual test and should be treated as a reference system, not an immediate refactor target.

## Repair sequence

1. Do not delete, migrate, merge, or consolidate existing records during discovery.
2. ManiBot: identify current model call sites/fallback handling and make the smallest replacement/guard change for the two confirmed dead IDs.
3. NyxBot: inspect broader route logs and terminal exception behavior before changing models, Firebase, or memory code.
4. Plex-Sable: preserve the current `plex_sessions/joe` record before changing its write strategy; then make persistence failure nonfatal and begin a new/rotated future session record.
5. HexBot: continue mapping; do not change the currently working primary chat path.
6. Continue building the evidence-backed Plex 3 × 3 map: Nyx, Hex, and Mani remain distinct real systems coordinated by Plex, rather than copies folded into one UI.

## Related discovery records

- `Ecko-7/hexbot/docs/audits/hexbot-discovery-2026-09-07.md`
- `Ecko-7/nyxbot/docs/audits/nyxbot-discovery-2026-09-07.md`

## Next evidence pass

- Read ManiBot's actual chat route and model configuration.
- Retrieve NyxBot route-level runtime details around its 500 responses.
- Map Plex-Sable's `plex_sessions/joe` writer/readers before any data operation.
- Refresh this checkpoint after each verified repair or runtime test.
