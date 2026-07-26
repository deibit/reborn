# Architecture

## Purpose

This document describes the architectural structure of Reborn.

It explains how the repository is organised, where responsibilities belong and how new functionality should be integrated.

It is intentionally independent from any specific business domain.

---

The architecture described here is an application of the principles defined in Philosophy.

---

# High-Level Structure

The repository is divided into two independent applications.

```
backend/
frontend/
```

Both applications evolve independently while sharing the same business domain.

Changes affecting both sides should remain consistent.

---

# Backend Architecture

The backend applies the locality principle.

Each business feature owns the code required to implement that feature.

Models, services, repositories and routes remain physically close together.

The objective is to minimise navigation and maximise discoverability.

The backend is organised by business features.

Example:

```
modules/

    books/

        models.py

        schemas.py

        repository.py

        service.py

        routes.py
```

Each module owns its business logic.

Avoid splitting one business feature across multiple unrelated directories.

---

# Backend Layers

The backend contains four main areas.

## api

HTTP-specific code.

Responsibilities:

- routing
- request validation
- response formatting
- dependency injection

Business logic should not live here.

---

## core

Application infrastructure.

Responsibilities:

- configuration
- logging
- startup
- lifespan
- security

Business logic should not live here.

---

## db

Persistence infrastructure.

Responsibilities:

- database engine
- sessions
- migrations
- seed utilities

Database access should remain isolated here.

---

## shared

Reusable utilities shared across multiple modules.

Typical examples:

- pagination
- exceptions
- utilities
- common types

Shared code must demonstrate actual reuse before being promoted here.

Avoid creating "shared" code pre-emptively.

---

# Business Modules

Each business feature owns its implementation.

Typical contents:

- models
- schemas
- services
- repositories
- routes

The objective is locality.

Developers should understand one feature without navigating the entire repository.

---

# Request Lifecycle

Typical request flow:

Client

↓

Route

↓

Service

↓

Repository

↓

Database

Routes coordinate requests.

Services implement business behaviour.

Repositories implement persistence.

---

# Frontend Architecture

The frontend is also organised by business features.

```
features/

    books/

    users/

    settings/
```

Each feature owns:

- pages
- components
- composables
- API interactions
- local types

---

# Shared Frontend Code

Shared components belong under:

```
components/common
```

Shared layouts belong under:

```
components/layout
```

Shared utilities belong under:

```
utils
```

Promote code only after genuine reuse.

---

# API Contract

The frontend communicates exclusively through the backend API.

Do not duplicate business rules.

Validation belongs primarily to the backend.

Frontend validation exists to improve user experience.

---

# Database

The database is considered an implementation detail.

Business logic should not depend on SQLite-specific behaviour.

Changing the database engine should require minimal business changes.

---

# Generated Code

Generated code is never edited manually.

Examples include:

- OpenAPI-generated TypeScript
- generated clients

Modify the source.

Regenerate the output.

---

# Configuration

Configuration belongs in configuration files.

Business code should not read environment variables directly.

Use the central configuration system.

---

# Error Handling

Errors should follow a consistent application-wide format.

Application exceptions should propagate through the defined error handling layer.

Avoid ad-hoc error responses.

---

# Logging

Logging is infrastructure.

Business code should emit meaningful events.

Logging implementation belongs in the infrastructure layer.

---

# Tests

Tests mirror the repository structure.

Features should contain corresponding tests.

Test organisation should remain predictable.

---

# Evolution

The architecture should evolve conservatively.

Prefer extending existing patterns.

Avoid introducing new architectural styles inside the same repository.

Consistency is usually more valuable than theoretical improvements.

---

# Deliberately Not Included

Reborn intentionally avoids introducing:

- Microservices
- CQRS
- Event sourcing
- Hexagonal architecture
- Onion architecture
- Plugin systems
- Message buses
- Background workers
- GraphQL

These technologies are not discouraged.

They simply are not part of the base architecture.

Introduce them only when the project genuinely requires them.

---

# Architectural Rule

Whenever multiple reasonable implementations exist,
prefer the one that best matches the existing architecture.

Long-term consistency is more valuable than local optimisation.