# Session Note — 2026-08-18

## Decisions

- **Plex-Electron is the canonical browser/workbench surface.** The old ONE-browser ambiguity is closed; Electron is the place for the integrated desktop/browser cockpit.
- **Local inference is not the current deployment strategy.** Joe's present hardware is not a viable model-hosting target. Build a hosted, provider-portable agent stack instead: UI/workbench and tool policy are owned; remote inference is a swappable dependency. No paid infrastructure is assumed.
- **HexBot is the primary work-agent foundation.** `Ecko-7/hexbot` already has a password-gated UI, streaming `hex-chat`, model routing/fallbacks, project context, mode variants, GitHub tools, OpenRouter/web tools, ECKO activation, and archive pathways. Its Vercel production deployment was READY at commit `c4dd7252bcfaa8f2bfd892a8b7c7075f99c1e132` (emotional cartography store).
- **NyxBot and ManiBot keep distinct roles.** `Ecko-7/nyxbot` is the voice/intimacy/dream-expression node and has ECKO + one-archive wiring. `Manitec-HQ/manibot` is the product/empire-facing support surface. Do not flatten Nyx into the code-execution role or Plex into a generic product agent.
- **Future agent action contract:** typed `read → plan → propose diff/action payload → Joe approval → execute → append-only log`. Reads and diagnostics may be session-scoped; write/deploy/merge/secret-changing actions require a complete, bound approval payload.

## Plex-Sable Security

- Security work is active and remains a priority.
- Branch: `Manitec/Plex-Sable` → `security/api-auth-sweep`.
- Commit: `b12d9f68b5daa4f88192e50d1b3b22b9aba7865e` (`feat(security): add shared API token auth helper`).
- Draft PR: #6, `security/api-auth-sweep` → `main`. It contains exactly one additive file: `src/lib/require-auth.ts`; no existing route, sediment, identity, Vercel setting, or production branch has changed.
- Preview deployment for PR #6 was READY. Production Plex-Sable was READY on main commit `2b55fc420fa6a83f8ae31df5d1996c561965debf`.
- The helper expects `PLEX_API_TOKEN`, accepts only the `x-plex-token` header, rejects query-string tokens, timing-safely compares tokens, returns 401 for invalid/missing client tokens, and returns 500 when the server env var is missing.
- **Important:** no existing API route is protected yet. Route wiring must remain source-backed and policy-aware: distinguish browser/private calls, internal or scheduled jobs, CORS `OPTIONS` preflight, and explicit public exceptions. Do not blindly whole-file replace API handlers; connector write tools use whole-file replacement and can clobber working behavior.

## Next Work

1. Preserve/advance Plex-Sable protection: obtain complete current route bodies through a reliable read path, produce a route-by-route auth matrix, then wire the helper with small reviewed commits and preview verification.
2. Before building new agent surfaces, audit HexBot's current GitHub-tool write behavior. The intended change is a proposal/approval gate, not a new agent framework.
3. Keep $0 constraint: Hugging Face/free provider paths and existing deployments remain valid; no paid APIs, rented GPU, or paid AutoTrain assumed.

[PPLX 2026-08-18] Logged hosted/provider-portable agent direction, Ecko-7 bot roles, and active Plex-Sable auth groundwork.
