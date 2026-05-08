# Information Architecture

```mermaid
flowchart TD
    App["GJP AI Mobile App"] --> Tabs["Primary Navigation"]
    Tabs --> Websites["Websites"]
    Tabs --> Questions["Q&A"]
    Tabs --> Articles["Articles"]
    Tabs --> Images["Images"]
    Tabs --> Videos["Videos"]
    Tabs --> More["More"]
    More --> Audios["Audio"]
    More --> Files["Files"]
    Articles --> ArticleDetail["Article Detail"]
    Images --> ImagePreview["Image Preview"]
    Videos --> VideoPlayer["Video Player"]
    Audios --> AudioPlayer["Audio Player"]
    Files --> FileOpen["OS File Viewer"]
```

## Recommended Navigation

Use bottom tabs for the most common sections:

- Websites
- Q&A
- Articles
- Images
- Videos

Place Audio, Files, language/theme settings, app information, and support links in a More screen unless product testing shows they are frequently used.
