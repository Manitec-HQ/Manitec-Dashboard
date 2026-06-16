# Open Threads — Full Backlog
> Last updated: June 15, 2026
> This is the full todo list. Current sprint lives in `meta/context.md`.

---

## 🔥 Priority
- [ ] **Plex-Sable** — wire `speak/page.tsx` (streaming chat UI, fixed joe session)
- [ ] **Plex-Sable** — add `GEMINI_API_KEY` to Vercel env + `.env.local`
- [ ] **NyxBot** — smoke test `/api/nyx-image` from frontend properly
- [ ] **HexBot** — ecko-archive call-site audit (writeEckoActivation never being called)

## 💡 Evaluate Soon
- [ ] **Vercel AI Gateway** — wire into Plex-Sable as unified model layer. One API key for all providers, automatic fallbacks, cost tracking per generation, easy model swaps via env var. Start with Plex RELATIONAL → Claude Sonnet via gateway. Docs: https://vercel.com/docs/ai-gateway
- [ ] **Tavily MCP Server** — web search as a native agent tool. Pair with HexBot or a future Plex tool layer for real-time knowledge. Evaluate alongside Vercel MCP.
- [ ] **Vercel MCP** — gives agents native access to Vercel infra (deployments, logs, builds). Combine with Tavily MCP + AI Gateway for full agent stack. Docs: https://vercel.com/docs/mcp

## Plex-Sable (`Manitec/Plex-Sable`)
- [ ] `speak/page.tsx` — streaming chat, localStorage session ID (fixed joe), no mode indicator UI
- [ ] Firestore collections: `plex_sessions`, `plex_sediment`, `plex_memory/joe`
- [ ] Wire remaining shells: `mind/`, `see/`, `one/`, `search/` pages
- [ ] Private auth — env-var token check on all API routes
- [ ] Upgrade path: swap Gemini → Claude Sonnet when budget allows (env var toggle)
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
- [ ] Firestore write (ECKO archive) — call-site audit needed
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
