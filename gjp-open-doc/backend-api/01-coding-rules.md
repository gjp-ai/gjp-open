# Backend API Coding Rules

## Response Patterns

Single object:

```java
ApiResponse<T>
```

Paginated list:

```java
ApiResponse<PaginatedResponse<T>>
```

Non-paginated list:

```java
ApiResponse<List<T>>
```

Success:

```java
return ApiResponse.success(data, "Message");
```

Error:

```java
return ApiResponse.error(404, "Resource not found", null);
```

## Controller Rules

- Controllers stay thin.
- Validate `lang` with `CmsUtil.parseLanguage`.
- Return `ApiResponse.error(400, "Invalid lang", null)` for invalid language.
- Return `ApiResponse.error(404, "... not found", null)` when detail lookup returns null.
- Do not add POST, PUT, PATCH, or DELETE endpoints for public content unless explicitly approved.

## Service Rules

- Use constructor injection with `@RequiredArgsConstructor`.
- Use `@Transactional(readOnly = true)` for reads.
- Use `CmsUtil.buildPageable(page, size, sort, direction)` for pagination.
- Keep mapping methods private, for example `mapToResponse`.
- Use `.orElse(null)` for detail lookup patterns already established in the project.

## Entity And DTO Rules

- Do not use Lombok `@Data` on JPA entities.
- Entity IDs are string UUIDs stored as `CHAR(36)` where tables already use UUIDs.
- DTOs may use Lombok `@Data` and `@Builder`.
- Public DTOs expose only public fields.

## Media/File Rules

- Validate filenames with `CmsUtil.validateFilename`.
- Determine content type with `CmsUtil.determineContentType`.
- Support byte range requests for streamable audio/video and large media where already established.
- Raw media endpoints return `ResponseEntity<Resource>` or stream responses, not `ApiResponse`.
