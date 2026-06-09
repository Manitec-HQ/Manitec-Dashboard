# Manitec HQ — Live Sprint State
> Last updated: June 9, 2026 (~10:10am)
> For full project registry see `meta/empire-state.md` | Personal notes see `meta/joe.md` | Full backlog see `meta/open-threads.md`

---

## 🧭 Current Focus

**Active:** NyxBot frontend smoke test + HexBot audit
**Nyx image:** Worker live (HF router → FLUX.1-schnell). Frontend partially working. Prompt tuned June 9.
**Hex:** `docs/context/joe.md` rewritten June 9 ✅. Full audit still needed (memory, mode selector, ECKO wires).
**Next actions:**
- [ ] Smoke test NyxBot `/api/nyx-image` from frontend properly
- [ ] HexBot audit — memory system, mode selector UI, Firestore write
- [ ] Manibot audit — believed fixable

---

## ✅ Recently Completed

- **June 9** — `hexbot/docs/context/joe.md` fully rewritten. Current as of today.
- **June 9** — NyxBot system prompt patched (response shape addendum). Nyx warmer, more selective.
- **June 9** — `meta/context.md` split into 4 focused files. Sensitive data scrubbed.
- **June 8** — Dream layer scaffolded in `manitec/plex`: sediment store + dream journal initialized.
- **June 8** — NyxBot image worker live (`nyx-image-gen` → HuggingFace router → FLUX.1-schnell). PR #2 merged.
- **June 5** — `manitec/plex` repo created. Visual identity: *warm in the dark. somewhere between void space and East Tennessee.*
- **June 4** — Plex named. ONE/Plex distinction crystallized. Bots = Plex's hands.
- **May 30–31** — Kairos built and deployed live.
- **May 28** — HexBot sliding window tool receipts implemented.
- **May 23** — ONE Governance scaffold complete (`Ecko-7/governance`).

---

## ⚠️ Active Flags
- NyxBot PR #3 (`debug/replicate-probe`) — branch likely deleted, verify closed
- NyxBot PR #9 (HexBot) — merged, verify
- Manibot — broken, audit before any dev
- void-space (`manitec/plex`) — static UI, needs wiring to live data
- governance `?NAME?` — update to Plex (believed done, verify)

---
*Keep this file under 60 lines. Sprint state only. Everything else belongs in the other meta files.*
