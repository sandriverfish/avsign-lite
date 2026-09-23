# avSign.lite

**Offline-first digital signage with an embedded CMS — no separate server required.**

Transform Windows PCs, Android devices, and Fire TV sticks into professional
digital signage displays. Content keeps playing from local storage even when
the network drops.

[![License](https://img.shields.io/badge/License-Commercial-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Android%20%7C%20Fire%20TV-lightgrey.svg)]()
[![Version](https://img.shields.io/badge/Version-v2.1.0-green.svg)](https://github.com/sandriverfish/avsign-lite/releases/tag/v2.1.0)
[![Website](https://img.shields.io/badge/Website-apexvuedigital.com-informational.svg)](https://www.apexvuedigital.com)

**Product / company:** [Apex Vue Digital](https://www.apexvuedigital.com) (`apexvuedigital` on GitHub). This public repo distributes release binaries and docs.

**Product site:** [apexvuedigital.com](https://www.apexvuedigital.com) · **Docs:** [Documentation](https://www.apexvuedigital.com/docs/) · **Downloads:** [Releases](https://github.com/sandriverfish/avsign-lite/releases)

---

## Pricing

| Plan | Price | Notes |
|------|-------|--------|
| **Free trial** | $0 for 14 days | Full core features to evaluate on your device |
| **Lifetime license** | **$49.99** one-time, per device | Commercial use, email support, lifetime updates for that license tier |
| **Server Edition** | Contact sales | Centralized / multi-device management (see website) |

Purchase and trial details: [apexvuedigital.com](https://www.apexvuedigital.com)

---

## Quick start

### Download v2.1.0 (Consultation Mode)

| Platform | Download | Requirements |
|----------|----------|--------------|
| **Windows** | [ZIP](https://github.com/sandriverfish/avsign-lite/releases/download/v2.1.0/avsign-lite-2.1.0-windows.zip) | Windows 10+ (64-bit) |
| **Android** | [APK](https://github.com/sandriverfish/avsign-lite/releases/download/v2.1.0/avsign-lite-2.1.0-android.apk) | Android 9+ |
| **Fire TV** | [APK](https://github.com/sandriverfish/avsign-lite/releases/download/v2.1.0/avsign-lite-2.1.0-firetv-arm64-v8a.apk) | Fire TV Stick 4K or newer |
| **Linux** | Coming soon | — |

Installation steps: [Installation Guide](docs/Installation_Guide.md)

---

## Features

### Core

- **Resource management** — images, video, and media libraries
- **Drag-and-drop layout editor** — multi-zone layouts without coding
- **Templates** — full screen, picture-in-picture, side-by-side, quad, video wall, digital menu board
- **Playlists & scheduling** — timed programs and playback order
- **Offline-first** — scheduled content continues from local storage without internet
- **Embedded CMS** — manage the device from a browser on the local network; no separate server required for lite deployments

### Highlights in recent releases

**v2.1.0 — Consultation Mode**
- Interactive before/after comparisons (medical, beauty, service use cases)
- Tablet remote control for the main display
- Split-screen comparison and smart audio mute (“zero audio bleed”)

**v2.0.0 — Multi-screen & ops**
- Multi-screen grid / panorama walls
- Kiosk mode with PIN
- NTP time sync for coordinated playback
- Calendar integration (iCal / Google & Outlook style feeds)

### Media types

Images (JPG, PNG, GIF, BMP, WebP), video (MP4, AVI, MKV, MOV, WebM), text overlays, clocks, and multi-zone layouts.

---

## Documentation

- [Quick Start](docs/Quick_Start.md)
- [User Guide](docs/User_Guide.md)
- [Installation Guide](docs/Installation_Guide.md)
- [Troubleshooting](docs/Troubleshooting.md)
- [FAQ](docs/FAQ.md) *(repo FAQ; site FAQ at [apexvuedigital.com/faq](https://www.apexvuedigital.com/faq/) is authoritative for pricing and support email)*
- [Changelog](CHANGELOG.md)

Website docs hub: [apexvuedigital.com/docs](https://www.apexvuedigital.com/docs/)

---

## Support & community

| Channel | Use for |
|---------|---------|
| **Email** `support@apexvuedigital.com` | License, billing, and customer support (target: reply within 2 business days) |
| **[GitHub Issues](https://github.com/sandriverfish/avsign-lite/issues)** | Bug reports and feature requests |
| **[GitHub Discussions](https://github.com/sandriverfish/avsign-lite/discussions)** | Questions, ideas, roadmap talk |
| **[Discord](https://discord.gg/EMh8zanC)** | Community chat |
| **X** [@sandriverfish](https://twitter.com/sandriverfish) | Announcements |

**Security:** email `support@apexvuedigital.com` — do not file public issues for vulnerabilities.

---

## Roadmap (honest status)

| Area | Status |
|------|--------|
| Windows / Android / Fire TV binaries | Shipped (v2.1.0) |
| Consultation Mode, remote control, split-screen | Shipped (v2.1.0) |
| Multi-screen grid, kiosk, NTP, calendar | Shipped (v2.0.0) |
| Raspberry Pi / Linux desktop builds | Planned — not shipped yet |
| MCP / AI agent control | In progress / rolling out — see site and release notes |
| Cloud sync & Server Edition | Planned / contact sales |
| Open-source source release | **Not currently available** — no committed public date |

Older README text that promised AGPLv3 in 2025 is outdated and removed. Licensing today is the commercial EULA in [LICENSE](LICENSE).

---

## System requirements

### Windows
Windows 10+ 64-bit · 4 GB RAM (8 GB recommended) · ~500 MB disk · DirectX 11 GPU

### Android
Android 9.0+ · 2 GB RAM (4 GB recommended) · ~200 MB disk

### Fire TV
Fire OS 7+ · Fire TV Stick 4K or newer recommended · D-pad / TV-oriented UI

### Linux
Not shipped yet. Requirements will be published with the first Linux build.

---

## Use cases

Retail and menu boards, lobbies and meeting rooms, education and healthcare wayfinding, events, Fire TV living-room displays, and consultation / before-after presentations.

---

## License

avSign.lite binaries are **commercial software**.

- 14-day free trial for evaluation
- Paid **lifetime per-device** license for continued and commercial use
- Full terms: [LICENSE](LICENSE)
- This repository currently distributes **binaries and documentation**, not application source code

---

## Contributing

Source code is not open for pull requests at this time.

You can still help by:

- Testing builds and filing [bug reports](https://github.com/sandriverfish/avsign-lite/issues/new?template=bug_report.yml)
- Submitting [feature requests](https://github.com/sandriverfish/avsign-lite/issues/new?template=feature_request.yml)
- Improving docs (typos, clarity) via issues or discussions
- Sharing real-world use cases

---

## Acknowledgments

- Inspired by / based on concepts from [EasyDisplayClient](https://github.com/EasyDisplayClient)
- Built with [Flutter](https://flutter.dev/), [media_kit](https://github.com/media-kit/media-kit), and [Drift](https://drift.simonbinder.eu/)

---

## Project status

| | |
|--|--|
| **Current version** | v2.1.0 (Consultation Mode) |
| **Platforms** | Windows, Android, Fire TV |
| **Status** | Actively maintained product |
| **Next focus** | Linux/Pi builds, MCP polish, support & community ops |

---

## Support the project

- Star this repository
- Report bugs and request features
- Tell others who need offline-capable signage
- Buy a license if the trial fits your deployment

---

<div align="center">

[Website](https://www.apexvuedigital.com) · [Download](https://github.com/sandriverfish/avsign-lite/releases) · [Docs](https://www.apexvuedigital.com/docs/) · [Issues](https://github.com/sandriverfish/avsign-lite/issues)

</div>
