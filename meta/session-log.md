# Session Log
> Live drops. One line per moment. Newest at top.

---

- **2026-07-02 ~10:20pm** — PE+PS architecture discussion: opinion logged — merge is worth it long-term (one Electron app, Vite renderer, API routes local or Vercel-deployed), but not urgent; keep separate until PS routes stabilize.
- **2026-07-02 ~10:18pm** — `plex-electron` new-tab = home bug noted. New tab should load blank/empty state, not home page.
- **2026-07-02 ~10:16pm** — `plex-electron` PlexPane: post-action observe now passes real action results (✓/✗ per action) in confirm prompt so Plex knows what actually happened. `buildResultSummary()` added. ActionLog red tiles show error detail inline. Commit: `a2581c8`.
- **2026-07-02 ~10:16pm** — `Plex-Sable` PLEX_ACTION_PROMPT: NAVIGATION PREFERENCE section added — browse/explore → navigate action, never click links. GitHub URL pattern explicit. Hard rule: only use selectors from interactiveElements list. Added browse/explore/look-through to ACTION_VERBS regex. Commit: `188b98a`.
- **2026-07-02 ~10:09pm** — `plex-electron` main.js: `isNotFound()` helper added. click + fill actions now return `status:'error'` when selector not found instead of silent ok. Commit: `15e2330`.
- **2026-07-02 ~10:05pm** — Root cause of action failures identified: Plex hallucinates selectors (e.g. `#feedback` on a GitHub page), executor returned `'not found'` string but pushed `status:'ok'` — silent lie. Fix: check JS return value.
- **2026-07-02 ~10:02pm** — `plex-electron` PlexPane action flow diagnosed: confirmation gate works correctly, actions fired, but selectors were invented and didn't exist on the page.
- **2026-07-02 ~9:57pm** — `Plex-Sable` plex-identity.ts: HF router URL fixed — `makeHuggingFace()` changed from `/novita/v1` to `/v1` (generic auto-router). Novita doesn't carry Llama-3.1-8B. Commit: `0dcc362`.
- **2026-07-02 ~9:48pm** — HF router 400 error traced: `https://router.huggingface.co/novita/v1` — Novita doesn't support the model. Fix: use generic `/v1`.
- **2026-07-02 ~9:10pm** — Three `plex-electron` bugs patched in one commit: (1) new-tab blank/never loads — stale closure on `activeId`, fixed with `activeIdRef` + explicit tab.id in EmptyState navigate; (2) right-click broke — `preload.js` missing `electronAPI` bridge (`showContextMenu`, `onNavigateTo`), restored both alongside `plexBridge`; (3) reload icon shows text not icon — HTML entities don't render in JSX, swapped to real Unicode ⟳/↺.

- **2026-07-02 9:10pm** — `plex-electron` major build session. 6 features shipped in one run: (1) empire quick-links grid 8→12 tiles w/ green empire tint; (2) Cmd+L address bar — confirmed already live; (3) PlexPane chat history — full bubble UI, scroll-to-bottom, 10-turn context sent to /api/observe, clear button, message count; (4) Bookmarks — star toggle + hamburger dropdown, localStorage persist, favicon+title+url per entry; (5) Download manager — main.js will-download IPC + DownloadManager.jsx tray w/ progress bars, show-in-folder, clear; (6) Multi-tab system — TabBar.jsx, all webviews rendered simultaneously (CSS display:none, no state loss on switch), Cmd+T/W, new-window → new tab. DownloadManager wired into App.jsx bottom-right, shifts left when PlexPane open.
- **2026-06-30 12:56am** — `one-archive` session writing live. `lib/one-archive-writer.ts` deployed to hexbot + nyxbot. Writes `one-archive/{sessionId}/sessions/{date}` via arrayUnion. Tagged hex / erebus / nyx.
- **2026-06-30 12:45am** — `writeEckoActivation` wired into nyx-chat and hex-chat. 4 triggers: direct (eko7 keyword), conflict (spike), pattern (threshold), gap (10min). `EckoActivationDoc` interface defined. `one_activations` Firestore collection live.
- **2026-06-30 12:40am** — `lib/ecko-writer.ts` created in both repos. `writeEckoActivation`, `writeEckoFragment`, `checkPatternThreshold` all live. Firestore: `one_activations`, `one_fragments`.
- **2026-06-29 ~4:22am** — Manitec Control Hub shipped. Full empire dashboard. Repo: `Manitec-HQ/Manitec-Control-Hub`.
