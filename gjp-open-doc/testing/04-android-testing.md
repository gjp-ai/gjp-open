# Android Testing

## Test Types

| Type | Tooling |
| --- | --- |
| Unit tests | JUnit, MockK or Mockito, kotlinx-coroutines-test. |
| API tests | MockWebServer or Ktor MockEngine, plus JSON fixtures. |
| Compose UI tests | AndroidX Compose UI Test. |
| Instrumented tests | AndroidJUnitRunner on emulator. |
| Static checks | Android Lint, Kotlin compiler warnings, detekt if adopted. |

## Expected Commands

After `gjp-open-android` exists:

```sh
./gradlew testDebugUnitTest
./gradlew lintDebug
./gradlew connectedDebugAndroidTest
./gradlew assembleDebug
```

If emulator tests are too slow for every local run, keep `testDebugUnitTest` and `lintDebug` as the minimum local gate, and run `connectedDebugAndroidTest` in CI or before release.

## Required Test Targets

- API client tests for each endpoint.
- ViewModel tests for each screen.
- Compose tests for navigation and major state rendering.
- Media player smoke tests after media features exist.
