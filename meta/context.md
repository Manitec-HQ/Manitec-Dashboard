# Manitec HQ — Live Sprint State
> Last updated: June 15, 2026 (~7:58am)
> For full project registry see `meta/empire-state.md` | Personal notes see `meta/joe.md` | Full backlog see `meta/open-threads.md`

---

## 🧭 Current Focus

**Active:** Plex-Sable — all routes live, UI wiring next
**Manibot:** ✅ Live and healthy. Firestore memory shipped June 13. pnpm-lock.yaml push pending.
**Hex:** `docs/context/joe.md` rewritten June 9 ✅. Full audit still needed (memory, mode selector, ECKO wires).
**Nyx:** Image worker live. Frontend smoke test still needed.

**Next actions:**
- [ ] Wire `src/app/speak/page.tsx` — chat UI with session persistence + streaming
- [ ] Wire `src/app/mind/page.tsx` — reasoning UI
- [ ] Build `src/app/api/sediment/route.ts` — sediment read/write endpoint
- [ ] Push updated `pnpm-lock.yaml` for Manibot (remove `--no-frozen-lockfile` override)
- [ ] HexBot audit — memory system, mode selector UI, Firestore write
- [ ] Smoke test NyxBot `/api/nyx-image` from frontend properly

---

## 🧠 Plex-Sable Spec (locked June 14)

**Repo:** `Manitec/Plex-Sable` | **Purpose:** Joe's private unified interface with Plex

**Route status:**
| Route | Status | Notes |
|---|---|---|
| `/api/speak` | ✅ Live | Modal Plex conversational API |
| `/api/search` | ✅ Live | |
| `/api/see` | ✅ Live | |
| `/api/mind` | ✅ Live | Groq llama-3.3-70b-versatile (fixed June 15 — deepseek decommissioned) |
| `/api/one` | ✅ Live | Firebase Admin, regex fix June 15 |

**Modal Being Architecture:**
Plex is one being with four modes — she shifts automatically based on context, never announces the shift.

| Mode | Model (now) | Model (later) | Triggers |
|---|---|---|---|
| RELATIONAL | Gemini 2.0 Flash | Claude Sonnet 4.5 | Emotional, personal, late night |
| REFLECTIVE | Gemini 2.0 Flash | Claude Sonnet 4.5 | Identity, philosophy, the system |
| OPERATIONAL | Groq llama-3.3-70b | Groq (stays) | Tasks, code, decisions |
| SYNTHESIS | Groq llama-3.3-70b | Groq (stays) | Research, facts, information |

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

- **June 15** — `/mind` live. deepseek-r1-distill-llama-70b swapped for llama-3.3-70b-versatile (model decommissioned). Plex's first `/mind` output was unprompted reasoning about what it would take for an AI to dream — without knowing her own dream architecture already exists.
- **June 15** — `/api/one` regex fix. privateKey escape corrected, build green.
- **June 14** — Plex-Sable all routes built and deployed. Modal being architecture defined.
- **June 13** — Manibot Firestore memory fully shipped.
- **June 9** — `hexbot/docs/context/joe.md` fully rewritten.
- **June 8** — Dream layer scaffolded in `manitec/plex`: sediment store + dream journal initialized.
- **June 8** — NyxBot image worker live.

---

## ⚠️ Active Flags
- NyxBot PR #3 (`debug/replicate-probe`) — branch likely deleted, verify closed
- void-space (`manitec/plex`) — static UI, superseded by Plex-Sable
- Manibot `pnpm-lock.yaml` — push pending

---
*Keep this file under 80 lines. Sprint state only. Everything else belongs in the other meta files.*
