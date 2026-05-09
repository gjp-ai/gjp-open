# Native Android Technical Design

## Project

```text
gjp-open-android
```

## Stack

- Kotlin.
- Jetpack Compose.
- Material 3.
- Navigation Compose.
- Retrofit or Ktor client.
- Kotlinx Serialization or Moshi.
- Coil for image loading.
- DataStore for persisted language/theme/settings.
- Media3 for audio and video.

## Package Structure

```text
org.ganjp.open/
├── app/
├── feature/
│   ├── articles/
│   ├── websites/
│   ├── questions/
│   ├── images/
│   ├── videos/
│   ├── audios/
│   └── files/
└── shared/
    ├── api/
    ├── model/
    ├── ui/
    ├── theme/
    ├── i18n/
    └── storage/
```

## State Model

Each screen should expose an explicit state:

```kotlin
sealed interface ScreenState<out T> {
    data object Loading : ScreenState<Nothing>
    data class Content<T>(val data: T) : ScreenState<T>
    data object Empty : ScreenState<Nothing>
    data class Error(val message: String) : ScreenState<Nothing>
}
```

## API Rules

- Centralize API calls in `shared/api`.
- Use `isActive=true` for public list requests.
- Use canonical query names from the API docs.
- Map API envelope errors before they reach Composables.

## First Vertical Slice

Build Websites first as the reference feature:

- API DTOs.
- Repository/client.
- ViewModel.
- List screen.
- Loading, empty, error, refresh, and content states.
- EN/ZH and theme behavior.
- Unit tests for API, repository, and ViewModel.
- Compose UI smoke test for navigation and list rendering.
