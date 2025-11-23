# Build Release Binaries for Phase 0

**Target Platforms**: Windows and Android
**Version**: v1.0.0-beta

---

## Prerequisites

### Required Tools

**For Windows:**
- Flutter SDK 3.24.3+
- Visual Studio 2019+ with C++ tools
- Rust toolchain (for super_native_extensions)

**For Android:**
- Flutter SDK 3.24.3+
- Android SDK
- Java JDK 17+

### Verify Setup

```bash
# Check Flutter version
flutter --version

# Check Flutter doctor
flutter doctor -v
```

---

## Step 1: Prepare the Codebase

```bash
# Navigate to main project directory
cd D:\avsign-lite

# Clean previous builds
flutter clean

# Get dependencies
flutter pub get

# Run code generation (if needed)
flutter packages pub run build_runner build --delete-conflicting-outputs
```

---

## Step 2: Build Windows Release

### Build Command

```bash
# Build Windows release
flutter build windows --release
```

**Output Location:**
```
D:\avsign-lite\build\windows\x64\runner\Release\
```

### Package Windows Binary

**Option 1: Create ZIP archive (Recommended)**

```powershell
# Navigate to Release folder
cd D:\avsign-lite\build\windows\x64\runner\Release

# Create ZIP using PowerShell
Compress-Archive -Path * -DestinationPath "D:\avsign-lite\phase0-release\binaries\avsign-lite-v1.0.0-beta-windows.zip" -Force
```

**Option 2: Create Installer (Advanced)**

If you have Inno Setup or NSIS installed, you can create an EXE installer. For Phase 0, ZIP is sufficient.

### Verify Windows Build

1. Extract ZIP to test folder
2. Run `avsign-lite.exe` or `runner.exe`
3. Verify application starts
4. Access http://localhost:8080
5. Test basic functionality

**Expected Size:** ~120-150 MB (compressed)

---

## Step 3: Build Android Release

### Build APK

```bash
# Navigate to project root
cd D:\avsign-lite

# Build release APK
flutter build apk --release
```

**Output Location:**
```
D:\avsign-lite\build\app\outputs\flutter-apk\app-release.apk
```

### Rename and Move APK

```bash
# Copy and rename APK
copy "D:\avsign-lite\build\app\outputs\flutter-apk\app-release.apk" "D:\avsign-lite\phase0-release\binaries\avsign-lite-v1.0.0-beta.apk"
```

### (Optional) Build App Bundle (for Play Store)

```bash
# Build App Bundle
flutter build appbundle --release
```

**Output:**
```
D:\avsign-lite\build\app\outputs\bundle\release\app-release.aab
```

### Verify Android Build

1. Transfer APK to Android device
2. Install APK (enable unknown sources)
3. Launch app
4. Verify functionality

**Expected Size:** ~80-100 MB

---

## Step 4: Calculate SHA256 Checksums

For security, provide SHA256 checksums in GitHub release.

**Windows (PowerShell):**
```powershell
# Navigate to binaries folder
cd D:\avsign-lite\phase0-release\binaries

# Calculate checksums
Get-FileHash avsign-lite-v1.0.0-beta-windows.zip -Algorithm SHA256
Get-FileHash avsign-lite-v1.0.0-beta.apk -Algorithm SHA256
```

**Output Format:**
```
Algorithm       Hash                                                                   Path
---------       ----                                                                   ----
SHA256          ABC123...                                                              avsign-lite-v1.0.0-beta-windows.zip
SHA256          DEF456...                                                              avsign-lite-v1.0.0-beta.apk
```

**Save these checksums** - you'll add them to the GitHub Release description.

---

## Step 5: Organize Binaries

Create binaries folder structure:

```bash
mkdir D:\avsign-lite\phase0-release\binaries
```

**Final structure:**
```
phase0-release\binaries\
├── avsign-lite-v1.0.0-beta-windows.zip    (~120-150 MB)
├── avsign-lite-v1.0.0-beta.apk            (~80-100 MB)
└── checksums.txt                          (SHA256 hashes)
```

