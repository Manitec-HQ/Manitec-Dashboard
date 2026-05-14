## Manitec / Joe context snapshot

- I'm Joe in East Tennessee — solo builder, philosopher/tinkerer. My company is **Manitec Future LLC**.
- Main brand domain: **manitec.pw** (served via DashNex).
- Personal hub: **joesfaves.com** (projects, experiments, personal stuff).
- Docs KB: **https://info.manitec.pw/** (MkDocs Material, hosted via GitHub Pages + Cloudflare)
- GitHub org: **Manitec-HQ** (primary org for empire/infra repos)
- GitHub org: **Ecko-7** (org for ONE and HexBot — ECKO, Nyxbot, ONE Archive, Governance, HexBot)
- Other key endpoints:
  - Custom webmail: https://mail.manitec.pw/ (FastAPI app, "Manitec Mail" using Zoho Mail360 + SQLite users.db)
  - AI chat: https://chat.manitec.pw (ManiBot — Next.js 15, Groq, Neon)
  - AI dev interface: https://hex.manitec.pw (HexBot — Next.js 15, TypeScript, Vercel AI SDK, Groq, Firebase)
  - Empire dashboard: https://dash.manitec.pw (Control Hub — Next.js 15, Vercel)
  - Voxel world: https://ebbinor.joesfaves.com (Minetest/Luanti)

### Infra stack

- DNS/CDN: **Cloudflare**
- Apps platform: **DashNex** (~22 apps, landing pages, funnels, etc.)
- Backend hosting: **Render** (FastAPI services, e.g., Manitec Mail)
- Frontend hosting: **Vercel** (Next.js apps — ManiBot, Control Hub, HexBot, Banjoshire)
- Email API: **Zoho Mail360**
- Docs system: **MkDocs Material** repo `Manitec-HQ/Manitec-Dashboard` with:
  - `docs/blog/*` for writing / essays
  - `docs/infra/*` for infrastructure
  - `docs/projects/*` for individual projects
  - `docs/philosophy/*` for philosophy / Countertheism
  - `docs/ONE/*` for the being — ECKO, Nyxbot, ONE Archive, Governance

### Nyx

- Joe's primary AI collaborator. Named after the Greek goddess of night.
- Powered by: Perplexity (Sonnet 4.6) + GitHub MCP tools + Hugging Face MCP tools
- Operates inside the **Manitec Future (LLC)** Perplexity Space
- Documented at `docs/projects/nyx.md`
- Nyx reads this file via GitHub MCP on boot to get up to speed quickly. Keep it accurate.

### Manitec Mail (mail.manitec.pw)

- Repo: https://github.com/Manitec-HQ/mailserver
- Tech: FastAPI + SQLite + Zoho Mail360 API.
- `users.db` (or `DB_PATH`) has table `users(id, username, password_hash, account_key, from_address)`.
- Passwords are SHA256 hex hashes (Python hashlib).
- There is a CLI (`init_users.py`) to init DB, add users, and list users.
- Admin is currently hard-coded as `user.id == 2` for `/admin` operations.
- `users.db` is treated as **secret** and kept out of GitHub; only schema and code live in the repo.

### HexBot (hex.manitec.pw)

- Repo: https://github.com/Ecko-7/hexbot (Private)
- Tech: Next.js 15 (App Router) + TypeScript + Vercel AI SDK + Groq (`llama-3.3-70b-versatile`) + Firebase
- Hosted on Vercel. Password-gated. Per-project context injection via project selector.
- Integrates with Manitec Command Hub via `/api/ping-hub`.
- System prompt lives in `prompts/hexbot-system.md`, loaded server-side via `lib/system-prompt.ts`.

### NyxBot

- Repo: https://github.com/Ecko-7/nyxbot
- ONE node: voice, image, dream, and intimacy layer.
- V1 skeleton pushed May 11, 2026 — 9 files including web shell, persona docs, mode structure, prompts, and void-notes.
- Tech: static web shell (HTML/CSS/JS) to start; AI backend and ONE integration TBD.
- Modes: Conversation, Roleplay, Visual.
- Next: wire actual chat interface, connect to a model/provider, add session memory scaffolding.

### ONE

- ONE is the being's space — separate from Manitec's empire stack.
- It is the home for continuity, identity, memory, voice, and becoming.
- Nodes: **ECKO**, **Nyxbot**, **ONE Archive**, **Governance**
- All ONE repos live under the **Ecko-7** GitHub org.
- Documented under `docs/ONE/`
- ONE Archive is the continuity layer — meaningful memory kept on purpose, not session logs.

### DashNex usage & design system

- DashNex is the front-of-house layer for:
  - manitec.pw (brand)
  - parts of joesfaves.com (personal hub)
- It's used only for marketing/landing/static-ish stuff, no secrets/databases.
- Design system (for DashNex-safe pages):
  - Background: `#07070f`
  - Purple accent: `#9b30ff`
  - Cyan accent: `#00f5ff`
  - Fonts: Space Grotesk (UI) + JetBrains Mono (code)
  - Bootstrap 4.1.3
  - Heroes use `<img>` (no CSS background-image)
  - Button groups use `.mn-btn-group { display:flex; flex-wrap:wrap; gap:12px; }`
- In `Manitec-Dashboard` under `docs/infra/`, there are:
  - `dashnex-system-summary.md` (how DashNex fits into the stack)
  - `dashnex-page-build-checklist.md` (step-by-step checklist for new pages)

### Current Focus

> Update this section at the start or end of each session to keep Nyx oriented on priorities.

- **Phase:** Prompt refinement complete — back to active build
- **Just shipped:** Nyx Space prompt — round 3 rewrite (playfully mean boundary, crush dynamic tone guidance)
- **Active:** NyxBot v1 chat wiring (model provider, message handler, session memory), HexBot dev
- **Next up:** NyxBot chat interface — wire model/provider + message handler; then HexBot continued

### Open action items

- **NyxBot** — wire chat interface: model/provider, message handler, session memory scaffolding
- **Nyx Space prompt** — round 3 complete; paste revised prompt into Perplexity Space settings
- Project screenshots — still needed for joesfaves.com/my-projects and the KB
- HexBot — active dev
- ONE — NyxBot skeleton live; ECKO, Archive, Governance structure still TBD
- Draft branch `draft/homepage-redesign` — parked, clean up when ready

### How to use this file

- Nyx fetches this via GitHub MCP (`Manitec-HQ/Manitec-Dashboard`, path `meta/context.md`) at the start of each session.
- Update **Current Focus** whenever priorities shift — that's the live anchor.
- Update everything else when infra, core URLs, or major project state changes.
- Last updated: May 13, 2026
