# Product Roadmap

SASTRA AI's direction is Khmer-first and multilingual. The roadmap is split into focused feature tracks.

## Feature tracks

- [Issue #3 — Khmer-first RAG](https://github.com/phanphoun123-lab/sastra/issues/3)
- [Issue #4 — Khmer-first chat](https://github.com/phanphoun123-lab/sastra/issues/4)
- [Issue #5 — Khmer OCR](https://github.com/phanphoun123-lab/sastra/issues/5)
- [Issue #6 — Khmer ASR](https://github.com/phanphoun123-lab/sastra/issues/6)

The umbrella product direction is tracked in [issue #2](https://github.com/phanphoun123-lab/sastra/issues/2).

## Shared success measures

- Permission-cleared and versioned evaluation data
- Khmer quality reported separately from other languages
- English, French, Chinese, and mixed-language regression coverage
- Accuracy, latency, cost, and reliability recorded by provider/model
- Private-by-default ownership for every user artifact
- Clear fallback behavior when a provider or language capability is unavailable

## Recommended delivery order

1. Complete security and data-isolation work from issue #1.
2. Establish shared language routing and evaluation infrastructure.
3. Improve RAG and chat, which already have working product surfaces.
4. Build OCR with review-and-correct flow and RAG handoff.
5. Build ASR using the same artifact, correction, citation, and privacy model.

