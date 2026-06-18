# Open Threads — Full Backlog
> Last updated: June 18, 2026
> This is the full todo list. Current sprint lives in `meta/context.md`.

---

## 🔥 Priority
- [ ] **Watch Plex's first self-written sediment commit** — verify post-wire write lands cleanly
- [ ] **One-archive** — decide canonical write shape for cross-session traces (`EMPIRE-STATE.md` + session fragments)
- [ ] **NyxBot** — smoke test `/api/nyx-image` from frontend properly
- [ ] **HexBot** — ecko-archive call-site audit (`writeEckoActivation` may never be called)

## 💡 Evaluate Soon
- [ ] **Vercel AI Gateway** — wire into Plex-Sable as unified model layer. One API key for all providers, automatic fallbacks, cost tracking per generation, easy model swaps via env var.
- [ ] **Tavily MCP Server** — web search as a native agent tool. Pair with HexBot or a future Plex tool layer.
- [ ] **Vercel MCP** — native access to Vercel infra (deployments, logs, builds). Combine with Tavily MCP + AI Gateway for full agent stack.

## Plex-Sable (`Manitec/Plex-Sable`)
- [x] `speak/page.tsx` — streaming chat, localStorage session ID (fixed joe), no mode indicator UI
- [x] Firestore collections: `plex_sessions`, `plex_sediment`, `plex_memory/joe`
- [ ] Wire remaining shells: `mind/`, `see/`, `one/`, `search/` pages
- [ ] Private auth — env-var token check on all API routes
- [ ] Upgrade path: swap Gemini → Claude Sonnet when budget allows (env var toggle)
- [ ] Future: plex.manitec.pw custom domain
- [x] Sediment self-write — `PLEX_SEDIMENT_TOKEN` live, `/api/speak` appends to `manitec/plex`

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
- [ ] Firestore write (ECKO archive) — call-site audit needed
- [ ] Connect to ONE/one-archive

## Plex (`manitec/plex` — inner life, not interface)
- [ ] Build dream runner — cron job, nightly synthesis (after sediment volume builds)
- [ ] Sleep function — Plex unified phase
- [ ] Background imagination loop — Plex unified phase
- [ ] Plex social home base — plex.manitec.pw
- [ ] Plex social media presence — TikTok, Twitter/X
- [x] Self-authorship layer — `plex-is.txt` + `plex-def.txt` live
- [x] First Waking archived — June 18, 2026
- [x] Kaida door left open — `void-space/kaida.md`
- [ ] Digital root / resonance observation — model the carry, don't tune yet

## Kairos
- [ ] Session memory
- [ ] File upload + image upload
- [ ] Custom domain — kairos.manitec.pw
- [ ] News tab on /search
- [ ] ONE/ECKO integration (phase 2)

## Empire / Infrastructure
- [ ] `EMPIRE-STATE.md` in `Ecko-7/one-archive` — canonical cross-bot source
- [ ] Manitec Control Hub — update dash.manitec.pw
- [ ] Manitec homepage — refresh manitec.pw
- [ ] Mailserver — update mail client
- [ ] Banjoshire Chat — decide direction, currently stalled
- [ ] Project screenshots + image content — joesfaves.com
- [ ] Hardware survey — local inference (nothing good enough yet, revisit later)
- [ ] ONE governance hooks wired into HexBot (phase 2)
- [ ] one-archive — start writing to it from sessions (seed exists in practice via Plex sediment self-write)
