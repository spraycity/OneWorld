# Proposed Repository Structure

```text
oneworld/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── GOVERNANCE.md
├── SECURITY.md
├── PRIVACY.md
├── CHANGELOG.md
├── CONTACT.md
├── .gitignore
├── .editorconfig
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.yml
│   │   ├── feature_request.yml
│   │   └── language_request.yml
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows/
│       └── ci.yml
├── apps/
│   ├── web/
│   │   ├── src/
│   │   ├── public/
│   │   └── tests/
│   ├── android/                 # later phase
│   └── ios/                     # later phase
├── packages/
│   ├── conversation-core/
│   ├── speech-engine/
│   ├── translation-engine/
│   ├── voice-engine/
│   ├── privacy-core/
│   └── language-registry/
├── models/
│   ├── MODEL_CATALOG.md
│   └── THIRD_PARTY_NOTICES.md
├── docs/
│   ├── REPOSITORY_STRUCTURE.md
│   ├── TECHNICAL_SPEC.md
│   ├── ROADMAP.md
│   ├── THREAT_MODEL.md
│   ├── ACCESSIBILITY.md
│   ├── LANGUAGE_POLICY.md
│   └── decisions/
│       ├── 0001-offline-first.md
│       └── 0002-modular-engines.md
├── infra/
│   ├── dev/
│   └── release/
└── tools/
    ├── model-audit/
    └── language-test-harness/
```

## Repository hygiene
- Never commit model weights by default; document download sources, hashes, and licenses.
- Keep secrets out of source control.
- Use signed releases and dependency pinning before beta.
- Separate app code from model adapters.
- Keep language metadata machine-readable and community-reviewable.
