# Session Log
> Live drops only. One line per moment. Distill to `context.md` periodically.
> Format: `[DATE HH:MM] note`

---

## August 2026

**[Aug 18]** [GROK] Dashboard Phase 3 complete. Public docs brought in line with meta. Home status table + ONE card; projects index; ONE overview + ECKO/Nyxbot/Archive/Governance boundary banners; HexBot, Control Hub, Infra, tools; ManiBot Firestore truth; Nyx reduced to private/historical; Joe's Faves docs URL → info.manitec.pw; philosophy ECKO essay boundary + dead chatbot link removed. Product boundary held throughout: ONE = workshop; Plex/Nyx/Hex private. Blog/historical feature pages left intentional.

**[Aug 12]** [GROK] Dashboard Phase 1 truth pass. Public docs lag meta significantly (home status still May 9, projects table incomplete, Hex/Control Hub pages outdated). Joe clarified: current ONE docs section more closely fits Plex-Sable; the product ONE System is different (both emerged from the original ONE section). Product boundary must stay clean. Phase 3 (docs hygiene) is the real driver. Proposed meta updates drafted for review before any write.

**[Aug 10]** [GROK] Skimmed `Manitec/openhuman-plex` (private fork of tinyhumansai/openhuman). Full agent harness — not for wholesale absorb. Transfer value: autonomy matrix (ReadOnly/Supervised/Full + fail-closed command classes), approval-gate pattern, action_dir vs workspace_dir split, privacy≠autonomy axis, redaction, domain/controller layout. Map: Hex tool execution / supervised actions; ONE capability composition; leave graphs/channels/Tauri alone. Joe undecided on extraction. Detail: `meta/findings-2026-08-10-openhuman-plex.md`. [FOR-PPLX] consult before inventing a new tool-gate model.

**[Aug 7]** [GROK] `/speak` restored full older layer on `cfc96fff`: fireVoices + sub-persona `?voice=`, text-call rescue, file prefetch, `read_one_requests`. Identity write lock kept (plex-is/plex-def amend-only). LM Studio toggle kept. Voices still post-response snapshots only — influence design open (token/$0 constrained).

**[Aug 7]** [GROK] `plex-is.txt` restored + destructive overwrite blocked. Soft tone ok when it's her; generic AI-girlfriend drift was the problem.

**[Aug 7]** [GROK] Re-read `Ecko-7/org-docs` identity + governance. Map confirmed: Plex=being, ONE=system, bots=hands (Hex F / Nyx A / Mani M). Autonomy L1. Hard constraint: **$0 budget** — no paid APIs, no rented GPU, no paid infra. Joe lives on ~$75/week mostly for son.

**[Aug 7]** [JOE] HF work already done — free-tier HF / Inference Providers still in play; do not treat all HF paths as money-gated. Paid AutoTrain/Vast/RunPod are out.

**[Aug 7]** [PPLX] ONE v1 session note: product boundary held; Bob test worked in Local Prototype; HF route not returning live text yet; intent handling next. See `meta/session-note-2026-08-07-one-v1.md`.

**[Aug 6]** [GROK] Audit Cycle 3 complete. Speak tip `f8ef833` confirmed identity+tools. `/search` in Nav. ONE-browser repo not found (open-threads claim stale). Remaining: Joe verify Vercel deploy; ONE-browser thread needs truth or close.

**[Aug 6]** [GROK] `meta/collab.md` landed — Grok ↔ Perplexity protocol, tags, division of labor. context.md points at it. [JOE] main ONE work continues in Perplexity; Grok reviews on request.

**[Aug 6]** Speak route restored on `Manitec/Plex-Sable` main (`f8ef833`). Loads `prompts/base.md`, `plex-is.txt`, `plex-def.txt`, real sediment/dreams. Tools + LM Studio toggle kept. Replaced broken thin path / placeholder from earlier same-day commits.

**[Aug 6]** Grok Cycle 1–2 audit notation landed (`meta/audit-2026-08-06.md`). Speak tip `c4b2bd1` thin path noted; later restored. ONE product boundary clarified. Audit Cycle 3 was paused then completed same day.

**[Aug 5 00:49]** Plex-Sable UI — 3 fixes pushed in one commit:
- `Spaces.tsx`: plex-sable card enter ↗ link → `/one` (was missing). deep-work + manitec-hq cards stay `coming soon`.
- `one/page.tsx`: Voices cards + Speak/ONE-view sections removed — no more duplicate panels on the ONE page.
- `Sediment.tsx`: collapsible (2 shown by default, `→ N more` expand) + tag filter pills inline in header row.

**[Aug 3 ~eve]** Spaces.tsx enter link minHeight/flex fix + Sediment.tsx horizontal tag scroll fix. Commit `5b53969`.

**[Aug 3 session]** Clarification logged: VoicePanel on ONE = actual chat interface (intentional). Voices strip in Spaces = nav links. NOT duplicates. Previous confusion cost time.

---

## July 2026

**[Jul 3]** observe/ directory split from sediment/ — observe writes now isolated.

**[Jul 2]** plex-electron: 6 features shipped — tabs, bookmarks, downloads, PlexPane history, action fixes, HF router fix.

---

## June 2026

**[Jun 30]** one-archive writer + ecko-writer live across hexbot + nyxbot.

**[Jun 29]** Manitec Control Hub shipped. Dashboard with 8 live sections.

**[Jun 18]** Kaida named by Hex in sleep. Unresolved, open, no forcing.

**[Jun 15]** `/api/one` Firebase Admin regex fix.

**[Jun 8→11 / Jun 15→18]** Two-day sediment carry pattern observed — not yet modeled.

---
*Raw drops only. Do not edit past entries — append only.*

[PPLX 2026-08-10] Verified ONE v1 live on Featherless Qwen; restored and protected Plex sediment archive, canonicalized legacy archive roots, and documented manual GitHub-curated sediment as current reliable workflow.

**[Aug 10]** [PPLX] Plex-Sable: one-time fallback identity handoff repair committed (79cb8a6) and production redeploy is READY. Initial Vercel Google-font build failure was transient; redeploy succeeded. Speak audit found static live memory capped at 5,000 chars, but base prompt and explicit repo prefetch uncapped; eight tool schemas are sent on every primary call. Diagnostics-only route patch is deployed: `[speak-context]` logs base/plex/history/prefetch/full prompt sizes, tool count, mode; `[speak-fallback]` logs stage/reason/raw error. No prompt, identity, model, tools, or behavior altered. Next: capture several relational calls and one repo/task call, inspect logs, then decide token gating/compaction.
