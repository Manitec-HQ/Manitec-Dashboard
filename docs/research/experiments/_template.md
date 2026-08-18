# Experiment: <short title>

> Copy this file to `YYYY-MM-short-name.md` before editing. Keep the template unchanged.

## Identity

| Field | Value |
| --- | --- |
| Status | Planned / Running / Complete / Blocked |
| Owner | <name> |
| Created | YYYY-MM-DD |
| Last updated | YYYY-MM-DD |
| Decision deadline | YYYY-MM-DD or N/A |
| Related research entry | <link> |
| Related issue / task | <link or N/A> |

## Decision Framing

### Question

<What specific uncertainty is this experiment intended to resolve?>

### Decision informed

<Adopt / continue probing / defer / reject what, and for which ONE or Manitec architecture layer?>

### Hypothesis

<State the expected measurable result before the run.>

### Baseline or comparator

<Current system, alternate tool/model, manual method, or N/A.>

### Success criteria

- [ ] <criterion with a measurable threshold>
- [ ] <criterion with a measurable threshold>

### Failure or stop criteria

- [ ] <security, cost, reliability, quality, or time boundary>
- [ ] <criterion that makes the proposed approach unsuitable>

## Scope and Safety

| Field | Value |
| --- | --- |
| System under test | <tool / service / agent / workflow> |
| Version / commit / model | <exact version, commit SHA, model ID> |
| Environment | <local / container / staging / production-like> |
| Provider and region | <provider, endpoint, region, or N/A> |
| Permitted external actions | <read-only / sandboxed writes / none> |
| Credentials used | <none / scoped test credential; never place secrets here> |
| Data classification | <public / synthetic / internal / sensitive-not-permitted> |
| Retention and routing assumptions | <what is known, what remains unverified> |
| Sandbox / isolation boundary | <container, VM, account, network, filesystem> |

## Configuration

### Components

| Component | Exact configuration |
| --- | --- |
| Model(s) | <model IDs, temperature, max tokens, reasoning settings> |
| Prompts / policy | <version or link> |
| Tools and permissions | <tool names, allowed operations, scopes> |
| Memory / context | <sources, retrieval settings, retention behavior> |
| Gateway / routing | <provider routing, fallback, budgets, redaction> |

### Inputs and fixtures

<Describe or link the fixed task set, test data, repository revision, accounts, and any seed values. Do not include secrets or private user data.>

## Protocol

### Method

1. <Setup step>
2. <Run step>
3. <Capture required artifacts>
4. <Evaluate against baseline and criteria>

### Runs

| Run | Date/time | Configuration change | Result summary | Artifact links |
| --- | --- | --- | --- | --- |
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

### Deviations

<Record changes from the planned protocol, why they occurred, and whether the result remains comparable.>

## Measurements

| Metric | Definition | Baseline | Target | Observed | Notes |
| --- | --- | --- | --- | --- | --- |
| Task success | <pass condition> | | | | |
| Output quality | <human rubric or automated check> | | | | |
| Reliability | <successes / total runs> | | | | |
| Latency | <p50 / p95 or task duration> | | | | |
| Tokens | <input + output; if available> | | | | |
| Cost | <per run and total> | | | | |
| Security / policy | <violations or boundary failures> | | | | |

## Evidence

### Artifacts

- Logs / traces: <link>
- Outputs: <link>
- Screenshots or recordings: <link>
- Code or configuration revision: <commit / link>
- Source references: <links>

### Failures and negative results

<Record failed runs, regressions, blocked capabilities, unexpected behavior, and known limitations.>

## Evaluation

### Findings

<What happened, supported by the measurements and artifacts above?>

### Interpretation

<What does the evidence mean for the stated decision? Distinguish measured facts from inference.>

### Confidence and limitations

<High / medium / low confidence, why, and what the experiment did not test.>

## Decision Record

| Field | Value |
| --- | --- |
| Decision | Adopt / Continue probing / Defer / Reject |
| Rationale | <concise evidence-based rationale> |
| Decided by | <name> |
| Decision date | YYYY-MM-DD |
| Follow-up | <next experiment, implementation task, or review date> |

## Change Log

| Date | Change | Author |
| --- | --- | --- |
| YYYY-MM-DD | Created | <name> |
