# Mobile Quality Gates

## Android

Expected commands after `gjp-open-android` exists:

```sh
./gradlew testDebugUnitTest
./gradlew lintDebug
./gradlew connectedDebugAndroidTest
./gradlew assembleDebug
```

Add project-specific commands to `gjp-open-android/AGENTS.md` after the project is created.

For local fast checks, `testDebugUnitTest` and `lintDebug` are the minimum. Run `connectedDebugAndroidTest` in CI or before release if no emulator is available locally.

## iOS

Expected commands after `gjp-open-ios` exists:

```sh
xcodebuild test -scheme <SchemeName> -destination 'platform=iOS Simulator,name=iPhone 16'
```

Add the exact scheme and destination to `gjp-open-ios/AGENTS.md` after the project is created.

If unit and UI tests are separated into different schemes or test plans, document both commands.

## Manual Smoke Tests

- App launches without login.
- Language toggle works and persists.
- Theme toggle works and persists.
- `/open/app-settings` loads.
- One list screen can refresh and load more.
- Empty and API error states are visible and recoverable.
- Article detail opens from article list.
- Image, video, audio, and file handoff/playback work once those features exist.
