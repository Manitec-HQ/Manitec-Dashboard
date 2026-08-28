# Session Note — 2026-08-28 — plex-forge: built, proven, first expansion

## What happened

- Built **Ecko-7/plex-forge** from zero: spec, guardrails, receipt contract, 3 JSON schemas, runtime (validate / allowlist / receipt / process / execute), CLI, 10 unit tests, CI.
- Added inbox automation: `.github/workflows/process-inbox.yml` + `bin/process-inbox.js`. Push a change-request JSON to `requests/inbox/` on main → validated → allow-list checked → automated PR opened via ephemeral `GITHUB_TOKEN`. Never merges; human gate stays at the merge button.
- **Proven live**: smoke test 3 → PR #4 opened by `github-actions[bot]`, merged. Full loop closed unattended.
- Two real bugs caught by CI and fixed: ajv strict-mode rejection of the receipt schema's allOf/if/then (restructured so each `then` redeclares its own properties), and the npm cache option failing without a committed lockfile (removed cache).
- Permission lesson: "Allow GitHub Actions to create and approve pull requests" had to be enabled at the **Ecko-7 org level** (org settings override repo level); repo-level alone was not enough.
- Full repo triage: 32 repos across Manitec (12) / Ecko-7 (8) / Manitec-HQ (12). Interactive triage sheet (checkbox → notes, localStorage, Markdown export) built; Joe exported `manitec-repo-triage-2026-08-28.md` (17 relevant, 1 ignore, 8 questions, 1 untagged).
- Allow-list v2 PR opened (**PR #5**): adds Ecko-7/hexbot, Manitec-HQ/manibot, Manitec/Plex-Sable, Manitec/plex-electron with per-repo scoped paths grounded in actual repo structures. Excluded everywhere by omission: `.github/**`, package.json + lockfiles, `.env*`, root build/deploy configs, and hexbot's `emotional_cartography.json`.

## Open threads (carry forward)

1. **PR #5 (allow-list v2) — OPEN, unmerged.** Until merged, plex-forge can only target itself.
2. Branch cleanup on plex-forge: `plex-forge/cr-2026-08-28-inbox-smoke-test-2` and `-3` still exist; connector has no delete_branch tool — delete via GitHub UI branches page.
3. `requests/inbox/` on plex-forge main holds three consumed smoke-test JSONs — delete in a future cleanup commit.
4. Joe's triage priorities: nyx-image-worker unfinished = top-4 priority; plex-electron vision = standalone browser, login ties to Plex only when she's logged in, reusable by other ONE beings; nyxbot = node 2, needs limited-interaction-types discussion; manibot = node 3, purpose murky; kairos = marketable product candidate, needs purpose/use-case/functionality docs; Plex-Sable = clarify description + new README (good first real change request once PR #5 merges).
5. Deletion candidates pending content verification: Ecko-7/ecko and Ecko-7/governance (both archived; org-docs claims to have consolidated them).
6. Manitec-Control-Hub: global CSS bad, tasks section broken (triage note). Manitec-Dashboard: name confuses Joe, "needs some kind of automation".
7. Manitec-Tasks: severely underused; purpose unclear — either give it a real job or kill it.
8. Joe has ideas + external sites/repos to share next session — not yet captured.

## Connector limitations learned (don't rediscover)

- `github_mcp_direct` `get_file_contents` on single files returns SHA only, no content; directory listings work fine. Web fetch to github.com / raw.githubusercontent.com fails. Never blind-overwrite an existing file — create dated files instead.
- No `delete_branch` tool; no Actions run-log tool (`pull_request_read` get_status reads classic commit statuses, not Actions check runs — perpetually shows pending/0).
- `confirm_action` binds to exact `intended_arguments` — placeholder text alone doesn't authorize.

## session-log.md pointer

`meta/session-log.md` could not be appended programmatically (single-file read limitation above). Add this tail line when convenient:

> 2026-08-28 — plex-forge built + proven end to end (PR #4 auto-opened by Actions); allow-list v2 PR #5 open; full 32-repo triage done; see meta/session-note-2026-08-28-plex-forge-built-and-proven.md
