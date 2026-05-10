# Logos API

Logos are currently exposed by the API and may be used by the app if needed for branding or website logo lookup.

## Endpoints

### 1. Paged Logo List
`GET /api/open/logos`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for logos. |

**Response Payload**
Returns a `PaginatedResponse` where `data.content` is an array of [Logo Response Items](#logo-response-item).

### 2. Full Logo List (Non-Paginated)
`GET /api/open/logos/all`

**Query Parameters** (Also see [common query parameters](00-common.md#common-query-parameters))
| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for logos. |
| `updatedAfter` | string | Filter data updated after this time (incremental sync).<br>Example: `2024-05-10T15:30:00Z` or `2024-05-10 15:30:00` |

**Response Payload**
Returns an array of [Logo Response Items](#logo-response-item) directly in the `data` field (no pagination envelope).

### 3. Logo Detail
`GET /api/open/logos/{id}`

**Response Payload**
Returns a single [Logo Response Item](#logo-response-item) in the `data` field.

### 4. View Logo
`GET /api/open/logos/view/{filename}`
Raw logo image response.

---

## Logo Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `name` | string |
| `url` | string |
| `thumbnailUrl` | string |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Mobile Notes

- Send `isActive=true` for public list screens if the app directly queries logos.
- Prefer website `logoUrl` for website cards unless a logo-specific workflow needs this endpoint.
