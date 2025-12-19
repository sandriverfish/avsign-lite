# avSign.lite v1.0.2 — Phase 0 (Soft Launch Patch)

Release Date: 2025-11-25

## Summary
This patch improves the Android first-run experience by removing the runtime external storage permission prompt and switching the app to scoped storage (app-support path). The release includes updated build artifacts for Android and Windows and updated documentation.

## Key Changes
- Removed runtime storage permission prompt on Android first run (switched to scoped app storage).
- Removed `permission_handler` runtime dependency and cleaned Android manifest entries.
- Updated packaging for Phase 0: ready-to-download Android APK and Windows bundle.

## Installation Notes
- Android: Install the APK on Android 9+ devices. The app will not request an external storage permission on first run.
- Windows: Use the provided ZIP/installer to deploy the Admin UI and app files.

## Validation Steps
1. Install the APK on Android 9–14 devices and verify no permission prompt on first run.
2. Confirm scoped app storage read/write operations succeed (resources, playlist downloads).
3. Verify Admin UI loads and functions on Windows 10+.

## Known Issues
- Some older Android devices with deprecated hardware may still have codec or playback limitations unrelated to this change.

## Artifacts
- Android APK: `avsign-lite-1.0.2-android.apk`
- Windows bundle: `avsign-lite-1.0.2-windows-android.zip`

---

This file is part of the Phase 0 public release and excludes any internal or private investigation materials.
