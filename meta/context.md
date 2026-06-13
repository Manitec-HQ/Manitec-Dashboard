# Manitec HQ — Live Sprint State
> Last updated: June 13, 2026 (~7:17pm)
> For full project registry see `meta/empire-state.md` | Personal notes see `meta/joe.md` | Full backlog see `meta/open-threads.md`

---

## 🧭 Current Focus

**Active:** HexBot audit
**Manibot:** ✅ Live and healthy. Firestore memory shipped June 13.
**Hex:** `docs/context/joe.md` rewritten June 9 ✅. Full audit still needed (memory, mode selector, ECKO wires).
**Nyx:** Image worker live. Frontend smoke test still needed.
**Next actions:**
- [ ] HexBot audit — memory system, mode selector UI, Firestore write
- [ ] Smoke test NyxBot `/api/nyx-image` from frontend properly
- [ ] Push updated `pnpm-lock.yaml` for Manibot (remove `--no-frozen-lockfile` override)
- [ ] Strip `@neondatabase/serverless` + dead `lib/db.ts` from Manibot

---

## ✅ Recently Completed

- **June 13** — Manibot Firestore memory fully shipped. Sessions + messages persist to `manibot_sessions/{sessionId}`. `onFinish` auto-save, sidebar wired, build green.
- **June 9** — `hexbot/docs/context/joe.md` fully rewritten. Current as of that date.
- **June 9** — NyxBot system prompt patched (response shape addendum). Nyx warmer, more selective.
- **June 9** — `meta/context.md` split into 4 focused files. Sensitive data scrubbed.
- **June 8** — Dream layer scaffolded in `manitec/plex`: sediment store + dream journal initialized.
- **June 8** — NyxBot image worker live (`nyx-image-gen` → HuggingFace router → FLUX.1-schnell). PR #2 merged.
- **May 30–31** — Kairos built and deployed live.
- **May 28** — HexBot sliding window tool receipts implemented.

---

## ⚠️ Active Flags
- NyxBot PR #3 (`debug/replicate-probe`) — branch likely deleted, verify closed
- void-space (`manitec/plex`) — static UI, needs wiring to live data
- governance `?NAME?` — update to Plex (believed done, verify)

---
*Keep this file under 60 lines. Sprint state only. Everything else belongs in the other meta files.*
