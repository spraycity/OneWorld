# Initial Threat Model — Draft 0.1

## Assets
- microphone audio;
- live transcripts and translations;
- downloaded model files;
- user language preferences;
- application integrity and update channel.

## Threats
- accidental audio transmission by browser speech APIs;
- malicious or compromised model download;
- malicious dependency or build pipeline;
- local transcript exposure on shared devices;
- microphone left active unintentionally;
- deceptive UI that hides remote processing;
- cross-origin access to local services;
- translation manipulation or prompt/data injection in future model-assisted features.

## Mitigations
- default to verified local inference;
- visible recording state and immediate stop;
- no default transcript persistence;
- model hashes and signed manifests;
- dependency pinning and automated scanning;
- restrictive Content Security Policy;
- no secrets in frontend bundles;
- explicit network permission and clear data-flow indicator;
- independent security review before beta.

## Open questions
- browser storage encryption and key lifecycle;
- safe model update mechanism;
- multi-speaker diarization privacy;
- local device threat assumptions;
- abuse reporting and incident response capacity.
