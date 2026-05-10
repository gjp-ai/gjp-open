# Questions API

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/questions` | Paged Q&A list. |
| `GET` | `/api/open/questions/all` | Full Q&A list (no pagination). |
| `GET` | `/api/open/questions/{id}` | Q&A detail. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `question` | string | Canonical search field for Q&A. |
| `updatedAfter` | string | Filter data updated after this time (incremental sync).<br>Example: `2024-05-10T15:30:00Z` or `2024-05-10 15:30:00` |

## Response Item

| Field | Type |
| --- | --- |
| `id` | string |
| `question` | string |
| `answer` | string |
| `tags` | string |
| `lang` | `EN` or `ZH` |
| `displayOrder` | number |
| `updatedAt` | string |

## Mobile Notes

- Send `isActive=true` for public list screens.
- Use a readable expandable or card layout for long answers.
- Keep answer copy/select/share actions optional for MVP.
