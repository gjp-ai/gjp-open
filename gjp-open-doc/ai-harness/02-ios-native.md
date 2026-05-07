# iOS Native Harness

Use this harness for `gjp-open-ios`.

## Recommended Stack

- Swift.
- SwiftUI for UI.
- Swift Concurrency with `async`/`await`.
- URLSession for HTTP unless a dependency is intentionally chosen.
- Codable for JSON.
- Observation or ObservableObject for state, depending on selected iOS target.
- UserDefaults for simple language/theme settings.
- AVKit / AVFoundation for video and audio playback.
- XCTest for unit and UI tests.

## Project Shape

```text
gjp-open-ios/
├── App/                  # App entry, navigation, app state
├── Features/             # Feature folders by domain
│   ├── Articles/
│   ├── Websites/
│   └── ...
├── Shared/
│   ├── API/
│   ├── Models/
│   ├── UI/
│   ├── Theme/
│   ├── I18n/
│   └── Storage/
└── Tests/
```

## Generation Rules

- Use SwiftUI navigation and tab structure for the first release.
- Keep API models and endpoint clients in `Shared/API` and `Shared/Models`.
- Keep feature screens in `Features/{Resource}`.
- Model loading, refreshing, empty, error, and content states explicitly.
- Use `isActive=true` on public list calls.
- Use canonical API query names.
- Follow iOS testing rules in `testing/05-ios-testing.md`.
- Do not store API secrets, certificates, provisioning profiles, or signing material in the repository.

## First Build Target

The first generated iOS project should:

- Build in Xcode.
- Open to tab navigation.
- Persist language/theme choice.
- Fetch `/open/app-settings`.
- Include one complete list screen as a vertical slice before copying the pattern to all resources.
- Include unit tests and at least one XCUITest smoke test for the vertical slice.
