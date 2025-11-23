# avSign.lite - Frequently Asked Questions (FAQ)

**Version**: 1.0.0-beta (Phase 0)
**Last Updated**: 2025-11-23

---

## General Questions

### What is avSign.lite?

avSign.lite is an open-source digital signage platform that allows you to create, manage, and display content on screens. It's designed to work offline-first, meaning you don't need an internet connection for basic functionality.

### Is avSign.lite free?

**Yes!** avSign.lite is free and open-source software.

- **Phase 0 (Current)**: Free beta binaries for testing
- **Phase 1 (Q4 2025)**: Full source code release under AGPLv3 license
- No subscription fees, no hidden costs

### What platforms does it support?

avSign.lite runs on:
- **Windows** 10/11 (64-bit)
- **Android** 5.0+ (Lollipop and later)
- **Linux** (Coming soon! Ubuntu 20.04+, or equivalent distributions)
- **Future**: iOS, macOS, Web (planned)

### Do I need internet to use avSign.lite?

**No!** avSign.lite is designed to work completely offline. Internet is only needed for:
- Downloading the initial installation
- Future Phase 2 features (cloud sync, AI features - optional)

---

## Installation & Setup

### How do I install avSign.lite?

See the [Installation Guide](Installation_Guide.md) for detailed platform-specific instructions:
- **Windows**: Download EXE or ZIP, run/extract, launch
- **Android**: Download APK, enable unknown sources, install
- **Linux**: Download tar.gz, extract, install dependencies, run

### What are the system requirements?

**Minimum Requirements:**
- **RAM**: 2-4 GB
- **Storage**: 200-500 MB for app + space for your content
- **Display**: 1024x768 or higher
- **CPU**: Modern dual-core or better

