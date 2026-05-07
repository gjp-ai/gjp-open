# Testing Strategy

This file is the testing strategy map.

Testing is a first-class part of the mobile plan. Details live under `testing/` so unit tests, API contract tests, UI automation, and platform-specific commands can evolve without becoming one large document.

## Testing Structure

| File | Purpose |
| --- | --- |
| [testing/00-overview.md](testing/00-overview.md) | Testing principles, test pyramid, and coverage expectations. |
| [testing/01-unit-tests.md](testing/01-unit-tests.md) | Unit testing scope and required cases. |
| [testing/02-api-contract-tests.md](testing/02-api-contract-tests.md) | API client and public API contract testing. |
| [testing/03-ui-automation.md](testing/03-ui-automation.md) | Automated UI testing and smoke flows. |
| [testing/04-android-testing.md](testing/04-android-testing.md) | Native Android test harness. |
| [testing/05-ios-testing.md](testing/05-ios-testing.md) | Native iOS test harness. |
| [testing/06-ci-quality-gates.md](testing/06-ci-quality-gates.md) | CI gates and release readiness checks. |
| [testing/_template.md](testing/_template.md) | Template for future testing docs. |

## How To Add Testing Docs

1. Add a focused file under `testing/`.
2. Use one file per test layer, platform, feature test plan, or quality gate.
3. Link new files in the Testing Structure table above.
4. Keep this root file as the testing map.
