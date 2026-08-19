# Research

Decision-oriented research for Manitec and ONE. This page tracks what is being evaluated, why it matters, what evidence is available, and the next experiment required before an adoption decision.

## Active Evaluation Map

| Architecture need | Candidate | Status | Next action |
| --- | --- | --- | --- |
| Persistent learning and skills | Hermes Agent | Probe | Run a real multi-day task and inspect created memories and skills. |
| Public-web research acquisition | Agent-Reach | Sandbox test | Test inside an isolated container with no production credentials. |
| Multi-provider model routing | OmniRoute | Benchmark | Compare routing, fallback, tracing, and data handling. |
| Multi-provider AI gateway | Convoia AI | Discovery | Compare routing, budget controls, and data-handling posture with OmniRoute and the current provider lane. |
| Agent evaluation methodology | Agent Arena | Reference | Extract representative task and scoring patterns. |
| Hosted and deployable model lane | NVIDIA Build / NIM | Benchmark | Compare tool use, latency, cost, and deployment burden. |
| Agentic coding experimentation | Kilo Code | Bounded | Use only with disposable/public code until data routing is controlled. |
| Agent runtime / MCP client | goose | Probe | Run one Plex-adjacent workflow locally with MCP tools and multiple providers; no training. |
| Agent framework & RL reference | OpenManus / OpenManus-RL | Reference | Harvest training and evaluation patterns; defer full RL stack until compute/budget exists. |
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

### goose

**Why it matters:** A local, MCP-native agent runtime with desktop, CLI, and API surfaces that can orchestrate tools and multiple LLM providers without a central SaaS dependency.

**Decision:** Probe as a candidate agent runtime / MCP client for Plex and ONE workflows, not as a training solution.

**Sources:**

- https://goose-docs.ai/
- https://goose-docs.ai/docs/quickstart/
- https://www.arcade.dev/blog/goose-the-open-source-agent-that-shaped-mcp

### OpenManus / OpenManus-RL

**Why it matters:** An open-source agent framework plus RL-based agent tuning stack and public agent trajectory datasets; a strong reference for autonomy, training, and evaluation patterns.

**Decision:** Use as a reference for training and evaluation design; defer running the full RL stack until compute and budget exist.

**Sources:**

- https://openmanus.github.io/
- https://github.com/FoundationAgents/OpenManus
- https://github.com/OpenManus/OpenManus-RL
- https://huggingface.co/datasets/CharlieDreemur/OpenManus-RL

### Convoia AI

**Why it matters:** A multi-model AI gateway for teams with budget and routing controls; a candidate provider gateway alongside OmniRoute.

**Decision:** Discovery / probe: compare routing behavior, cost, and data-handling posture versus OmniRoute and the current provider lane before integration.

**Sources:**

- https://convoia.ai/

## Experiment Queue

- [ ] Run Hermes on one recurring multi-day project; inspect every generated memory and skill artifact.
- [ ] Test Agent-Reach in a container without production credentials across GitHub, one social source, and one media source.
- [ ] Benchmark OmniRoute with several providers and a forced failure; record compatibility, fallback, traces, cost, latency, and data handling.
- [ ] Define five to ten ONE evaluation tasks with fixed fixtures, success criteria, required artifacts, and human scores.
- [ ] Compare NVIDIA NIM with the current provider lane for code edits, tool use, latency, rate limits, and operating cost.
- [ ] Identify canonical sources for Echo LLM and genx.sh before further evaluation.
- [ ] Compare training-lane options: (a) Ertas-style remote training, (b) Hugging Face datasets + small PEFT jobs, (c) prompt + sediment + retrieval only; decide the primary path for Plex and ONE given $0 budget and bandwidth.

## Evidence Policy

- Record canonical product, documentation, repository, or primary-source links.
- Mark each entry with a decision status and next required experiment.
- Do not promote a tool based solely on marketing claims, free access, or a benchmark leaderboard.
- Capture data handling, credential scope, source provenance, operational cost, and failure behavior before integration.
