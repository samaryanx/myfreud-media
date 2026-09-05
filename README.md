# myfreud-media

Public asset host for MyFreud social videos (TikTok, Instagram, etc.).

This repo exists for one reason: Metricool's post-scheduling API only accepts
a **public URL** for video/image media, not a direct upload. This repo is
public specifically so `raw.githubusercontent.com/<owner>/<repo>/<branch>/<path>`
resolves without authentication, giving Metricool something it can fetch.

## Layout

```
<platform>/<account>/<filename>
```

- `<platform>` — `tiktok`, `instagram`, etc.
- `<account>` — the Metricool brand / platform handle the video is for
  (e.g. `myfreud_app_health`).
- `<filename>` — matches the naming convention from the main site's
  `docs/sop-tiktok-posting.md`: `psychology-<topic>-video<N>-<dd>-<monthname>-<yyyy>.mp4`.

Example: `tiktok/myfreud_app_health/psychology-anxiety-video1-05-september-2026.mp4`.

## Getting a fetchable URL

```
https://raw.githubusercontent.com/samaryanx/myfreud-media/main/<platform>/<account>/<filename>
```

Works immediately after a push to `main` — no build/deploy step, unlike the
main `myfreud-website` site.

## This repo is a durable host, not scratch space

Files here are kept (not cleaned up after each post) so a video can be
re-posted, re-checked, or referenced later without regenerating it. Standing
convention going forward for all future videos across TikTok/Instagram and
multiple accounts.
