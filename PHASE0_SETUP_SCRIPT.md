# Phase 0 Repository Setup Script

This guide walks you through setting up your Phase 0 public repository on GitHub.

---

## Prerequisites

- [ ] Git installed on your system
- [ ] GitHub account: https://github.com/sandriverfish
- [ ] Release binaries built (Windows, Android, Linux)
- [ ] Screenshots captured and ready

---

## Step 1: Verify Phase 0 Files

Check that you have all Phase 0 files ready:

```bash
cd D:\avsign-lite\phase0-release

# List all files
dir /s
```

**Expected structure:**
```
phase0-release/
├── README.md                  ✓ Created
├── LICENSE                    ✓ Created
├── CHANGELOG.md               ✓ Created
├── .gitignore                 ✓ Created
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.yml     ✓ Created
│       ├── feature_request.yml ✓ Created
│       └── config.yml         ✓ Created
├── docs/                      ⚠️ TODO: Add user documentation
└── screenshots/               ⚠️ TODO: Add screenshots
```

---

## Step 2: Add Documentation Files

Create simplified user documentation (NO developer docs!):

```bash
# Create docs directory
mkdir docs
cd docs
```

**Required docs** (copy from your main project, remove technical details):
- `User_Guide.md` - How to use the app
- `Installation_Guide.md` - Platform-specific installation
- `Quick_Start.md` - 5-minute getting started
- `Troubleshooting.md` - Common issues
- `FAQ.md` - Frequently asked questions

**Command to copy and simplify:**
```bash
# Copy from main project (you'll need to simplify these manually)
copy D:\avsign-lite\docs\USER_MANUAL.md D:\avsign-lite\phase0-release\docs\User_Guide.md
# ... edit to remove technical/developer content
```

---

## Step 3: Add Screenshots

```bash
mkdir screenshots
cd screenshots
```

**Required screenshots:**
1. `dashboard.png` - Main dashboard/resource list
2. `layout-editor.png` - Visual layout editor in action
3. `display-mode.png` - Full-screen display mode
4. `settings.png` - Settings screen

**How to capture:**
- Run your app on Windows/Android
- Navigate to each screen
- Take high-quality screenshots (1920x1080 recommended)
- Save as PNG format
- Copy to `phase0-release/screenshots/`

---

## Step 4: Initialize Git Repository

```bash
cd D:\avsign-lite\phase0-release

# Initialize git
git init
git branch -M main

# Add all files
git add .

# Initial commit
git commit -m "Initial Phase 0 release - Binaries and documentation"
```

---

## Step 5: Create GitHub Repository

