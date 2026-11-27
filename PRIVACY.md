# Privacy Principles and Data Flow

## Default promise
The intended production product is offline-first. Audio, transcripts, and translations should remain on the user's device by default.

## Prototype warning
The current web prototype uses browser speech recognition where available. Browser implementations may send audio to a vendor-operated service. This is not equivalent to offline processing. The prototype also sends recognized text to the configured translation endpoint. Do not use confidential or sensitive conversations.

## Production requirements
- microphone permission only after an explicit user action;
- visible recording indicator and obvious stop control;
- no audio or transcript retention by default;
- no analytics, advertising trackers, or session replay by default;
- local model downloads must be integrity-checked;
- optional network services must be opt-in, clearly described, and disabled by default;
- clear deletion controls for locally stored transcripts and downloaded models;
- no account required for basic local translation;
- privacy threat model before public beta.

## High-stakes warning
Machine translation can be wrong. The app must warn users not to rely on it as the sole interpreter for emergency, medical, legal, immigration, or other high-stakes decisions. Provide an option to seek a qualified human interpreter.
