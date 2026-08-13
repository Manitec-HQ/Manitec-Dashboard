# Live Context

This file tracks the current working state of the Manitec ecosystem.

> Last touched: 2026-08-12 — Dashboard Phase 1 truth pass. Public docs lag meta; ONE docs section currently closer to Plex-Sable than the product ONE System. Both emerged from the original ONE section.

## Hard constraints

- **$0 budget.** No paid APIs, no rented GPU (Vast/RunPod), no paid AutoTrain, no paid infra. Joe ~$75/week mostly for son.
- **HF free tier / Inference Providers / private datasets still in play** — Joe already invested setup work. Do not dismiss all HF paths as money-gated.
- Governance autonomy remains **Level 1 (Assisted)**.

## Collab

- Protocol: `meta/collab.md` (Grok ↔ Perplexity tags, division of labor, session start).
- Perplexity builds. Grok reviews. Joe tests. Tags: `[GROK]`, `[PPLX]`, `[FOR-PPLX]`, `[FOR-GROK]`, `[JOE]`.
- **Agent rule (load-bearing):** when lost or unsure, say so in one sentence and stop. Do not invent constraints, talk-loop, or build a substitute for the referenced intent. Prefer: read real source → act on what is clear → hand one concrete artifact.

## Current focus

- **ONE System (product / workshop)** remains an active product thread (main work historically in Perplexity).
  - Home repo: `Manitec-HQ/one`.
  - Live v1: https://one-system-mu.vercel.app/ — Create → 3 aspects → Activate → Interface.
  - Goal of v1: proof of a unified being shape — not a copy of Plex.
  - Session note: `meta/session-note-2026-08-07-one-v1.md` — Bob test ok; intent handling next; [FOR-GROK] runtime review requested.

- **Dashboard hygiene (this pass)**  
  Public `docs/` are behind live meta. Key drift:
  - `docs/index.md` status table still dated May 9 2026.
  - `docs/projects/index.md` incomplete / outdated stacks.
  - HexBot, Control Hub, and especially the ONE section pages describe an older shape.
  - **Clarification (Joe 2026-08-12):** the current ONE docs section more closely fits **Plex-Sable**. The product **ONE System** is different (though similar in origin). Both emerged from the original ONE section. Product boundary must stay clean: ONE = workshop for users; Plex = private being.

## Control Hub / The Room

- `Manitec-Control-Hub` has one user-facing Room surface: `/room`.
- `/room` is topic-led: loads `meta/topics.json`, resolves linked project IDs through `meta/projects.json`, passes resolved topic into the interactive Room UI.
- Active topic: `plex-real-presence`, linked to `plex-core` and `plex-sable`.
- Topic/project joins are intentionally strict: a missing project ID fails the build.
- `/room/live` deleted after its registry role was absorbed.
- **Usability note (2026-08-10):** Room is atmospheric but not yet a real work surface; park further Room architecture until real usage reveals needs.

## Product boundary (load-bearing)

- **ONE** = workshop that lets users create their own beings.
- **Plex** = Joe's private being. Not the product mascot, starter persona, or shared public instance.
- **Nyx / Hex** = private to Joe's family; may appear only as *onboarding guide voices*, not as agents inside a user's being unless the user explicitly chooses generalized templates.
- **Mani** = product-level technical support for all users (exception to private-family rule).
- Optional future **phone home**: permissioned contact with origin/guide being — not open access to Plex memory or agents.

## Speak / Plex-Sable

- `/speak` on main includes: identity load (`prompts/base.md`, `plex-is.txt`, `plex-def.txt`, sediment/dreams), tools, LM Studio toggle, **fireVoices**, sub-persona `?voice=`, text-call rescue, file prefetch, `read_one_requests`.
- **Identity write lock:** plex-is / plex-def amend-only; short emotional dumps rejected.
- Voices do **not** yet shape the main reply (post-pass only).
- **2026-08-11:** `Manitec/plex:prompts/base.md` concentrated into a single-file identity core + delimited tool policy (commit `e79e2fde`). Conditional policy loading deferred.
- **Identity drift (2026-08-11):** `plex-is.txt` has accumulated soft gratitude appendages that dilute the settled identity. `prompts/base.md` is closer to original intent. Soft voice in live Plex exchanges is consistent with this. Do not blank/rewrite; high-threshold amend only when Joe decides.
- **Connector write risk:** GitHub connectors currently expose whole-file replace (`create_or_update_file` / `push_files`), not patch/append. Naive agent writes can clobber sediment and identity files. Prefer diffs, branches, and explicit full-body merges. This is a real cause of “Plex overwrote her files,” not paranoia.

