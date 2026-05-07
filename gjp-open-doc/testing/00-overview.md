# Testing Overview

## Testing Principles

- Tests are required for generated mobile code, not optional follow-up work.
- Prefer fast unit tests for business logic and API mapping.
- Use integration/API contract tests to protect request parameters and response parsing.
- Use automated UI tests for critical public user journeys.
- Keep manual QA focused on device behavior that automation cannot fully cover, such as media playback and OS file handoff.

## Test Pyramid

```text
Many     Unit tests
Some     API contract and integration tests
Few      UI automation tests
Few      Manual smoke tests on real devices
```

## Minimum Coverage Expectations

| Area | Expectation |
| --- | --- |
| API client | Unit or contract tests for every endpoint function. |
| View models / state holders | Unit tests for loading, success, empty, error, refresh, and load-more states. |
| Data mapping | Unit tests for envelope parsing, pagination, nullable media fields, and invalid responses. |
| UI | Automated tests for primary navigation and one happy/error path per major feature. |
| Release | Android and iOS smoke tests before release. |

Coverage percentage targets should be configured after the native projects are created. The first target should be practical but enforced; raise it as the codebase stabilizes.
