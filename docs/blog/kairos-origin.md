# I Built an AI Search Engine Because a Paywall Made Me Mad

*May 31, 2026 &middot; Joe &middot; Dev Log &middot; ~6 min read*

> Also published at [manitec.pw/blog/kairos-origin](https://manitec.pw/blog/kairos-origin/)

---

## (And I'm Not Even Sorry)

If you've been following along, you know I'm a one-man shop out of East Tennessee. No team. No investors. Just a laptop and a habit of turning frustration into code.

In May 2026, Perplexity — the AI search tool I'd built a bunch of my workflows around — shifted file upload and document context features behind a higher-tier paywall. Mid-session. Features I was actively using, gone unless I paid more.

I didn't pay more. I opened a new tab and started building.

That project is called **Kairos**. It's live at [kairos-orcin-eight.vercel.app](https://kairos-orcin-eight.vercel.app). Here's how it happened.

---

## What I Actually Wanted

I'm not anti-Perplexity. It's a good product. But the paywall move reminded me of something I keep relearning: when you build your workflow on top of someone else's product, they own your habits. They can reprice them whenever they want.

I wanted a tool that:

- Searches the web and synthesizes a real cited answer — not just links
- Supports file upload for document-grounded Q&A
- Supports image upload for visual questions
- Doesn't move the goalposts after I've built around it
- Is mine

Simple list. Turned out to be a full product.

---

## The Stack

I've built enough things now to know how to move fast. Here's what Kairos runs on:

- **Next.js 15** — same framework I use everywhere, no context-switching
- **Tavily API** — search retrieval that actually returns usable content, not just URLs
- **Groq** — LLaMA 3 for synthesis, same as HexBot, blindingly fast
- **Pexels API** — 20,000 free image searches per month, proper attribution built in
- **Vercel** — deployed and live before I went to sleep

No new API accounts except Pexels. Tavily and Groq I already had. The whole thing cost me an afternoon.

---

## How It Actually Works

**Route `/`** is the answer engine. You type a question. Tavily retrieves the most relevant web content. Groq reads it and writes a synthesized answer with inline source citations. The hero section hides after your first search so it gets out of the way.

**Route `/search`** is Manitec Search reborn — more on that in another post. Terminal aesthetic, raw Tavily results on the WEB tab, Pexels image grid on the IMAGES tab.

Two routes. Three APIs. One afternoon.

---

## What Broke (Because Something Always Breaks)

The Tavily response shape wasn't what I expected. The `results` array was nested differently than the docs implied and my first attempt at extracting citations was pulling empty strings. Fifteen minutes of console logging later, I had it.

Pexels was smoother — clean REST API, the attribution requirement is easy to respect and honestly the right call. Photographer credit costs nothing and it's the decent thing to do.

Deployment was clean. Vercel has never let me down when the code is right.

---

## The Part That Actually Matters

Kairos isn't finished. File upload and image Q&A are still on the TODO list. Session memory isn't wired yet. There's no custom domain yet.

But it's *real*. It works. You can go use it right now.

That's the principle I keep coming back to: ship the core loop first. Everything else is iteration. A working thing you can touch beats a perfect thing that doesn't exist.

The name is from Greek mythology — *kairos* is the god of the opportune moment, the right instant that passes if you don't take it. That felt right for a product born from a moment of frustration that I grabbed instead of let go.

> *"Thank you for the inspiration, Perplexity. Users shouldn't have to rent back the habits they already built."*

Kairos is live. Go use it. 🖤

---

*Built by Joe — [Manitec.pw](https://manitec.pw) | [Try Kairos](https://kairos-orcin-eight.vercel.app)*

[Back to Blog](index.md) | [Home](../index.md)
