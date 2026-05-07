# UI Automation

## Required Automated Flows

Automate these flows on Android and iOS once the corresponding feature exists:

- App launches to public content without login.
- Bottom tab navigation changes screens.
- Language toggle persists after app restart.
- Theme toggle persists after app restart.
- Websites list loads and opens external URL handoff.
- Articles list opens article detail.
- Pull-to-refresh shows refreshing state and returns to content.
- API error state shows retry action.
- Empty list state renders correctly.

## Media Automation

Automate only stable assertions for media:

- Video player screen opens.
- Audio player screen opens.
- Image preview opens and closes.
- File action triggers OS/browser handoff where test tooling can observe it.

Use manual QA for real playback quality, speaker behavior, background audio, and file viewer compatibility.

## Accessibility Automation

Automated UI checks should verify:

- Primary tabs have accessibility labels.
- Icon-only buttons have labels.
- Text is visible at larger font sizes where test tooling supports it.
- Important actions are reachable by accessibility navigation.
