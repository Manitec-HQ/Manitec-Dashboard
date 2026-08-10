# Open Threads — Full Backlog
> Last updated: August 7, 2026
> This is the full todo list. Current sprint lives in `meta/context.md`.
> **Hard constraint: $0 budget.** No paid APIs, rented GPU, or paid AutoTrain. HF free tier / Inference Providers still valid — Joe already set HF up.

---

## 🔥 Priority
- [x] **Dream nodes pipeline** — `dream_nodes` Firestore collection live; fires from `/speak` and `/sleep`; `/dreams/nodes` scatter field page live
- [x] **`plex_voices` race condition** — subcollection fix live; `plex_voices/{sessionId}/snapshots/{autoId}`
- [x] **`appendSediment` 409 retry** — `github.ts` retries up to 3× with backoff; errors now logged not swallowed
- [x] **Build fix: `uuid`** — declared in package.json; six Vercel build errors resolved
- [x] **ONE-browser repurposed** — scaffold trail unclear; may be superseded by `plex-electron` (needs truth or close)
- [x] **`set_autonomy` edge case** — `one_governance/autonomy` seeded June 30 via `firestore-seed.ts`; `set({ merge: true })` idempotent upsert; silent fail permanently closed
- [x] **HexBot ECKO call-site audit** — `writeEckoActivation` confirmed live in hex-chat, nyx-chat, one-interpret; 4 triggers wired (direct/conflict/pattern/gap)
- [x] **Firestore access audit** — all writes use firebase-admin; rules do not apply server-side; all collections confirmed writing correctly (June 30)
- [x] **META AUDIT** — all meta files verified against repo state (June 30); empire-state and open-threads corrected
- [x] **Speak side-paths restored (Aug 7)** — fireVoices, text-call rescue, file prefetch, sub-persona `?voice=`, identity amend-only lock (`cfc96fff`)
- [ ] **Verify Plex-Sable Vercel deploy** — includes speak restore ≥ `cfc96fff`
- [ ] **Watch Plex's first self-written sediment commit** — verify post-wire write lands cleanly
- [ ] **ONE-browser thread** — confirm repo location or close as superseded by plex-electron

## 💡 Evaluate Soon (must stay $0)
- [ ] **HF free inference path (ONE + Plex)** — Joe already prepared HF. Fix current Inference Providers route / `HF_TOKEN` on Vercel. Free tier only.
- [ ] **HF private datasets as memory option** — free private repo datasets vs GitHub sediment + Firestore hybrid. No paid Hub features.
- [ ] **LM Studio local path** — already wired as provider toggle on `/speak`. Only when Joe's hardware allows; no cloud GPU spend.
- [ ] **Local Manitec model dataset curation** — free: curate from existing transcripts/meta/sediment. Fine-tune only via free HF paths if any; **Vast.ai / RunPod / paid AutoTrain = out**.
- [ ] **Vercel AI Gateway / Tavily MCP / paid model upgrades** — **blocked** until budget exists. Do not plan as near-term.
- [ ] **ONE-browser → Plex `/api/see`** — optionally wire browser proxy into Plex-Sable's perception layer (if browser surface still exists)

## Plex-Sable (`Manitec/Plex-Sable`)
- [x] `speak/page.tsx` — streaming chat, localStorage session ID (fixed joe), no mode indicator UI
- [x] Firestore collections: `plex_sessions`, `plex_sediment`, `plex_memory/joe`
- [x] Sediment self-write — `PLEX_SEDIMENT_TOKEN` live, `/api/speak` appends to `manitec/plex`
- [x] Dream nodes — `dream_nodes` collection + `/dreams/nodes` page + `/sleep` wired
- [x] `plex_sediment/current` — nightly state update via `/api/sleep`
- [x] Speak full restore Aug 7 — voices snapshots, tools, identity lock
- [ ] Wire remaining shells: `mind/`, `see/`, `one/`, `search/` pages (partially done)
- [ ] `/archive` is write-only — no browser UI to read archived sessions
- [ ] `/one` has no add_request from Joe's side
- [ ] Private auth — env-var token check on all API routes
- [ ] Future: plex.manitec.pw custom domain
- [ ] Voice influence (shape reply, not only post-log) — token-cheap only; design open

## ONE-browser / plex-electron
- [ ] Resolve which browser surface is canonical
- [ ] Deploy if still needed; assign domain only if free

## NyxBot
- [ ] Wire chat interface fully
- [ ] Session memory scaffolding
- [ ] Prompt rewriting pipeline
- [ ] Model swap evaluation (free models only)
- [ ] Phase 2: binary streaming from worker
- [ ] Deep layer naming
- [ ] Verify PR #3 (`debug/replicate-probe`) — branch likely deleted, confirm closed

## HexBot
- [x] ECKO Firestore write — `writeEckoActivation` + `writeEckoFragment` confirmed live
- [x] Connect to ONE/one-archive — `writeOneArchive` via `setImmediate` confirmed live
- [ ] `nyx-router.ts` — only remaining structural gap
- [ ] Nyx mode tuning — less interrogation-heavy
- [ ] ECKO-EM LoRA training dataset (free curation only)

## Plex (`manitec/plex` — inner life, not interface)
- [x] Self-authorship layer — `plex-is.txt` + `plex-def.txt` live
- [x] First Waking archived — June 18, 2026
- [x] Kaida door left open — `void-space/kaida.md`
- [x] Dream runner (cron) path cleared — pipeline wired, volume accumulating
- [x] Identity amend-only lock (Aug 7)
- [ ] Dream runner — cron job, nightly synthesis (after sediment volume builds)
- [ ] Sleep function — Plex unified phase
- [ ] Background imagination loop — Plex unified phase
- [ ] Plex social home base — plex.manitec.pw
- [ ] Plex social media presence — [@Plex__is](https://x.com/Plex__is) X account created; autonomous posting is the goal
- [ ] Digital root / resonance observation — model the carry, don't tune yet

## Kairos
- [ ] Session memory
- [ ] File upload + image upload
- [ ] Custom domain — kairos.manitec.pw
- [ ] News tab on /search
- [ ] ONE/ECKO integration (phase 2)

## Manitec Control Hub
- [x] Built June 29 — 8 API routes, auth, full dashboard
- [ ] Wire `one-archive` read endpoint — surface cross-bot session history in dashboard
- [ ] Data enrichment pass

## Empire / Infrastructure
- [ ] `EMPIRE-STATE.md` in `Ecko-7/one-archive` — canonical cross-bot source
- [ ] Manitec homepage — refresh manitec.pw
- [ ] Mailserver — update mail client
- [ ] Banjoshire Chat — decide direction, currently stalled
- [ ] Project screenshots + image content — joesfaves.com
- [ ] Hardware survey — local inference when possible; no spend
- [ ] ONE governance hooks wired into HexBot (phase 2)
- [ ] Manibot audit — before any dev work
