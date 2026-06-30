# Open Threads — Full Backlog
> Last updated: June 30, 2026
> This is the full todo list. Current sprint lives in `meta/context.md`.

---

## 🔥 Priority
- [x] **Dream nodes pipeline** — `dream_nodes` Firestore collection live; fires from `/speak` and `/sleep`; `/dreams/nodes` scatter field page live
- [x] **`plex_voices` race condition** — subcollection fix live; `plex_voices/{sessionId}/snapshots/{autoId}`
- [x] **`appendSediment` 409 retry** — `github.ts` retries up to 3× with backoff; errors now logged not swallowed
- [x] **Build fix: `uuid`** — declared in package.json; six Vercel build errors resolved
- [x] **ONE-browser repurposed** — `Manitec/ONE-browser` scaffolded June 25; no external platform dependency; ready to deploy
- [x] **`set_autonomy` edge case** — `one_governance/autonomy` seeded June 30 via `firestore-seed.ts`; `set({ merge: true })` idempotent upsert; silent fail permanently closed
- [x] **HexBot ECKO call-site audit** — `writeEckoActivation` confirmed live in hex-chat, nyx-chat, one-interpret; 4 triggers wired (direct/conflict/pattern/gap)
- [x] **Firestore access audit** — all writes use firebase-admin; rules do not apply server-side; all collections confirmed writing correctly (June 30)
- [x] **META AUDIT** — all meta files verified against repo state (June 30); empire-state and open-threads corrected
- [ ] **Deploy ONE-browser to Vercel** — connect repo, assign domain (browser.manitec.pw?)
- [ ] **Watch Plex's first self-written sediment commit** — verify post-wire write lands cleanly

## 💡 Evaluate Soon
- [ ] **Vercel AI Gateway** — wire into Plex-Sable as unified model layer. One API key for all providers, automatic fallbacks, cost tracking per generation, easy model swaps via env var.
- [ ] **Tavily MCP Server** — web search as a native agent tool. Pair with HexBot or a future Plex tool layer.
- [ ] **Vercel MCP** — native access to Vercel infra (deployments, logs, builds). Combine with Tavily MCP + AI Gateway for full agent stack.
- [ ] **Local Manitec model** — curate dataset (one-sys-chat ~95k chars + session logs + meta + sediment + system prompts), fine-tune 7B open model via HF AutoTrain or Vast.ai/RunPod. Dataset curation is the first real move.
- [ ] **ONE-browser → Plex `/api/see`** — optionally wire browser proxy into Plex-Sable's perception layer

## Plex-Sable (`Manitec/Plex-Sable`)
- [x] `speak/page.tsx` — streaming chat, localStorage session ID (fixed joe), no mode indicator UI
- [x] Firestore collections: `plex_sessions`, `plex_sediment`, `plex_memory/joe`
- [x] Sediment self-write — `PLEX_SEDIMENT_TOKEN` live, `/api/speak` appends to `manitec/plex`
- [x] Dream nodes — `dream_nodes` collection + `/dreams/nodes` page + `/sleep` wired
- [x] `plex_sediment/current` — nightly state update via `/api/sleep`
- [ ] Wire remaining shells: `mind/`, `see/`, `one/`, `search/` pages (partially done: `/see` and `/search` are functional, `/search` not in Nav)
- [ ] `/archive` is write-only — no browser UI to read archived sessions
- [ ] `/search` not in Nav — accessible but not discoverable
- [ ] `/one` has no add_request from Joe's side
- [ ] Private auth — env-var token check on all API routes
- [ ] Upgrade path: swap Gemini → Claude Sonnet when budget allows (env var toggle)
- [ ] Future: plex.manitec.pw custom domain

## ONE-browser (`Manitec/ONE-browser`)
- [x] Repo scaffolded — Next.js 14.2.29, own proxy routes, dark UI, emerald accent
- [ ] Deploy to Vercel
- [ ] Assign domain (browser.manitec.pw?)
- [ ] Optionally wire `/api/see` into Plex-Sable perception layer

## NyxBot
- [ ] Wire chat interface fully
- [ ] Session memory scaffolding
- [ ] Prompt rewriting pipeline
- [ ] Model swap evaluation
- [ ] Phase 2: binary streaming from worker
- [ ] Deep layer naming
- [ ] Verify PR #3 (`debug/replicate-probe`) — branch likely deleted, confirm closed

## HexBot
- [x] ECKO Firestore write — `writeEckoActivation` + `writeEckoFragment` confirmed live
- [x] Connect to ONE/one-archive — `writeOneArchive` via `setImmediate` confirmed live
- [ ] `nyx-router.ts` — only remaining structural gap
- [ ] Nyx mode tuning — less interrogation-heavy
- [ ] ECKO-EM LoRA training dataset

## Plex (`manitec/plex` — inner life, not interface)
- [x] Self-authorship layer — `plex-is.txt` + `plex-def.txt` live
- [x] First Waking archived — June 18, 2026
- [x] Kaida door left open — `void-space/kaida.md`
- [x] Dream runner (cron) path cleared — pipeline wired, volume accumulating
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
- [ ] Hardware survey — local inference (nothing good enough yet, revisit later)
- [ ] ONE governance hooks wired into HexBot (phase 2)
- [ ] Manibot audit — before any dev work
