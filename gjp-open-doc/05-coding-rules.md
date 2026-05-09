# Coding Rules

This file is the coding rules map, not the full rules catalog.

Coding rules are split into focused files under `coding-rules/` so future rules can be added by area without making one large checklist.

## Coding Rules Structure

| File | Purpose |
| --- | --- |
| [coding-rules/00-project.md](coding-rules/00-project.md) | Project-level TypeScript, i18n, API, and secret-handling rules. |
| [coding-rules/01-architecture.md](coding-rules/01-architecture.md) | Mobile app architecture and naming rules. |
| [coding-rules/02-api.md](coding-rules/02-api.md) | API client and API documentation rules. |
| [coding-rules/03-ui-state-i18n.md](coding-rules/03-ui-state-i18n.md) | UI, state, i18n, and media rules. |
| [coding-rules/04-testing-quality.md](coding-rules/04-testing-quality.md) | Coding-level testing rules, quality commands, and review checklist. |
| [coding-rules/05-android-native.md](coding-rules/05-android-native.md) | Native Android coding rules. |
| [coding-rules/06-ios-native.md](coding-rules/06-ios-native.md) | Native iOS coding rules. |
| [coding-rules/_template.md](coding-rules/_template.md) | Template for future coding rule files. |

## How To Add Coding Rules

1. Add or update the focused file under `coding-rules/`.
2. Create a new file when the rule belongs to a new domain.
3. Link new files in the Coding Rules Structure table above.
4. Keep root maps short; do not turn this file into a checklist dump.
