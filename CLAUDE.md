# GJP Open Claude Code Workspace Guide

Claude Code should use this file as the workspace entry point for all `gjp-open` projects.

## First Step

Read [AGENTS.md](AGENTS.md), then choose the project path below based on the task.

## Project Router

| Project / Task | Read |
| --- | --- |
| Workspace-wide task | [AGENTS.md](AGENTS.md) |
| Public API implementation | [gjp-open-doc/09-backend-api-harness.md](gjp-open-doc/09-backend-api-harness.md) |
| Public API contract | [gjp-open-doc/04-api-reference.md](gjp-open-doc/04-api-reference.md) |
| Public website implementation | [gjp-open-web-react/AGENTS.md](gjp-open-web-react/AGENTS.md) |
| Documentation work | [gjp-open-doc/README.md](gjp-open-doc/README.md) |
| Mobile app planning or generation | [gjp-open-doc/07-ai-generation-harness.md](gjp-open-doc/07-ai-generation-harness.md) |
| Native Android app | [gjp-open-doc/ai-harness/01-android-native.md](gjp-open-doc/ai-harness/01-android-native.md) |
| Native iOS app | [gjp-open-doc/ai-harness/02-ios-native.md](gjp-open-doc/ai-harness/02-ios-native.md) |
| Testing strategy | [gjp-open-doc/08-testing-strategy.md](gjp-open-doc/08-testing-strategy.md) |

## Project Commands

| Project | Verification |
| --- | --- |
| `gjp-open-api-boot` | `./mvnw test -Dspring.profiles.active=test` |
| `gjp-open-web-react` | `npm run check` |
| `gjp-open-android` | `./gradlew testDebugUnitTest lintDebug` after project creation. |
| `gjp-open-ios` | `xcodebuild test` with the selected scheme after project creation. |

## Rules

- Do not bulk-read every document. Start from the relevant map, then open focused files as needed.
- Keep generated code aligned with `gjp-open-doc` and project-local harness files.
- Update docs before changing shared behavior or public API contracts.
- Do not commit secrets, signing files, local environment files, or credentials.
- Preserve public EN/ZH behavior for user-facing work.
