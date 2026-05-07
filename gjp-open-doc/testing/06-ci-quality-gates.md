# CI Quality Gates

## Pull Request Gate

Every mobile pull request should run:

- Formatting check.
- Static analysis/lint.
- Unit tests.
- API contract tests.
- Build or compile check.

## Scheduled Or Release Gate

Before release, run:

- Android emulator UI tests.
- iOS simulator UI tests.
- Manual smoke tests on at least one Android device and one iOS device when available.
- Media playback checks.
- File handoff checks.
- Accessibility spot checks.

## Failure Policy

- Failing unit tests block merge.
- Failing API contract tests block merge.
- Failing compile/build blocks merge.
- Failing UI automation blocks release unless explicitly documented as flaky with an owner and follow-up.

## Project AGENTS Updates

When `gjp-open-android` and `gjp-open-ios` are created, each project must add its own `AGENTS.md` with exact test commands, emulator/simulator assumptions, and known slow/flaky tests.
