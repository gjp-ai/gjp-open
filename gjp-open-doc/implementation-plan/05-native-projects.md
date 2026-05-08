# Native Project Creation Plan

Use this plan when creating separate native apps:

```text
gjp-open-android
gjp-open-ios
```

## Android First Steps

- Create `gjp-open-android`.
- Add `AGENTS.md` with Android-specific commands.
- Configure Kotlin, Compose, Material 3, Navigation Compose, and tests.
- Add app shell and bottom navigation.
- Add API client foundation.
- Implement Websites as the first vertical slice.

## iOS First Steps

- Create `gjp-open-ios`.
- Add `AGENTS.md` with iOS-specific scheme and test commands.
- Configure SwiftUI app shell and tab navigation.
- Add API client foundation.
- Implement Websites as the first vertical slice.

## Cross-Platform Rule

Do not build all Android features before iOS starts. Build one complete vertical slice on both platforms, compare behavior, then repeat the pattern for the remaining features.
