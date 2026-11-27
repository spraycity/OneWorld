# ONEWORLD Technical Specification — Draft 0.1

## 1. Product objective

Build a privacy-first, offline-first, two-way speech translation application. The first deliverable is a web prototype that validates the conversation UX; production offline speech translation is a subsequent milestone.

## 2. User flow

1. User selects two languages or enables language auto-detection.
2. User explicitly starts a conversation and grants microphone permission.
3. The app indicates which microphone/listener is active.
4. Speech recognition emits partial and final transcript segments.
5. Translation engine translates finalized or suitably stable segments.
6. Speech synthesis plays the translation to the intended listener.
7. Both original and translated text appear on screen.
8. User can pause, stop, clear local history, or switch direction.
9. Session ends with no retained audio/transcript unless user explicitly saves it.

## 3. Non-functional requirements

- Offline-first: core speech/translation/synthesis path runs locally after models are installed.
- No account required for basic use.
- No mandatory server dependency for offline mode.
- No default audio/transcript persistence.
- Explicit microphone indicator and one-action stop.
- Accessible controls, keyboard operation, screen-reader labels, captions.
- Graceful degradation on low-memory devices.
- Measurable latency, memory, battery, and translation-quality targets.
- No claim of universal language support without test evidence.

## 4. Architecture

### Client
- Progressive Web App shell.
- Web Audio API for capture/playback, subject to browser permissions.
- Worker isolation for compute-heavy inference where supported.
- IndexedDB/Cache Storage for user-approved model assets.
- WebAssembly CPU inference baseline; WebGPU acceleration when available.
- Capability detection and transparent fallback messaging.

### Speech engine
Adapter interface:
- `load(modelManifest)`
- `start(stream, languageHint)`
- `pushAudio(chunk)`
- `onPartialTranscript(segment)`
- `onFinalTranscript(segment)`
- `stop()`

Candidate model families may include Whisper-compatible implementations, but exact model, quantization, runtime, and license must be evaluated for browser size, latency, language coverage, and redistribution rights.

### Translation engine
Adapter interface:
- `translate(text, sourceLanguage, targetLanguage, context?)`
- `supportedPairs()`
- `qualityMetadata()`

Candidate offline systems include Argos Translate or other multilingual models. Do not assume every language pair is directly supported; pivot translation may introduce quality loss and must be disclosed.

### Voice engine
Adapter interface:
- `synthesize(text, language, voiceId?)`
- `availableVoices(language)`
- `cancel()`

Candidate local TTS engines include Piper-compatible runtimes. Every voice model requires a separate license, provenance, and quality review.

### Conversation coordinator
- manages two directions and turn-taking;
- prevents playback from being re-captured as microphone input where possible;
- uses headphones/echo cancellation where supported;
- marks uncertainty and supports correction;
- never silently treats uncertain language detection as certain.

## 5. Web-specific constraints

- Browser speech recognition is not reliably offline and may transmit audio to a browser vendor. It must not be used as the production privacy path unless its behavior is verified and disclosed.
- Microphone access requires secure context (HTTPS or localhost) and user permission.
- WebGPU availability and performance vary by device/browser.
- Large model downloads require storage, integrity, versioning, and quota handling.
- Browser audio routing to separate participants/headphones varies by operating system and device.
- Background execution and continuous microphone operation may be suspended by browsers/mobile operating systems.

## 6. Initial implementation strategy

Phase A — UX prototype:
- two language selectors;
- manual text translation;
- optional browser speech APIs clearly labeled as non-private/experimental;
- transcript display and TTS playback.

Phase B — local inference experiment:
- benchmark a small ASR model in browser/WASM or WebGPU;
- benchmark offline translation for Hungarian-English;
- benchmark local TTS for both languages;
- test model download size, cold-start time, RAM, battery, and sustained latency.

Phase C — offline alpha:
- integrate compatible local models;
- remove cloud speech recognition from the default path;
- make network use opt-in;
- add session deletion and model integrity checks.

Phase D — two-device and mobile:
- robust turn-taking and audio routing;
- PWA installation;
- Android packaging;
- iOS feasibility assessment based on browser/runtime limits.

## 7. Initial acceptance criteria

The first offline alpha is not complete until:
- airplane-mode test succeeds after model installation;
- no audio/transcript network requests are observed;
- user can stop capture immediately;
- transcript and translation are readable and screen-reader accessible;
- Hungarian↔English test set has published quality results;
- sustained 15-minute session has documented latency, memory, and battery results on named devices;
- model licenses and hashes are recorded;
- known failure modes are disclosed.

## 8. High-stakes safety

The app is an assistive communication tool, not a certified interpreter. It must show uncertainty, allow repetition/correction, and advise qualified human interpretation for medical, legal, emergency, immigration, and other high-stakes situations.
