# Stack And Repository

## Recommended Stack

There are two valid mobile directions:

| Direction | When to use |
| --- | --- |
| React Native with Expo | Use when the goal is one shared cross-platform mobile codebase. |
| Native Android + native iOS | Use when creating separate `gjp-open-android` and `gjp-open-ios` projects. |

For the user's current direction, prefer native Android and native iOS:

- `gjp-open-android`: Kotlin + Jetpack Compose.
- `gjp-open-ios`: Swift + SwiftUI.

React Native with Expo remains a good alternative if the project later chooses one shared app.

Expo alternative reasons:

- The existing public website already uses React and TypeScript.
- React Native supports Android and iOS from one codebase.
- Expo provides app setup, development builds, native module management, and build/distribution tooling.
- Official React Native documentation recommends using a framework such as Expo for new React Native apps.

Avoid pinning versions in this document. Choose current stable versions when creating the mobile repository and record them in the mobile app README.

## Proposed Repository

Recommended shared-codebase project name if Expo is chosen:

```text
gjp-open-mobile-expo
```

Recommended native project names:

```text
gjp-open-android
gjp-open-ios
```

Recommended initial structure:

```text
src/
├── app/                    # App shell, navigation, providers
├── features/               # Feature screens by domain
│   ├── websites/
│   ├── questions/
│   ├── articles/
│   ├── images/
│   ├── videos/
│   ├── audios/
│   └── files/
├── shared/
│   ├── api/                # API client, endpoint functions, response types
│   ├── components/         # Shared UI components
│   ├── hooks/              # Reusable hooks
│   ├── i18n/               # Translation registry and hooks
│   ├── storage/            # Persisted language/theme/cache helpers
│   ├── theme/              # Tokens and theme provider
│   └── utils/              # Small pure utilities
└── test/                   # Test helpers
```

This mirrors the current web project shape without copying browser-only assumptions. Native project structures are documented in [05-android-native.md](05-android-native.md) and [06-ios-native.md](06-ios-native.md).
