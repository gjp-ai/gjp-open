# Articles API

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/articles` | Paged article list. |
| `GET` | `/api/open/articles/{id}` | Article detail. |
| `GET` | `/api/open/articles/cover-images/{filename}` | Raw cover image response. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `title` | string | Canonical search field for articles. |

## List Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `title` | string |
| `summary` | string |
| `originalUrl` | string |
| `sourceName` | string |
| `coverImageOriginalUrl` | string or null |
| `coverImageUrl` | string or null |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Detail Adds

| Field | Type |
| --- | --- |
| `content` | string |

## Mobile Notes

- Send `isActive=true` for public list screens.
- Use `coverImageUrl` for app-hosted image loading.
- Open `originalUrl` in the system browser.
- Render `content` through a safe HTML/rich-text renderer if markup is present.
