# AIEF Database Schema

Version: 1.0

Status: Approved

---

# Philosophy

The database should be normalized, scalable, and easy to extend.

Every entity should have:

- UUID primary key
- created_at
- updated_at

Soft deletion will be considered in future versions.

---

# Entity Relationship Diagram

Workspace
    │
    ├── Users
    │
    ├── Projects
    │       │
    │       ├── Workflows
    │       │      │
    │       │      ├── Tasks
    │       │      ├── Artifacts
    │       │      └── Memory
    │       │
    │       └── Settings
    │
    └── Provider Configurations

---

# Tables

## users

Fields

- id
- name
- email
- password_hash
- avatar_url
- created_at
- updated_at

---

## workspaces

Fields

- id
- name
- description
- owner_id
- created_at
- updated_at

---

## workspace_members

Fields

- id
- workspace_id
- user_id
- role

---

## projects

Fields

- id
- workspace_id
- name
- description
- status
- created_at
- updated_at

---

## workflows

Fields

- id
- project_id
- goal
- status
- started_at
- completed_at

---

## tasks

Fields

- id
- workflow_id
- title
- description
- module
- provider
- status
- priority
- retry_count

---

## artifacts

Fields

- id
- workflow_id
- task_id
- type
- filename
- content
- metadata

---

## memories

Fields

- id
- project_id
- memory_type
- title
- content
- confidence
- tags

---

## provider_configs

Fields

- id
- workspace_id
- provider
- encrypted_api_key
- default_model

---

## settings

Fields

- id
- workspace_id
- theme
- preferred_provider
- language

---

# Relationships

One User

↓

Many Workspaces

↓

Many Projects

↓

Many Workflows

↓

Many Tasks

↓

Many Artifacts

Memory belongs to Project.

Provider Config belongs to Workspace.

---

# Indexes

Create indexes for:

- email
- workspace_id
- project_id
- workflow_id
- task_id
- provider
- status

---

# Future Tables

- audit_logs
- notifications
- plugin_registry
- module_registry
- vector_embeddings
- workflow_templates
- billing
- organizations

---

# Notes

Use UUIDs instead of auto-increment IDs.

All timestamps should use UTC.

Foreign keys should enforce referential integrity.

Database migrations must be managed with Alembic.