**On GitHub** (https://github.com/sandriverfish):

1. Click **"New repository"** (or go to https://github.com/new)

2. **Repository settings:**
   - Repository name: `avsign-lite`
   - Description: `AI-enhanced digital signage platform - Beta binaries and documentation`
   - Visibility: **✅ Public**
   - **❌ DO NOT** initialize with README, .gitignore, or license (we have them already)

3. Click **"Create repository"**

4. **Copy the remote URL** shown (should be like):
   ```
   https://github.com/sandriverfish/avsign-lite.git
   ```

---

## Step 6: Push to GitHub

```bash
# Add remote
git remote add origin https://github.com/sandriverfish/avsign-lite.git

# Push to GitHub
git push -u origin main
```

**If you get authentication errors:**
- Use GitHub Personal Access Token (PAT) instead of password
- Or use GitHub Desktop app
- Or use SSH key authentication

---

## Step 7: Configure Repository Settings

**On GitHub** (https://github.com/sandriverfish/avsign-lite/settings):

### General Settings

1. **Features:**
   - ✅ Issues (enable)
   - ✅ Discussions (enable for community Q&A)
   - ❌ Wiki (disable - not needed for Phase 0)
   - ❌ Projects (disable)
   - ❌ Sponsorships (optional)

2. **Pull Requests:**
   - ❌ Allow merge commits (disable - not accepting PRs in Phase 0)
   - ❌ Allow squash merging (disable)
   - ❌ Allow rebase merging (disable)

### Repository Details

Update the "About" section (top-right of main page):

- **Description**: `AI-enhanced digital signage - Phase 0 Beta`
- **Website**: (leave blank or add https://avsign.com if you have one)
- **Topics**: Add tags:
  - `digital-signage`
  - `flutter`
  - `signage`
  - `display-management`
  - `beta`
  - `offline-first`
  - `cross-platform`

---

## Step 8: Build Release Binaries

**On your main codebase** (D:\avsign-lite):

```bash
cd D:\avsign-lite

# Clean first
flutter clean
flutter pub get

# Build Windows
flutter build windows --release
# Output: build/windows/x64/runner/Release/

# Build Android
flutter build apk --release
# Output: build/app/outputs/flutter-apk/app-release.apk

# Build Linux (optional)
flutter build linux --release
# Output: build/linux/x64/release/bundle/
```

**Package the binaries:**

```bash
# Windows - create installer or zip
# For now, zip the Release folder
cd build/windows/x64/runner/Release
powershell Compress-Archive -Path * -DestinationPath avsign-lite-v1.0.0-beta-windows.zip

# Android - rename APK
copy build\app\outputs\flutter-apk\app-release.apk avsign-lite-v1.0.0-beta.apk

# Linux - create tar.gz
cd build/linux/x64/release/bundle
tar -czf avsign-lite-v1.0.0-beta-linux.tar.gz *
```

---

## Step 9: Create GitHub Release

**On GitHub** (https://github.com/sandriverfish/avsign-lite/releases):

1. Click **"Create a new release"**

2. **Release details:**
   - **Tag version**: `v1.0.0-beta` (create new tag)
   - **Target**: `main` branch
   - **Release title**: `v1.0.0-beta - Phase 0 Public Beta`

3. **Description** (copy this):

```markdown
## avSign.lite v1.0.0-beta

**Phase 0 Public Beta** - First release with compiled binaries for testing.

### ✨ Features

- 🖼️ Resource management (images, videos)
- 🎨 Visual layout editor with drag-and-drop
- 📋 Template library (full screen, PIP, quad dashboard, etc.)
- 🎬 Program/playlist creation
- 📱 Multi-platform support (Windows, Android, Linux)
- 🔌 Offline-first architecture

### 📦 Downloads

| Platform | File | Size |
|----------|------|------|
| Windows | avsign-lite-v1.0.0-beta-windows.zip | ~XX MB |
| Android | avsign-lite-v1.0.0-beta.apk | ~XX MB |
| Linux | avsign-lite-v1.0.0-beta-linux.tar.gz | ~XX MB |

### 📖 Documentation

- [User Guide](https://github.com/sandriverfish/avsign-lite/blob/main/docs/User_Guide.md)
- [Installation Guide](https://github.com/sandriverfish/avsign-lite/blob/main/docs/Installation_Guide.md)
- [Quick Start](https://github.com/sandriverfish/avsign-lite/blob/main/docs/Quick_Start.md)

### 🐛 Known Issues

- Windows 11 may require administrator rights for installation
- Large video files (>500MB) may take time to load
- Layout editor may lag on older Android devices (<2GB RAM)

### 🙏 Beta Testers

Thank you for testing! Please report issues at:
https://github.com/sandriverfish/avsign-lite/issues

---

**⚠️ This is a beta release** - Please use with caution and backup your data.
```

4. **Upload binaries**: Drag and drop your compiled files:
   - `avsign-lite-v1.0.0-beta-windows.zip`
   - `avsign-lite-v1.0.0-beta.apk`
   - `avsign-lite-v1.0.0-beta-linux.tar.gz`

5. **Options:**
   - ✅ Check **"This is a pre-release"**
   - ❌ Don't check "Create a discussion" (yet)

6. Click **"Publish release"**

---

## Step 10: Update README with Actual Links

After creating the release, update the download links in README.md:

```bash
cd D:\avsign-lite\phase0-release

# Edit README.md and replace download links with actual GitHub release URLs
# Example:
# https://github.com/sandriverfish/avsign-lite/releases/download/v1.0.0-beta/avsign-lite-v1.0.0-beta-windows.zip
```

**Commit and push the update:**

```bash
git add README.md
git commit -m "docs: Update download links with release URLs"
git push
```

---

## Step 11: Calculate SHA256 Checksums

For security, provide SHA256 checksums in README:

**On Windows (PowerShell):**
```powershell
Get-FileHash avsign-lite-v1.0.0-beta-windows.zip -Algorithm SHA256
Get-FileHash avsign-lite-v1.0.0-beta.apk -Algorithm SHA256
Get-FileHash avsign-lite-v1.0.0-beta-linux.tar.gz -Algorithm SHA256
```

**Update README.md** with checksums and push again.

---

## Step 12: Enable GitHub Discussions

**On GitHub** (https://github.com/sandriverfish/avsign-lite/settings):

1. Scroll to **"Features"**
2. ✅ Check **"Discussions"**
3. Click **"Set up discussions"**

**Create welcome discussion:**
- Title: "Welcome to avSign.lite Phase 0 Beta!"
- Category: Announcements
- Content:
```markdown
Welcome to the avSign.lite beta!

Thanks for your interest in testing our digital signage platform.

## How to Get Started

1. Download the beta for your platform from [Releases](https://github.com/sandriverfish/avsign-lite/releases)
2. Follow the [Installation Guide](docs/Installation_Guide.md)
3. Report bugs via [Issues](https://github.com/sandriverfish/avsign-lite/issues)

## What We're Looking For

- Installation feedback
- Bug reports
- Feature suggestions
- Use case ideas

Looking forward to your feedback!
```

---

## Step 13: Announce the Beta

**Optional announcement channels:**

1. **Reddit:**
   - r/digitalsignage
   - r/selfhosted
   - r/FlutterDev (if relevant)

2. **Twitter/X:**
   - Create account @avsignlite
   - Tweet announcement with screenshots

3. **Email:**
   - If you have an email list, send announcement

**Sample announcement:**
```
🚀 Introducing avSign.lite v1.0.0-beta!

AI-enhanced digital signage platform, now in public beta.

✨ Features:
- Offline-first architecture
- Visual layout editor
- Multi-platform (Windows, Android, Linux)
- Free and open-source (soon)

Download: https://github.com/sandriverfish/avsign-lite/releases

Your feedback appreciated! 🙏
```

---

## Verification Checklist

Before considering Phase 0 launch complete:

- [ ] Repository is public and accessible
- [ ] README looks professional (with screenshots)
- [ ] All documentation files are present
- [ ] GitHub Release is published with binaries
- [ ] Download links in README work
- [ ] Issue templates work correctly
- [ ] Discussions are enabled
- [ ] Repository topics/tags are set
- [ ] License file is present
- [ ] CHANGELOG is up to date

---

## Next Steps After Launch

**Week 1:**
- Monitor GitHub issues daily
- Respond to questions and feedback
- Fix critical bugs immediately

**Week 2-4:**
- Collect feedback and testimonials
- Update documentation based on common questions
- Plan bug fix release if needed

**Week 5-8:**
- Prepare for Phase 1 transition
- Fix all critical issues
- Finalize open-source release plan

---

## Need Help?

If you encounter issues during setup:

1. Check GitHub documentation: https://docs.github.com
2. Ask in GitHub Discussions (after setup)
3. Contact: sandriverfish@gmail.com

---

**Good luck with your Phase 0 launch! 🚀**
