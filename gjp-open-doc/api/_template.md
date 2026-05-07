# Resource Name API

Use this template when adding a new API resource. Keep one file scoped to one resource or one bounded context.

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/open/resource-name` | Paged resource list. |
| `GET` | `/api/open/resource-name/{id}` | Resource detail. |

## List Filters

Also see [common query parameters](00-common.md#common-query-parameters).

| Parameter | Type | Notes |
| --- | --- | --- |
| `name` | string | Canonical search field, if supported. |

## Request Body

Public mobile APIs should normally be GET-only. Add this section only if a future public write endpoint is approved.

## Response Item

| Field | Type | Notes |
| --- | --- | --- |
| `id` | string | Public UUID. |

## Error Cases

| Case | Expected Result |
| --- | --- |
| Invalid `lang` | API envelope with `status.code=400`. |
| Missing resource | API envelope with `status.code=404`, where implemented. |

## Mobile Notes

- Send `isActive=true` for public list screens when the resource supports it.
- Add feature-specific client rules here.
