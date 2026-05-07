# Media, i18n, And Theme

## Media Handling

- Use API-provided media URLs directly.
- Video and audio endpoints support byte range requests; player components should use URLs that allow native playback controls.
- Image preview should load thumbnails in lists and full image on preview.
- File URLs should be opened through platform linking or document viewing.

## Internationalization

Use the same language codes as the API:

```text
EN
ZH
```

Rules:

- Store selected language locally.
- Default from OS language when possible.
- Send `lang=EN` or `lang=ZH` on list requests.
- Keep visible copy in i18n files, not inline inside feature components.

## Theming

Match the web app behavior where practical:

- Light and dark themes.
- Theme color token if retained.
- Persist user choice locally.
- Respect OS color scheme if a system mode is added.
