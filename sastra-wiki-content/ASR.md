# Khmer ASR

Automatic Speech Recognition will convert Khmer speech into editable, searchable transcripts that can be used in chat and RAG.

## Target workflow

1. Record from the browser or upload an audio file.
2. Validate duration, format, and size.
3. Select Khmer or another supported language.
4. Produce transcript segments with timestamps and speakers where available.
5. Let the user review and correct the transcript.
6. Send approved text to chat or index it for RAG with time-based citations.

## Khmer-specific requirements

- Evaluate common Cambodian accents, speaking speeds, and code-switching.
- Handle background noise and typical phone microphones.
- Preserve names, Cambodian locations, numbers, dates, and domain terminology.
- Support mixed Khmer/English speech without unnecessary translation.

English, French, and Chinese ASR should be available when supported by the selected provider.

## Privacy

Users must be informed about recording, retention, deletion, and any third-party provider processing. Source audio and transcripts must remain private to their owner by default.

Track the dedicated roadmap in [issue #6](https://github.com/phanphoun123-lab/sastra/issues/6).

