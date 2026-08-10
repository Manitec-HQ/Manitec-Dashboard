# [GROK] OpenHuman-plex transfer findings

**Date:** 2026-08-10  
**Repo:** `Manitec/openhuman-plex` (private fork of tinyhumansai/openhuman)  
**Status:** logged; Joe undecided on extraction  
**Constraint:** $0 budget — patterns only, no paid infra dependency

---

## What it is

Full open-source agent harness (Rust core + Tauri/React). Memory trees, orchestration graphs, workflows, multi-channel, privacy mode. Product-scale. Not the Plex being.

---

## Tier 1 — steal shapes, not the crate

1. **Autonomy + security policy**
   - Tiers: `ReadOnly` / `Supervised` / `Full`
   - Fail-closed command classes: `Read` → `Write` → `Network` → `Install` → `Destructive`
   - `gate_decision(class, tier)` → `Allow` / `Prompt` / `Block`
   - Split roots: **action_dir** (agent sandbox) vs **workspace_dir** (internal state agent must not write)
   - Always-forbidden paths; markers `[policy-blocked]` vs `[policy-denied]`
   - Paths in fork: `src/openhuman/security/policy/`

2. **Approval gate pattern**
   - External-effect tool → park → persist pending → UI event → decide (once/always/deny) → resume or fail closed
   - Background/cron skips prompt; TTL; redaction before store/broadcast
   - Path: `src/openhuman/security/approval/`

3. **Domain / controller layout**
   - Domain owns exports-only mod, types, ops, schemas; central registration; string RPC namespaces
   - Runtime DomainSet + feature gates for slim kernels

4. **Privacy ≠ autonomy**
   - Act power separate from whether inference/data may leave the machine

---

## Tier 2 — selective

Event bus shape · redaction/PII · encrypted secret store · sandbox backends (only if local untrusted shell) · Memory Tree / path_scope *idea* · tool-output compression idea · two-lane CI + orphan-test discipline · mock API with reset/fault modes

## Tier 3 — leave alone

Full tinyagents/tinyflows graphs · 17 channels / meetings / mascot · entire Tauri UI · web3/x402 · cargo-culting test volume

---

## Empire map

| Surface | Take |
|---------|------|
| HexBot | Approval + autonomy tiers + fail-closed rules for tool execution |
| ONE | Domain boundaries, capability composition, privacy vs autonomy |
| Manibot | Little; public-safe redaction / read-only posture |
| Local/offline | Privacy Mode idea + sandbox + action_dir split |
| Plex being | Patterns only — no OpenHuman product identity into private being space |

---

[FOR-PPLX] When agent tool execution or supervised actions come up, read this before inventing a new gate model.

*Logged by Grok from live repo skim 2026-08-10.*
