# GJP Open Workspace Harness

This workspace contains the public GJP AI access projects. AI assistants and Claude Code should use this file as the workspace entry point before editing or generating code.

## Projects

| Project | Purpose |
| --- | --- |
| `gjp-open-api-boot` | Spring Boot public API for unauthenticated, read-only public content. |
| `gjp-open-web-react` | React public access website. |
| `gjp-open-doc` | Requirements, design, API, coding rules, implementation plans, and AI generation harness for mobile apps. |
| `gjp-open-android` | Future native Android app. |
| `gjp-open-ios` | Future native iOS app. |

## Read Order

For Claude Code, start with [CLAUDE.md](CLAUDE.md). For all tools, use the relevant project map below instead of reading every document.

Before mobile code generation, read these maps first:

1. `gjp-open-doc/README.md`
2. `gjp-open-doc/01-requirements.md`
3. `gjp-open-doc/02-product-design.md`
4. `gjp-open-doc/03-technical-design.md`
5. `gjp-open-doc/04-api-reference.md`
6. `gjp-open-doc/05-coding-rules.md`
7. `gjp-open-doc/06-implementation-plan.md`
8. `gjp-open-doc/07-ai-generation-harness.md`
9. `gjp-open-doc/08-testing-strategy.md`

For backend API work, also read:

10. `gjp-open-doc/09-backend-api-harness.md`

Then open only the focused files relevant to the task. Do not bulk-load every document when one feature file is enough.

## Documentation Pattern

- Numbered root files in `gjp-open-doc` are maps.
- Details live in matching folders such as `requirements/`, `api/`, `technical-design/`, and `ai-harness/`.
- Add new focused docs from the `_template.md` file in the matching folder.
- If a focused doc grows beyond roughly 200-300 lines, split it by feature, operation group, phase, or platform.

## Mobile Generation Rules

- For `gjp-open-android`, use the native Android harness in `gjp-open-doc/ai-harness/01-android-native.md`.
- For `gjp-open-ios`, use the native iOS harness in `gjp-open-doc/ai-harness/02-ios-native.md`.
- Use the testing strategy in `gjp-open-doc/08-testing-strategy.md`; generated code should include relevant unit tests and automation hooks.
- Keep Android and iOS behavior aligned with the same requirements, API docs, and acceptance criteria.
- Do not invent private APIs. Mobile apps must use public `/api/open/*` endpoints only.
- Public list requests must send `isActive=true`.
- Use canonical API query names documented in `gjp-open-doc/api/00-common.md` and the resource-specific API file.

## Existing Project Quality Gates

Run the project-specific quality gate before handing work back when relevant:

| Project | Quality command |
| --- | --- |
| `gjp-open-api-boot` | `./mvnw test` |
| `gjp-open-web-react` | `npm run check` |
| `gjp-open-android` | `./gradlew testDebugUnitTest lintDebug` once the project exists. |
| `gjp-open-ios` | `xcodebuild test` with the selected scheme once the project exists. |

If a command is unavailable because the project has not been created yet, document that in the final response.

## Safety Rules

- Do not commit secrets, signing files, keystores, provisioning profiles, or local environment files.
- Do not modify unrelated projects unless the task requires it.
- Keep generated code aligned with existing docs; update docs first when behavior changes.
- Preserve bilingual EN/ZH behavior for all visible public mobile UI.
