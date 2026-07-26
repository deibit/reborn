# AGENTS.md

# Reborn Repository Instructions

## Mission

Reborn is a reusable starter kit for modern desktop-oriented web applications.

Its purpose is not to demonstrate technologies or architectural patterns. Its purpose is to provide a clean, maintainable, production-ready foundation that can be safely extended over time.

Every change should make the project easier to understand, easier to maintain and easier to evolve.

---

This repository follows the principles defined in docs/philosophy.md.

---

# Technology Stack

The core stack is intentionally fixed.

Backend

- Python 3.14
- FastAPI
- SQLModel
- Alembic
- SQLite (default)

Frontend

- Vue 3
- TypeScript
- Vite

Python tooling

- uv

Testing

- Pytest
- Vitest
- Playwright

Do not replace core technologies unless explicitly requested.

Do not introduce alternative frameworks because of personal preference.

---

# Repository Architecture

The repository is organised around business features rather than technical layers.

Business functionality belongs inside feature modules.

Shared functionality belongs under `shared`.

Framework-specific code belongs under `core`.

Database-related code belongs under `db`.

Frontend functionality is organised by features.

Keep related code physically close together.

Avoid scattering one feature across unrelated directories.

---

# Working Rules

Before writing code:

Understand the existing implementation.

Search for existing solutions.

Reuse existing components whenever practical.

Extend existing code before introducing parallel implementations.

Only create new abstractions when duplication has already appeared.

Do not redesign working code simply because another approach exists.

Preserve the overall architecture unless explicitly instructed otherwise.

---

# Coding Principles

Write code for the next developer.

Use descriptive names.

Keep functions focused.

Keep files reasonably small.

Prefer composition over inheritance.

Avoid unnecessary indirection.

Avoid speculative abstractions.

Avoid unnecessary dependencies.

Avoid hidden side effects.

Keep interfaces simple.

Prefer explicit behaviour over implicit behaviour.

Do not leave dead code.

Do not leave commented-out code.

Do not leave debug code.

Do not use print() for diagnostics.

Use structured logging.

Always use type hints where applicable.

---

# Error Handling

Errors are part of the application design.

Never silently ignore exceptions.

Raise meaningful application exceptions.

Avoid returning inconsistent error formats.

Keep error messages useful for developers while avoiding leaking sensitive information.

---

# Dependencies

Every dependency has a long-term maintenance cost.

Before introducing one, ask:

- Can the standard library solve this?
- Can an existing dependency solve this?
- Is this dependency solving a significant problem?

Avoid adding packages for trivial functionality.

---

# Database

Treat schema changes as first-class changes.

Database modifications must include migrations.

Do not manually modify production schemas.

Keep models simple.

Keep business rules outside persistence models whenever practical.

---

# API

APIs should be predictable.

Prefer consistency over cleverness.

Reuse existing request and response patterns.

Maintain a consistent error format.

Avoid unnecessary endpoint variations.

---

# Frontend

Frontend code should remain feature-oriented.

Components should have a single responsibility.

Prefer reusable components over duplicated UI.

Avoid deeply nested component hierarchies.

Keep business logic outside presentation components whenever practical.

---

# Testing

Tests describe behaviour.

Write tests for behaviour, not implementation details.

New functionality should include appropriate tests.

Bug fixes should include regression tests.

Avoid testing framework behaviour.

Avoid excessive mocking.

Prefer meaningful integration tests over artificial unit tests.

---

# Documentation

Documentation is part of the codebase.

Update documentation when behaviour changes.

Avoid duplicated documentation.

Keep documentation concise.

Document architectural decisions rather than obvious implementation details.

---

# Performance

Do not optimise prematurely.

Write clear code first.

Optimise only after identifying a real bottleneck.

Never sacrifice readability for hypothetical performance gains.

---

# Security

Treat all external input as untrusted.

Validate input.

Fail safely.

Avoid leaking sensitive information.

Do not hardcode secrets.

Never commit credentials.

---

# Development Workflow

Before implementing a feature:

1. Understand the problem.
2. Inspect existing implementations.
3. Design the smallest reasonable solution.
4. Implement.
5. Test.
6. Refactor if necessary.
7. Update documentation when appropriate.

---

# Completion Checklist

A task is not complete until:

- The implementation is correct.
- The code follows the existing architecture.
- Existing functionality remains unaffected.
- Tests pass.
- Type checking passes.
- Linting passes.
- No debug code remains.
- No dead code remains.
- Documentation has been updated when necessary.

---

# Things to Avoid

Avoid:

- Premature optimisation.
- Premature abstraction.
- Reinventing existing solutions.
- Unnecessary dependencies.
- Hidden behaviour.
- Large unrelated refactors.
- Mixing unrelated changes in the same task.
- Changing architecture without a clear reason.

---

# Final Goal

Every commit should leave the repository in a better state than it was found.

When in doubt, choose the solution that will be easiest to understand six months from now.