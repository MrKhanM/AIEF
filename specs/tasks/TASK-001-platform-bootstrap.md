# TASK-001 - Platform Bootstrap

Status: Ready

Priority: Critical

Estimated Time: 2-4 hours

---

## Objective

Bootstrap the AIEF development platform.

This task only establishes infrastructure.

No business logic should be implemented.

---

## Requirements

Initialize:

- Turborepo
- pnpm workspace
- Next.js application
- FastAPI application
- Docker Compose
- PostgreSQL
- Redis

---

## Frontend

Create:

apps/web

Requirements:

- Next.js
- TypeScript
- Tailwind CSS
- App Router

Display:

"AIEF Platform"

---

## Backend

Create:

apps/api

Requirements:

- FastAPI

Endpoints:

GET /

Response

{
    "status":"running"
}

GET /health

Response

{
    "health":"ok"
}

Swagger must work.

---

## Shared Packages

Create:

packages/shared

packages/ai-kernel

packages/provider-sdk

packages/workflow-engine

packages/memory-engine

Each package should contain:

README

package configuration

placeholder structure

---

## Docker

Create containers:

Frontend

Backend

PostgreSQL

Redis

---

## Environment

Create:

.env.example

Include:

DATABASE_URL

REDIS_URL

OPENAI_API_KEY

ANTHROPIC_API_KEY

JWT_SECRET

---

## GitHub Actions

Create CI pipeline.

Run:

Lint

Build

Tests

---

## Success Criteria

Repository installs.

Repository builds.

Repository runs.

Frontend opens.

Backend opens.

Swagger opens.

Database connects.

Redis connects.

No business logic exists.
