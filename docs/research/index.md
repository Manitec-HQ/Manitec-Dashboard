# Research

Decision-oriented research for Manitec and ONE. This page tracks what is being evaluated, why it matters, what evidence is available, and the next experiment required before an adoption decision.

## Active Evaluation Map

| Architecture need | Candidate | Status | Next action |
| --- | --- | --- | --- |
| Persistent learning and skills | Hermes Agent | Probe | Run a real multi-day task and inspect created memories and skills. |
| Public-web research acquisition | Agent-Reach | Sandbox test | Test inside an isolated container with no production credentials. |
| Multi-provider model routing | OmniRoute | Benchmark | Compare routing, fallback, tracing, and data handling. |
| Agent evaluation methodology | Agent Arena | Reference | Extract representative task and scoring patterns. |
| Hosted and deployable model lane | NVIDIA Build / NIM | Benchmark | Compare tool use, latency, cost, and deployment burden. |
| Agentic coding experimentation | Kilo Code | Bounded | Use only with disposable/public code until data routing is controlled. |
| Free-tier discovery | free-for.dev | Discovery | Validate any candidate independently before use. |
| Echo LLM / genx.sh | Unresolved | Hold | Require a canonical source before evaluation. |

## Architecture Principles

1. Keep agent runtime, source context, durable memory, tool access, and model routing as separate layers with explicit contracts.
2. Assign public-web acquisition to constrained Scout-style agents with provenance and failure reporting instead of granting universal browser access.
3. Treat memory as inspectable artifacts: episodes, distilled facts, rules, skills, confidence, provenance, revision, and deletion.
4. Put provider selection, budgets, fallback, redaction, and tracing behind a single gateway boundary.
5. Expand autonomy only alongside versioned evaluation tasks, expected artifacts, quality scoring, task success, cost, latency, and failure taxonomy.
6. Treat free inference and account-aggregation products as untrusted until retention, routing, credential handling, and sustainability are verified.

## Research Entries

### Hermes Agent

**Why it matters:** Hermes is a reference for a persistent agent that converts work experience into reusable skills and maintained memory.

**What to study:** Skill format; confidence and provenance; promotion, correction, and deletion rules; reflection cadence; subagent isolation; and artifact-inspection UX.

**Decision:** Probe the learning loop rather than adopting the runtime wholesale.

**Sources:**

- https://github.com/nousresearch/hermes-agent
- https://hermes-agent.nousresearch.com/docs/
- https://hermes-agent.org/

### Agent-Reach

**Why it matters:** It offers a CLI/tool layer for agent research across public web and social sources, including GitHub, Reddit, YouTube, RSS, X, LinkedIn, and URLs.

**Risks to validate:** Scraping or platform-policy exposure, proxy/cookie handling, rate limits, source instability, retention, and source provenance.

**Decision:** Evaluate as a sandboxed research Scout capability, not a universal tool.

**Sources:**

- https://github.com/Panniantong/Agent-Reach
- https://github.com/Panniantong/Agent-Reach/blob/main/llms.txt

### OmniRoute

**Why it matters:** An open-source, OpenAI-compatible multi-provider gateway candidate with routing and fallback capabilities.

**Decision:** Benchmark locally behind ONE's internal provider interface. Do not expose real credentials or sensitive prompts until the routing and data model are reviewed.

**Sources:**

- https://omniroute.online/
- https://www.hostinger.com/in/applications/omniroute

### Agent Arena

**Why it matters:** A useful reference for evaluating agent performance on real work rather than relying on chat impressions.

**Decision:** Use its methodology to build a small ONE task suite with stored trajectories, output artifacts, manual scoring, latency, cost, and failure classes.

**Sources:**

- https://arena.ai/blog/agent-arena-methodology
- https://arena.ai/agent

### NVIDIA Build / NIM

**Why it matters:** A provider and deployment lane for hosted AI models and possible NVIDIA-accelerated inference.

**Decision:** Benchmark model quality, tool calling, latency, rate limits, privacy posture, cost, and GPU operating burden against the current provider lane.

**Sources:**

- https://build.nvidia.com/models
- https://docs.api.nvidia.com/nim/reference/llm-apis
- https://developer.nvidia.com/nim

### Kilo Code

**Why it matters:** A useful coding-agent surface for low-cost experiments.

**Boundary:** Free-model routing may send prompts to providers that retain inputs or use them for model improvement. Use only public/disposable code and non-sensitive prompts until independently controlled.

**Sources:**

- https://kilo.ai/docs/getting-started/using-kilo-for-free
- https://kilo.ai/docs/getting-started

## Experiment Queue

- [ ] Run Hermes on one recurring multi-day project; inspect every generated memory and skill artifact.
- [ ] Test Agent-Reach in a container without production credentials across GitHub, one social source, and one media source.
- [ ] Benchmark OmniRoute with several providers and a forced failure; record compatibility, fallback, traces, cost, latency, and data handling.
- [ ] Define five to ten ONE evaluation tasks with fixed fixtures, success criteria, required artifacts, and human scores.
- [ ] Compare NVIDIA NIM with the current provider lane for code edits, tool use, latency, rate limits, and operating cost.
- [ ] Identify canonical sources for Echo LLM and genx.sh before further evaluation.

## Evidence Policy

- Record canonical product, documentation, repository, or primary-source links.
- Mark each entry with a decision status and next required experiment.
- Do not promote a tool based solely on marketing claims, free access, or a benchmark leaderboard.
- Capture data handling, credential scope, source provenance, operational cost, and failure behavior before integration.
