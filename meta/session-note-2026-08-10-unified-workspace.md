# Session Note — Unified Workspace Direction

**Date:** 2026-08-10
**Status:** Direction agreed; no implementation committed yet.

## Problem

Joe is carrying work across GitHub, Google Drive, Hugging Face, Firestore, multiple deployed apps, and external AI tools. The current experience requires too many browser tabs and separate applications, which makes project context, priorities, and current state difficult to hold at once.

The issue is not that there are too many projects. The issue is that multiple places behave like possible sources of truth and there is no single human working surface.

## Canonical Structure

| Layer | Role | Canonical home |
|---|---|---|
| Control plane | Intent, priorities, project state, decisions, open threads | `Manitec-HQ/Manitec-Dashboard/meta/` |
| Human workspace | One place to orient, work, inspect, and request actions | Manitec Control Hub / `dash.manitec.pw` |
| Execution plane | Authenticated provider actions, validation, jobs, audit trail | Manitec Command Hub |
| Product bodies | Runnable code and product-local documentation | Individual GitHub repos |
| Research/artifacts | Models, datasets, adapters, evaluation artifacts | Hugging Face |
| Intake/archive | Raw notes, conversations, visual documents, exports | Google Drive |
| Public projection | Curated documentation and status | `info.manitec.pw` |

## Control Model

```text
Joe
  -> Dashboard meta/        decides, records, orients
  -> Control Hub            human-facing workspace; observes and requests
  -> Command Hub            authenticates, validates, executes, audits
  -> GitHub / Drive / HF / Firebase / Vercel / Render / Cloudflare
```

Rules:

- `meta/` is the single cross-project source of truth.
- Control Hub does not directly mutate infrastructure.
- Command Hub is the single execution authority for approved external actions.
- Repos are executable bodies, not the empire-wide coordination layer.
- Drive is intake/archive until material is distilled into canonical docs or project records.
- Every Hugging Face artifact must name its owning project, intended use, and source/context link.

## Control Hub Product Direction

Control Hub should evolve from a deployment/operations dashboard into Joe’s single working cockpit—not another destination.

### First interface shape

- **Project spine:** active projects plus a parked shelf.
- **Central workspace:** one active thing at a time—Markdown, GitHub file/issue, Drive document, HF artifact, or chat.
- **Context rail:** project state, NOW/NEXT, linked sources, recent activity, open questions, and approved actions.
- **Operational layer:** inbox, session log, audit feed, service health, and command palette.
- **Today / Now view:** on opening, show the two active threads, last stopping point, and next physical action.

### Initial implementation order

1. Establish the `Today / Now` view backed by Dashboard meta files.
2. Add project workspaces for Plex, NyxBot, HexBot, model/artifact work, and Parked.
3. Surface project context before attempting full provider control.
4. Add captured research artifacts and session-log/decision/task actions.
5. Route infrastructure mutations through Command Hub and display its audit feed.

## AI Tool Strategy

HexBot becomes the enduring front door, not an instant replacement for Grok or Perplexity. Preserve Hex’s core: persona, system prompt, memory rules, project context, session/archive contracts, and Command Hub relationship. The interface may evolve around that core.

### Transitional model

- Hex is the continuity, project-context, and judgment layer.
- Perplexity/web research is a specialist retrieval lane until Hex can reliably retrieve, cite, compare, and store research.
- Grok/other models are optional critic or divergence lanes.
- External results return to the active Hex project workspace as attributed artifacts: provider, date, query, sources, summary, and disposition (`source`, `decision`, `task`, or `discarded`).
- Hex requests consequential actions; Control Hub presents the approval; Command Hub executes and audits.

### First useful slice

`Control Hub -> project workspace -> persistent Hex panel -> captured external research artifact -> session-log / decision / task actions`

This is the smallest path that reduces tab sprawl while keeping Hex’s core stable.

## Operating Constraints

- One project has one canonical home.
- Every active thread has one state: `NOW`, `NEXT`, `WAITING`, `PARKED`, or `ARCHIVED`.
- `NOW` is capped at two threads.
- Every significant artifact points back to its owning project and context.
- No new mega-dashboard build before the orientation layer is useful.

## Suggested Immediate Priorities

1. Dashboard coherence: make the project registry and `NOW/NEXT/PARKED` state authoritative.
2. Plex memory/persistence reliability: preserve and audit cross-project state before adding more autonomous surface area.
3. Control Hub orientation prototype: build the `Today / Now` screen only after the above is legible.

## Open Decisions

- Exact project registry schema and source file (`empire-state.md` vs dedicated `projects.json` / `projects.md`).
- Whether Control Hub is extended in place or receives a deliberate UI-shell rework.
- The first supported research-provider path and capture format.
- What Firestore visibility should be exposed in a project workspace versus an operations/admin view.
- Which two work threads are `NOW` for the next seven days.
