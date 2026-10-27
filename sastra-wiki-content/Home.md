# 🇰🇭 SASTRA AI

**SASTRA AI is a Khmer-first, multilingual AI platform for Cambodia.** Its product direction centers on four connected capabilities: grounded knowledge through RAG, natural AI chat, Khmer OCR, and Khmer ASR. English, French, and Chinese are supported as additional languages.

The platform combines a FastAPI backend, React applications, pluggable AI providers, document retrieval, authentication, telemetry, and local-model support.

## Product principles

- **Khmer first:** Khmer language quality, script handling, terminology, and Cambodian context are the primary benchmark.
- **Grounded answers:** RAG responses should be traceable to source documents and citations.
- **Multilingual by design:** English, French, Chinese, and mixed-language content should work without weakening Khmer defaults.
- **Provider flexibility:** Run with Gemini, Ollama, cloud models, or registered compatible providers.
- **Privacy and sovereignty:** Local execution is supported, and user artifacts should be private by default.
- **Measurable quality:** RAG, chat, OCR, and ASR should be evaluated with versioned benchmarks.

## Core capabilities

| Capability | Purpose | Status |
| --- | --- | --- |
| [[RAG]] | Upload, index, retrieve, and cite Khmer and multilingual knowledge | Implemented; hardening and quality improvements planned |
| [[Chat]] | Khmer-first streaming conversation across multiple AI providers | Implemented; language evaluation and access controls planned |
| [[OCR]] | Extract Khmer text from images and scanned documents | Early capability; dedicated pipeline planned |
| [[ASR]] | Convert Khmer speech and recordings into searchable text | Planned |

## Applications

- **User workspace** (`frontend/`, port `5173`) — chat, documents, providers, history, themes, sharing, and export.
- **Admin portal** (`admin-site/`, port `5174`) — users, model providers, telemetry, and audit logs.
- **Public website** (`public-sastra/`, port `5175`) — product presentation and interactive demonstrations.
- **API backend** (`backend/`, port `8001`) — authentication, chat, RAG, tools, document generation, telemetry, and agent mode.

## Start here

- [[Getting Started]]
- [[Architecture]]
- [[API Guide]]
- [[Security and Privacy]]
- [[Product Roadmap]]
- [Project issues](https://github.com/phanphoun123-lab/sastra/issues)

> SASTRA means knowledge, scholarship, and learning. The project aims to make advanced AI genuinely useful in Khmer—not merely translated into Khmer.

