# Phase 0 Launch Checklist

**Version**: v1.0.0-beta
**Target**: Windows + Android
**Repository**: https://github.com/sandriverfish/avsign-lite

---

## ✅ Completed Preparation

- [x] README.md created with professional content
- [x] LICENSE (Beta) created
- [x] CHANGELOG.md created
- [x] .gitignore configured
- [x] GitHub issue templates created
- [x] All 5 user documentation files written
- [x] **Screenshots captured and copied** (4 images, 736 KB total)
- [x] BUILD_BINARIES.md guide created

---

## 🔨 Step 1: Build Release Binaries

### Windows Binary

```bash
# Navigate to main project
cd D:\avsign-lite

# Clean and prepare
flutter clean
flutter pub get

# Build Windows release
flutter build windows --release

# Package as ZIP
cd build\windows\x64\runner\Release
powershell Compress-Archive -Path * -DestinationPath "D:\avsign-lite\phase0-release\binaries\avsign-lite-v1.0.0-beta-windows.zip" -Force
```

**Checklist:**
- [ ] Build completed without errors
- [ ] ZIP created (~120-150 MB)
- [ ] Tested: ZIP extracts and runs
- [ ] Verified: http://localhost:8080 accessible

### Android Binary

```bash
# Build Android APK
cd D:\avsign-lite
flutter build apk --release

# Copy and rename
mkdir D:\avsign-lite\phase0-release\binaries
copy "build\app\outputs\flutter-apk\app-release.apk" "D:\avsign-lite\phase0-release\binaries\avsign-lite-v1.0.0-beta.apk"
```

**Checklist:**
- [ ] Build completed without errors
- [ ] APK copied (~80-100 MB)
- [ ] Tested: APK installs on Android device
- [ ] Verified: App runs and server starts

### Calculate Checksums

```powershell
cd D:\avsign-lite\phase0-release\binaries

Get-FileHash avsign-lite-v1.0.0-beta-windows.zip -Algorithm SHA256
Get-FileHash avsign-lite-v1.0.0-beta.apk -Algorithm SHA256
```

**Checklist:**
- [ ] Windows SHA256 calculated
- [ ] Android SHA256 calculated
- [ ] Checksums saved to checksums.txt

---

## 📁 Step 2: Initialize Git Repository

```bash
cd D:\avsign-lite\phase0-release

# Initialize git
git init
git branch -M main

# Add all files EXCEPT binaries
git add .

# Verify binaries are NOT staged
git status
# Should NOT show .zip or .apk files

# Initial commit
git commit -m "Initial Phase 0 release - Documentation and screenshots"
```

**Checklist:**
- [ ] Git initialized
- [ ] All files added (except binaries/)
- [ ] Binaries confirmed NOT in git (check .gitignore)
- [ ] Initial commit created

---

## 🌐 Step 3: Create GitHub Repository

1. Go to https://github.com/new
2. **Repository name**: `avsign-lite`
3. **Description**: `AI-enhanced digital signage platform - Beta binaries and documentation`
4. **Visibility**: ✅ **Public**
5. **DO NOT** initialize with README, .gitignore, or license
6. Click **"Create repository"**

**Checklist:**
- [ ] Repository created on GitHub
- [ ] Repository is public
- [ ] Remote URL copied

---

## 📤 Step 4: Push to GitHub

```bash
# Add remote (replace with your actual URL)
git remote add origin https://github.com/sandriverfish/avsign-lite.git

# Push to GitHub
git push -u origin main
```

**Checklist:**
- [ ] Files pushed to GitHub
- [ ] README displays correctly on GitHub
- [ ] Screenshots visible in README
- [ ] Documentation accessible

---

## 🎁 Step 5: Create GitHub Release

1. Go to https://github.com/sandriverfish/avsign-lite/releases
2. Click **"Create a new release"**

**Release Configuration:**
- **Tag**: `v1.0.0-beta` (create new tag)
- **Target**: `main` branch
- **Title**: `v1.0.0-beta - Phase 0 Public Beta`

**Description** (copy this):

