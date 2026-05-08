# Backend API Overview

## Project

`gjp-open-api-boot` is the GJP AI public Spring Boot API.

## Runtime

| Item | Value |
| --- | --- |
| Java | 21 |
| Spring Boot | 3.4.5 |
| Database | MySQL 8 in production, H2 in tests |
| Port | 8084 |
| Context path | `/api/` |
| Local base URL | `http://localhost:8084/api` |

## Core Constraints

- Public API only.
- No authentication.
- No authorization annotations such as `@PreAuthorize`.
- GET-only public endpoints.
- Mutations belong in admin API projects, not `gjp-open-api-boot`.
- Shares public content tables with admin API.
- Public list responses should use pagination.
- Test and coverage gates must pass before handoff.

## Read Order For Backend Work

1. [../04-api-reference.md](../04-api-reference.md)
2. Relevant resource file under `../api/`
3. [01-coding-rules.md](01-coding-rules.md)
4. [02-testing-quality.md](02-testing-quality.md)
5. Local `gjp-open-api-boot/tooling/docs/guide/CODING_STANDARDS.md` if implementation details are needed.
