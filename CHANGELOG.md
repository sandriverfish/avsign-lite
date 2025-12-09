# Changelog

All notable changes to avSign.lite will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned for Phase 1 (Q1 2025)
- Open source code release under AGPLv3
- Developer documentation and contribution guidelines
- Community contribution process
- Enhanced architecture documentation

### Planned for Phase 2 (Q2 2025)
- AI-powered content generation (Claude Skills)
- Cloud synchronization and backup
- MCP server for AI agent control
- Advanced scheduling system
- Multi-device management dashboard

---

## [1.0.4] - 2025-12-08

### Added
- **Fire TV AppStore Support**: Full Amazon In-App Purchase (IAP) integration
  - One-click subscription purchase via Amazon account
  - 14-day free trial for new users
  - Lifetime license: $49.99 (one-time payment)
  - Automatic subscription restoration
  - Trial countdown notifications (last 3 days)
- **Fire TV Optimized UI**:
  - D-pad navigation with focus management
  - Simplified Quick Settings overlay (Language & Subscription)
  - Floating Settings button on display page
  - TV-optimized button sizes and spacing
  - Visual focus indicators for remote control
- **Subscription Management**:
  - Automatic subscription check on app startup
  - Trial period management with grace period
  - Forced subscription overlay when trial expires
  - Restore purchases functionality
  - Receipt validation with Amazon RVS

### Changed
- Fire TV builds now include Amazon IAP SDK integration
- Subscription overlay redesigned for TV remote control
- Settings page updated with Fire TV-specific options
- Display page includes floating settings access (Fire TV only)

### Fixed
- D-pad focus management in subscription overlay
- Focus traversal order for TV navigation
- Subscription status persistence across app restarts
- Trial expiration handling

### Technical
- Amazon IAP SDK integration via platform channels
- Receipt validation service (RVS) implementation
- Subscription state management with Riverpod
- Fire TV platform detection utilities

---

## [1.0.3] - 2025-12-07

### Added
- Preparation for Fire TV AppStore submission
- Enhanced documentation for release process

### Changed
- Updated release SOP with Fire TV build instructions
- Improved version numbering documentation

---

## [1.0.1] - 2025-11-24

### Added
- **Port Configuration**: Configure HTTP server and MCP server ports in Settings
  - Settings → Server Settings → Port Configuration
  - Automatic conflict detection (e.g., SuperSign on port 8080)
  - Auto-allocation to alternative ports (8081, 8082, etc.)
  - Persists across app restarts
  - Environment variable support (`SERVER_PORT`, `MCP_PORT`)
- Port validation with recommended ranges (Admin UI: 8080-8180, MCP: 3333-3433)
- Port diagnostics helper for availability testing

### Fixed
- **Android Icon**: Fixed black border around app icon on Android 10+
  - Changed adaptive icon background from dark gray to white
  - Proper adaptive icon configuration for all Android versions 8.0+

### Changed
- Version bump: 1.0.0+1 → 1.0.1+2
- Updated `flutter_launcher_icons` configuration for consistent icon generation

---

## [1.0.2] - 2025-11-25

### Fixed
- **Android First-Run UX**: Removed runtime external storage permission prompt on Android first run by switching to scoped app storage paths and removing runtime permission requests.
  - Removed `READ_EXTERNAL_STORAGE`, `WRITE_EXTERNAL_STORAGE`, and `MANAGE_EXTERNAL_STORAGE` from `AndroidManifest.xml`.
  - Removed runtime permission request code from `MainActivity.kt` and simplified `ExternalStorageManager` to use app-scoped storage.
  - Removed `permission_handler` dependency from `pubspec.yaml` to avoid unnecessary runtime permission handling logic.
  - Cleaned `AndroidManifest.xml` to remove `requestLegacyExternalStorage` attribute and other legacy entries.

### Changed
- Updated packaging for Phase 0 release: Android APK and Windows installer prepared and documented in Phase 0 plan.
- Documentation updates: `docs/PHASE0_SOFT_LAUNCH_PLAN.md` and `docs/RELEASE_NOTES_1.0.2.md`.



