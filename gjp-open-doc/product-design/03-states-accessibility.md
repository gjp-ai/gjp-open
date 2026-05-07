# States And Accessibility

## State Design

Every content screen needs these states:

- Initial loading skeleton.
- Refreshing.
- List with content.
- Empty state for no results.
- Error state with retry.
- End of list.

## Accessibility

- Support dynamic font scaling.
- Keep interactive targets at least 44 x 44 points.
- Do not rely on color alone for selected tabs, tags, or errors.
- Provide screen reader labels for icon-only actions.
- Preserve keyboard/focus behavior where Android/iOS accessibility tools depend on it.

## Empty And Error Copy

Use simple, action-oriented copy:

| State | Example |
| --- | --- |
| Empty list | No items found. |
| Empty search | No results for this search. |
| API error | Could not load content. |
| Media error | Could not play this media. |
| Retry action | Retry |

Copy should be bilingual through the same i18n system as the rest of the app.
