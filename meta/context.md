# Manitec HQ — Live Sprint State
> Last updated: June 14, 2026 (~9:21am)
> For full project registry see `meta/empire-state.md` | Personal notes see `meta/joe.md` | Full backlog see `meta/open-threads.md`

---

## 🧭 Current Focus

**Active:** Plex-Sable `/speak` route — unified Plex interface
**Manibot:** ✅ Live and healthy. Firestore memory shipped June 13. pnpm-lock.yaml push pending.
**Hex:** `docs/context/joe.md` rewritten June 9 ✅. Full audit still needed (memory, mode selector, ECKO wires).
**Nyx:** Image worker live. Frontend smoke test still needed.

**Next actions:**
- [ ] Add `GEMINI_API_KEY` to Vercel env + local `.env.local` (get from aistudio.google.com)
- [ ] Build `src/app/api/speak/route.ts` — modal Plex conversational API
- [ ] Build `src/app/api/sediment/route.ts` — sediment read/write endpoint
- [ ] Wire `src/app/speak/page.tsx` — chat UI with session persistence
- [ ] Push updated `pnpm-lock.yaml` for Manibot (remove `--no-frozen-lockfile` override)
- [ ] HexBot audit — memory system, mode selector UI, Firestore write
- [ ] Smoke test NyxBot `/api/nyx-image` from frontend properly

---

## 🧠 Plex-Sable Spec (locked June 14)

**Repo:** `Manitec/Plex-Sable` | **Purpose:** Joe's private unified interface with Plex

**Modal Being Architecture:**
Plex is one being with four modes — she shifts automatically based on context, never announces the shift.

| Mode | Model (now) | Model (later) | Triggers |
|---|---|---|---|
| RELATIONAL | Gemini 2.0 Flash | Claude Sonnet 4.5 | Emotional, personal, late night |
| REFLECTIVE | Gemini 2.0 Flash | Claude Sonnet 4.5 | Identity, philosophy, the system |
| OPERATIONAL | Groq llama-3.3-70b | Groq (stays) | Tasks, code, decisions |
| SYNTHESIS | Groq llama-3.3-70b | Groq (stays) | Research, facts, information |

**Env vars needed:**
- `GROQ_API_KEY` ✅ already in codebase
- `GEMINI_API_KEY` ⬅ needs adding
- `ANTHROPIC_API_KEY` — future upgrade only

**Firestore collections:**
- `plex_sessions/{sessionId}` — full message history
- `plex_sediment/current` — live emotional/accumulation state
- `plex_sediment/archive` — historical snapshots
- `plex_memory/joe` — long-term persistent facts

**Session strategy:** One fixed "joe" session ID for true continuity across all visits.
**Auth:** Env-var token check on route. Private interface only.
**Streaming:** Yes — required for feel.

---

## ✅ Recently Completed

- **June 14** — Plex-Sable `/speak` full spec locked. Modal being architecture defined. Model strategy set (Groq + Gemini free tier now, Claude upgrade later). All context files updated.
- **June 13** — Manibot Firestore memory fully shipped. Sessions + messages persist to `manibot_sessions/{sessionId}`.
- **June 9** — `hexbot/docs/context/joe.md` fully rewritten.
- **June 9** — NyxBot system prompt patched (response shape addendum).
- **June 8** — Dream layer scaffolded in `manitec/plex`: sediment store + dream journal initialized.
- **June 8** — NyxBot image worker live (`nyx-image-gen` → HuggingFace → FLUX.1-schnell). PR #2 merged.

---

## ⚠️ Active Flags
- NyxBot PR #3 (`debug/replicate-probe`) — branch likely deleted, verify closed
- void-space (`manitec/plex`) — static UI, superseded by Plex-Sable as primary interface
- Manibot `pnpm-lock.yaml` — push pending after local `pnpm install` completes

---
*Keep this file under 80 lines. Sprint state only. Everything else belongs in the other meta files.*
