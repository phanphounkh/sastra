# Security and Privacy

SASTRA AI processes sensitive artifacts: conversations, documents, images, recordings, transcripts, account data, provider credentials, and telemetry. Privacy must be enforced by architecture, not only by UI.

## Production requirements

- Require authentication for chat, document, OCR, ASR, generated-file, and administration APIs.
- Derive user identity from verified tokens.
- Scope every stored artifact to an owner or authorized workspace.
- Validate resolved filesystem paths remain under their configured storage root.
- Block URL ingestion from loopback, private, link-local, and cloud metadata addresses, including after redirects.
- Encrypt transport with HTTPS and protect provider credentials at rest.
- Set strong unique secrets and passwords through environment variables.
- Define retention and deletion behavior for every data type.
- Record security-relevant administration actions without logging secrets or full private content.
- Keep coding-agent mode disabled on public deployments.

## Repository hygiene

Runtime databases, chat history, activity logs, uploaded artifacts, generated files, `.env` files, API keys, and password hashes must never be committed. If private data enters Git history, remove it from the complete history and rotate affected credentials.

## Current hardening tracker

See [issue #1](https://github.com/phanphoun123-lab/sastra/issues/1) for the consolidated security review and remediation checklist.

## Responsible operation

Before enabling OCR or ASR through an external provider, document what leaves the deployment, which provider receives it, retention terms, and how users can delete source and derived data.

