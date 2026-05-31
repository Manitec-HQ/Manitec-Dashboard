# Kairos

!!! success "Status: Live"
    Kairos is deployed and fully functional. Core loop, search mode, and image search are all live.

## Overview

Kairos is Manitec's AI-powered search product — built in one afternoon session on May 30, 2026. It synthesizes the web into a single cited answer using Tavily for retrieval and Groq for synthesis. It also includes a dedicated search mode at `/search` that preserves the Manitec Search terminal aesthetic, with web and image search tabs.

**Tagline:** *The right answer at the right moment.*

---

## Quick Links

| Resource | URL |
|---|---|
| Live App | [kairos-orcin-eight.vercel.app](https://kairos-orcin-eight.vercel.app) |
| Concept Page | [manitec.pw/kairos](https://manitec.pw/kairos) |
| GitHub Repo | [Manitec-HQ/kairos](https://github.com/Manitec-HQ/kairos) |
| Search Mode | [kairos-orcin-eight.vercel.app/search](https://kairos-orcin-eight.vercel.app/search) |

---

## Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 15, TypeScript |
| Search / Retrieval | Tavily API |
| AI Synthesis | Groq (LLaMA 3) |
| Image Search | Pexels API |
| Deployment | Vercel |
| Repo | Manitec-HQ/kairos |

---

## Routes

### `/` — Answer Mode
The main Kairos interface. User enters a query, Tavily retrieves web results, Groq synthesizes a cited answer. Hero section hides after first search for a clean results experience.

### `/search` — Manitec Search
Terminal-aesthetic search page. Replaces the original Google CSE-powered Manitec Search (deprecated — Google no longer allows full web search via PSE).

- **WEB tab** — Tavily raw results: title, URL, snippet
- **IMAGES tab** — Pexels image grid with photographer attribution

---

## API Routes

| Route | Method | Purpose |
|---|---|---|
| `/api/answer` | POST | Tavily search + Groq synthesis + citations |
| `/api/search` | POST | Tavily raw web results (no AI synthesis) |
| `/api/images` | POST | Pexels image search |

---

## Origin Story

Kairos was born when Perplexity shifted file upload and document context features behind a higher paywall in May 2026, mid-workflow. Rather than pay more or accept the loss, the decision was made to build the exit ramp. Kairos is the result — a cleaner tool built for people who got stranded by tier games.

> *"Thank you for the inspiration. And no — users should not have to rent back the habits they already built."*

---

## Open TODOs

- [ ] File upload — PDF, docs, plain text for document-grounded answers
- [ ] Image upload — visual Q&A
- [ ] Session memory / persistent threads
- [ ] Shareable answer pages or exportable notes
- [ ] Custom domain — kairos.manitec.pw or standalone
- [ ] News tab on /search — Tavily `topic: "news"`, zero new API key needed
- [ ] ONE/ECKO integration path (phase 2)
