# Runtime Architecture

```mermaid
flowchart LR
    User["Mobile User"] --> App["Native Mobile App"]
    App --> Nav["Navigation"]
    App --> Theme["Theme + Language Providers"]
    App --> Query["Paged Fetch Hooks"]
    Query --> ApiClient["API Client"]
    ApiClient --> PublicApi["gjp-open-api-boot /api/open/*"]
    App --> Storage["Local Storage"]
    App --> OS["System Browser / Media / File Viewer"]
```

## Module Rules

- App shell, navigation, and providers live in `src/app`.
- Feature screens live in `src/features/{feature}`.
- Reusable UI, API, hooks, theme, i18n, storage, and utilities live in `src/shared`.
- Feature modules may import from `shared`; `shared` must not import from feature folders.
