# Functional Requirements

## Navigation

- The app opens to the Websites screen unless a future product decision selects a different home screen.
- Primary navigation must expose Websites, Q&A, Articles, Images, and Videos.
- Audio and Files may be primary tabs or secondary menu items; this is a product decision to confirm.
- Deep links should be supported for article detail and content detail screens after MVP if app-store launch timing allows.

## Content Lists

- Each list screen shows public active content from the API by sending `isActive=true` on list requests.
- Items sort by `displayOrder asc` by default.
- Users can refresh manually.
- Users can load more content without losing scroll position.
- Users can filter by language and tags.
- Users can search where the API exposes a canonical field: `name`, `title`, or `question`.

## Article Detail

- Article detail shows title, summary, content, source name, cover image, tags, and updated date.
- External original source URLs open outside the app.
- Content rendering must support rich text or HTML if API content contains markup.

## Media

- Images open in a full-screen preview with pinch zoom if feasible.
- Videos play inline or in a dedicated player screen and support server range requests.
- Audio plays in a dedicated player and should continue while the player screen is active.
- Files open using the OS document viewer or browser handoff.

## Settings

- The app remembers language, theme, and theme color.
- The app reads public app settings from `/open/app-settings` for configurable labels/tags used by the public experience.
