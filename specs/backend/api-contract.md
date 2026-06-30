# AIEF Backend API Contract

Version: 1.0

Status: Approved

---

# API Philosophy

The AIEF API follows REST principles.

Rules:

- JSON only
- Versioned endpoints
- JWT Authentication
- UTC timestamps
- UUID identifiers
- Standard response format
- Consistent error handling

Base URL

/api/v1

---

# Standard Success Response

```json
{
    "success": true,
    "message": "Operation completed successfully.",
    "data": {}
}
```

---

# Standard Error Response

```json
{
    "success": false,
    "error": {
        "code": "PROJECT_NOT_FOUND",
        "message": "The requested project does not exist."
    }
}
```

---

# Authentication

## POST /auth/register

Purpose

Create a new user account.

Authentication

None

Request

```json
{
    "name": "John Doe",
    "email": "john@example.com",
    "password": "StrongPassword123"
}
```

Response

```json
{
    "success": true,
    "data": {
        "userId": "uuid"
    }
}
```

Validation

- Email must be unique
- Password minimum 8 characters

---

## POST /auth/login

Purpose

Authenticate user.

Request

```json
{
    "email": "john@example.com",
    "password": "password"
}
```

Response

```json
{
    "success": true,
    "data": {
        "accessToken": "...",
        "refreshToken": "...",
        "expiresIn": 3600
    }
}
```

---

# Projects

## GET /projects

Purpose

Return all projects for the authenticated user.

Authentication

Required

Response

```json
{
    "success": true,
    "data": [
        {
            "id": "...",
            "name": "...",
            "status": "ACTIVE"
        }
    ]
}
```

---

## POST /projects

Purpose

Create a project.

Request

```json
{
    "name": "QueryQuest",
    "description": "Interactive SQL Learning Platform"
}
```

Response

```json
{
    "success": true,
    "data": {
        "projectId": "uuid"
    }
}
```

Validation

- Name required
- Name max 100 characters

---

## GET /projects/{projectId}

Purpose

Retrieve project details.

---

## PUT /projects/{projectId}

Purpose

Update project.

---

## DELETE /projects/{projectId}

Purpose

Archive project.

---

# Workflows

## POST /workflows

Purpose

Create a workflow.

Request

```json
{
    "projectId": "uuid",
    "goal": "Build a SQL Learning Website"
}
```

Response

```json
{
    "success": true,
    "data": {
        "workflowId": "uuid",
        "status": "CREATED"
    }
}
```

---

## GET /workflows/{workflowId}

Purpose

Retrieve workflow details.

---

## POST /workflows/{workflowId}/execute

Purpose

Execute workflow.

Business Rules

- Workflow must exist.
- User must own the project.
- AI Provider must be configured.

---

## GET /workflows/{workflowId}/tasks

Return workflow tasks.

---

# Tasks

## GET /tasks/{taskId}

Return task details.

---

## PATCH /tasks/{taskId}

Update task status.

---

# Memory

## GET /projects/{projectId}/memory

Return project memory.

---

## POST /projects/{projectId}/memory

Create memory item.

---

## DELETE /projects/{projectId}/memory/{memoryId}

Delete memory item.

---

# Artifacts

## GET /projects/{projectId}/artifacts

Return artifacts.

---

## POST /artifacts

Create artifact.

---

## GET /artifacts/{artifactId}

Return artifact.

---

# AI Execution

## POST /execute

Purpose

Execute AI request.

Request

```json
{
    "provider": "anthropic",
    "projectId": "uuid",
    "prompt": "...",
    "workflowId": "uuid"
}
```

Response

```json
{
    "success": true,
    "data": {
        "artifactId": "uuid",
        "executionTime": 12.3,
        "tokensUsed": 4230
    }
}
```

---

# Settings

## GET /settings

Return workspace settings.

---

## PUT /settings

Update settings.

---

# Health

## GET /health

Returns API status.

---

# Future APIs

- Team Management
- Plugins
- Marketplace
- Billing
- Notifications
- AI Benchmarking
- Module Marketplace
