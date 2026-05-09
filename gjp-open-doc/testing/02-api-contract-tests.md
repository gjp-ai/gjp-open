# API Contract Tests

## Purpose

API contract tests protect the mobile apps from drifting away from `gjp-open-api-boot`.

## Contract Rules

- Every public endpoint function must have a test that verifies path and canonical query parameters.
- Public list requests must include `isActive=true`.
- List requests should include `lang` when the current language is known.
- Do not send `search` or `tag` unless the API intentionally adds aliases.
- Media/file endpoints must be treated as raw responses, not JSON envelopes.

## Response Fixtures

Keep representative fixtures for:

- Success envelope.
- Error envelope.
- Empty page.
- Paged content.
- Article detail.
- Nullable media URLs.
- Invalid/missing optional fields where the app must be tolerant.

## Compatibility Checklist

- [ ] `ApiResponse<T>` parses `status`, `data`, and `meta`.
- [ ] `PagedData<T>` parses `content`, `page`, `size`, `totalElements`, and `totalPages`.
- [ ] `status.code !== 200` becomes an app error.
- [ ] HTTP non-2xx becomes a transport error.
- [ ] Raw media URLs bypass JSON parsing.
