# Android Native Harness

Use this harness for `gjp-open-android`.

## Recommended Stack

- Kotlin.
- Jetpack Compose for UI.
- Material 3 components.
- Navigation Compose.
- Retrofit or Ktor client for HTTP.
- Kotlinx Serialization or Moshi for JSON.
- Coil for image loading.
- DataStore for language/theme/settings persistence.
- ExoPlayer / Media3 for video and audio playback.
- JUnit, MockK or Mockito, and Compose UI tests.

## Project Shape

```text
app/src/main/java/org/ganjp/open/
├── app/                  # MainActivity, app shell, navigation
├── feature/              # Feature packages by domain
│   ├── articles/
│   ├── websites/
│   └── ...
├── shared/
│   ├── api/
│   ├── model/
│   ├── ui/
│   ├── theme/
│   ├── i18n/
│   └── storage/
└── test/
```

## Generation Rules

- Use a single Activity Compose app unless a native integration requires otherwise.
- Keep API DTOs in `shared/api` or `shared/model`.
- Keep feature UI in `feature/{resource}`.
- Use ViewModels for screen state.
- Model loading, refreshing, empty, error, and content states explicitly.
- Use `isActive=true` on public list calls.
- Use canonical API query names.
- Follow Android testing rules in `testing/04-android-testing.md`.
- Do not store API secrets or signing material in the repository.

## First Build Target

The first generated Android project should:

- Build in Android Studio.
- Open to bottom navigation.
- Persist language/theme choice.
- Fetch `/open/app-settings`.
- Include one complete list screen as a vertical slice before copying the pattern to all resources.
- Include unit tests and at least one Compose UI smoke test for the vertical slice.
