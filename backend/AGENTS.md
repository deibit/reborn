# Backend Instructions

Follow the repository-wide instructions in `../AGENTS.md`.

## Scope

These instructions apply to files inside `backend/`.

## Backend Rules

- Use Python 3.14.
- Use FastAPI, SQLModel and Alembic.
- Use `uv` for dependency management and command execution.
- Keep routes thin.
- Place business behaviour in services.
- Keep persistence logic in repositories.
- Use API schemas instead of exposing persistence models directly.
- Raise application exceptions from business code, not HTTP exceptions.
- Add or update tests for behavioural changes.
- Do not introduce new architectural layers without a demonstrated need.