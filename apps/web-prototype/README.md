# Web prototype 0.1

This is a minimal interaction experiment, not the offline production implementation.

- Requires a locally running LibreTranslate-compatible endpoint.
- Browser speech recognition may transmit audio to a browser vendor.
- Browser TTS uses installed/system voices.
- Use only non-sensitive test phrases.
- Serve from localhost or HTTPS.

The next phase is to replace browser speech recognition and remote translation with local, audited inference engines as described in `docs/TECHNICAL_SPEC.md`.
