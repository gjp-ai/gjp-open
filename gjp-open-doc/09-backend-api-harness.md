# Backend API Harness

This file is the backend API harness map for `gjp-open-api-boot`.

Use this map when generating or modifying the Spring Boot public API. The detailed API contract remains in [04-api-reference.md](04-api-reference.md) and `api/`; implementation rules live here in `backend-api/`.

## Backend API Structure

| File | Purpose |
| --- | --- |
| [backend-api/00-overview.md](backend-api/00-overview.md) | Backend project overview, constraints, and read order. |
| [backend-api/01-coding-rules.md](backend-api/01-coding-rules.md) | Spring Boot coding rules and mandatory patterns. |
| [backend-api/02-testing-quality.md](backend-api/02-testing-quality.md) | Backend test and coverage rules. |
| [backend-api/_template.md](backend-api/_template.md) | Template for future backend API harness docs. |

## Claude Code Rule

Claude Code should use the workspace [CLAUDE.md](../CLAUDE.md) and this map instead of duplicated project-local instruction files.
