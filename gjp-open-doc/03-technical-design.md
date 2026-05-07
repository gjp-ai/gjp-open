# Technical Design

This file is the technical design map, not the full technical catalog.

Technical decisions and architecture details are split into focused files under `technical-design/`. Add new areas there as the mobile app grows.

## Technical Design Structure

| File | Purpose |
| --- | --- |
| [technical-design/00-stack.md](technical-design/00-stack.md) | Recommended stack and repository shape. |
| [technical-design/01-runtime-architecture.md](technical-design/01-runtime-architecture.md) | Runtime architecture and app module structure. |
| [technical-design/02-data-api.md](technical-design/02-data-api.md) | API base URLs, data fetching, caching, and API integration notes. |
| [technical-design/03-media-i18n-theme.md](technical-design/03-media-i18n-theme.md) | Media handling, internationalization, and theming. |
| [technical-design/04-security-privacy.md](technical-design/04-security-privacy.md) | Security, privacy, and error handling. |
| [technical-design/05-android-native.md](technical-design/05-android-native.md) | Native Android architecture for `gjp-open-android`. |
| [technical-design/06-ios-native.md](technical-design/06-ios-native.md) | Native iOS architecture for `gjp-open-ios`. |
| [technical-design/_template.md](technical-design/_template.md) | Template for future technical design docs. |

## How To Add Technical Design Docs

1. Add a focused file under `technical-design/`.
2. Use one file per architecture area, integration, library decision, or runtime concern.
3. Link the new file in the Technical Design Structure table above.
4. Split large files by subsystem or decision area when they grow beyond roughly 200-300 lines.
