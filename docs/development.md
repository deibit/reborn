# Development Workflow

## Purpose

This document describes the expected development workflow for projects based on Reborn.

It focuses on day-to-day development practices rather than architecture or coding conventions.

The objective is to keep development predictable, reproducible and consistent across the repository.

---

# Development Philosophy

Development should be incremental.

Small, focused changes are preferred over large rewrites.

Every commit should leave the repository in a working state whenever practical.

Avoid introducing unrelated changes while implementing a feature.

---

# Development Environment

Projects based on Reborn use modern Python tooling.

Python dependencies are managed with **uv**.

Do not use:

- pip
- virtualenv
- python -m venv

Prefer:

```bash
uv sync
uv add
uv remove
uv run
```

The frontend uses the standard package manager selected by the project.

---

# Daily Workflow

A typical development cycle should follow this order:

1. Understand the problem.
2. Review existing implementations.
3. Design the smallest reasonable change.
4. Implement the solution.
5. Run formatting tools.
6. Run static analysis.
7. Run relevant tests.
8. Update documentation when required.
9. Commit only related changes.

Do not skip validation steps.

---

# Before Writing Code

Before implementing new functionality:

- Read the surrounding code.
- Identify existing patterns.
- Search for reusable components.
- Avoid introducing duplicate behaviour.

Implementation should begin only after understanding the existing design.

---

# Making Changes

Prefer modifying existing code over introducing parallel implementations.

Keep changes focused.

Avoid mixing refactoring with new functionality unless necessary.

When a refactoring is required, keep it as small as practical.

---

# Dependencies

Before adding a dependency:

- Check whether the standard library is sufficient.
- Check whether an existing dependency already solves the problem.
- Consider the long-term maintenance cost.

Dependencies should solve meaningful problems rather than provide small conveniences.

---

# Validation

Every change should be validated before completion.

Validation may include:

- formatting
- linting
- type checking
- automated tests
- manual verification

Run only the validation steps relevant to the change.

---

# Documentation

Documentation is part of the implementation.

Update documentation whenever behaviour, architecture or workflows change.

Do not leave documentation inconsistent with the codebase.

---

# Generated Files

Do not manually edit generated artifacts.

Modify the source.

Regenerate the output.

---

# Version Control

Commits should represent one logical change.

Avoid mixing unrelated improvements.

Write commit messages that describe intent rather than implementation details.

Small commits are preferred over large batches of unrelated changes.

---

# Pull Requests

A pull request should have a clear objective.

Before submitting:

- ensure the project builds successfully
- ensure relevant tests pass
- remove temporary debugging code
- remove commented-out code
- update documentation if necessary

Review your own changes before requesting review.

---

# Temporary Code

Temporary code should remain temporary.

Before considering work complete, remove:

- debug prints
- commented-out code
- experimental implementations
- unused variables
- dead code

The repository should not accumulate development artifacts.

---

# Continuous Improvement

Leave the repository slightly better than you found it.

Small improvements accumulate over time.

Avoid large clean-up efforts by maintaining quality continuously.

---

# Final Rule

Development is not finished when the code works.

Development is finished when the implementation naturally fits the repository.