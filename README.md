# Tracker AI — Concept and Architecture Plan

**Status: concept / pre-implementation.** This repository currently documents the idea only; it does not contain a working application, backend, frontend, or tests. Do not treat it as a deployed or functioning product.

## Problem

Developer workflows split project planning, debugging guidance, and production error monitoring across separate tools. Tracker AI is a proposed developer portal that would bring these workflows into one place.

## Proposed scope

1. **Project workspace** — organize projects, milestones, tasks, and technical notes.
2. **AI debugging tutor** — help developers understand errors and build a reproducible debugging checklist. Suggestions should be grounded in supplied code and logs rather than inventing causes.
3. **Deployment telemetry** — ingest error events and traces after deployment, group recurring failures, and link them back to project context.
4. **Retrieval over project knowledge** — optionally index README files, architecture notes, and approved logs for grounded answers.

## Proposed stack (not implemented)

- **Frontend:** Next.js, TypeScript, Tailwind CSS.
- **API:** FastAPI, Python, Pydantic.
- **Data:** PostgreSQL/Supabase; pgvector only if retrieval is implemented and evaluated.
- **Observability:** structured logs and OpenTelemetry/Sentry-compatible error ingestion.
- **AI integration:** provider abstraction with explicit timeouts, error handling, and tests.

These are design candidates, not claims about the current codebase.

## Implementation milestones

- [ ] Write a minimal product requirements document and define the first user flow.
- [ ] Implement project CRUD with database migrations and authorization tests.
- [ ] Add a deterministic error-ingestion endpoint and an integration test.
- [ ] Add a small, opt-in debugging assistant with source-grounded responses.
- [ ] Add retrieval only after creating a test set and measuring answer grounding.
- [ ] Document local setup and publish a successful CI run before calling it implemented.

## Current verification

- **Application implementation:** not present in this repository at this time.
- **Automated tests:** none available to run.
- **Live deployment:** not claimed.

The next meaningful milestone is the first end-to-end vertical slice, not adding more planned features.
