# Websites API

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/websites` | Paged website list. |
| `GET` | `/api/open/websites/{id}` | Website detail. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for websites. |

## Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `name` | string |
| `description` | string |
| `url` | string |
| `logoUrl` | string |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Mobile Notes

- Send `isActive=true` for public list screens.
- Open `url` in the system browser.
- Use `logoUrl` for card thumbnails when present.