**Create checksums.txt:**
```txt
avsign-lite-v1.0.0-beta-windows.zip
SHA256: [paste hash here]

avsign-lite-v1.0.0-beta.apk
SHA256: [paste hash here]
```

---

## Troubleshooting

### Windows Build Issues

**"Rust toolchain not found":**
```bash
# Install Rust from https://rustup.rs/
# Then restart terminal and rebuild
```

**"Visual Studio not found":**
- Install Visual Studio 2019+ with "Desktop development with C++"
- Or install Build Tools for Visual Studio 2019

**"Missing dependencies":**
```bash
flutter doctor -v
# Fix any issues shown
```

### Android Build Issues

**"SDK not found":**
- Set ANDROID_HOME environment variable
- Point to Android SDK location

**"Java version mismatch":**
```bash
# Use Java JDK 17
java -version
```

**"Signing error":**
- For Phase 0 beta, debug signing is fine
- Use `--release` flag as shown above

**"Out of memory":**
- Increase gradle memory in `android/gradle.properties`:
```properties
org.gradle.jvmargs=-Xmx4096M -XX:MaxPermSize=512m
```

---

## Build Checklist

### Pre-Build
- [ ] Flutter doctor shows no critical issues
- [ ] All dependencies installed (flutter pub get)
- [ ] Code generation complete (if needed)
- [ ] Clean build (flutter clean)

### Windows Build
- [ ] Build completed successfully
- [ ] ZIP archive created
- [ ] Binary verified (runs and starts server)
- [ ] Size reasonable (~120-150 MB)
- [ ] SHA256 checksum calculated

### Android Build
- [ ] APK build completed successfully
- [ ] APK renamed appropriately
- [ ] APK verified (installs and runs)
- [ ] Size reasonable (~80-100 MB)
- [ ] SHA256 checksum calculated

### Post-Build
- [ ] Both binaries in `binaries/` folder
- [ ] checksums.txt created
- [ ] Binaries NOT committed to git (use .gitignore)
- [ ] Ready to upload to GitHub Release

---

## Next Steps

After building binaries:

1. **Verify builds work** on test devices
2. **Upload to GitHub Release** (see PHASE0_SETUP_SCRIPT.md Step 9)
3. **Update README.md** with actual file sizes and checksums
4. **Test download links** after release is published

---

## Important Notes

### Do NOT Commit Binaries to Git

Binaries should be uploaded to GitHub Releases, NOT committed to the repository.

**Verify .gitignore excludes:**
```gitignore
*.exe
*.zip
*.apk
*.aab
binaries/
```

### File Size Guidelines

If your binaries are significantly larger than expected:
- **Windows**: Check if debug symbols are included (should be stripped in release)
- **Android**: Verify release build (not debug)
- **Both**: Check if unnecessary assets are bundled

### Version Consistency

Ensure version matches across:
- `pubspec.yaml`: `version: 1.0.0+1`
- Binary filenames: `v1.0.0-beta`
- GitHub Release tag: `v1.0.0-beta`
- CHANGELOG.md: `[1.0.0-beta]`

---

## Quick Reference

**Build Commands:**
```bash
# Windows
flutter build windows --release

# Android
flutter build apk --release
```

**Package Commands:**
```powershell
# Windows ZIP
Compress-Archive -Path D:\avsign-lite\build\windows\x64\runner\Release\* -DestinationPath D:\avsign-lite\phase0-release\binaries\avsign-lite-v1.0.0-beta-windows.zip

# Android APK (rename)
copy D:\avsign-lite\build\app\outputs\flutter-apk\app-release.apk D:\avsign-lite\phase0-release\binaries\avsign-lite-v1.0.0-beta.apk
```

**Checksum Commands:**
```powershell
Get-FileHash avsign-lite-v1.0.0-beta-windows.zip -Algorithm SHA256
Get-FileHash avsign-lite-v1.0.0-beta.apk -Algorithm SHA256
```

---

**Ready to build?** Follow the steps above, then proceed to PHASE0_SETUP_SCRIPT.md Step 9 to create the GitHub Release.

**Estimated Build Time:** 30-60 minutes (depending on hardware)
