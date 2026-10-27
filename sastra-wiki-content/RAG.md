# Khmer-first RAG

Retrieval-Augmented Generation is a flagship SASTRA AI capability. It grounds model responses in user-provided sources instead of relying only on model memory.

## Current flow

1. Ingest text, a URL, an uploaded document, or extracted PDF text.
2. Clean and split the content into overlapping chunks.
3. Generate sentence-transformer embeddings.
4. Store metadata, chunks, and compressed vectors per document.
5. Embed the user's query and rank chunks with cosine similarity.
6. Add the best passages to the model prompt and return citations.

## Khmer-first requirements

- Chunk Khmer without breaking meaningful words or clauses.
- Retrieve Khmer spelling variants, transliterations, and Cambodian named entities.
- Support mixed Khmer/English technical content.
- Preserve page, section, timestamp, and source metadata.
- Support cross-language queries across Khmer, English, French, and Chinese sources.
- Evaluate retrieval recall, answer faithfulness, citation accuracy, latency, and cost.

## Supported sources

- Plain text and Markdown
- PDFs with extractable text
- Web pages and URLs
- OCR output from images and scanned PDFs
- ASR transcripts when the speech pipeline is implemented

## Planned work

Track the dedicated roadmap in [issue #3](https://github.com/phanphoun123-lab/sastra/issues/3).

Before production use, document ownership, authorization, path validation, and safe URL ingestion must be enforced. See [[Security and Privacy]].

