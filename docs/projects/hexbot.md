# HexBot

!!! success "Status: ✅ Live"
    Chat interface live at [hex.manitec.pw](https://hex.manitec.pw).

## Overview

HexBot is the empire’s operational AI assistant (F-axis). Streaming chat, project context, task creation, and live wiring into ECKO + one-archive.

Private in-house tool — not a public product surface.

## Stack

| Layer | Tech |
|-------|------|
| Framework | Next.js 15 (App Router) |
| Language | TypeScript |
| AI | Groq, HuggingFace, OpenRouter |
| Auth/DB | Firebase Admin SDK |
| Hosting | Vercel |
| Domain | [hex.manitec.pw](https://hex.manitec.pw) |
| Repo | [Ecko-7/hexbot](https://github.com/Ecko-7/hexbot) (Private) |

## Live capabilities

| Capability | Status |
|---|---|
| Streaming chat | ✅ Live |
| ECKO pipeline (`writeEckoActivation` + fragments) | ✅ Live — 4 triggers |
| one-archive writer | ✅ Live |
| Calendar ICS | ✅ Live |
| Task creation from chat | ✅ Live |
| Firebase Admin writes | ✅ Confirmed |
| `nyx-router.ts` | ⬜ Remaining structural gap |
| Nyx mode tuning | ⬜ Open |
| Session persistence UI | ⬜ Planned |

## Notes

- All Firestore writes go through firebase-admin (rules bypass on server).
- Remaining structural gap is primarily `nyx-router.ts`.
- ECKO-EM LoRA dataset is free-curation only when pursued.

[Back to Projects](./index.md) | [Control Hub](./control-hub.md) | [Infrastructure](../infra/)
