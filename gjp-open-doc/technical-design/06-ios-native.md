# Native iOS Technical Design

## Project

```text
gjp-open-ios
```

## Stack

- Swift.
- SwiftUI.
- Swift Concurrency with `async`/`await`.
- URLSession.
- Codable.
- UserDefaults for simple persisted language/theme settings.
- AVKit / AVFoundation for media.
- XCTest.

## Folder Structure

```text
gjp-open-ios/
├── App/
├── Features/
│   ├── Articles/
│   ├── Websites/
│   ├── Questions/
│   ├── Images/
│   ├── Videos/
│   ├── Audios/
│   └── Files/
└── Shared/
    ├── API/
    ├── Models/
    ├── UI/
    ├── Theme/
    ├── I18n/
    └── Storage/
```

## State Model

Each screen should expose an explicit state:

```swift
enum ScreenState<Value> {
    case loading
    case content(Value)
    case empty
    case error(String)
}
```

## API Rules

- Centralize API calls in `Shared/API`.
- Use `isActive=true` for public list requests.
- Use canonical query names from the API docs.
- Map API envelope errors before they reach SwiftUI views.

## First Vertical Slice

Build Websites first as the reference feature:

- API models.
- API client.
- View model.
- List screen.
- Loading, empty, error, refresh, and content states.
- EN/ZH and theme behavior.
- Unit tests for API client and view model.
- XCUITest smoke test for navigation and list rendering.
