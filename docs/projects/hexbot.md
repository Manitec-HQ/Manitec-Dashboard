# HexBot

!!! info "Status: 🟢 Active Development"
    Chat interface live at [hex.manitec.pw](https://hex.manitec.pw).

## Overview
HexBot is Joe's private in-house AI assistant for the Manitec empire. Streaming chat interface with per-project context injection, password-gated access, and integration with Command Hub.

## Stack

| Layer | Tech |
|-------|------|
| Framework | Next.js 15 (App Router) |
| Language | TypeScript |
| AI | Vercel AI SDK + Groq (`llama-3.3-70b-versatile`) |
| Multi-provider | `@ai-sdk/openai` + OpenRouter (available, not default) |
| Auth/DB | Firebase + Firebase Admin SDK |
| Hosting | Vercel |
| Domain | [hex.manitec.pw](https://hex.manitec.pw) |
| Repo | [Ecko-7/hexbot](https://github.com/Ecko-7/hexbot) (Private) |

## Routes

| Route | Purpose |
|---|---|
| `/login` | Password gate |
| `/hex` | Main chat UI |
| `/api/hex-chat` | `POST { message, project, history }` → streaming response |
| `/api/login` | `POST { password }` → auth |
| `/api/create-task` | Task creation from chat |
| `/api/ping-hub` | Pings Manitec Command Hub |

## Prompt Architecture

| File | Purpose |
|---|---|
| `prompts/hexbot-system.md` | Canonical system prompt — single source of truth |
| `lib/system-prompt.ts` | Server-side loader, reads and caches the `.md` at runtime |
| `lib/hexbot.config.ts` | Per-project context strings + future mode/persona variants |
| `lib/types.ts` | Shared TypeScript types (`ChatMessage`, etc.) |

## Features

| Feature | Status |
|---|---|
| AI chat (streaming) | 🟢 Live |
| Full markdown rendering | 🟢 Live |
| Per-project context injection | 🟢 Live |
| Password-gated login | 🟢 Live |
| Task creation from chat | 🟢 Live |
| Command Hub integration (`ping-hub`) | 🟢 Live |
| Session persistence | ⚪ Planned |
| Note/reminder persistence | ⚪ Planned |

## Env Vars

```
GROQ_API_KEY=gsk_...
GATE_PASSWORD=your-password
```

> Firebase credentials must also be configured. Regen Firebase Admin SDK key if stale — required before any Firebase-dependent features work.

## Notes
> This is the brains of the empire. Treat it like the precious little gremlin it is. 🤖

[Back to Projects](./index.md) | [ManiBot](./manibot.md) | [Command Hub](./command-hub.md) | [Infrastructure](../infra/)