See [Installation Guide - System Requirements](Installation_Guide.md#system-requirements) for details.

### How do I access the admin interface?

1. Launch the avSign.lite application
2. Open a web browser
3. Navigate to: `http://(Actual IP v4):8080`
4. Login with credentials (default: admin/admin123)

### What are the default login credentials?

- **Username**: `admin`
- **Password**: `admin123`

⚠️ **IMPORTANT**: Change the default password immediately after first login!

### Can I change the port from 8080?

Port configuration options may be available in Settings. If port 8080 is unavailable, see [Troubleshooting - Port Already in Use](Troubleshooting.md#port-8080-already-in-use).

---

## Features & Capabilities

### What file formats are supported?

**Images:**
- JPG/JPEG
- PNG
- GIF
- BMP
- WebP

**Videos:**
- MP4 (recommended - best compatibility)
- AVI
- MKV
- MOV
- WebM

### What's the maximum file size?

**Recommended limits:**
- **Images**: Under 10 MB
- **Videos**: Under 500 MB

Larger files may work but can cause performance issues.

### Can I display videos?

**Yes!** avSign.lite supports video playback. Use MP4 format with H.264 codec for best compatibility across all platforms.

### Does it support playlists?

**Yes!** You can create programs (playlists) with multiple content items that play in sequence and loop automatically.

### Can I have multiple zones on one screen?

**Yes!** Create custom layouts with multiple zones showing different content simultaneously. Use templates like:
- Side-by-Side (2 zones)
- Quad Dashboard (4 zones)
- Picture-in-Picture
- Custom layouts (unlimited zones)

### Can I schedule content for specific times?

**Not in Phase 0.** Scheduling features are planned for Phase 2 (Q2 2025). Currently, all content loops continuously.

### Does it have cloud features?

**Not in Phase 0.** Cloud synchronization and remote management are planned for Phase 2. Current version is fully offline.

### Can I use AI to generate content?

**Not in Phase 0.** AI-powered content generation (Claude Skills) is planned for Phase 2.

---

## Usage Questions

### How do I create my first display?

Follow our [Quick Start Guide](Quick_Start.md) - you'll be up and running in 5 minutes:
1. Upload an image
2. Create or use a template layout
3. Create a program
4. Add a terminal
5. Publish!

### How do I update content on a live display?

1. Go to Programs
2. Edit your program (add/remove/change content)
3. Save changes
4. Republish to the same terminal
5. Display updates automatically

### Can I control multiple displays?

**Yes!** Create multiple terminals and publish programs to specific displays. Each terminal can show different content.

### How do I make content fullscreen?

1. Access the display URL in a browser
2. Press **F11** for fullscreen mode
3. Or use kiosk mode in browser settings

### Can I display a website or web content?

**Not directly in Phase 0.** Web content display may be added in future versions. Current version supports images, videos, and text only.

### How do I rotate content (portrait mode)?

1. Create a layout with portrait dimensions (e.g., 1080x1920)
2. Rotate your physical display
3. Use content sized for portrait orientation

---

## Technical Questions

### Where is my data stored?

**Locally on your device:**
- **Windows**: `%APPDATA%\avSign.lite\`
- **Android**: App-specific internal storage
- **Linux**: `~/.local/share/avsign-lite/`

No data is sent to external servers in Phase 0.

### How do I backup my data?

1. Go to Settings → Backup
2. Click "Create Backup"
3. Save the backup file to a safe location (USB drive, cloud storage, etc.)

**Manual backup:**
- Copy the data directory (see above) to a safe location

### How do I restore from backup?

1. Go to Settings → Backup
2. Click "Restore from Backup"
3. Select your backup file
4. Confirm restoration
5. ⚠️ Warning: This overwrites current data

### Can I export my layouts?

Export/import features may be available in Settings. If not currently available, it's planned for a future update.

### Is my data secure?

**Yes:**
- All data stored locally on your device
- Admin interface accessible only on localhost by default
- No external data transmission in Phase 0
- Password-protected admin access

**Security tips:**
- Change default password
- Keep software updated
- Use firewall if exposing to network
- Regular backups

### Can I access avSign.lite from another computer?

**Yes, but not recommended for Phase 0:**
1. Find your device's IP address
2. On another computer, navigate to `http://[device-ip]:8080`
3. ⚠️ **Security Warning**: This exposes admin interface to network
4. Configure firewall rules appropriately

**Safer approach**: Use remote desktop instead.

---

## Troubleshooting Questions

### Why won't the app start?

Common causes:
1. Port 8080 already in use
2. Missing dependencies (Linux)
3. Antivirus blocking (Windows)
4. Insufficient permissions

See [Troubleshooting - Application Won't Start](Troubleshooting.md#application-wont-start).

### Why can't I access http://localhost:8080?

Possible solutions:
1. Verify app is running
2. Try `http://127.0.0.1:8080`
3. Check firewall settings
4. Try different browser
5. Clear browser cache

See [Troubleshooting - Admin Interface Issues](Troubleshooting.md#admin-interface-issues).

### Why won't my image upload?

Check:
1. File size (keep under 10 MB)
2. File format (JPG, PNG supported)
3. Available storage space
4. File is not corrupted

See [Troubleshooting - Upload Problems](Troubleshooting.md#upload-and-resource-problems).

### Why is my video not playing?

Solutions:
1. Use MP4 format with H.264 codec
2. Reduce file size (under 500 MB)
3. Verify video plays in other media players
4. Check device codec support

See [Troubleshooting - Display Issues](Troubleshooting.md#display-and-playback-issues).

### Why is the app running slow?

Performance tips:
1. Reduce image file sizes
2. Limit playlist length
3. Close other applications
4. Clear cache in Settings
5. Restart application

See [Troubleshooting - Performance Problems](Troubleshooting.md#performance-problems).

---

## Licensing & Open Source

### What license does avSign.lite use?

**Phase 0 (Current)**: Beta testing license (proprietary, free for testing)
**Phase 1 (Q1 2025)**: AGPLv3 (open source)

See [LICENSE](../LICENSE) for current terms.

### When will the source code be released?

**Planned for Q1 2025** (Phase 1). The full source code will be released under AGPLv3 license on GitHub.

### Can I contribute to the project?

**Phase 0**: Not accepting code contributions yet (no source code public)
**You can help by:**
- Testing the software
- Reporting bugs
- Suggesting features
- Improving documentation

**Phase 1**: Full contribution guidelines will be provided with source code release.

### Can I use this for commercial purposes?

**Phase 0**: Beta license restricts commercial use during testing
**Phase 1**: AGPLv3 will allow commercial use with source code disclosure requirements

See [LICENSE](../LICENSE) for current terms.

### Is this based on other software?

**Yes.** avSign.lite is forked from [EasyDisplayClient](https://github.com/EasyDisplayClient) v1.0.2+6 and maintains 100% compatibility with its core features.

---

## Advanced Usage

### Can I run multiple instances?

**On same device**: No - port 8080 can only be used by one instance
**On different devices**: Yes - each device runs its own instance

### Can I use this on a Raspberry Pi?

**Yes!** Linux builds should work on Raspberry Pi (tested on Pi 4):
- Install Ubuntu or Raspberry Pi OS
- Follow Linux installation steps
- Performance depends on Pi model (Pi 4 recommended)

### Can I build custom layouts programmatically?

**Phase 0**: Manual layout creation via UI only
**Phase 1+**: API and programmatic access may be available

### Can I integrate with other systems?

**Phase 0**: Limited integration capabilities
**Phase 2**: MCP (Model Context Protocol) server for AI agent integration planned

### Can I use custom fonts?

Font customization options may be available in Settings. If not currently available, it's planned for future updates.

### Can I add my own logo to displays?

**Yes!** Create a layout with a zone for your logo and add it to your program. Use templates like "Picture-in-Picture" for logo overlay.

---

## Getting Help

### Where can I find documentation?

- **Quick Start**: [Quick Start Guide](Quick_Start.md) - 5-minute setup
- **User Guide**: [Complete User Guide](User_Guide.md) - Full documentation
- **Installation**: [Installation Guide](Installation_Guide.md) - Setup instructions
- **Troubleshooting**: [Troubleshooting Guide](Troubleshooting.md) - Common issues

### How do I report a bug?

1. Check [existing issues](https://github.com/sandriverfish/avsign-lite/issues) first
2. If not found, [create new bug report](https://github.com/sandriverfish/avsign-lite/issues/new?template=bug_report.yml)
3. Include:
   - Platform and version
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots if applicable

### How do I request a feature?

1. Check [existing requests](https://github.com/sandriverfish/avsign-lite/issues?q=label%3Aenhancement)
2. If not found, [create feature request](https://github.com/sandriverfish/avsign-lite/issues/new?template=feature_request.yml)
3. Describe the problem it solves and your proposed solution

### Where can I ask questions?

- **GitHub Discussions**: [Ask the community](https://github.com/sandriverfish/avsign-lite/discussions)
- **Email**: sandriverfish@gmail.com (response within 48 hours)

### Is there a community forum?

**GitHub Discussions**: https://github.com/sandriverfish/avsign-lite/discussions

Join to:
- Ask questions
- Share use cases
- Help other users
- Discuss features

---

## Roadmap & Future Plans

### What's coming in Phase 1?

**Planned for Q1 2025:**
- Full source code release (AGPLv3)
- Developer documentation
- Contribution guidelines
- Community contributions enabled

### What's coming in Phase 2?

**Planned for Q2 2025:**
- AI-powered content generation (Claude Skills)
- Cloud synchronization
- Remote device management
- MCP server for AI agent control
- Advanced scheduling
- Analytics and reporting

### When will scheduling features be available?

**Planned for Phase 2** (Q2 2025). This will include:
- Time-based schedules
- Day of week scheduling
- Date-specific content
- Automatic transitions

### Will there be a mobile app for management?

**Phase 0**: Web-based admin interface accessible from mobile browsers
**Future**: Dedicated mobile management app may be considered based on user feedback

### Can I vote on features?

**Yes!** Participate in [GitHub Discussions](https://github.com/sandriverfish/avsign-lite/discussions) and upvote feature requests with 👍 reactions.

---

## Still Have Questions?

### Documentation

- [User Guide](User_Guide.md)
- [Installation Guide](Installation_Guide.md)
- [Quick Start](Quick_Start.md)
- [Troubleshooting](Troubleshooting.md)

### Support

- **GitHub Issues**: [Bug reports & features](https://github.com/sandriverfish/avsign-lite/issues)
- **Discussions**: [Community Q&A](https://github.com/sandriverfish/avsign-lite/discussions)
- **Email**: sandriverfish@gmail.com

---

**Last Updated**: 2025-11-23

Have a question not answered here? [Ask in Discussions](https://github.com/sandriverfish/avsign-lite/discussions) or email sandriverfish@gmail.com
