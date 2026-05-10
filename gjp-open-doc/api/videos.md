# Videos API

## Endpoints

### 1. Paged Video List
`GET /api/open/videos`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for videos (maps to the `title` field in the response). |

**Response Payload**
Returns a `PaginatedResponse` where `data.content` is an array of [Video Response Items](#video-response-item).

### 2. Full Video List (Non-Paginated)
`GET /api/open/videos/all`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for videos (maps to the `title` field in the response). |
| `updatedAfter` | string | Filter data updated after this time (incremental sync).<br>Example: `2024-05-10T15:30:00Z` or `2024-05-10 15:30:00` |

**Response Payload**
Returns an array of [Video Response Items](#video-response-item) directly in the `data` field (no pagination envelope).

### 3. Video Detail
`GET /api/open/videos/{id}`

**Response Payload**
Returns a single [Video Response Item](#video-response-item) in the `data` field.

### 4. Stream Video
`GET /api/open/videos/view/{filename}`
Raw streamable video response.

### 5. Cover Image
`GET /api/open/videos/cover-images/{filename}`
Raw cover image response.

---

## Video Response Item

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
