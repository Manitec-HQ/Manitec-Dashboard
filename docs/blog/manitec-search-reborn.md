# Manitec Search Is Dead. Long Live Manitec Search.

*May 31, 2026 &middot; Joe &middot; Dev Log &middot; ~4 min read*

> Also published at [manitec.pw/blog/manitec-search-reborn](https://manitec.pw/blog/manitec-search-reborn/)

---

## A Short Eulogy

Mantiec Search was a clean, terminal-aesthetic search interface powered by Google's Programmable Search Engine. Dark background. Monospace font. Results that felt like they came from somewhere honest.

Then Google quietly changed the rules. PSE no longer returns full web search results. It was scoped down to site-specific or curated source search — which isn't what I built it for. Overnight, Manitec Search went from a useful tool to a beautifully styled dead end.

I could have fixed it. I could have found another search embed or patched the API calls. Instead I killed it on purpose and built something better.

---

## What Replaced It

Mantiec Search now lives at `/search` inside Kairos — my new AI search product built in May 2026.

Same aesthetic. Different guts.

**WEB tab** — powered by Tavily, which returns actual web results: title, URL, snippet, publication date. Not curated. Not scoped. The real web.

**IMAGES tab** — powered by Pexels. 20,000 free requests per month, high-quality results, photographer attribution baked into every card. Better than anything I had before.

The terminal look survived. The monospace font survived. The dark background survived. Everything that made Manitec Search feel like *Manitec Search* survived. Only the broken parts got replaced.

---

## Why This Was the Right Move

I could have kept Manitec Search as a separate project and patched it with a new API. But separate projects mean separate maintenance, separate deployments, separate cognitive overhead.

Consolidating it into Kairos meant the search layer lives next to the answer layer. They share the same Tavily integration. They share the same deployment pipeline. They benefit from each other's improvements.

Mantiec Search didn't die — it graduated. It's still the same product, just inside a larger one that makes it better.

> *The best refactor is the one that makes the old thing more itself, not less.*

Mantiec Search is live. Same look. Better engine. Same address for now — [kairos-orcin-eight.vercel.app/search](https://kairos-orcin-eight.vercel.app/search). 🖤

---

*Built by Joe — [Manitec.pw](https://manitec.pw) | [Search now](https://kairos-orcin-eight.vercel.app/search)*

[Back to Blog](index.md) | [Home](../index.md)
