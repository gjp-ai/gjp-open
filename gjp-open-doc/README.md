# gjp-open-doc

Documentation for the GJP AI public mobile app initiative.

This project captures the product requirements, user experience design, technical design, public API contract, coding rules, testing strategy, and AI generation harness that should be agreed before creating the Android and iOS app.

## Related Projects

| Project | Purpose |
| --- | --- |
| `gjp-open-api-boot` | Spring Boot public API for unauthenticated, read-only GJP AI content. |
| `gjp-open-web-react` | Current public access website built with React and TypeScript. |
| `gjp-open-doc` | Planning and engineering documentation for the upcoming mobile app. |

## Mobile Direction

If the goal is two separate native projects, use:

- `gjp-open-android`: Kotlin + Jetpack Compose.
- `gjp-open-ios`: Swift + SwiftUI.

React Native with Expo remains a valid alternative if the project later chooses one shared cross-platform app.

References:

- Android Developers: https://developer.android.com/
- Apple Developer Documentation: https://developer.apple.com/documentation/
- React Native: https://reactnative.dev/
- Expo: https://docs.expo.dev/

## Documents

Read these in order:

1. [Requirements](01-requirements.md)
2. [Product Design](02-product-design.md)
3. [Technical Design](03-technical-design.md)
4. [API Reference Map](04-api-reference.md)
5. [Coding Rules](05-coding-rules.md)
6. [Implementation Plan](06-implementation-plan.md)
7. [AI Generation Harness](07-ai-generation-harness.md)
8. [Testing Strategy](08-testing-strategy.md)
9. [Backend API Harness](09-backend-api-harness.md)

## Documentation Structure

The root contains cross-project map documents. Details live in matching topic folders so every area can scale without becoming one large file.

```text
gjp-open-doc/
├── README.md
├── 01-requirements.md       # Requirements map
├── 02-product-design.md     # Product design map
├── 03-technical-design.md   # Technical design map
├── 04-api-reference.md      # API map and navigation
├── 05-coding-rules.md       # Coding rules map
├── 06-implementation-plan.md # Implementation plan map
├── 07-ai-generation-harness.md # AI generation harness map
├── 08-testing-strategy.md   # Testing strategy map
├── 09-backend-api-harness.md # Backend API harness map
├── requirements/
├── product-design/
├── technical-design/
├── api/
├── coding-rules/
├── implementation-plan/
├── ai-harness/
├── testing/
└── backend-api/
```

Do not put all details into the numbered root files. Those files should stay small and point to focused files in the matching folder.

## Decisions To Confirm

- App display name, bundle identifier, and package name.
- Whether the first app release includes audio and files in the main navigation.
- Whether the API should add `search`/`tag` aliases for web/mobile compatibility, or clients should use only canonical API parameters.
- App Store and Google Play publishing accounts, signing ownership, and privacy policy URL.

## Documentation Rules

- Keep docs close to current code behavior in `gjp-open-api-boot` and `gjp-open-web-react`.
- Update the relevant focused file when details change, for example `requirements/02-functional.md` or `api/articles.md`.
- Update numbered root map files only when adding, removing, renaming, or splitting focused files.
- Use the `_template.md` file in each folder when adding a new focused doc.
- Update coding rules before starting the mobile repository so generated code follows the agreed pattern from day one.
- Record open questions explicitly instead of hiding assumptions inside implementation tasks.

## File Size Rule

Any focused file should stay easy to scan. If a file grows beyond roughly 200-300 lines, split it by feature, operation group, phase, or decision area and update the matching root map.
