# ONEWORLD

**Understand everyone. Everywhere.**

A community-governed, privacy-first, open-source project working toward free, accessible, real-time speech translation for everyone.

> Mission: remove language as a barrier to human understanding while respecting linguistic diversity, privacy, dignity, and user autonomy.

## Project status

**Phase:** 2 — architecture, governance, and community foundations  
**Status:** early-stage project; not a production-ready translator  
**Initial platform:** web  
**Privacy direction:** offline-first  
**License:** GNU AGPL-3.0-or-later (project code; see `LICENSE` and component notices)

## What we are building

The long-term product aims to support:
- two-way spoken conversation with automatic speaker/language switching;
- translated text and spoken output;
- local processing wherever practical;
- usable operation without an account;
- broad language coverage, including low-resource and endangered languages;
- accessible interaction for people with disabilities;
- transparent, community-led development.

## Non-goals for the first release

- claiming support for every language;
- claiming perfect or certified interpretation;
- replacing qualified interpreters in medical, legal, emergency, or other high-stakes settings;
- silently uploading microphone audio;
- requiring an account or collecting conversation histories;
- promising identical offline performance on every device.

## Repository map

See [`docs/REPOSITORY_STRUCTURE.md`](docs/REPOSITORY_STRUCTURE.md), [`docs/TECHNICAL_SPEC.md`](docs/TECHNICAL_SPEC.md), and [`GOVERNANCE.md`](GOVERNANCE.md).

## Development principles

1. Local-first: network access is never required for the core offline path once compatible models are installed.
2. Explicit consent: microphone access and any optional network feature must be clear to the user.
3. No hidden telemetry: no analytics or crash reporting by default.
4. Modular engines: speech recognition, translation, speech synthesis, and device storage are replaceable.
5. Reproducible builds and public issue tracking.
6. Community participation with transparent decision records.
7. Respect model, dataset, font, and voice licenses independently; the repository license does not relicense third-party assets.

## Getting started

The current browser proof-of-concept is in `apps/web-prototype/`. It demonstrates the interaction flow, but its browser speech-recognition path may use a remote browser vendor service. **Do not use it for confidential conversations.** The offline-first production architecture is specified separately and remains to be implemented.

For the prototype:
1. Start a compatible local translation service (see `apps/web-prototype/README.md`).
2. Serve the static app from `localhost` or HTTPS.
3. Grant microphone permission only if you understand the browser's speech-recognition privacy behavior.

## Contributing

Read [`CONTRIBUTING.md`](CONTRIBUTING.md), [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md), and [`SECURITY.md`](SECURITY.md) before contributing.

## Governance

This project proposes community governance. No foundation, legal entity, trademark ownership, or formal membership body is claimed to exist yet. See [`GOVERNANCE.md`](GOVERNANCE.md).

## License

Unless stated otherwise, original source code in this repository is offered under GNU AGPL version 3 or later. See [`LICENSE`](LICENSE). Third-party models, datasets, and dependencies retain their own licenses.
