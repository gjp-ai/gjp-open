# Audios API

## Endpoints

### 1. Paged Audio List
`GET /api/open/audios`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for audios (maps to the `title` field in the response). |

**Response Payload**
Returns a `PaginatedResponse` where `data.content` is an array of [Audio Response Items](#audio-response-item).

### 2. Full Audio List (Non-Paginated)
`GET /api/open/audios/all`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for audios (maps to the `title` field in the response). |
| `updatedAfter` | string | Filter data updated after this time (incremental sync).<br>Example: `2024-05-10T15:30:00Z` or `2024-05-10 15:30:00` |

**Response Payload**
Returns an array of [Audio Response Items](#audio-response-item) directly in the `data` field (no pagination envelope).

### 3. Audio Detail
`GET /api/open/audios/{id}`

**Response Payload**
Returns a single [Audio Response Item](#audio-response-item) in the `data` field.

### 4. Stream Audio
`GET /api/open/audios/view/{filename}`
Raw streamable audio response.

### 5. Cover Image
`GET /api/open/audios/cover-images/{filename}`
Raw cover image response.

---

## Audio Response Item

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