```markdown
## avSign.lite v1.0.0-beta

**Phase 0 Public Beta** - First release with compiled binaries for testing.

### ✨ Features

- 🖼️ Resource management (images, videos)
- 🎨 Visual layout editor with drag-and-drop
- 📋 Template library (full screen, PIP, quad dashboard, etc.)
- 🎬 Program/playlist creation
- 📱 Multi-platform support (Windows, Android)
- 🔌 Offline-first architecture

### 📦 Downloads

| Platform | File | Size | SHA256 |
|----------|------|------|--------|
| Windows | [avsign-lite-v1.0.0-beta-windows.zip](https://github.com/sandriverfish/avsign-lite/releases/download/v1.0.0-beta/avsign-lite-v1.0.0-beta-windows.zip) | ~XXX MB | `[PASTE_CHECKSUM]` |
| Android | [avsign-lite-v1.0.0-beta.apk](https://github.com/sandriverfish/avsign-lite/releases/download/v1.0.0-beta/avsign-lite-v1.0.0-beta.apk) | ~XXX MB | `[PASTE_CHECKSUM]` |

### 📖 Documentation

- [User Guide](https://github.com/sandriverfish/avsign-lite/blob/main/docs/User_Guide.md)
- [Installation Guide](https://github.com/sandriverfish/avsign-lite/blob/main/docs/Installation_Guide.md)
- [Quick Start](https://github.com/sandriverfish/avsign-lite/blob/main/docs/Quick_Start.md)
- [Troubleshooting](https://github.com/sandriverfish/avsign-lite/blob/main/docs/Troubleshooting.md)
- [FAQ](https://github.com/sandriverfish/avsign-lite/blob/main/docs/FAQ.md)

### 🐛 Known Issues

- Windows 11 may require administrator rights for installation
- Large video files (>500MB) may take time to load
- Layout editor: Manual zone positioning required (no snap-to-grid yet)

### 🙏 Beta Testers

Thank you for testing! Please report issues at:
https://github.com/sandriverfish/avsign-lite/issues

### ⚠️ Important Notes

- **This is a beta release** - Use with caution and backup your data
- **Source code** will be released in Phase 1 (Q1 2025) under AGPLv3
- **Default credentials**: admin/admin123 (change immediately after login!)

---

**⭐ Star this repo** if you find avSign.lite useful!
```

3. **Upload binaries** (drag and drop):
   - `avsign-lite-v1.0.0-beta-windows.zip`
   - `avsign-lite-v1.0.0-beta.apk`

4. Check **✅ "This is a pre-release"**

5. Click **"Publish release"**

**Checklist:**
- [ ] Release created with tag v1.0.0-beta
- [ ] Windows ZIP uploaded
- [ ] Android APK uploaded
- [ ] SHA256 checksums added to description
- [ ] File sizes updated in description
- [ ] Marked as pre-release
- [ ] Release published

---

## 📝 Step 6: Update README with Real Links

After release is published, update README.md with actual file sizes and checksums:

```bash
cd D:\avsign-lite\phase0-release

# Edit README.md
# Update download table with:
# - Actual file sizes
# - SHA256 checksums

git add README.md
git commit -m "docs: Update download links with release info"
git push
```

**Checklist:**
- [ ] README updated with actual download links
- [ ] File sizes filled in
- [ ] SHA256 checksums added
- [ ] Changes committed and pushed

---

## ⚙️ Step 7: Configure GitHub Settings

Go to https://github.com/sandriverfish/avsign-lite/settings

### General Settings

**Features:**
- [x] ✅ Issues
- [x] ✅ Discussions
- [ ] ❌ Wiki
- [ ] ❌ Projects

**Pull Requests:**
- [ ] ❌ Allow merge commits (disable - not accepting PRs in Phase 0)

### About Section (Top-right of main page)

- **Description**: `AI-enhanced digital signage - Phase 0 Beta`
- **Topics**: Add tags:
  - `digital-signage`
  - `flutter`
  - `signage`
  - `display-management`
  - `beta`
  - `offline-first`
  - `cross-platform`

**Checklist:**
- [ ] Issues enabled
- [ ] Discussions enabled
- [ ] Wiki disabled
- [ ] Projects disabled (optional)
- [ ] Description set
- [ ] Topics added

---

## 💬 Step 8: Enable Discussions

1. Go to https://github.com/sandriverfish/avsign-lite/settings
2. Scroll to **"Features"**
3. Check **✅ "Discussions"**
4. Click **"Set up discussions"**

**Create Welcome Discussion:**

**Title**: Welcome to avSign.lite Phase 0 Beta!

**Category**: Announcements

