# Files API

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/files` | Paged file list. |
| `GET` | `/api/open/files/all` | Full file list (no pagination). |
| `GET` | `/api/open/files/{id}` | File detail. |
| `GET` | `/api/open/files/view/{filename}` | Raw file download response. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field for files. |

## Response Item

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
