# Security Policy

## Supported versions
During the prototype phase, only the latest default branch is supported. Stable release support periods will be defined before a production release.

## Reporting a vulnerability
Do not publish exploitable details in a public issue. Use the hosting platform's private vulnerability reporting feature, if enabled, or contact the maintainers through the private contact route in `CONTACT.md`.

Include:
- affected version/commit and environment;
- steps to reproduce;
- impact and realistic attack scenario;
- suggested mitigation, if known.

Do not include real user audio, transcripts, credentials, or personal data.

## Security priorities
- microphone permission and recording lifecycle;
- local storage and cache isolation;
- model/package supply-chain integrity;
- dependency vulnerabilities;
- WebAssembly/WebGPU sandbox boundaries;
- cross-origin and content security policy;
- no secrets embedded in client code;
- secure update and model-download verification.

## Disclosure
The project will coordinate fixes and disclosure timelines with reporters. Do not promise a response time until a staffed security team exists.
