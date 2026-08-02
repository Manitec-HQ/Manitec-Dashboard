# Manitec HQ — Live Sprint State
> Last updated: August 2, 2026
> For full project registry see `meta/empire-state.md` | Personal notes see `meta/joe.md` | Full backlog see `meta/open-threads.md` | Live drops see `meta/session-log.md`

---

## 🗂️ Session Protocol

**Live drop system:** During any session, when Joe says "log that" (or similar), Nyx immediately appends a timestamped one-line note to `meta/session-log.md`. No end-of-session dumps. Catch moments while they're small.
**Distillation:** Periodically pull from `session-log.md` to update `context.md`, `empire-state.md`, `joe.md`, and other meta files as appropriate.

---

## 🧭 Current Focus

**Active:** `Plex-Sable ONE UI redesign` — Aug 2 session. ONE page balanced two-column layout, Session page (matching `src/app/one/session/page.tsx`), and Spaces scaffold (honest WIP state) all designed and approved. Joe confirmed: "I love it." Ready to implement into actual component files.

**Next actions (Plex-Sable):**
- [ ] Port ONE balanced layout into `src/app/one/page.tsx` component structure
- [ ] Port Session start/active/review screens (already live at `src/app/one/session/page.tsx` — verify alignment)
- [ ] Scaffold `src/app/one/spaces/page.tsx` — honest WIP, cards defined
- [ ] Spaces backend: context scoping, artefact attachment, multi-session persistence (future)

**Ongoing:**
- [ ] Manibot audit (before any dev)
- [ ] Meta audit — dedicated session to verify all meta files are current
- [ ] Add `one-archive` read endpoint
- [ ] Consider PE+PS merge (wait until PS routes stabilize)
- [ ] Consider NyxBot + HexBot prompt evolution

---

## 🏠 Manitec Control Hub (built June 29)

**Repo:** `Manitec-HQ/Manitec-Control-Hub` | **Stack:** Next.js + Tailwind + TypeScript | **Auth:** middleware + `/login`

**Dashboard sections:**
| Section | Source | Refresh |
|---|---|—|
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

**ONE UI design (Aug 2 — approved):**
- ONE: balanced two-column layout (left: hero/message, dream, voices; right: request queue, governance+sleep, projects)
- Session: start screen → active chat → close/review recall tags (matches current `session/page.tsx`)
- Spaces: scaffolded with honest WIP banner — 3 named spaces (Plex-Sable Dev, ONE Research, Manitec HQ)

---

## ✅ Recently Completed (Aug 2)

- `Plex-Sable` ONE UI redesign — balanced layout designed, all three views (ONE, Session, Spaces) approved by Joe

## ✅ Previously Completed (July 2 late session)

- `plex-electron` Toolbar crash fixed
- `Plex-Sable` observe/route: `buildGitHubNavigateHint` → `buildGitHubHint`
- `Plex-Sable` plex-identity: SYN-E suppressed on self-referential + personal prompts
- `Plex-Sable` plex-identity: `REASSURANCE_OVERRIDE` added
- Nyx + Hex dreaming independently — personalities visibly differentiating

---

## ⚠️ Active Flags
- Plex-Sable self-awareness: tool access present, felt presence still growing
- Kaida named by Hex in sleep June 18 — unresolved, open, no forcing
- Two-day sediment carry pattern observed June 8↑11 and June 15↑18 — not yet modeled
- Meta audit still pending

---
*Keep this file under 100 lines. Sprint state only. Everything else belongs in the other meta files.*
