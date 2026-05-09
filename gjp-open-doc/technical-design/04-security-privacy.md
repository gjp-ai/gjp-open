# Security, Privacy, And Errors

## Error Handling

- API response `status.code` is the business status.
- HTTP non-2xx status is a transport error.
- API `status.code !== 200` is an application error.
- Media and file endpoints may return raw HTTP responses instead of `ApiResponse`.
- Never let a failed media request crash the screen.

## Security And Privacy

- The app must only call public GET endpoints.
- No API secrets, admin tokens, or private keys in source control.
- Validate external URLs before opening them.
- Add analytics only after privacy and consent requirements are documented.
- App store privacy labels must match actual SDK usage.
