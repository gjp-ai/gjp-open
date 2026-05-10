# API Common Reference

## Base URL

| Environment | URL |
| --- | --- |
| Local API | `http://localhost:8084/api/open/` |
| Production | `https://www.ganjianping.com/api/open/` |

The Spring Boot context path is `/api/`; public endpoints are under `/open/*`.

## Response Envelope

JSON API endpoints return:

```json
{
  "status": {
    "code": 200,
    "message": "Message",
    "errors": null
  },
  "data": {},
  "meta": {
    "serverDateTime": "2026-05-06 10:30:00"
  }
}
```

Errors use the same envelope where practical:

```json
{
  "status": {
    "code": 404,
    "message": "Article not found",
    "errors": null
  },
  "data": null,
  "meta": {
    "serverDateTime": "2026-05-06 10:30:00"
  }
}
```

## Paginated Data

List endpoints return `data` in this shape:

```json
{
  "content": [],
  "page": 0,
  "size": 20,
  "totalElements": 0,
  "totalPages": 0
}
```

## Non-Paginated List Endpoints

Resources may expose a `/all` endpoint (e.g. `/api/open/articles/all`) to return the full dataset without pagination. This is intended for mobile apps that need to perform a full sync or refresh of local data.

## Incremental Synchronization

To efficiently sync data, client applications should:
1. Store the latest `updatedAt` value from their local database.
2. Use the `updatedAfter` query parameter on the `/all` endpoint to fetch only records changed since that time.
3. The server filters results using `updatedAt > :updatedAfter`.

## Common Query Parameters

| Parameter | Type | Default | Notes |
| --- | --- | --- | --- |
| `lang` | `EN` or `ZH` | none | Invalid values return `status.code=400`. |
| `tags` | string | none | Filter by tag text. |
| `isActive` | boolean | none | Mobile should send `true` for public list screens; omitted means no active/inactive filter. |
| `page` | number | `0` | Zero-based page index. |
| `size` | number | `20` | Page size. |
| `sort` | string | `displayOrder` | Use API-supported fields only. |
| `direction` | `asc` or `desc` | `asc` | Sort direction. |
| `updatedAfter` | string | none | Filters data updated after this time. Supported formats:<br>• ISO 8601: `2024-05-10T15:30:00Z`<br>• Standard: `2024-05-10 15:30:00` |

Important: use canonical API parameter names. Do not assume `search` or `tag` aliases exist unless the API adds them.

## Root

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/api/` | Returns welcome text. |

## TypeScript API Types

The mobile app should start with these shared shapes:

```ts
export interface ApiStatus {
  code: number
  message: string
  errors: unknown | null
}

export interface ApiMeta {
  serverDateTime: string
}

export interface ApiResponse<TData> {
  status: ApiStatus
  data: TData
  meta?: ApiMeta
}

export interface PagedData<TItem> {
  content: TItem[]
  page: number
  size: number
  totalElements: number
  totalPages: number
}

export type ApiPagedResponse<TItem> = ApiResponse<PagedData<TItem>>
export type LanguageCode = 'EN' | 'ZH'
```

## API Client Rules

- Centralize all fetch code in `shared/api`.
- Set `Accept: application/json` for JSON endpoints.
- Treat HTTP errors and API envelope errors separately.
- Use canonical filter parameters: `name`, `title`, `question`, `tags`, `lang`, and `isActive=true`.
- Do not call admin endpoints from the mobile app.
- Keep raw media/file URLs out of JSON parsing functions.
