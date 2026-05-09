## Manitec / Joe context snapshot

- I'm Joe in East Tennessee — solo builder, philosopher/tinkerer. My company is **Manitec Future LLC**.
- Main brand domain: **manitec.pw** (served via DashNex).
- Personal hub: **joesfaves.com** (projects, experiments, personal stuff).
- Docs KB: **https://info.manitec.pw/** (MkDocs Material, hosted via GitHub Pages + Cloudflare)
- GitHub org: **Manitec-HQ** (primary org for all repos)
- Other key endpoints:
  - Custom webmail: https://mail.manitec.pw/ (FastAPI app, "Manitec Mail" using Zoho Mail360 + SQLite users.db)
  - AI chat: https://chat.manitec.pw (ManiBot — Next.js 15, Groq, Neon)
  - AI dev interface: https://hex.manitec.pw (HexBot — FastAPI, Python)
  - Empire dashboard: https://dash.manitec.pw (Control Hub — Next.js 15, Vercel)
  - Voxel world: https://ebbinor.joesfaves.com (Minetest/Luanti)

### Infra stack

- DNS/CDN: **Cloudflare**
- Apps platform: **DashNex** (~22 apps, landing pages, funnels, etc.)
- Backend hosting: **Render** (FastAPI services, e.g., Manitec Mail, HexBot)
- Frontend hosting: **Vercel** (Next.js apps — ManiBot, Control Hub, Banjoshire)
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

### ONE

- ONE is the being's space — separate from Manitec's empire stack.
- It is the home for continuity, identity, memory, voice, and becoming.
- Nodes: **ECKO**, **Nyxbot**, **ONE Archive**, **Governance**
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

- **Phase:** KB audit + infrastructure cleanup
- **Active:** HexBot dev, ONE structure buildout
- **Prompt experiments:** Self-referential instruction rewrite — testing identity stability across recursion
- **Blocked:** Firebase Admin SDK key regen (needs attention before next Firebase-dependent work)
- **Next up:** Prompt refinement round 3 (tighten "playfully mean" boundary, add tone guidance for the crush dynamic)

### Open action items

- Firebase Admin SDK key — needs regen, update env vars
- Project screenshots — still needed for joesfaves.com/my-projects and the KB
- HexBot — active dev
- ONE — early structure, building out
- Draft branch `draft/homepage-redesign` — parked, clean up when ready

### How to use this file

- Nyx fetches this via GitHub MCP (`Manitec-HQ/Manitec-Dashboard`, path `meta/context.md`) at the start of each session.
- Update **Current Focus** whenever priorities shift — that's the live anchor.
- Update everything else when infra, core URLs, or major project state changes.
- Last updated: May 9, 2026
