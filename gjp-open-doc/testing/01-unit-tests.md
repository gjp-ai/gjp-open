# Unit Tests

## Required Unit Test Areas

- API URL and query parameter building.
- API envelope parsing.
- API error mapping.
- Pagination state.
- Pull-to-refresh state.
- Load-more state.
- Language selection and persistence.
- Theme selection and persistence.
- Tag filtering and search parameter behavior.
- View model state transitions.

## Required Cases Per List Feature

For each resource list, test:

- Initial load success with content.
- Initial load success with empty content.
- API envelope error.
- HTTP/network error.
- Invalid language handling where applicable.
- Refresh success.
- Refresh failure while previous content exists.
- Load-more success.
- Load-more no-op when already at end.

## Naming

Use readable test names that describe behavior and condition.

Examples:

- Android: `should_loadWebsites_when_apiReturnsContent`
- iOS: `testLoadWebsitesWhenAPIReturnsContent`

## Mocking Rules

- Mock network boundaries, not pure mappers.
- Keep sample JSON fixtures close to API tests.
- Do not mock the view model under test.
- Prefer deterministic fake repositories for state tests.
