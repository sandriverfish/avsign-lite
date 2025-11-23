# avSign.lite Troubleshooting Guide

**Version**: 1.0.0-beta (Phase 0)
**Last Updated**: 2025-11-23

---

## Table of Contents

1. [Installation Issues](#installation-issues)
2. [Application Won't Start](#application-wont-start)
3. [Admin Interface Issues](#admin-interface-issues)
4. [Upload and Resource Problems](#upload-and-resource-problems)
5. [Display and Playback Issues](#display-and-playback-issues)
6. [Performance Problems](#performance-problems)
7. [Error Messages](#error-messages)
8. [Platform-Specific Issues](#platform-specific-issues)

---

## Installation Issues

### Windows: "Windows protected your PC" Warning

**Problem**: SmartScreen prevents installation

**Solution**:
1. Click "More info" link
2. Click "Run anyway" button
3. This is normal for unsigned applications

**Alternative**:
- Extract ZIP instead of running EXE
- Run application from extracted folder

---

### Android: "App not installed" Error

**Problem**: Cannot install APK

**Solutions**:

**Enable Unknown Sources:**
1. Settings → Apps & notifications
2. Advanced → Special app access
3. Install unknown apps → Select browser
4. Toggle "Allow from this source"

**Check Storage:**
- Ensure 200+ MB free space
- Settings → Storage → Free up space

**Uninstall Previous Version:**
1. Settings → Apps → avSign.lite
2. Uninstall
3. Reinstall new version

---

### Linux: Missing Dependencies

**Problem**: Application won't start due to missing libraries

**Solution (Ubuntu/Debian)**:
```bash
# Update package list
sudo apt update

# Install dependencies
sudo apt install -y libgtk-3-0 libglu1-mesa libmpv-dev

# Check for missing libraries
ldd /path/to/avsign-lite | grep "not found"
```

**Solution (Fedora/RHEL)**:
```bash
sudo dnf install gtk3 mesa-libGLU mpv-libs
```

---

## Application Won't Start

### Check if Port 8080 is Available

**Windows**:
```cmd
netstat -ano | findstr :8080
```

**Linux/Mac**:
```bash
lsof -i :8080
```

**Solution if port is in use**:
1. Stop the application using port 8080
2. Or configure avSign.lite to use different port (if available in settings)

---

### Antivirus Blocking (Windows)

**Problem**: Antivirus quarantines or blocks application

**Solution**:
1. Open your antivirus software
2. Add avSign.lite to exceptions/whitelist
3. Add installation folder to excluded locations
4. Temporarily disable antivirus to test

**Common antiviruses**:
- Windows Defender: Settings → Virus & threat protection → Exclusions
- Norton: Settings → Antivirus → Exclusions
- McAfee: Settings → Real-Time Scanning → Excluded Files

---

### Permission Errors (Linux)

**Problem**: Permission denied when running application

**Solution**:
```bash
# Make executable
chmod +x /path/to/avsign-lite

# If still fails, run as sudo (not recommended for regular use)
sudo ./avsign-lite
```

---

## Admin Interface Issues

### Can't Access http://localhost:8080

**Problem**: Browser shows "can't reach this page" or "connection refused"

**Solutions**:

**1. Verify application is running:**
- Check if avSign.lite is in task manager/process list
- Look for console window (Windows/Linux)

**2. Try alternative URLs:**
- `http://127.0.0.1:8080`
- `http://[your-computer-ip]:8080`

**3. Check firewall:**
- Windows: Allow app through firewall
- Linux: `sudo ufw allow 8080`

**4. Clear browser cache:**
- Ctrl+Shift+Delete → Clear cache
- Try incognito/private mode

**5. Try different browser:**
- Chrome (recommended)
- Firefox
- Edge

---

### Page Loads but Shows Errors

**Problem**: Admin interface loads with blank page or errors

**Solutions**:

**Clear browser cache:**
1. Ctrl+Shift+Delete
2. Select "Cached images and files"
3. Select "All time"
4. Click "Clear data"

**Disable browser extensions:**
1. Try incognito/private mode first
2. If works, disable extensions one by one to find culprit

**Check browser console:**
1. Press F12 to open developer tools
2. Go to "Console" tab
3. Look for error messages
4. Report errors to support if needed

---

### Login Not Working

**Problem**: Credentials rejected

**Solutions**:

**Default credentials:**
- Username: `admin`
- Password: `admin`

**If changed and forgotten:**
1. Reset via application settings (if accessible)
2. Or reinstall application (will reset all data)

**Caps Lock:**
- Check if Caps Lock is on
- Password is case-sensitive

---

## Upload and Resource Problems

### Upload Fails or Hangs

**Problem**: File upload doesn't complete

**Solutions**:

**Check file size:**
- Images: Keep under 10 MB
- Videos: Keep under 500 MB
- Compress files if too large

**Check file format:**
- **Supported images**: JPG, PNG, GIF, BMP, WebP
- **Supported videos**: MP4, AVI, MKV, MOV, WebM
- Convert unsupported formats

**Check storage space:**
- Windows: Check drive has 1GB+ free
- Android: Settings → Storage
- Linux: `df -h`

**Network timeout:**
- Refresh page and try again
- Upload smaller file to test
- Check if app is still running

---

### Uploaded Image Not Displaying

**Problem**: Image uploads but shows as broken/blank

**Solutions**:

**Verify image file:**
- Open image in photo viewer to confirm it's valid
- Try re-saving image in different format
- Check if image is corrupted

**Check file permissions:**
- Ensure app has read access to uploaded files
- Windows: Right-click file → Properties → Security

**Clear thumbnail cache:**
1. Go to Settings → Storage
2. Click "Clear Cache"
3. Refresh resource page

---

### Video Thumbnail Missing

**Problem**: Video uploads but no thumbnail appears

**Solution**:
- This is normal - thumbnails may take time to generate
- Video will still play normally
- Refresh page after 30 seconds

---

## Display and Playback Issues

### Content Not Displaying on Screen

**Problem**: Published program doesn't show on display

**Checklist**:

**1. Verify program is published:**
- Go to Programs
- Check if program shows as "Published"
- Verify correct terminal selected

**2. Check terminal status:**
- Go to Terminals
- Ensure terminal status is "Active"
- Verify terminal resolution matches display

**3. Refresh display:**
- Press F5 on display browser
- Or republish program

**4. Check display URL:**
- Ensure display is accessing correct URL
- Should be `http://[device-ip]:8080/display`

---

### Video Won't Play

**Problem**: Video shows black screen or doesn't start

**Solutions**:

**Check video codec:**
- MP4 with H.264 codec works best
- Convert video to MP4 if needed
- Use tools like HandBrake or VLC

**File size:**
- Very large videos (>500MB) may fail
- Compress video to reduce size

**Corruption:**
- Verify video plays on local media player
- Re-upload if corrupted

**Platform limitations:**
- Some older Android devices lack codec support
- Try different video format

---

### Images Display Stretched or Distorted

**Problem**: Images don't display correctly

**Solutions**:

**Match aspect ratios:**
- Check zone aspect ratio (width÷height)
- Use images with matching aspect ratio
- Or resize zones to match content

**Check zone size:**
- Verify zone dimensions are correct
- Ensure zones don't overlap

**Image resolution:**
- Use images at or near display resolution
- Avoid very low or very high resolution

---

### Slideshow Transitions Not Smooth

**Problem**: Choppy transitions between images

**Solutions**:

**Reduce file sizes:**
- Compress images to under 2MB each
- Use JPG instead of PNG for photos

**Limit playlist length:**
- Keep under 20 items per zone
- Split into multiple programs if needed

**Close other apps:**
- Free up system resources
- Restart device to clear memory

---

## Performance Problems

### Slow Admin Interface

**Problem**: Web interface is sluggish

**Solutions**:

**Clear cache:**
1. Settings → Storage → Clear Cache
2. Clear browser cache (Ctrl+Shift+Delete)

**Reduce resources:**
- Delete unused media files
- Keep resource library under 100 items

**System resources:**
- Close other applications
- Restart avSign.lite
- Restart computer

---

### High Memory Usage

**Problem**: Application uses too much RAM

**Solutions**:

**Optimize content:**
- Reduce image file sizes
- Limit video resolution to 1080p
- Use shorter playlists

**Restart application:**
- Stop and restart avSign.lite weekly
- Clear cache before restarting

**System upgrade:**
- Upgrade to 8GB RAM if possible
- Close background applications

---

### Display Freezes or Crashes

**Problem**: Display stops responding

**Solutions**:

**Immediate fix:**
1. Refresh browser (F5)
2. Republish program
3. Restart display device

**Long-term fixes:**
- Update to latest version
- Reduce content complexity
- Use recommended file formats
- Schedule automatic restarts (weekly)

---

## Error Messages

### "Failed to connect to server"

**Cause**: Application not running or network issue

**Solution**:
1. Verify avSign.lite application is running
2. Check firewall settings
3. Try `http://127.0.0.1:8080` instead
4. Restart application

---

### "Upload failed: file too large"

**Cause**: File exceeds size limit

**Solution**:
1. Compress image (use TinyPNG, etc.)
2. Compress video (use HandBrake)
3. Target sizes:
   - Images: Under 5MB
   - Videos: Under 300MB

---

### "Permission denied"

**Cause**: Insufficient permissions

**Solution (Windows)**:
- Run as administrator
- Check folder permissions

**Solution (Android)**:
- Grant storage permission
- Settings → Apps → avSign.lite → Permissions

**Solution (Linux)**:
```bash
sudo chmod +x /path/to/avsign-lite
```

---

### "Port 8080 already in use"

**Cause**: Another application is using the port

**Solution**:

**Find and stop the process:**

Windows:
```cmd
netstat -ano | findstr :8080
taskkill /PID <process_id> /F
```

Linux:
```bash
lsof -i :8080
sudo kill -9 <PID>
```

---

## Platform-Specific Issues

### Windows: Blank Screen on Startup

**Problem**: Application window is blank/white

**Solution**:
1. Press Ctrl+R to refresh
2. Restart application
3. Update graphics drivers
4. Disable hardware acceleration in Settings

---

### Android: App Keeps Closing

**Problem**: App closes in background

**Solution**:

**Disable battery optimization:**
1. Settings → Battery → Battery optimization
2. Find avSign.lite
3. Select "Don't optimize"

**Keep app in foreground:**
- Use "Lock" or "Pin" feature to keep app active
- Disable battery saver mode

---

### Linux: GTK Warnings

**Problem**: GTK-related warnings in console

**Solution**:
```bash
# Install GTK3
sudo apt install libgtk-3-0

# Set GTK theme
export GTK_THEME=Adwaita
```

---

## Getting Additional Help

### Before Contacting Support

**Gather this information:**
1. Platform (Windows/Android/Linux) and version
2. avSign.lite version (v1.0.0-beta)
3. Exact error message (screenshot if possible)
4. Steps to reproduce the issue
5. When the problem started

### Diagnostic Information

**Check application logs:**
- Windows: `%APPDATA%\avSign.lite\logs\`
- Linux: `~/.local/share/avsign-lite/logs/`
- Android: May not be accessible without developer mode

**System information:**
- OS version
- RAM amount
- Available storage
- Screen resolution

---

## Support Channels

### Self-Service Resources

- **FAQ**: [Frequently Asked Questions](FAQ.md)
- **User Guide**: [Complete User Guide](User_Guide.md)
- **Installation**: [Installation Guide](Installation_Guide.md)
- **Quick Start**: [Quick Start Guide](Quick_Start.md)

### Contact Support

- **GitHub Issues**: [Report bugs](https://github.com/sandriverfish/avsign-lite/issues)
  - Search existing issues first
  - Use bug report template
  - Include screenshots and error messages

- **Email**: sandriverfish@gmail.com
  - Response within 48 hours (weekdays)
  - Include diagnostic information

- **Community**: [GitHub Discussions](https://github.com/sandriverfish/avsign-lite/discussions)
  - Ask questions
  - Share solutions
  - Community help

---

## Known Issues (Phase 0)

### Acknowledged Limitations

**Windows 11 Installation:**
- May require administrator rights on some systems
- Workaround: Extract ZIP instead of using installer

**Large Video Files:**
- Files over 500MB may take time to load
- Workaround: Compress videos before uploading

**Android Performance:**
- Older devices (<2GB RAM) may experience lag
- Workaround: Reduce content complexity

**Layout Editor:**
- Manual zone positioning required (no snap-to-grid yet)
- Workaround: Use templates as starting point

---

**Last Updated**: 2025-11-23

For the latest troubleshooting tips, visit:
https://github.com/sandriverfish/avsign-lite/discussions
