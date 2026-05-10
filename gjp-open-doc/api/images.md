# Images API

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/images` | Paged image list. |
| `GET` | `/api/open/images/all` | Full image list (no pagination). |
| `GET` | `/api/open/images/{id}` | Image detail. |
| `GET` | `/api/open/images/view/{filename}` | Raw image response. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for images. |

## Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `name` | string |
| `altText` | string |
| `url` | string |
| `thumbnailUrl` | string |
| `originalUrl` | string |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Mobile Notes

- Send `isActive=true` for public list screens.
- Use `thumbnailUrl` in grids.
- Use `url` or `originalUrl` in preview depending on quality/performance needs.
- Use `altText` as the accessibility label when present.
