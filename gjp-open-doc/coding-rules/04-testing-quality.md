# Testing And Quality Rules

Also read [../08-testing-strategy.md](../08-testing-strategy.md) before generating mobile code.

## Testing Rules

- Add unit tests for API client parameter building and response handling.
- Add unit tests for view models/state holders with loading, success, empty, error, refresh, and load-more behavior.
- Add automated UI tests for navigation and important empty/error states.
- Add API contract tests for canonical request parameters and response parsing.
- Manual QA must cover Android and iOS before release.

## Quality Commands

The exact commands will be finalized in each mobile repository. Native gates are documented in [../testing/04-android-testing.md](../testing/04-android-testing.md) and [../testing/05-ios-testing.md](../testing/05-ios-testing.md).

```sh
./gradlew testDebugUnitTest lintDebug
xcodebuild test -scheme <SchemeName> -destination 'platform=iOS Simulator,name=iPhone 16'
```

If a command is not available yet, document the reason in the mobile README.

## Review Checklist

- [ ] API calls use canonical query parameters.
- [ ] Public list calls include `isActive=true`.
- [ ] New visible text is translated in EN and ZH.
- [ ] Loading, empty, error, retry, and refresh states are present.
- [ ] Screen works in light and dark themes.
- [ ] Screen works with larger OS text.
- [ ] External links and media/file URLs open safely.
- [ ] Tests cover changed business logic or shared behavior.
- [ ] API contract tests cover changed endpoint behavior.
- [ ] UI automation covers changed critical journeys where practical.
- [ ] No secrets or local machine paths are committed.
