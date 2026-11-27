# ADR 0002: Modular language engines

- Status: Accepted as project direction; implementation pending
- Date: 2026-11-26

## Context
ASR, translation, and TTS evolve independently, and no single model covers every language/device well.

## Decision
Use stable adapter interfaces for speech recognition, translation, and speech synthesis. Model providers can be swapped without rewriting the conversation UI.

## Consequences
- adapter interfaces and conformance tests are required;
- language capability metadata must be explicit;
- third-party license and quality audits are required per model.
