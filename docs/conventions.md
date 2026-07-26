# Coding Conventions

## Purpose

This document defines the coding conventions used throughout Reborn.

These conventions exist to keep the codebase predictable, readable and easy to evolve.

Most formatting concerns are intentionally delegated to automated tools.

This document focuses on design conventions rather than formatting rules.

---

# General Principles

Whenever multiple correct solutions exist, prefer the solution that best matches the surrounding code.

Consistency across the repository is usually more valuable than local optimisation.

Code should be easy to understand without requiring additional explanation.

Write code for the next developer, not for the current one.

---

# Naming

Names should describe intent rather than implementation.

Prefer names that describe what something represents.

Good

```
calculate_total_price()
expired_sessions
user_repository
```

Avoid vague names.

```
process()
handle()
manager()
helper()
misc()
data()
temp()
```

Abbreviations should only be used when they are already universally understood.

---

# Files

Each file should have a clear responsibility.

Avoid files that continuously accumulate unrelated functionality.

Large files are usually a symptom of multiple responsibilities.

Split files around cohesive concepts rather than arbitrary size limits.

---

# Functions

Functions should perform one logical task.

Prefer small functions with clear responsibilities.

Avoid functions that both calculate and perform side effects.

Prefer returning values instead of mutating external state.

Avoid unnecessary parameters.

Avoid boolean flags that completely change function behaviour.

---

# Classes

Classes should model meaningful concepts.

Avoid classes that simply group unrelated functions.

Prefer composition over inheritance.

Inheritance should model "is-a" relationships, not code reuse.

---

# Modules

Modules own business functionality.

A module should contain everything required to understand that feature.

Avoid scattering one feature across unrelated directories.

New modules should follow the existing repository structure.

---

# Services

Services implement business behaviour.

Services should:

- contain business rules
- coordinate operations
- remain framework-independent whenever practical

Services should not:

- build HTTP responses
- know about FastAPI
- perform presentation logic
- contain SQL queries

Raise application exceptions rather than framework exceptions whenever possible.

---

# Repositories

Repositories encapsulate persistence.

Repositories are responsible for retrieving and storing data.

Repositories should not contain business rules.

Simple CRUD operations should remain simple.

Do not introduce unnecessary repository abstractions.

---

# Models

Persistence models describe storage.

Business behaviour should not be hidden inside persistence models.

Prefer explicit service logic over model magic.

Avoid complex lifecycle hooks unless absolutely necessary.

---

# Schemas

Schemas define communication contracts.

Separate persistence models from API schemas.

Avoid exposing internal database structures directly through the API.

---

# Routes

Routes are coordinators.

Routes should:

- validate requests
- invoke services
- return responses

Routes should remain thin.

Business behaviour belongs elsewhere.

---

# Error Handling

Errors should be explicit.

Do not silently ignore failures.

Use application-specific exceptions whenever appropriate.

Avoid inconsistent return values for error conditions.

Choose one approach and remain consistent.

---

# Logging

Logging should describe meaningful events.

Avoid excessive logging.

Avoid duplicate log entries.

Do not log sensitive information.

Use structured logging instead of debugging output.

Never use print() for application diagnostics.

---

# Configuration

Configuration belongs in the configuration system.

Business code should never access environment variables directly.

Avoid configuration values scattered throughout the codebase.

---

# Dependencies

Prefer existing project dependencies before introducing new ones.

Avoid adding dependencies for small utility functions.

Every dependency increases maintenance cost.

---

# Comments

Good code should explain itself.

Comments should explain why.

Code should explain how.

Avoid comments that merely repeat the implementation.

Bad

```python
# Increment i
i += 1
```

Good

```python
# The external API starts counting from one.
index += 1
```

---

# TODOs

Avoid permanent TODO comments.

Every TODO should explain:

- why it exists
- what remains to be done

Temporary TODOs should eventually disappear.

---

# Code Duplication

Do not remove duplication too early.

Some duplication is healthy.

Once a pattern has clearly emerged, extract the shared behaviour.

Avoid speculative abstractions.

---

# Refactoring

Refactoring should preserve behaviour.

Avoid combining refactoring with feature development unless necessary.

Small incremental refactorings are preferred over large rewrites.

---

# Testing

Tests should describe behaviour.

Test names should explain what is expected.

Avoid tests that merely verify implementation details.

Keep test organisation consistent with the production code.

---

# Vue Components

Components render UI.

Pages coordinate user flows.

Composables encapsulate reusable behaviour.

Stores own global client state.

Avoid mixing responsibilities.

---

# API Clients

HTTP communication belongs inside API clients.

Components should not perform HTTP requests directly.

Business logic should not be duplicated between frontend and backend.

---

# Generated Code

Generated files are read-only.

Modify the source.

Regenerate the output.

Never manually edit generated files.

---

# Imports

Imports should remain predictable.

Avoid circular dependencies.

Prefer explicit imports.

Avoid wildcard imports.

Group imports consistently throughout the repository.

---

# Code Review Expectations

Every change should improve at least one of:

- readability
- maintainability
- consistency
- correctness

Large unrelated refactorings should be avoided.

When reviewing code, optimise for long-term maintainability rather than personal preference.

---

# Final Rule

If a decision requires explaining why it is different from the surrounding code, it is probably the wrong decision.

Consistency is the default.