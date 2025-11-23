# Screenshots Folder

This folder contains screenshots used for documentation, marketing, and releases.

Conventions:
- Place admin UI screenshots under `docs/screenshots/admin/` (or prefix `avsign.admin.`)
- Place client screenshots under `docs/screenshots/client/` (or prefix `avsign.lite.client.`)
- File naming: `avsign.<component>.<view>.<num>.<ext>` (e.g., `avsign.admin.dashboard.2.png`)
- Recommended sizes: 1920x1080 (full), 1280x720 (web thumbnails)
- Use `png` for screenshots, `gif` for short animations, and `mp4`/`webm` for recordings
- Add a brief `README.md` or caption for new sets if you're contributing many images

Optimization:
- Keep README GIFs small (< 2MB) and MP4s optimized for web (H.264/H.265)
- Add alt text when referencing images in docs for accessibility

Test artifacts and CI screenshots should be placed in `test/screenshots/` and are not meant for documentation.

If you have questions or want a new screenshot created, open an issue or PR with the image attached.

