# Videos API

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/videos` | Paged video list. |
| `GET` | `/api/open/videos/all` | Full video list (no pagination). |
| `GET` | `/api/open/videos/{id}` | Video detail. |
| `GET` | `/api/open/videos/view/{filename}` | Raw streamable video response. |
| `GET` | `/api/open/videos/cover-images/{filename}` | Raw cover image response. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for videos. |

## Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `title` | string |
| `description` | string |
| `url` | string |
| `coverImageUrl` | string |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Mobile Notes

- Send `isActive=true` for public list screens.
- The stream endpoint supports byte range requests.
- Use `coverImageUrl` for list cards.
- Player screens must handle buffering and playback errors.
