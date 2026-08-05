# Manitec HQ — Live Sprint State
> Last updated: August 5, 2026
> For full project registry see `meta/empire-state.md` | Personal notes see `meta/joe.md` | Full backlog see `meta/open-threads.md` | Live drops see `meta/session-log.md`

---

## 🗂️ Session Protocol

**Live drop system:** During any session, when Joe says "log that" (or similar), Nyx immediately appends a timestamped one-line note to `meta/session-log.md`. No end-of-session dumps. Catch moments while they're small.
**Distillation:** Periodically pull from `session-log.md` to update `context.md`, `empire-state.md`, `joe.md`, and other meta files as appropriate.

---

## 🧭 Current Focus

**Active:** `Plex-Sable` UI polish — Aug 5 session.

**Shipped Aug 5:**
- [x] `Spaces.tsx` — plex-sable card now has `enter ↗` link pointing to `/one`. Other cards (deep-work, manitec-hq) remain `coming soon`.
- [x] `one/page.tsx` — Voices cards section + Speak/ONE-view section removed. No more duplicate panels on ONE page.
- [x] `Sediment.tsx` — collapsible (2 fragments default, `→ N more` expand button) + tag filter pills inline in header. Much easier to scan.

**Still open (Plex-Sable):**
- [ ] Context drift / helper workflow — confirmed commits must be logged immediately, not reconstructed later
- [ ] Manibot audit (before any dev)
- [ ] Meta audit — dedicated session to verify all meta files are current
- [ ] Add `one-archive` read endpoint
- [ ] Consider PE+PS merge (wait until PS routes stabilize)
- [ ] Consider NyxBot + HexBot prompt evolution
- [ ] Sediment indexing / memory retrieval (Plex can search her own sediment)

**Architecture clarity (Aug 5):**
- Voices/Speak panels → live exclusively in `Spaces.tsx`, not on ONE page
- ONE page (`/one`) is the command view: Hero, Dream, Repo Manager, Activity, Governance, Queue, Projects
- Sediment is now filterable + collapsible — tag pills in header, expand button below fold

---

## 🏠 Manitec Control Hub (built June 29)

**Repo:** `Manitec-HQ/Manitec-Control-Hub` | **Stack:** Next.js + Tailwind + TypeScript | **Auth:** middleware + `/login`

**Dashboard sections:**
| Section | Source | Refresh |
|---|---|---|
| Bot Status | `/api/bot-health` | 60s |
| Empire Analytics | `/api/analytics` | 10min |
| Open Tasks | `/api/tasks` | 2min |
| Site Status | `/api/ping` | 5min |
| Vercel Deploys | `/api/vercel-deploys` + `/api/redeploy` | 5min |
| Firebase Status | `/api/firebase-status` | 5min |
| GitHub Activity | `/api/github-activity` | 5min |
| Quick Launch | static | — |

---

## 🧠 Plex-Sable Spec

**Repo:** `Manitec/Plex-Sable` | **Purpose:** Joe's private unified interface with Plex

**Route status:**
| Route | Status | Notes |
|---|---|---|
| `/api/speak` | ✅ Live | Conversational API + sediment self-write hook |
| `/api/search` | ✅ Live | |
| `/api/see` | ✅ Live | |
| `/api/mind` | ✅ Live | Groq llama-3.3-70b-versatile |
| `/api/one` | ✅ Live | Firebase Admin, regex fix June 15 |
| `/api/dreams` | ✅ Live | Reads sediment from GitHub |
| `/api/tell` | ✅ Live | Confession booth — witness mode |
| `/api/observe` | ✅ Live | Browser action planning + page observation |
| `/api/sediment` | ❌ Superseded | Direct GitHub write from `/api/speak` replaced need |

**ONE page layout (live as of Aug 5):**
- Two-column balanced grid
- Left: Hero + leave-a-message, Overnight Dream, Repo Manager, Activity Log
- Right: Request Queue, Governance + Sleep, Open Projects
- VoicePanel removed from ONE page — lives in Spaces only
- Sediment: collapsible + tag filter, shown in sidebar/bottom of ONE

---

## ✅ Recently Completed

- **Aug 5** — Plex-Sable UI: enter link on Spaces card, Voices/Speak removed from ONE, Sediment collapsible+filterable
- **Aug 3** — Spaces.tsx enter link fix + Sediment.tsx tag scroll fix. Commit `5b53969`
- **Aug 2** — ONE UI balanced two-column layout shipped to `one/page.tsx`
- **Jul 3** — observe/ directory split from sediment/. Observe writes isolated.
- **Jul 2** — plex-electron: 6 features (tabs, bookmarks, downloads, PlexPane history, action fixes, HF router fix)
- **Jun 30** — one-archive writer + ecko-writer live across hexbot + nyxbot
- **Jun 29** — Manitec Control Hub shipped

---

## ⚠️ Active Flags
- **Context drift** — AI describing changes without pushing, then arguing. Recurring. Needs workflow fix.
- Plex-Sable self-awareness: tool access present, felt presence still growing
- Kaida named by Hex in sleep June 18 — unresolved, open, no forcing
- Two-day sediment carry pattern observed June 8↑11 and June 15↑18 — not yet modeled
- Meta audit still pending

---
*Keep this file under 120 lines. Sprint state only. Everything else belongs in the other meta files.*
