# AIEF MVP v0.1 Specification

Version: 1.0

Status: Approved for Development

---

# Objective

Build the smallest version of AIEF that provides real value to users while establishing the architecture for future expansion.

The MVP must prioritize simplicity, stability, and extensibility over feature completeness.

---

# Core Goal

A user should be able to:

1. Sign in.
2. Create a project.
3. Describe a goal.
4. Execute an AI-powered workflow.
5. Receive structured output.
6. Save project history.
7. Continue the project later.

If these seven actions work reliably, the MVP is successful.

---

# Included Features

## Authentication

- Email login
- Google login (optional)
- JWT-based authentication

---

## Dashboard

- List projects
- Create project
- Delete project
- Search projects

---

## Project

Each project contains:

- Name
- Description
- Status
- Created Date
- Updated Date

---

## AI Workflow

Users can submit one goal.

Example:

"Design a SQL Learning Website."

AIEF should:

- Analyze intent
- Create execution plan
- Execute workflow
- Return structured output

---

## Memory

Store:

- Project history
- Artifacts
- Previous executions

No semantic search in MVP.

---

## AI Providers

Support:

- OpenAI
- Anthropic

Provider selection will be manual for v0.1.

Automatic routing will come later.

---

## Artifacts

Support:

- Markdown
- JSON
- Code
- Text

---

## User Interface

Pages:

- Login
- Dashboard
- Project
- Workflow
- Settings

---

## Settings

Users can configure:

- API Keys
- Preferred Provider
- Theme

---

# Excluded Features

Do NOT build in v0.1:

- Marketplace
- Plugins
- Team Collaboration
- Billing
- Workflow Templates
- Mobile App
- Voice
- Consensus Engine
- Capability Engine
- Workflow Marketplace
- Fine-tuned Models
- Local LLMs

---

# Success Criteria

The MVP succeeds if a user can complete one project from start to finish without switching to another AI platform.

---

# Non-functional Requirements

- Responsive UI
- FastAPI backend
- Next.js frontend
- PostgreSQL
- Docker support
- TypeScript
- Python
- REST API
- Clean architecture

---

# Future Versions

v0.2

- Multiple providers
- Automatic routing
- Semantic memory
- Review engine

v0.3

- Teams
- Plugins
- Marketplace

v1.0

- Full AI Operating System
- Module ecosystem
- Enterprise support
