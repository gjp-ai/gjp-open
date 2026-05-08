# App Settings API

## Endpoint

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/app-settings` | Returns public app settings. |

## Response Item

| Field | Type |
| --- | --- |
| `name` | string |
| `value` | string |
| `lang` | string |

## Mobile Notes

- Use this endpoint for public configurable labels, tags, and settings.
- Only public settings are returned by the API.
- Cache the latest successful response so the app can start with known settings while refreshing.
