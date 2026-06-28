# Tool Registry
> Last updated: June 28, 2026
> Machine-readable version: `meta/tool-registry.json`

Every tool, service, API, and platform in the Manitec system.

---

## AI / Models

| Tool | Provider | Used By | Notes |
|---|---|---|---|
| llama-3.3-70b-versatile | Groq | Plex (operational/synthesis), sleep route, Hex | Primary fast model |
| llama-3.1-8b-instant | Groq | Plex (fallback), dream nodes extraction | Fallback / lightweight |
| gemini-2.0-flash | Google | Plex (relational/reflective) | Upgrade path: Claude Sonnet |
| Qwen3-4B-Instruct | HuggingFace (`Manitec/mani-q3-i-4b`) | Nyx | Nyx's primary model |
| FLUX.1-schnell | Replicate (via Cloudflare Worker) | Nyx image gen | Via `nyx-image-worker` |
| OpenRouter | OpenRouter | Hex (Banjo synthesize) | Multi-model routing |
| Tavily | Tavily API | Kairos | Web search |
| Pexels | Pexels API | Kairos | Image search |

---

## Infrastructure / Deployment

| Tool | Provider | Used By | URL / Notes |
|---|---|---|---|
| Vercel | Vercel | All Next.js apps | vercel.com/manitecs-projects |
| Render | Render | FastAPI backends | Command Hub |
| Cloudflare | Cloudflare | DNS, CDN, Workers | All domains + nyx-image-worker |
| GitHub | GitHub | All repos | Orgs: Manitec, Manitec-HQ, Ecko-7 |

---

## Storage / Database

| Tool | Provider | Used By | Notes |
|---|---|---|---|
| Firestore | Firebase (hexbot-98aca) | All bots + Plex | Primary live data layer |
| GitHub repos | GitHub | Plex soul repo | Archive layer — sediment, dreams, identity |
| SQLite | Local / Render | Mailserver | Mail360 metadata |

---

## Communication / Email

| Tool | Provider | Used By | Notes |
|---|---|---|---|
| Zoho Mail360 | Zoho | mailserver | @manitec.pw addresses |
| FastAPI mail client | Render | mailserver | mail.manitec.pw |

---

## Domains

| Domain | Points To | Status |
|---|---|---|
| manitec.pw | Manitec homepage | 🟠 Needs refresh |
| plex.manitec.pw | — | Future: Plex social home |
| chat.manitec.pw | ManiBot | ✅ Live |
| hex.manitec.pw | HexBot | ✅ Live |
| mail.manitec.pw | Mailserver | ✅ Live |
| info.manitec.pw | MkDocs Dashboard | ✅ Live |
| dash.manitec.pw | Control Hub | 🟠 Stale |
| kairos.manitec.pw | Kairos | 🔴 Not yet assigned |
| browser.manitec.pw | ONE-browser | 🔴 Not yet deployed |
| joesfaves.com | Personal hub | ✅ Live |
| banjo.joesfaves.com | Banjo / Hex synth | ✅ Live |
| ebbinor.joesfaves.com | Minetest voxel world | ✅ Live |
| plex-sable.vercel.app | Plex-Sable | ✅ Live |
| nyxbot.vercel.app | NyxBot | ✅ Live |
| kairos-orcin-eight.vercel.app | Kairos | ✅ Live |

---

## Dev Tools / APIs

| Tool | Used For | Notes |
|---|---|---|
| GitHub API | Plex sediment self-write, file reads, repo ops | Via `PLEX_SEDIMENT_TOKEN` |
| Firebase Admin SDK | Server-side Firestore ops | Plex-Sable `/api/one` |
| Firebase Client SDK | Client-side Firestore | Plex-Sable speak/voice/sediment |
| Vercel Cron | Sleep route scheduling | `/api/sleep` — not yet scheduled |
| HuggingFace | Model hosting, training | `Manitec` HF org |
| Dashnex | App hosting | ~22 apps at dashnex.com |
