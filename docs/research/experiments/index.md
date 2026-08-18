# Experiments

This directory contains reproducible decision records for ONE and Manitec research work. Create one file per experiment from [_template.md](_template.md).

## Workflow

1. Copy `_template.md` to a dated, descriptive filename such as `2026-08-hermes-learning-loop.md`.
2. Define the decision, hypothesis, metrics, safety boundary, and success criteria before running the test.
3. Record exact configuration, inputs, versions, raw artifacts, and deviations while testing.
4. Record failures and negative results; they are evidence, not noise.
5. End with an explicit decision: adopt, continue probing, defer, or reject.

## Naming

Use `YYYY-MM-short-name.md`. Keep source data, logs, traces, screenshots, and generated artifacts outside the dashboard when needed, then link them from the experiment record.

## Quality Bar

An experiment is decision-ready only when another person can understand the question, reproduce the material configuration and method, inspect the evidence, and see why the recorded decision follows from the results.
