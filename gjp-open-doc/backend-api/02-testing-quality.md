# Backend API Testing And Quality

## Required Gate

Run from `gjp-open-api-boot`:

```sh
./mvnw test -Dspring.profiles.active=test
```

The Maven build enforces JaCoCo coverage:

- Instruction coverage must be at least 90%.
- Line coverage must be at least 90%.

## Coverage Report

Generate and open the HTML report:

```sh
./tooling/script/coverage.sh
```

Manual commands:

```sh
./mvnw clean test -Dspring.profiles.active=test
open target/site/jacoco/index.html
```

## Test Rules

- Add controller tests for endpoint status, response envelope, invalid language, and not-found cases.
- Add service tests for repository calls, pagination, mapping, null handling, and file lookup behavior.
- Add utility tests for shared helpers.
- Add tests for media range behavior when changing stream endpoints.
- Test names should follow `should_doSomething_when_condition`.

## Known Test Environment Note

The H2 test schema may log a warning around `master_app_settings.value` because `value` is reserved in H2. The current test suite still passes. If schema-generation noise becomes a blocker, fix the column mapping or H2 compatibility configuration deliberately.
