# AI Generation Harness

This file is the AI generation harness map.

Use this section when an AI tool needs to generate or modify mobile code. The goal is to keep generation consistent across `gjp-open-android`, `gjp-open-ios`, the public API, and the public web experience.

## Harness Structure

| File | Purpose |
| --- | --- |
| [ai-harness/00-read-order.md](ai-harness/00-read-order.md) | What AI tools should read before generating code. |
| [ai-harness/01-android-native.md](ai-harness/01-android-native.md) | Native Android generation harness. |
| [ai-harness/02-ios-native.md](ai-harness/02-ios-native.md) | Native iOS generation harness. |
| [ai-harness/03-cross-project-sync.md](ai-harness/03-cross-project-sync.md) | Rules for keeping Android, iOS, API, and web behavior aligned. |
| [ai-harness/04-quality-gates.md](ai-harness/04-quality-gates.md) | Expected validation commands and manual checks. |
| [ai-harness/_template.md](ai-harness/_template.md) | Template for future AI harness docs. |

## Harness Rule

AI tools should not start by reading every file. Start from this map, then read only the focused files needed for the requested platform and feature.

Testing is mandatory for generated code. Read [08-testing-strategy.md](08-testing-strategy.md) and the relevant platform testing file before creating native mobile features.
