# API Reference

This file is the API map, not the full API catalog.

For extensibility, each resource has its own file under `api/`. This keeps every API document small enough for humans and AI tools to search precisely. If the project grows to 100 APIs, add or split files by resource or bounded context instead of expanding this index into a long document.

## API Structure

| File | Purpose |
| --- | --- |
| [api/00-common.md](api/00-common.md) | Base URLs, response envelope, pagination, shared query rules, and API client rules. |
| [api/app-settings.md](api/app-settings.md) | Public app settings endpoint. |
| [api/websites.md](api/websites.md) | Website list/detail API. |
| [api/questions.md](api/questions.md) | Q&A list/detail API. |
| [api/articles.md](api/articles.md) | Article list/detail and cover image API. |
| [api/images.md](api/images.md) | Image list/detail and image file API. |
| [api/videos.md](api/videos.md) | Video list/detail, streaming, and cover image API. |
| [api/audios.md](api/audios.md) | Audio list/detail, streaming, and cover image API. |
| [api/files.md](api/files.md) | File list/detail and download API. |
| [api/logos.md](api/logos.md) | Logo list/detail and image API. |
| [api/_template.md](api/_template.md) | Template for adding future API docs. |

## How To Add A New API

1. Add a focused file under `api/`, for example `api/products.md`.
2. Keep the file scoped to one resource or one bounded context.
3. Link the new file in the API Structure table above.
4. Update [api/00-common.md](api/00-common.md) only when shared behavior changes.
5. Update [05-coding-rules.md](05-coding-rules.md) only when a new coding rule is needed.

## File Size Rule

An API file should stay easy to scan. If a file grows beyond roughly 200-300 lines, split it by operation group:

```text
api/articles/
├── README.md
├── list.md
├── detail.md
└── media.md
```

Use folders only when a single resource genuinely becomes large. Small resources should stay as one markdown file.