## [1.0.0-beta] - 2025-11-23

### Phase 0 Beta Release

First public beta release with compiled binaries for Windows, Android, and Linux.

#### Added

**Core Features:**
- Resource management system for uploading and organizing media files
- Visual drag-and-drop layout editor
- Template library with 5+ pre-built layouts (full screen, PIP, side-by-side, quad dashboard, video wall)
- Custom template creation and saving
- Program/playlist creation with multi-zone content support
- Device/terminal management
- Content publishing workflow
- Offline-first architecture with local HTTP server

**Supported Media Types:**
- Image support: JPG, PNG, GIF, BMP, WebP
- Video support: MP4, AVI, MKV, MOV, WebM
- Text widgets: Static text, scrolling text, clock displays
- Layout zones: Multi-zone layouts with independent content per zone

**User Interface:**
- Admin web interface accessible on port 8080
- Responsive design for desktop and tablet displays
- Settings management
- User authentication system

**Platform Support:**
- Windows 10/11 (64-bit)
- Android 5.0+ (API level 21+)
- Linux (Ubuntu 20.04+, or equivalent with GTK 3.0+)

#### Known Issues

**Installation:**
- Windows 11 may require administrator rights for installation
- Some antivirus software may flag the installer (false positive)
- Linux: GTK dependencies must be installed manually on some distributions

**Performance:**
- Large video files (>500 MB) may take time to load on first display
- Layout editor may experience lag on older Android devices (< 2GB RAM)
- 4K video playback may require hardware decoding support

**Compatibility:**
- Web browser access to admin UI works best with Chrome/Edge
- Firefox may have minor CSS rendering differences
- Safari on iOS is not officially supported for admin UI

**UI/UX:**
- Upload progress indicator may not update smoothly for very large files
- Drag-and-drop zone resizing has minimum size constraints
- Some error messages are technical and need clarification

#### Platform-Specific Notes

**Windows:**
- Requires DirectX 11 compatible graphics card
- Installation directory: `C:\Program Files\avSign.lite\`
- Default data directory: `%APPDATA%\avSign.lite\`

**Android:**
- Requires storage permissions for media file access
- Recommended for tablets with 7" or larger screens
- Some older devices may have video codec limitations

**Linux:**
- Tested on Ubuntu 20.04 and 22.04
- May require additional codecs for some video formats
- Desktop file integration included for application launcher

#### Security

- Default admin credentials should be changed on first run
- Admin interface accessible only on localhost by default
- No data transmitted to external servers (fully offline)
- Media files stored locally on device

#### Dependencies

**Built With:**
- Flutter 3.24.3
- Drift ORM for database
- Media Kit for video playback
- Shelf HTTP server for admin interface

---

## Version History Summary

| Version | Release Date | Type | Highlights |
|---------|--------------|------|------------|
| 1.0.0-beta | 2025-11-23 | Beta | Initial public beta with core features |
| Phase 1 | Q1 2025 | Stable | Open source release |
| Phase 2 | Q2 2025 | Feature | AI and cloud features |

---

## Upgrade Notes

### From Pre-Beta to v1.0.0-beta

This is the first public release. No upgrade path from previous versions.

### Future: From v1.0.0-beta to Phase 1

When Phase 1 launches:
- No data migration required
- Existing installations will continue working
- New AGPLv3 license will apply
- Optional update to Phase 1 binaries recommended

---

## Feedback and Bug Reports

Found a bug or have feedback? We'd love to hear from you:

- 🐛 [Report a bug](https://github.com/sandriverfish/avsign-lite/issues/new?template=bug_report.yml)
- 💡 [Request a feature](https://github.com/sandriverfish/avsign-lite/issues/new?template=feature_request.yml)
- 📧 Email: sandriverfish@gmail.com

---

## Legend

- `Added` - New features
- `Changed` - Changes in existing functionality
- `Deprecated` - Soon-to-be removed features
- `Removed` - Removed features
- `Fixed` - Bug fixes
- `Security` - Security fixes and improvements

---

Last updated: 2025-11-23
