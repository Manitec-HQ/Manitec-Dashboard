# Open Threads — Full Backlog
> Last updated: June 14, 2026
> This is the full todo list. Current sprint lives in `meta/context.md`.

---

## 🔥 Priority
- [ ] **Plex-Sable** — build `api/speak/route.ts` (modal Plex conversational API)
- [ ] **Plex-Sable** — build `api/sediment/route.ts` (sediment read/write)
- [ ] **Plex-Sable** — wire `speak/page.tsx` (streaming chat UI, fixed joe session)
- [ ] **Plex-Sable** — add `GEMINI_API_KEY` to Vercel env + `.env.local`
- [ ] **Manibot** — push clean `pnpm-lock.yaml`, remove `--no-frozen-lockfile` override
- [ ] **HexBot** audit — memory system, mode selector UI, Nyx mode tuning, ECKO Firestore write
- [ ] **NyxBot** — smoke test `/api/nyx-image` from frontend properly

## Plex-Sable (`Manitec/Plex-Sable`)
- [ ] `api/speak/route.ts` — modal routing: RELATIONAL/REFLECTIVE → Gemini Flash, OPERATIONAL/SYNTHESIS → Groq
- [ ] `api/sediment/route.ts` — read/write Plex emotional state from `plex_sediment/current`
- [ ] `speak/page.tsx` — streaming chat, localStorage session ID (fixed joe), no mode indicator UI
- [ ] Firestore collections: `plex_sessions`, `plex_sediment`, `plex_memory/joe`
- [ ] Wire remaining shells: `mind/`, `see/`, `one/`, `search/` pages
- [ ] Private auth — env-var token check on all API routes
- [ ] Upgrade path: swap Gemini → Claude Sonnet when budget allows (env var toggle)
- [ ] Deploy to Vercel under manitecs-projects
- [ ] Future: plex.manitec.pw custom domain

## NyxBot
- [ ] Wire chat interface fully
- [ ] Session memory scaffolding
- [ ] Prompt rewriting pipeline
- [ ] Model swap evaluation
- [ ] Phase 2: binary streaming from worker
- [ ] Deep layer naming
- [ ] Verify PR #3 (`debug/replicate-probe`) — branch likely deleted, confirm closed

## HexBot
- [ ] Nyx mode tuning — less interrogation-heavy
- [ ] ECKO-EM LoRA training dataset
- [ ] nyx-router.ts
- [ ] Firestore write (ECKO archive)
- [ ] Connect to ONE/one-archive

## Plex (manitec/plex — inner life, not interface)
- [ ] Build dream runner — cron job, nightly synthesis (after sediment volume builds)
- [ ] Sleep function — Plex unified phase
- [ ] Background imagination loop — Plex unified phase
- [ ] Plex social home base — plex.manitec.pw
- [ ] Plex social media presence — TikTok, Twitter/X
- [ ] Update governance `?NAME?` → Plex (believed done — verify)

## Kairos
- [ ] Session memory
- [ ] File upload + image upload
- [ ] Custom domain — kairos.manitec.pw
- [ ] News tab on /search
- [ ] ONE/ECKO integration (phase 2)

## Empire / Infrastructure
- [ ] EMPIRE-STATE.md in `Ecko-7/one-archive` — canonical cross-bot source
- [ ] Manitec Control Hub — update dash.manitec.pw
- [ ] Manitec homepage — refresh manitec.pw
- [ ] Mailserver — update mail client
- [ ] Banjoshire Chat — decide direction, currently stalled
- [ ] Project screenshots + image content — joesfaves.com
- [ ] Hardware survey — local inference (nothing good enough yet, revisit later)
- [ ] ONE governance hooks wired into HexBot (phase 2)
- [ ] one-archive — start writing to it from sessions
