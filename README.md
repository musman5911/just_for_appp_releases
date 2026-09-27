<div align="center">

# 📲 Wifi Transfer — Public Releases

### Private Controller ⇄ Twin Android Management Suite

*APK-only release mirror · Auto-update enabled · SHA-256 verified*

[![Latest Release](https://img.shields.io/badge/latest-v1.6.1-0A8674?style=flat-square&logo=github)](https://github.com/musman5911/just_for_appp_releases/releases/latest)
[![Platform](https://img.shields.io/badge/platform-Android%2010+-3DDC84?style=flat-square&logo=android)](https://developer.android.com/about/versions/android-10)
[![License](https://img.shields.io/badge/license-Private%20(Owner%20Use)-555?style=flat-square)](#support)

</div>

---

> 🔒 **Private owner-only project.** Source code: [`musman5911/just_for_appp`](https://github.com/musman5911/just_for_appp) (private). This public repo contains **only APK files** for owner-direct download and in-app auto-update.

---

## 📥 Quick Download

| APK | Role | Install On | Download |
|---|---|---|---|
| 🟢 **`app-mainline.apk`** | **Controller** (parent) | YOUR phone — the one that controls other devices | [Latest](https://github.com/musman5911/just_for_appp_releases/releases/latest/download/app-mainline.apk) |
| 🔵 **`app-twin.apk`** | **Twin** (managed device) | The phone BEING managed | [Latest](https://github.com/musman5911/just_for_appp_releases/releases/latest/download/app-twin.apk) |

📖 **All releases:** https://github.com/musman5911/just_for_appp_releases/releases

---

## 📲 Installation Guide

### Fresh install
1. Download the APK to your phone
2. Open **Files app** → **Downloads** → tap the APK
3. Allow **"Install from unknown sources"** if prompted
4. Tap **Install**

### Update existing install
Just open the app — it will automatically detect the new version, download it in the background, and prompt you to install. **No manual download needed.**

---

## 🔒 Verify Before Installing

**Signing Certificate SHA-256:**
```
c44606046726b7d6b4dfce3c7a290e4acd4ae2e8900dfd35cd5fe58b72844f0c
```

**Verify (Windows PowerShell):**
```powershell
keytool -printcert -jarfile app-mainline.apk
```

**Verify (Linux/macOS):**
```bash
apksigner verify --print-certs app-mainline.apk
# or
keytool -printcert -jarfile app-mainline.apk
```

The certificate fingerprint **must** match the SHA-256 above. If it doesn't, **do not install** — the APK has been tampered with or re-signed by an attacker.

---

## 🆕 Version History

| Version | Date | Highlights |
|---|---|---|
| **v1.6.1** | 2026-09-27 | Auto-bump README for v1.6.1 |
| **v1.6.0** | 2026-09-27 | 🔥 **Major:** Nonce removed from signed requests (must deploy Worker together) · Section dropdown fix · Devices tab visibility fix · NSD pairing · Pair-restore by code |
| v1.5.13 | 2026-09-27 | Devices tab blank-screen fix (SwipeRefreshLayout) · bulletproof status cards · dark-mode color collision fix |
| v1.5.12 | 2026-09-27 | Section dropdown toggle fix (was hiding entire card permanently) |
| v1.5.11 | 2026-09-26 | D1 write reduction (45s→90s heartbeat) · 40+ UI/UX enhancements · Tile cleanup 75→60 |
| v1.5.10 | 2026-09-26 | Controller device list redesign · Twin layout redesign · Dashboard tab · APK corruption fix |
| v1.5.9 | 2026-09-25 | Tile consolidation · Eye badge icons · Info text under tiles |
| v1.5.8 | 2026-09-25 | CI/CD manifest merge fix · Workflow fail-loudly · Beautiful release notes |
| v1.5.7 | 2026-09-24 | Performance: queue wake 2min, instant online check |
| v1.5.5 | 2026-09-22 | Wi-Fi History Logger · 90-day local retention · 5-min uploads |
| v1.5.4 | 2026-09-20 | Full audit fix (14 issues) · RealtimeHub · rate limiting · OOM fixes |
| v1.5.2 | 2026-09-18 | Takeover Chat · Real-time bidirectional chat over WebSocket |
| v1.5.0 | 2026-09-15 | 16 new features: retry policy, automation pause, file manager, mDNS, heatmap, remote touch, pair restore, macros |
| v1.1.3 | 2026-08-10 | Trusted physical-test baseline |

---

## 🎯 What is Wifi Transfer?

A private **Controller ⇄ Twin (managed device)** Android app. One controller phone manages up to **5 twin phones** for personal device automation:

- 📁 **File transfer** — send files to/from twin, batch send, duplicates scanner, FolderSync
- 📸 **Remote capture** — back/front camera, screenshot, auto-capture on schedule, live WebRTC camera
- 🔒 **Lockdown** — lock device, kiosk mode, screen timeout, button reaction config
- ⚡ **Remote actions** — open apps, open URLs, custom ring, wallpaper swap, brightness control
- 💬 **Real-time chat** — Takeover Chat (bidirectional, WebSocket)
- 🤖 **Automation** — macros, repeat actions, scheduled tasks, automation pause
- 📊 **Diagnostics** — usage heatmap, Wi-Fi history, storage map, self-test, OEM checklist
- 🔄 **Pairing methods** — QR code, drag-to-pair, NSD/mDNS local pairing, pair-restore by code

**Two flavors:**
- **`app-mainline.apk`** — Controller (parent phone, full UI)
- **`app-twin.apk`** — Twin (managed phone, background receiver)

---

## 🔄 Auto-Update System

When you open the app, it automatically:

1. Calls `GET /v17/update/check` on the Worker
2. Compares server version vs. installed version
3. If newer → downloads APK to `Download/Wifi/updates/`
4. Verifies SHA-256 hash matches manifest
5. Prompts you with **Install** / **Later**
6. After install, old APKs are auto-deleted

**Manual update check:** Open app → tap **"Check Updates"** button in the header.

---

## 🛡️ Security

- ✅ Every authenticated request is **ECDSA P-256 signed** (Android Keystore)
- ✅ Backend stores only **SHA-256 hashes** of device tokens, pairing codes
- ✅ All traffic is **HTTPS** — cleartext forbidden
- ✅ **No secrets in APK** — only public Worker URL + public Dropbox App Key
- ✅ Device tokens can be rotated via controller UI

**v1.6.0 breaking change:** Nonce removed from signed request canonical. APK and Worker must be deployed together. Old APK + new Worker = signature mismatch.

See full security model in source repo: [`docs/SECURITY.md`](https://github.com/musman5911/just_for_appp/blob/main/docs/SECURITY.md)

---

## 🚧 Known Limits

- ❌ Force-stop / power-off cannot be bypassed (Android hard limit)
- ❌ STUN-only WebRTC may fail on strict NAT without TURN (off by default)
- ❌ Huawei Y6P video decode: H.264 1080p@30 max (4K fails silently)
- ❌ MIUI autostart state cannot be auto-detected — user must manually tap "Confirm"
- ⏱️ Telegram large-file parts auto-delete after 24h
- 💾 D1 free tier: 100,000 row writes/day (v1.6.0 reduces daily writes to ~10-15k)

---

## 📞 Support

This is a **private owner-only project**. No public support is provided. Contact the owner directly for any issues.

For security vulnerabilities, contact the owner directly — **do NOT open public issues** for security reports.

---

<div align="center">

**Built with:** Android · Cloudflare Workers · D1 · Durable Objects · WebSocket · WebRTC · ECDSA P-256

*Repository: APK-only release mirror · Source: [`musman5911/just_for_appp`](https://github.com/musman5911/just_for_appp) (private)*

</div>
