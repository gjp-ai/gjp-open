# Audio API

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/audios` | Paged audio list. |
| `GET` | `/api/open/audios/all` | Full audio list (no pagination). |
| `GET` | `/api/open/audios/{id}` | Audio detail. |
| `GET` | `/api/open/audios/view/{filename}` | Raw streamable audio response. |
| `GET` | `/api/open/audios/cover-images/{filename}` | Raw cover image response. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for audio. |

## Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `title` | string |
| `description` | string |
| `subtitle` | string |
| `artist` | string |
| `url` | string |
| `coverImageUrl` | string |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Mobile Notes

- Send `isActive=true` for public list screens.
- The stream endpoint supports byte range requests.
- Background playback is optional after MVP.
- Show clear loading and playback error states.
