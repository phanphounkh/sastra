# API Guide

The FastAPI service runs on port `8001` by default. Interactive OpenAPI documentation is available at `/docs`.

## Main route groups

| Prefix | Purpose |
| --- | --- |
| `/api/auth` | Register, login, guest access, profile |
| `/api/chat`, `/api/chat/stream` | Chat completion and server-sent-event streaming |
| `/api/documents` | RAG ingestion, listing, retrieval, deletion, and document generation |
| `/api/admin` | Users, model providers, telemetry, and logs |
| `/api/tools` | Available model tools |
| `/api/agent` | Local coding-agent workflow; disabled by default |
| `/health` | Health check |
| `/metrics` | Prometheus metrics |

## Authentication

Authenticated routes use a bearer token:

```http
Authorization: Bearer <access-token>
```

Clients obtain a token from the login, registration, or guest authentication endpoint. User identity should always be derived from the verified token rather than trusted from request-body fields.

## Streaming chat

`POST /api/chat/stream` returns server-sent events. Frames may include:

- `session_id`
- incremental `content`
- final `citations`
- `done`
- `error`

## RAG documents

Document endpoints support text, URLs, uploads, metadata, chunks, and generated documents. Production deployments must authenticate these endpoints and scope each document to its owner.

## Agent mode

Agent mode can read project files and run allowlisted development commands. It is disabled by default and must never be exposed publicly. See `AGENT.md` in the repository for its security model and endpoints.

