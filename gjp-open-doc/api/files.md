# Files API

## Endpoints

### 1. Paged File List
`GET /api/open/files`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for files. |

**Response Payload**
Returns a `PaginatedResponse` where `data.content` is an array of [File Response Items](#file-response-item).

### 2. Full File List (Non-Paginated)
`GET /api/open/files/all`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for files. |
| `updatedAfter` | string | Filter data updated after this time (incremental sync).<br>Example: `2024-05-10T15:30:00Z` or `2024-05-10 15:30:00` |

**Response Payload**
Returns an array of [File Response Items](#file-response-item) directly in the `data` field (no pagination envelope).

### 3. File Detail
`GET /api/open/files/{id}`

**Response Payload**
Returns a single [File Response Item](#file-response-item) in the `data` field.

### 4. File Download
`GET /api/open/files/view/{filename}`
Raw file download response.

---

## File Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `name` | string |
| `url` | string |
| `originalUrl` | string |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Mobile Notes

- Send `isActive=true` for public list screens.
- Open file URLs through OS/browser document handling.
- Do not store large files locally in MVP.
