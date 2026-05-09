# Architecture And Naming Rules

## Architecture Rules

- Put app shell, navigation, and providers in `src/app`.
- Put feature screens in `src/features/{feature}`.
- Put reusable UI, API, hooks, theme, i18n, and utility code in `src/shared`.
- Feature components may import from `shared`; `shared` must not import from feature folders.
- Do not make API calls directly in presentational components.
- Keep list state behavior in shared hooks.
- Keep media player behavior in feature-level containers or shared media components.

## Naming Rules

| Item | Rule | Example |
| --- | --- | --- |
| Screen | `{Feature}Screen` | `ArticlesScreen` |
| Detail screen | `{Feature}DetailScreen` | `ArticleDetailScreen` |
| Component | PascalCase | `ArticleCard` |
| Hook | `use...` | `usePagedContent` |
| API function | verb + domain | `getArticles` |
| Type | PascalCase | `ArticleSummary` |
| Test file | same file name + `.test.tsx` | `ArticleCard.test.tsx` |
