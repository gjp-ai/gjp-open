# AI Read Order

## Native Mobile Project Creation

When creating `gjp-open-android` or `gjp-open-ios`, read in this order:

1. `README.md`
2. `01-requirements.md`
3. `requirements/00-overview.md`
4. `requirements/01-scope.md`
5. `requirements/02-functional.md`
6. `03-technical-design.md`
7. `technical-design/05-android-native.md` or `technical-design/06-ios-native.md`
8. `04-api-reference.md`
9. `api/00-common.md`
10. Resource-specific API files for the feature being built.
11. `05-coding-rules.md`
12. Platform-specific coding rules.
13. `08-testing-strategy.md`
14. Platform-specific testing docs.
15. `06-implementation-plan.md`

## Feature Implementation

When implementing one feature, read:

- The feature requirement file or relevant section.
- The product design file for the screen.
- The platform technical design file.
- The API common file and resource-specific API file.
- The platform coding rules.
- The testing strategy and platform-specific testing doc.

Avoid reading unrelated API resources or all implementation-plan files unless the task requires them.
