# Requirements

This file is the requirements map, not the full requirements catalog.

For extensibility, requirements are split into focused files under `requirements/`. Add new requirement areas there instead of growing this index into a large document.

## Requirements Structure

| File | Purpose |
| --- | --- |
| [requirements/00-overview.md](requirements/00-overview.md) | Product goal and target users. |
| [requirements/01-scope.md](requirements/01-scope.md) | MVP scope and out-of-scope items. |
| [requirements/02-functional.md](requirements/02-functional.md) | Functional requirements by app area. |
| [requirements/03-non-functional.md](requirements/03-non-functional.md) | Performance, reliability, accessibility, security, privacy, and maintainability requirements. |
| [requirements/04-acceptance.md](requirements/04-acceptance.md) | Release acceptance criteria. |
| [requirements/05-open-questions.md](requirements/05-open-questions.md) | Product and technical questions to confirm. |
| [requirements/_template.md](requirements/_template.md) | Template for future requirement files. |

## How To Add Requirements

1. Add a focused file under `requirements/`.
2. Keep one file scoped to one feature, quality attribute, user journey, or decision area.
3. Link the new file in the Requirements Structure table above.
4. Move details into subfiles if a file grows beyond roughly 200-300 lines.
