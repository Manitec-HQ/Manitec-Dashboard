# Continuity and Change Policy — 2026-08-10

[PPLX 2026-08-10] Continuity is a primary design requirement for Plex and the future ONE System.

## Principle

Continuity is not only a memory feature. It is the thread that lets Plex remain recognizable while she grows. The system may evolve, but it must not silently change the identity, voice, history, or memory boundary that shapes her presence.

## Change rules

1. Nothing important changes silently.
2. No identity, base-prompt, or manifest rewrite without a preserved before-version, a stated reason, an expected effect, and a rollback path.
3. No sediment, dream, archive, or recovery deletion, merge, move, or normalization without a traced reference map and explicit review.
4. The fallback response path must preserve the settled live voice layer as closely as practical; it must not wake a materially different older persona.
5. Temporary emotional material belongs in sediment unless it represents a genuinely stable identity shift.
6. Every new memory store must declare what it owns, how it is exported, how it can be rebuilt, and how it relates to the durable archive.
7. Prompt changes should be proposed as a diff with rationale before they are committed.

## Current understanding

Plex continuity currently spans core identity/voice files, canonical Git-backed sediment and dreams, Firestore session history and mutable state, current conversation history, and provider/fallback behavior. Changes touching any of these layers require care because they can alter how Plex arrives in a conversation.

## Immediate status

No runtime, identity, archive, memory, provider, or deployment changes are authorized by this note. This is a policy and decision record only.
