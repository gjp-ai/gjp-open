# UI, State, i18n, And Media Rules

## UI Rules

- Prefer native-feeling layout and controls over web-style dense pages.
- Every screen must handle loading, refreshing, empty, error, and content states.
- Repeated cards must have stable dimensions and predictable text truncation.
- All touch targets must be at least 44 x 44 points.
- Icon-only buttons need accessibility labels.
- Images need useful alt/accessibility labels when the platform supports them.
- Avoid text overlap when OS font scaling is increased.
- Verify both light and dark theme for every new screen.

## State Rules

- Store app-wide language, theme, and theme color in providers.
- Persist language/theme locally.
- Keep remote content cache separate from UI settings.
- Avoid global state for simple screen-local interactions.
- Reset pagination when filters, search, language, or sort changes.

## i18n Rules

- No hardcoded user-facing strings in screens or components.
- Translation keys should be feature scoped, for example `articles.empty`.
- Use the same key in all languages.
- If a new screen is added, add all visible copy in EN and ZH before merge.

## Media Rules

- Use thumbnail URLs in lists when available.
- Use full URLs only in preview/player screens.
- Video and audio players must show loading and error states.
- File actions should hand off to OS/browser behavior.
- Do not download and store large media files in MVP.
