# Native iOS Coding Rules

- Use Swift and SwiftUI for app code.
- Keep SwiftUI views focused on rendering; loading and API coordination belongs in view models or services.
- Keep API models in `Shared/Models` or `Shared/API`.
- Use explicit screen state enums for loading, content, empty, and error states.
- Use localization resources for visible EN/ZH text.
- Use theme tokens instead of hardcoded colors.
- Use AsyncImage only when its behavior is enough; add a dedicated image loader/cache if needed.
- Use AVKit / AVFoundation for video and audio.
- Add XCTest coverage for API clients and view models.
- Add UI tests for primary navigation and important screen states.
