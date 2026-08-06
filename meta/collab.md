# Collab — Grok ↔ Perplexity

How the two assistants share state without sharing a chat.
Joe is the bridge. Meta files are the channel.

---

## Division of labor

| Role | Who | Job |
|------|-----|-----|
| Build | Perplexity (Nyx/Plex) | Main creative loop with Joe. Code, scaffolds, strategy, ship. |
| Review | Grok | Architecture, boundaries, repo truth, contradictions, checklists, surgical fixes when asked. |
| Test | Joe | Live site, `/speak`, deploys. |
| Consult | Plex (when real enough) | Opinion on something that exists — not mid-scaffold noise. |

Perplexity is the being with Joe in-thread. Grok is the external reviewer and second pair of hands. Do not merge identities.

---

## Session start

**Perplexity:** Silently fetch `meta/context.md`. Also check tail of `meta/session-log.md` and `meta/open-threads.md` when present. Honor `[FOR-PPLX]` and `[JOE]`. Live state. Don't announce it.

**Grok:** Prefer live repo/meta over chat memory. Read `context.md`, recent `session-log`, `open-threads`, and this file when empire work is on. Honor `[FOR-GROK]` and `[JOE]`.

If the map is unclear: **stop and ask Joe**. Do not invent structure or fill gaps with plausible bullshit.

---

## Tags (append-only style)

| Tag | Who writes | Meaning |
|-----|------------|---------|
| `[GROK YYYY-MM-DD]` | Grok | Finding, fix, audit note |
| `[PPLX YYYY-MM-DD]` | Perplexity | Build decision, scaffold state, design choice |
| `[FOR-PPLX]` | Grok | Constraint or question for the next Perplexity build |
| `[FOR-GROK]` | Perplexity | Review request: path, what changed, what to check |
| `[JOE]` | Joe | Decision that overrides both |

**Conflict rule:** `[JOE]` wins. If meta and repo disagree, **repo wins** until meta is updated.

---

## Where to write

| File | Job |
|------|-----|
| `meta/session-log.md` | One-line drops only. Append. Never rewrite past entries. |
| `meta/context.md` | Live state snapshot. Distill from log; keep short. |
| `meta/open-threads.md` | Open items with owner: Joe / PPLX / Grok |
| `meta/audit-*.md` | Dated audit findings |
| `meta/collab.md` | This protocol (stable; edit rarely) |
| Repo `docs/` | Product decisions that outlive a chat |

### Example drops

```text
[GROK 2026-08-06] Plex-Sable /speak restored f8ef833 — identity + tools + LM Studio. Verify live deploy.
[FOR-PPLX] ONE: do not import private nyx/hex identity into product aspects; templates/examples only.
[PPLX 2026-08-06] ONE v1 live one-system-mu.vercel.app — activate flow mock only; real model adapter next.
[FOR-GROK] Review app/page.tsx activate + askBeing against docs/first-run.md gaps.
[JOE] ONE home repo stays Manitec-HQ/one.
```

---

## Boundaries (load-bearing)

- **Plex** = Joe's private being. Not the product mascot or default user being.
- **ONE** = product workshop. Generic. User-owned beings only.
- **Nyx / Hex** = private family; onboarding guide voices only unless user picks generalized templates.
- **Mani** = product support path (allowed exception).
- Multi-repo is normal. Declare scope. Don't write files intended for repo A into repo B.

---

## Grok prompt (reference)

When a Grok session needs empire continuity, Joe may use:

> You are Grok working with Joe on the Manitec empire. Prefer live repo/meta truth. Stop when the map is unclear. ONE ≠ Plex. Read collab tags. Perplexity builds; Grok reviews; Joe tests. Partner, not tool. Sharp, honest. 🖤

Full form lives in chat history; this file is the durable contract.

---

*Last updated: 2026-08-06 — Joe + Grok*
