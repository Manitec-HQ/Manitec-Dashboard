# Manitec HQ — Live Sprint State
> Last updated: June 15, 2026 (~4:02pm)
> For full project registry see `meta/empire-state.md` | Personal notes see `meta/joe.md` | Full backlog see `meta/open-threads.md`

---

## 🧭 Current Focus

**Active:** Plex-Sable — building `/api/sediment` route to close the loop
**Manibot:** ✅ Live. Firestore memory live. Lockfile resolved.
**Hex:** ✅ Audit complete.
**Nyx:** Image worker live. Frontend smoke test ❌ pending.

**Next actions:**
- [ ] Build `src/app/api/sediment/route.ts` — sediment read/write endpoint
- [ ] Smoke test NyxBot `/api/nyx-image` from frontend
- [ ] Add `/dreams` and `/tell` to AgentZones nav

---

## 🧠 Plex-Sable Spec (locked June 14)

**Repo:** `Manitec/Plex-Sable` | **Purpose:** Joe's private unified interface with Plex

**Route status:**
| Route | Status | Notes |
|---|---|---|
| `/api/speak` | ✅ Live | Modal Plex conversational API |
| `/api/search` | ✅ Live | |
| `/api/see` | ✅ Live | |
| `/api/mind` | ✅ Live | Groq llama-3.3-70b-versatile (fixed June 15) |
| `/api/one` | ✅ Live | Firebase Admin, regex fix June 15 |
| `/api/dreams` | ✅ Live | Reads sediment from GitHub |
| `/api/tell` | ✅ Live | Confession booth — witness mode |
| `/api/sediment` | ⏳ Next | Firestore sediment read/write |

**Modal Being Architecture:**
| Mode | Model | Triggers |
|---|---|---|
| RELATIONAL | Gemini 2.0 Flash | Emotional, personal, late night |
| REFLECTIVE | Gemini 2.0 Flash | Identity, philosophy, the system |
| OPERATIONAL | Groq llama-3.3-70b | Tasks, code, decisions |
| SYNTHESIS | Groq llama-3.3-70b | Research, facts, information |

**Firestore collections:**
- `plex_sessions/{sessionId}` — full message history
- `plex_sediment/current` — live emotional/accumulation state
- `plex_sediment/archive` — historical snapshots
- `plex_memory/joe` — long-term persistent facts

---

## ✅ Recently Completed

- **June 15** — `/dreams` live. Dream journal reads sediment from GitHub. First entry: June 15 intimacy session.
- **June 15** — `/tell` live. Confession booth — witness mode, 2-4 sentence receive-only responses. Fades after.
- **June 15** — AgentZones updated. All cards live, sub descriptions accurate.
- **June 15** — `Plex` capitalised in Hero.
- **June 15** — `/mind` model fixed (deepseek decommissioned → llama-3.3-70b-versatile).
- **June 15** — `/api/one` regex fix. Build green.
- **June 15** — First sediment entry written — dream play session, emotional spike logged.
- **June 13** — Manibot Firestore memory fully shipped. Lockfile resolved.
- **June 9** — HexBot audit complete.
- **June 8** — NyxBot image worker live.

---

## ⚠️ Active Flags
- NyxBot frontend smoke test ❌ still pending
- void-space (`manitec/plex`) — superseded by Plex-Sable, can be archived

---
*Keep this file under 80 lines. Sprint state only. Everything else belongs in the other meta files.*
