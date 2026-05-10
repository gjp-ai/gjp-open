# Articles API

## Endpoints

### 1. Paged Article List
`GET /api/open/articles`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `title` | string | Canonical search field for articles. |
| `isIncludeContent` | boolean | Set to `true` to include the `content` field. Defaults to `false`. |

**Response Payload**
Returns a `PaginatedResponse` where `data.content` is an array of [Article Response Items](#article-response-item). If `isIncludeContent` is false, the `content` field inside each item is an empty string.

### 2. Full Article List (Non-Paginated)
`GET /api/open/articles/all`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `title` | string | Canonical search field for articles. |
| `updatedAfter` | string | Filter data updated after this time (incremental sync).<br>Example: `2024-05-10T15:30:00Z` or `2024-05-10 15:30:00` |

**Response Payload**
Returns an array of [Article Response Items](#article-response-item) directly in the `data` field (no pagination envelope). The `content` field is always fully populated.

### 3. Article Detail
`GET /api/open/articles/{id}`

**Response Payload**
Returns a single [Article Response Item](#article-response-item) in the `data` field. The `content` field is fully populated.

### 4. Cover Image
`GET /api/open/articles/cover-images/{filename}`
Raw cover image response.

---

## Article Response Item

| Field | Type | Notes |
| --- | --- | --- |
| `id` | string | |
| `title` | string | |
| `summary` | string | |
| `content` | string | Empty string in paged list unless requested. Full text in `/all` and `/{id}` endpoints. |
| `originalUrl` | string | |
| `sourceName` | string | |
| `coverImageOriginalUrl` | string or null | |
| `coverImageUrl` | string or null | Computed full URL. |
| `tags` | string | |
| `lang` | `EN` or `ZH` | |
| `displayOrder` | number | |
| `updatedAt` | string | |

## Mobile Notes

- Send `isActive=true` for public list screens.
- Use `coverImageUrl` for app-hosted image loading.
- Open `originalUrl` in the system browser.
- Render `content` through a safe HTML/rich-text renderer if markup is present.
