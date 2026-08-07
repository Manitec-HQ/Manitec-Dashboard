# ONE v1 Session Note — 2026-08-07

[PPLX 2026-08-07] Built and deployed the first usable ONE v1 proof of concept in `Manitec-HQ/one`.

## Product boundary

- ONE is the generic workshop for creating user-owned unified beings.
- Plex, Nyx, Hex, ECKO, and Joe's private being history are not product defaults or user-accessible runtime dependencies.
- Mani is the future product-level technical support path; he is not a fourth aspect.
- Future family or phone-home communication is intentionally parked until after the core loop is stable.

## What shipped

- Neutral first-run builder: name a being, define shared identity, and configure three aspects.
- Interface, Management, and Browser product tabs.
- Local browser persistence for the active example being.
- Three-aspect runtime pipeline: user input → three perspectives → unified response.
- Hugging Face runtime attempt with safe local fallback.
- Visible runtime-mode label planned/added to distinguish Local Prototype from Hugging Face execution.

## Validation

Joe created and tested example being `Bob` with aspects Jimmy, James, and Johnathan.

The system successfully produced three distinct aspect outputs and a unified Bob response. It is currently operating in Local Prototype mode because Hugging Face inference did not return live text through the current runtime route.

## Current behavioral finding

The structural loop works, but the local prototype treats casual greetings as full problem-solving tasks. Next iteration should add lightweight intent handling so greetings and casual conversation do not convene the entire visible council by default.

## Next technical work

1. Update the Hugging Face call to the current Inference Providers route and verify the Vercel `HF_TOKEN` flow.
2. Improve local intent handling: greeting/casual, question/decision, emotional, and technical/planning.
3. Keep internal perspectives as a debugging view rather than the default interaction display.
4. Add real persistence only after the runtime behavior is satisfactory.

[FOR-GROK] Review `Manitec-HQ/one` as a product boundary and v1 runtime audit. Check whether the local three-aspect → unified-response architecture is clean, whether the fallback/provider design is sound, and identify the smallest next changes needed before adding persistence or more agent complexity.