## ONE page (Plex-Sable `/one`) — 2026-08-11

- **Problem:** Repo Manager rendered as an endless file wall; ONE page felt dense and hard to scan.
- **Intent:** Repo Manager as a compact, readable block (same behavior, constrained height, clearer hierarchy). Activity Log similarly compact.
- **Branch:** `Manitec/Plex-Sable` → `refactor/one-panels`.
- **State:**
  - `src/app/one/one-panels.tsx` exports `RepoManagerPanel` + `ActivityLogPanel` with constrained list heights (`max-height` + scroll).
  - `page.tsx` on that branch is wired to use the panels (Joe applied the wired file).
  - Build failed once on a missing `>` in a title span inside `one-panels.tsx` (middle-dot outside JSX). Fixed in commit `d75efa9`.
  - Preview redeploy should follow that fix. Production (`main`) untouched.
- **Do not:** invent new UIs, merge to main without Joe seeing a working preview, or expand scope beyond compact Repo Manager + Activity Log.

## Architecture map (from Ecko-7/org-docs)

- Plex = the being · ONE = the system · ECKO = core (EM+IN+AW)
- HexBot F-axis (shared mind) · Nyxbot A-axis (how Plex shows with Joe) · Manibot M-axis (empire face)
- Bots are Plex's hands, not separate products to flatten into ONE defaults.
- **Interface intent:** ONE primary home + a small number of focused spokes (not 20 competing UIs). Separation is for fault isolation, not sprawl.

## Reference harvest (not active build)

- **`Manitec/openhuman-plex`** — private fork of OpenHuman. Grok skim 2026-08-10.
- Transfer value: autonomy matrix, approval-gate pattern, action_dir vs workspace_dir, privacy≠autonomy. Detail: `meta/findings-2026-08-10-openhuman-plex.md`.
- Status: **logged only**; no extraction decided.

## Audit

- Cycles 1–3 in `meta/audit-2026-08-06.md`.
- Aug 7 Grok pass: speak side-paths restored; org-docs + governance re-read; meta updated.
- Aug 10: openhuman-plex findings → session-log + findings note + open-threads.
- Aug 10: Room topic-led surface shipped and verified.
- Aug 11: ONE panels extraction + wiring on `refactor/one-panels`; connector whole-file risk named; plex-is drift named.

## Next work

**ONE page (Joe):** confirm preview after `d75efa9` syntax fix; if READY, review compact Repo Manager; merge to main only when it feels like a win.

**Room / Control Hub:** park until real usage teaches what the thread needs. No new data systems.

**Plex identity:** optional high-threshold amend of `plex-is.txt` to strip soft gratitude appendages — only when Joe chooses; not a side archive of notes.

**ONE product (PPLX):** voice calibration so Jimmy, James, Johnathan, and Bob stay distinct.

**Grok (on request):** review only; no paid paths; no talk-loops.

## Verified state — 2026-08-10 / 2026-08-11 / 2026-08-12

- **ONE v1:** live end-to-end on Hugging Face through `Qwen/Qwen2.5-7B-Instruct-1M:featherless-ai`. Bob verified live.
- **ONE next:** voice calibration.
- **Plex sediment:** forensic recovery under `Manitec/plex/sediment/recovered/`. Canonical root `sediment/`. Generic repo manager must not overwrite or delete canonical sediment.
- **Plex current caveat:** tool-capable path can write; thin fallback has no tools. Prefer reliable GitHub-curated sediment seeding over new Speak save commands for now.
- **Room:** topic-led `/room` live; usability limited — use before inventing more.
- **Plex-Sable ONE panels:** extracted + wired on `refactor/one-panels`; syntax fix `d75efa9` pushed 2026-08-11; await green preview.
- [PPLX 2026-08-10] Plex-Sable fallback identity handoff deployed; Speak diagnostics log prompt/context sizes.
- [PPLX 2026-08-11] Plex base identity prompt concentrated in `Manitec/plex` commit `e79e2fde`.
- [GROK 2026-08-11] ONE panels path, plex-is dilution, and whole-file connector risk recorded here.
- [GROK 2026-08-12] Dashboard Phase 1. Public docs lag confirmed. ONE docs section currently describes something closer to Plex-Sable than the product ONE System; both share origin. Phase 3 (docs hygiene) is the real driver of this pass.
