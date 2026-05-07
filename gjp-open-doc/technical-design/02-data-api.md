# Data And API Design

## API Base URLs

Use environment configuration:

| Environment | Base URL |
| --- | --- |
| Local Android emulator | `http://10.0.2.2:8084/api/open/` |
| Local iOS simulator | `http://localhost:8084/api/open/` |
| Physical device | LAN IP, for example `http://192.168.x.x:8084/api/open/` |
| Production | `https://www.ganjianping.com/api/open/` |

Do not hardcode production URLs inside feature components. Centralize base URL selection in the API client.

## Data Fetching

Use a shared paged fetch hook for all list screens:

- Accept endpoint function, language, page size, search, selected tag, and sort options.
- Abort or ignore stale requests when filters change.
- Support pull-to-refresh.
- Support load-more.
- Preserve previous results while loading next page.
- Surface typed errors to screens.

## Caching

MVP caching should be simple:

- Persist language/theme settings.
- Cache last successful list responses per section and language.
- Show cached content while refreshing in the background.
- Do not cache large media files in MVP.

## Known Integration Notes

- The API controllers currently use canonical query names: `name`, `title`, `question`, and `tags`.
- The current web wrapper sends `search` and `tag` in some calls. Before mobile implementation, either update the clients to canonical names or add API aliases deliberately.
- API list defaults are `page=0`, `size=20`, `sort=displayOrder`, and `direction=asc`.
- Public mobile list requests should send `isActive=true`; the API treats omitted `isActive` as no active/inactive filter.
- Web currently requests `size=60`; mobile should choose page sizes based on screen and performance testing.
