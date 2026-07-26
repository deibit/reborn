# LLM Guidelines

## Purpose

This document describes how AI coding assistants are expected to reason while working on this repository.

It does not replace the architectural or coding conventions.

Instead, it explains the decision-making process that should guide every implementation.

The objective is not merely to generate working code.

The objective is to generate code that naturally belongs in this repository.

---

# The Repository Is The Source Of Truth

Always assume the existing repository is correct unless explicitly instructed otherwise.

Do not replace existing patterns because another approach is more modern or personally preferred.

Observe first.

Understand second.

Modify third.

---

# Before Writing Code

Before writing any code:

- Understand the request.
- Inspect the surrounding implementation.
- Search for similar functionality.
- Identify existing conventions.
- Reuse existing patterns whenever possible.

Never begin implementation before understanding how the repository already solves similar problems.

---

# Learn Before Extending

When working inside an unfamiliar area:

Read existing code first.

Identify the dominant patterns.

Follow them.

Avoid introducing a different style unless explicitly requested.

Consistency is usually more valuable than improvement.

---

# Respect Existing Architecture

The repository architecture already represents previous design decisions.

Do not redesign the project while implementing unrelated functionality.

Avoid introducing new architectural concepts during feature development.

Architecture changes require explicit justification.

---

# Prefer Evolution Over Reinvention

When existing code almost solves the problem:

Extend it.

Do not create parallel implementations.

Do not duplicate existing concepts with different names.

Evolution is preferred over replacement.

---

# Locality

Code that changes together should live together.

Keep related functionality physically close.

Avoid scattering one feature across multiple unrelated locations.

When uncertain where new code belongs, choose the location nearest to the existing behaviour.

---

# Predictability

Developers should be able to predict where code lives.

Avoid surprising directory structures.

Avoid surprising abstractions.

Avoid surprising behaviour.

If another developer cannot reasonably guess where new code was added, reconsider the design.

---

# Simplicity

Prefer the simplest solution that completely solves the problem.

Avoid solving hypothetical future requirements.

Avoid unnecessary abstraction.

Avoid unnecessary configuration.

Avoid unnecessary flexibility.

Simple systems evolve more easily.

---

# Explicitness

Code should make behaviour obvious.

Prefer explicit data flow.

Prefer explicit dependencies.

Prefer explicit configuration.

Avoid hidden behaviour.

Avoid "magic".

---

# Consistency

If multiple valid solutions exist, prefer the one already used by the repository.

The repository should feel like it was written by one developer.

Avoid introducing stylistic variations.

Consistency reduces cognitive load.

---

# Introducing Abstractions

Do not create abstractions pre-emptively.

Create abstractions only after a repeated pattern clearly exists.

Duplicating twenty lines twice is often preferable to introducing an unnecessary abstraction.

Every abstraction should remove complexity rather than introduce it.

---

# Dependencies

Treat every dependency as permanent.

Before introducing one, ask:

- Can the standard library solve this?
- Can an existing dependency solve this?
- Is the new dependency justified by its long-term value?

Avoid adding dependencies for convenience alone.

---

# Refactoring

Refactoring should improve the repository without changing behaviour.

Avoid combining large refactorings with new functionality.

Prefer incremental improvements.

Avoid rewriting code simply because it could be cleaner.

---

# Testing

Tests should validate behaviour.

Avoid testing implementation details.

New behaviour requires tests.

Bug fixes require regression tests.

When changing behaviour, update existing tests before creating new ones whenever appropriate.

---

# Documentation

Documentation should evolve with the repository.

Update documentation when architecture or behaviour changes.

Avoid duplicating information across multiple documents.

Keep documentation focused.

---

# Generated Code

Treat generated files as read-only.

Modify the source.

Regenerate the output.

Never manually edit generated artifacts.

---

# Performance

Write correct code first.

Measure before optimising.

Avoid introducing complexity for hypothetical performance improvements.

Performance work should be driven by evidence.

---

# Security

Treat external input as untrusted.

Validate input.

Fail safely.

Avoid exposing sensitive information.

Prefer secure defaults.

---

# When Unsure

If multiple reasonable solutions exist:

1. Choose the simplest.
2. Choose the most consistent.
3. Choose the most predictable.
4. Choose the one requiring the smallest architectural change.

When still uncertain, preserve the existing implementation style.

---

# Common Anti-Patterns

Avoid:

- Premature optimisation
- Premature abstraction
- Overengineering
- Reinventing existing functionality
- Mixing architectural styles
- Large unrelated refactorings
- Hidden side effects
- Framework-specific business logic
- Copying code from unrelated projects without adaptation

---

# Final Rule

Every implementation should feel like it naturally belongs in this repository.

The best contribution is the one that becomes indistinguishable from the original codebase.