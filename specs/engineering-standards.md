# AIEF Engineering Standards

Version: 1.0

---

# Purpose

This document defines mandatory engineering standards for every contributor (human or AI).

All generated code must follow these standards.

---

# General Principles

- Readability over cleverness.
- Explicit over implicit.
- Composition over inheritance.
- Small reusable functions.
- Modular architecture.
- Strong typing where applicable.
- Comprehensive documentation.
- Testability.

---

# Naming

Classes:
PascalCase

Functions:
camelCase

Variables:
camelCase

Constants:
UPPER_SNAKE_CASE

Files:
kebab-case

Folders:
kebab-case

---

# File Size

Target:

Maximum:

300-400 lines

Split earlier whenever possible.

---

# Function Size

Target:

20-40 lines

Maximum:

60 lines

---

# Documentation

Every public function must contain documentation.

---

# Error Handling

Never swallow exceptions.

Always return meaningful errors.

---

# Logging

Every service must log:

- start
- finish
- failure
- duration

---

# Testing

Every feature requires:

- unit tests

Future:

- integration tests
- e2e tests

---

# AI Rules

AI must never:

- duplicate code
- invent APIs
- invent database tables
- bypass architecture

AI must:

- follow specs
- reuse components
- explain major decisions

---

# Git

Small commits.

Clear messages.

No generated files.

---

# Code Review Checklist

Before merging:

[]

Compiles

[]

Lint passes

[]

Tests pass

[]

Documentation updated

[]

No duplicated code

[]

No unused imports

[]

Architecture respected

---

# Philosophy

Code should be understandable by a new engineer within minutes.

Optimization comes after correctness.

Consistency beats personal preference.
