# Cross-Project Sync Harness

Android and iOS should implement the same product behavior even when native code structure differs.

## Source Of Truth

| Concern | Source |
| --- | --- |
| User-facing requirements | `requirements/` |
| Screen behavior | `product-design/` |
| API contract | `api/` |
| Platform architecture | `technical-design/05-android-native.md` and `technical-design/06-ios-native.md` |
| Coding rules | `coding-rules/` |
| Testing strategy | `testing/` |

## Sync Rules

- If a feature exists on Android, create the matching iOS issue/task unless intentionally deferred.
- Keep route/tab names and visible labels aligned through EN/ZH translations.
- Keep API request parameters identical across platforms.
- Keep loading, empty, error, retry, refresh, and pagination behavior aligned.
- Keep unit, API contract, and UI automation coverage expectations aligned across platforms.
- Update docs before changing cross-platform behavior.

## API Compatibility Watchlist

- Do not inherit `search`/`tag` ambiguity from the current web wrapper.
- Use canonical filters: `name`, `title`, `question`, `tags`, `lang`, `isActive=true`.
- Media/file endpoints return raw responses, not JSON envelopes.
