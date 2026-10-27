# Architecture

SASTRA AI is a multi-application system built around a shared FastAPI backend.

```text
Public Site          User Chat Portal          Admin Portal
     │                       │                       │
     └───────────────────────┴───────────────────────┘
                             │
                       FastAPI Backend
                             │
       ┌─────────────────────┼─────────────────────┐
       │                     │                     │
 Authentication       Provider Layer        RAG / Documents
       │                     │                     │
 PostgreSQL/JSON      Gemini / Ollama       Embeddings + Files
                             │
                    Tools and Generation
```

## Repository layout

| Path | Responsibility |
| --- | --- |
| `backend/` | FastAPI routes, services, model providers, RAG, tools, auth, telemetry, tests |
| `frontend/` | React user chat workspace |
| `admin-site/` | React administration and telemetry application |
| `public-sastra/` | Public product website |
| `monitoring/` | Prometheus and Grafana configuration |
| `docker-compose.yml` | Local PostgreSQL, pgAdmin, and Adminer |
| `docker-compose.prod.yml` | Containerized application stack |

## Backend layers

- `routes/` exposes authentication, chat, documents, tools, health, administration, and coding-agent APIs.
- `providers/` provides a common interface for Gemini and Ollama-compatible engines.
- `services/chat_service.py` orchestrates prompts, providers, streaming, RAG context, and tools.
- `services/rag_service.py` extracts and chunks content.
- `services/rag_store.py` stores document metadata, chunks, and vector embeddings.
- `prompts/` contains Khmer language, cultural, and mode-specific guidance.
- `database/` contains SQLAlchemy models and PostgreSQL initialization.

## Request flow

1. The client authenticates and selects a provider, model, language, and optional documents.
2. The API loads conversation history and retrieves relevant document chunks.
3. The prompt builder combines system guidance, Khmer rules, conversation context, and RAG evidence.
4. The provider streams or returns a response.
5. The API records telemetry and returns citations, tool calls, and session metadata.

## Storage

- PostgreSQL is intended for users, providers, and telemetry.
- The current project also contains legacy JSON-backed repositories that should be migrated and excluded from source control.
- RAG artifacts are stored under the configured RAG directory.
- Generated documents are stored under the backend data directory.

See [[Security and Privacy]] before deploying this architecture publicly.