**Content**:
```markdown
Welcome to the avSign.lite beta! 🎉

Thanks for your interest in testing our digital signage platform.

## How to Get Started

1. **Download** the beta for your platform from [Releases](https://github.com/sandriverfish/avsign-lite/releases)
2. **Install** following the [Installation Guide](docs/Installation_Guide.md)
3. **Quick Start** with our [5-minute tutorial](docs/Quick_Start.md)
4. **Report bugs** via [Issues](https://github.com/sandriverfish/avsign-lite/issues)

## What We're Looking For

- Installation feedback (was it easy?)
- Bug reports (what broke?)
- Feature suggestions (what's missing?)
- Use case ideas (how are you using it?)

## Support

- 📖 [Documentation](docs/)
- 🐛 [Bug Reports](https://github.com/sandriverfish/avsign-lite/issues/new?template=bug_report.yml)
- 💡 [Feature Requests](https://github.com/sandriverfish/avsign-lite/issues/new?template=feature_request.yml)
- 📧 Email: sandriverfish@gmail.com

Looking forward to your feedback! 🚀
```

**Checklist:**
- [ ] Discussions enabled
- [ ] Welcome discussion created
- [ ] Discussion pinned (optional)

---

## 📣 Step 9: Announce Beta (Optional)

### Reddit

**r/digitalsignage:**
```markdown
[BETA] avSign.lite - Free open-source digital signage platform

Hi everyone! I'm launching the public beta of avSign.lite, a new digital signage platform that works offline-first.

**Key Features:**
- Offline-capable (no internet required)
- Visual layout editor
- Multi-zone displays
- Cross-platform (Windows, Android)
- Free and open-source (AGPLv3 in Q1 2025)

**Download:** https://github.com/sandriverfish/avsign-lite/releases

Looking for beta testers! Feedback appreciated.
```

**r/selfhosted:**
```markdown
[BETA] avSign.lite - Self-hosted digital signage platform

Launching public beta of avSign.lite - an offline-first digital signage platform perfect for self-hosting.

**Features:**
- Runs entirely offline
- No cloud dependencies
- Multi-display support
- Web-based admin interface

**Download:** https://github.com/sandriverfish/avsign-lite/releases

Feedback welcome!
```

### Twitter/X (@sandriverfish)

```
🚀 Launching avSign.lite v1.0.0-beta!

Free, offline-first digital signage platform:
✨ Visual layout editor
📱 Windows + Android
🔌 Works offline
🎨 Template library

Download beta: https://github.com/sandriverfish/avsign-lite/releases

Join our Discord: @avsign.lite

#digitalsignage #opensource #flutter
```

**Checklist:**
- [ ] Posted to r/digitalsignage (optional)
- [ ] Posted to r/selfhosted (optional)
- [ ] Tweeted announcement (optional)

---

## ✅ Final Verification

Before considering launch complete, verify:

### Repository
- [ ] README looks professional with screenshots
- [ ] All documentation links work
- [ ] Issue templates function correctly
- [ ] Discussions enabled and welcoming

### Release
- [ ] Binaries download successfully
- [ ] SHA256 checksums match
- [ ] Windows ZIP extracts and runs
- [ ] Android APK installs and works
- [ ] All documentation links in release work

### Functionality
- [ ] Tested Windows build on fresh machine
- [ ] Tested Android APK on device
- [ ] Verified http://localhost:8080 accessible
- [ ] Tested basic workflow (upload → layout → program → publish)

---

## 🎉 Launch Complete!

**Congratulations!** Your Phase 0 public beta is live.

### Post-Launch Tasks

**Daily (First Week):**
- Monitor GitHub issues
- Respond to questions in Discussions
- Fix critical bugs immediately

**Weekly:**
- Review feedback and plan improvements
- Update documentation based on common questions
- Consider bug fix release if needed

**Monthly:**
- Collect testimonials from satisfied users
- Analyze usage patterns and feedback
- Plan Phase 1 transition (open source release)

---

## Success Metrics

Track these metrics to measure Phase 0 success:

- **GitHub Stars**: Target 20+ in first month
- **Downloads**: Track via release download count
- **Issues**: Aim for <10 critical bugs
- **Engagement**: Active discussions and feedback
- **Testimonials**: Collect 5+ positive reviews

---

**Need Help?**

- **Setup Issues**: See BUILD_BINARIES.md
- **Git Problems**: See PHASE0_SETUP_SCRIPT.md
- **Questions**: Email sandriverfish@gmail.com

---

**Last Updated**: 2025-11-23
**Version**: 1.0 (Phase 0 Launch)
