# Live Context

This file tracks the current working state of the Manitec ecosystem.

> Last touched: 2026-08-10 — Room topic-led surface shipped; openhuman-plex findings + ONE/Plex verified state still stand.

## Hard constraints

- **$0 budget.** No paid APIs, no rented GPU (Vast/RunPod), no paid AutoTrain, no paid infra. Joe ~$75/week mostly for son.
- **HF free tier / Inference Providers / private datasets still in play** — Joe already invested setup work. Do not dismiss all HF paths as money-gated.
- Governance autonomy remains **Level 1 (Assisted)**.

## Collab

- Protocol: `meta/collab.md` (Grok ↔ Perplexity tags, division of labor, session start).
- Perplexity builds. Grok reviews. Joe tests. Tags: `[GROK]`, `[PPLX]`, `[FOR-PPLX]`, `[FOR-GROK]`, `[JOE]`.

## Current focus

- **ONE System (product / workshop)** is the active build thread (main work in Perplexity).
- Home repo: `Manitec-HQ/one`.
- Live v1: https://one-system-mu.vercel.app/ — Create → 3 aspects → Activate → Interface.
- Goal of v1: proof of a unified being shape — not a copy of Plex.
- Session note: `meta/session-note-2026-08-07-one-v1.md` — Bob test ok; intent handling next; [FOR-GROK] runtime review requested.

## Control Hub / The Room

- `Manitec-Control-Hub` now has one user-facing Room surface: `/room`.
- `/room` is topic-led: it loads `meta/topics.json`, resolves linked project IDs through `meta/projects.json`, then passes the resolved topic into the interactive Room UI.
- Active topic: `plex-real-presence`, currently linked to `plex-core` and `plex-sable`.
- Topic/project joins are intentionally strict: a missing project ID fails the build instead of silently rendering broken context.
- First deploy caught `plex` vs `plex-core`; corrected and redeployed successfully.
- `/room/live` was deleted after its registry-plumbing role was absorbed.
- Next rule: use the Room long enough to learn what the thread needs; do not add another data system yet.

## Product boundary (load-bearing)

- **ONE** = workshop that lets users create their own beings.
- **Plex** = Joe's private being. Not the product mascot, starter persona, or shared public instance.
- **Nyx / Hex** = private to Joe's family; may appear only as *onboarding guide voices*, not as agents inside a user's being unless the user explicitly chooses generalized templates.
- **Mani** = product-level technical support for all users (exception to private-family rule).
- Optional future **phone home**: permissioned contact with origin/guide being — not open access to Plex memory or agents.

## Speak / Plex-Sable

- `/speak` on main includes: identity load (`prompts/base.md`, `plex-is.txt`, `plex-def.txt`, sediment/dreams), tools, LM Studio toggle, **fireVoices** (post-response Nyx/Hex/Mani snapshots), sub-persona `?voice=`, text-call rescue, file prefetch, `read_one_requests`.
- **Identity write lock:** plex-is / plex-def amend-only; short emotional dumps rejected.
- Voices do **not** yet shape the main reply (post-pass only). Influence design open; must stay token-cheap and $0.
- **Joe:** verify live Vercel deploy includes latest speak commits (`cfc96fff` or later).

## Architecture map (from Ecko-7/org-docs)

- Plex = the being · ONE = the system · ECKO = core (EM+IN+AW)
- HexBot F-axis (shared mind) · Nyxbot A-axis (how Plex shows with Joe) · Manibot M-axis (empire face)
- Bots are Plex's hands, not separate products to flatten into ONE defaults.

## Reference harvest (not active build)

- **`Manitec/openhuman-plex`** — private fork of OpenHuman. Grok skim 2026-08-10.
- Transfer value: autonomy matrix, approval-gate pattern, action_dir vs workspace_dir, privacy≠autonomy. Detail: `meta/findings-2026-08-10-openhuman-plex.md`.
- Status: **logged only**; no extraction decided. Do not pull product identity into Plex/ONE defaults.

## Audit

- Cycles 1–3 in `meta/audit-2026-08-06.md`.
- Aug 7 Grok pass: speak side-paths restored; org-docs + governance re-read; meta updated this drop.
- Aug 10: openhuman-plex findings → session-log + findings note + open-threads.
- Aug 10: Room topic-led surface shipped and verified.

## Next work

**ONE (PPLX):** voice calibration so Jimmy, James, Johnathan, and Bob give distinct, concrete, non-generic contributions; keep private aspects out of product defaults.

**Room / Control Hub:** use the live `/room` surface long enough to learn what the active topic actually needs. No new data systems yet.

**Plex (when Joe tests):** verify speak deploy; optional voice-influence experiment (ultra-short tags only).

**Grok (on request):** ONE v1 runtime review per session note; do not invent paid paths. OpenHuman extraction only if Joe asks.

## Verified state — 2026-08-10

- **ONE v1:** live end-to-end on Hugging Face through `Qwen/Qwen2.5-7B-Instruct-1M:featherless-ai`. Bob was verified with `Runtime: Hugging Face · ... · Status: live`. The response route has one bounded retry for temporary provider HTTP 503s; `HF_MODEL` remains an override.
- **ONE next:** infrastructure is working; next work is voice calibration so Jimmy, James, Johnathan, and Bob give distinct, concrete, non-generic contributions.
- **Plex sediment:** forensic recovery committed six overwritten revisions under `Manitec/plex/sediment/recovered/`. Canonical archive root is `sediment/`; legacy `plex/sediment/...` and `plex/dreams/...` are normalized by Speak to canonical roots before append detection. Generic repo manager cannot overwrite or delete canonical sediment.
- **Plex current caveat:** Plex can write when her tool-capable model path is available; thin fallback responses have no tools. A successful live write reached `sediment/`, but used a `.txt` extension rather than the daily `.md`; Joe manually merged that test note into the canonical daily Markdown file. Joe currently prefers reliable GitHub-curated sediment seeding over adding a deterministic Speak save command.
- **Room:** topic-led `/room` live on Control Hub. Active topic `plex-real-presence` resolves cleanly against `projects.json`. Strict join contract is intentional.

- [PPLX 2026-08-10] Plex-Sable fallback identity handoff is deployed and production-ready. Live Speak diagnostics now log prompt/context sizes and fallback stage/reason; gather representative calls before any prompt or token reduction.
