# API Coding Rules

## API Documentation Rules

- Keep API docs split by resource under `api/`; `04-api-reference.md` is only the index.
- Add new API docs from `api/_template.md`.

## API Client Rules

- API base URL must be configured in one place.
- Endpoint functions must return typed response data.
- API errors must become typed app errors before reaching screens.
- Use zero-based `page` values.
- Use `displayOrder asc` as the default sort.
- List requests should include `lang` whenever the current language is known.
- Public list requests must include `isActive=true`.
- Use canonical API query names:
  - Websites, Images, Videos, Audio, Files, Logos: `name`
  - Articles: `title`
  - Questions: `question`
  - Tags: `tags`
- Do not send `search` or `tag` unless API aliases are intentionally added.
