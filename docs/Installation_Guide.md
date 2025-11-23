# avSign.lite Installation Guide

**Version**: 1.0.0-beta (Phase 0)
**Last Updated**: 2025-11-23

---

## Table of Contents

1. [System Requirements](#system-requirements)
2. [Windows Installation](#windows-installation)
3. [Android Installation](#android-installation)
4. [Linux Installation](#linux-installation)
5. [Post-Installation Setup](#post-installation-setup)
6. [Troubleshooting](#troubleshooting)

---

## System Requirements

### Windows

- **Operating System**: Windows 10 (64-bit) or later
- **Processor**: Intel Core i3 or equivalent
- **RAM**: 4 GB minimum, 8 GB recommended
- **Storage**: 500 MB free disk space
- **Display**: 1024x768 minimum resolution
- **Graphics**: DirectX 11 compatible graphics card
- **Network**: Not required (offline-capable)

### Android

- **Operating System**: Android 5.0 (Lollipop) or later
- **Processor**: Quad-core 1.5 GHz or better
- **RAM**: 2 GB minimum, 4 GB recommended
- **Storage**: 200 MB free disk space
- **Display**: 720p (1280x720) or higher
- **Permissions**: Storage access for media files

### Linux

- **Operating System**: Ubuntu 20.04 or later (or equivalent)
- **Processor**: Intel Core i3 or equivalent
- **RAM**: 4 GB minimum, 8 GB recommended
- **Storage**: 500 MB free disk space
- **Display**: 1024x768 minimum resolution
- **Dependencies**: GTK 3.0+, GLIBC 2.31+
- **Network**: Not required (offline-capable)

---

## Windows Installation

### Download

1. Go to the [Releases page](https://github.com/sandriverfish/avsign-lite/releases)
2. Download the latest Windows installer:
   - File name: `avsign-lite-v1.0.0-beta-windows.zip` or `.exe`
3. Save to your Downloads folder

### Installation Steps

#### If Downloaded as ZIP:

1. **Extract the ZIP file**
   - Right-click on `avsign-lite-v1.0.0-beta-windows.zip`
   - Select "Extract All..."
   - Choose destination folder (e.g., `C:\Program Files\avSign.lite\`)
   - Click "Extract"

2. **Run the Application**
   - Navigate to extracted folder
   - Double-click `avsign-lite.exe` or `runner.exe`
   - If Windows SmartScreen appears:
     - Click "More info"
     - Click "Run anyway"

#### If Downloaded as EXE Installer:

1. **Run the Installer**
   - Double-click `avsign-lite-v1.0.0-beta-windows.exe`
   - If UAC prompt appears, click "Yes" (requires admin rights)

2. **Follow Installation Wizard**
   - Welcome screen → Click "Next"
   - Choose installation directory → Click "Next"
   - Create shortcuts (optional) → Click "Next"
   - Click "Install"
   - Wait for installation to complete
   - Click "Finish"

3. **Launch Application**
   - Desktop shortcut: Double-click "avSign.lite"
   - Start Menu: Search for "avSign.lite" → Click to launch

### First Run on Windows

1. **Application launches** and starts local server
2. **Firewall prompt** may appear:
   - Click "Allow access" for private networks
   - ⚠️ Do NOT allow public network access unless needed
3. **Browser opens automatically** to `http://localhost:8080`
4. **Login** with default credentials (see [Post-Installation Setup](#post-installation-setup))

### Windows Troubleshooting

**"Windows protected your PC" message:**
- Click "More info" → "Run anyway"
- This is a false positive for unsigned applications

**Application won't start:**
- Right-click → "Run as administrator"
- Check if port 8080 is already in use
- Disable antivirus temporarily to test

**Firewall blocking:**
- Windows Settings → Update & Security → Windows Security → Firewall & network protection
- Allow app through firewall → Find "avSign.lite" → Check "Private"

---

## Android Installation

### Download

1. **On your Android device**, go to:
   - [Releases page](https://github.com/sandriverfish/avsign-lite/releases)
2. **Download** the latest APK:
   - File name: `avsign-lite-v1.0.0-beta.apk`
3. APK will save to your Downloads folder

### Enable Installation from Unknown Sources

**Android 8.0 and later:**
1. Settings → Apps & notifications
2. Advanced → Special app access
3. Install unknown apps
4. Select your browser (e.g., Chrome)
5. Toggle "Allow from this source"

**Android 7.1 and earlier:**
1. Settings → Security
2. Enable "Unknown sources"
3. Tap "OK" on warning

### Installation Steps

1. **Open the APK**
   - Open Downloads app or File Manager
   - Tap on `avsign-lite-v1.0.0-beta.apk`

2. **Install Application**
   - Tap "Install"
   - Wait for installation to complete
   - Tap "Open" or find app in app drawer

3. **Grant Permissions**
   - Storage permission: Tap "Allow" (needed for media files)
   - Other permissions: Grant as requested

### First Run on Android

1. **Launch app** from app drawer
2. **App starts** local server on port 8080
3. **Access admin interface**:
   - Open Chrome or other browser
   - Navigate to: `http://localhost:8080`
4. **Login** with default credentials

### Android Troubleshooting

**"App not installed" error:**
- Ensure "Unknown sources" is enabled
- Check available storage space (need 200+ MB free)
- Uninstall any previous version first

**App crashes on startup:**
- Clear app data: Settings → Apps → avSign.lite → Clear data
- Restart device
- Reinstall app

**Can't access admin interface:**
- Ensure app is running (check notifications)
- Try `http://127.0.0.1:8080` instead of localhost
- Clear browser cache

---

## Linux Installation

### Download

1. Go to [Releases page](https://github.com/sandriverfish/avsign-lite/releases)
2. Download: `avsign-lite-v1.0.0-beta-linux.tar.gz`
3. Save to your home directory or Downloads

### Install Dependencies (Ubuntu/Debian)

```bash
# Update package list
sudo apt update

# Install required dependencies
sudo apt install -y libgtk-3-0 libglu1-mesa libmpv-dev

# Optional: Install video codecs
sudo apt install -y ubuntu-restricted-extras
```

### Installation Steps

1. **Extract the archive**
```bash
cd ~/Downloads
tar -xzf avsign-lite-v1.0.0-beta-linux.tar.gz
```

2. **Move to installation directory** (optional)
```bash
sudo mv avsign-lite /opt/
cd /opt/avsign-lite
```

3. **Make executable**
```bash
chmod +x avsign-lite
```

4. **Run the application**
```bash
./avsign-lite
```

### Create Desktop Launcher (Optional)

Create file: `~/.local/share/applications/avsign-lite.desktop`

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=avSign.lite
Comment=Digital Signage Platform
Exec=/opt/avsign-lite/avsign-lite
Icon=/opt/avsign-lite/icon.png
Terminal=false
Categories=Utility;Application;
```

### First Run on Linux

1. **Application starts** local server
2. **Browser opens** to `http://localhost:8080`
   - If browser doesn't open, manually navigate to the URL
3. **Login** with default credentials

### Linux Troubleshooting

**Missing dependencies error:**
```bash
# Check missing libraries
ldd /opt/avsign-lite/avsign-lite | grep "not found"

# Install missing libraries (example)
sudo apt install -y libgtk-3-0 libmpv1
```

**Permission denied:**
```bash
chmod +x /opt/avsign-lite/avsign-lite
```

**Port 8080 already in use:**
```bash
# Check what's using port 8080
sudo lsof -i :8080

# Kill the process (if safe to do so)
sudo kill -9 <PID>
```

---

## Post-Installation Setup

### First Login

1. **Access admin interface** in browser: `http://localhost:8080`

2. **Login credentials**:
   - Username: `admin`
   - Password: `admin`

3. ⚠️ **IMPORTANT: Change default password immediately**
   - Go to Settings → User Management
   - Click on "admin" user
   - Click "Change Password"
   - Enter new secure password
   - Click "Save"

### Initial Configuration

**Set Display Resolution:**
1. Go to Settings → Display
2. Set default resolution (e.g., 1920x1080)
3. Click "Save"

**Add Your First Terminal:**
1. Go to Terminals → Add Terminal
2. Name: "Main Display"
3. Resolution: Your screen resolution
4. Click "Save"

**Upload Sample Content:**
1. Go to Resources → Upload
2. Upload test images or videos
3. Create a simple layout to test

### Verify Installation

✅ **Checklist:**
- [ ] Application launches without errors
- [ ] Admin interface accessible at http://localhost:8080
- [ ] Can login successfully
- [ ] Password changed from default
- [ ] Can upload a test image
- [ ] Can create a simple layout
- [ ] Can create and publish a program

---

## Troubleshooting

### General Issues

**Application won't start:**
1. Check system requirements
2. Verify all dependencies installed (Linux)
3. Check if port 8080 is available
4. Review application logs (if available)

**Can't access admin interface:**
1. Verify application is running
2. Check browser URL: `http://localhost:8080` (not https)
3. Try `http://127.0.0.1:8080`
4. Disable browser extensions temporarily
5. Clear browser cache

**Slow performance:**
1. Close other applications
2. Check available RAM (should have 2GB+ free)
3. Reduce media file sizes
4. Clear application cache in Settings

### Platform-Specific Issues

**Windows: Antivirus blocking**
- Add avSign.lite to antivirus exceptions
- Temporarily disable antivirus to test

**Android: Battery optimization**
- Settings → Battery → Battery optimization
- Find avSign.lite → Select "Don't optimize"

**Linux: GTK theme issues**
- Install GTK 3.0 theme package
- Set GTK_THEME environment variable

---

## Uninstallation

### Windows

**Via Programs and Features:**
1. Windows Settings → Apps
2. Find "avSign.lite"
3. Click → Uninstall
4. Follow prompts

**Manual Removal:**
1. Delete installation folder
2. Delete shortcuts (Desktop, Start Menu)
3. Delete data folder: `%APPDATA%\avSign.lite\`

### Android

1. Settings → Apps
2. Find "avSign.lite"
3. Tap → Uninstall

### Linux

```bash
# Remove application
sudo rm -rf /opt/avsign-lite

# Remove desktop launcher
rm ~/.local/share/applications/avsign-lite.desktop

# Remove data (optional)
rm -rf ~/.local/share/avsign-lite
```

---

## Next Steps

After successful installation:

1. **Read the** [Quick Start Guide](Quick_Start.md) to get started quickly
2. **Review the** [User Guide](User_Guide.md) for detailed usage
3. **Check** [FAQ](FAQ.md) for common questions

---

## Getting Help

### Support Resources

- **Quick Start**: [Quick Start Guide](Quick_Start.md)
- **User Manual**: [User Guide](User_Guide.md)
- **Common Issues**: [Troubleshooting Guide](Troubleshooting.md)
- **FAQ**: [Frequently Asked Questions](FAQ.md)

### Contact Support

- **GitHub Issues**: [Report installation problems](https://github.com/sandriverfish/avsign-lite/issues)
- **Email**: sandriverfish@gmail.com
- **Discussions**: [GitHub Discussions](https://github.com/sandriverfish/avsign-lite/discussions)

---

**Installation Complete!** 🎉

Your avSign.lite installation is ready. Proceed to the [Quick Start Guide](Quick_Start.md) to create your first display.
