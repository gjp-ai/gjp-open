# Logos API

Logos are currently exposed by the API and may be used by the app if needed for branding or website logo lookup.

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/logos` | Paged logo list. |
| `GET` | `/api/open/logos/all` | Full logo list (no pagination). |
| `GET` | `/api/open/logos/{id}` | Logo detail. |
| `GET` | `/api/open/logos/view/{filename}` | Raw logo image response. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for logos. |

## Response Item

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
