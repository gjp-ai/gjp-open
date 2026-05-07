# iOS Testing

## Test Types

| Type | Tooling |
| --- | --- |
| Unit tests | XCTest. |
| API tests | URLProtocol stubs or a lightweight local mock server. |
| View model tests | XCTest with async expectations. |
| UI tests | XCUITest. |
| Static checks | Swift compiler warnings, SwiftLint if adopted. |

## Expected Commands

After `gjp-open-ios` exists:

```sh
xcodebuild test -scheme <SchemeName> -destination 'platform=iOS Simulator,name=iPhone 16'
```

If the project separates unit and UI schemes, document both commands in `gjp-open-ios/AGENTS.md`.

## Required Test Targets

- API client tests for each endpoint.
- ViewModel tests for each screen.
- XCUITest coverage for tab navigation and major state rendering.
- Media player smoke tests after media features exist.
