# Non-Functional Requirements

| Area | Requirement |
| --- | --- |
| Performance | First visible content should render quickly on normal mobile networks. Use paged API calls and lazy media loading. |
| Reliability | API errors must show retry actions. Media errors must not crash the app. |
| Accessibility | Touch targets should be at least 44 x 44 points. Text should support OS font scaling. Colors must meet WCAG AA where practical. |
| Security | No secrets in the app bundle. No admin endpoints. Validate all external URL handoffs. |
| Privacy | Avoid analytics until privacy policy and consent decisions are complete. |
| Compatibility | Support current stable Android and iOS versions chosen during app setup. |
| Maintainability | Share TypeScript API types and fetch patterns with the web app where practical. |
