# Images API

## Endpoints

### 1. Paged Image List
`GET /api/open/images`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for images. |

**Response Payload**
Returns a `PaginatedResponse` where `data.content` is an array of [Image Response Items](#image-response-item).

### 2. Full Image List (Non-Paginated)
`GET /api/open/images/all`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for images. |
| `updatedAfter` | string | Filter data updated after this time (incremental sync).<br>Example: `2024-05-10T15:30:00Z` or `2024-05-10 15:30:00` |

**Response Payload**
Returns an array of [Image Response Items](#image-response-item) directly in the `data` field (no pagination envelope).

### 3. Image Detail
`GET /api/open/images/{id}`

**Response Payload**
Returns a single [Image Response Item](#image-response-item) in the `data` field.

### 4. View Image
`GET /api/open/images/view/{filename}`
Raw image response.

---

## Image Response Item

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
