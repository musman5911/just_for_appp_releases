Wifi Transfer — Public Releases
Public APK release repository for the Wifi Transfer Android app.

Source code (private): https://github.com/musman5911/just_for_appp

Latest release: v1.5.7
Download:

Controller (mainline): app-mainline.apk
Twin (managed device): app-twin.apk
All releases: https://github.com/musman5911/just_for_appp_releases/releases

What is Wifi Transfer?
A private Controller ⇄ Twin (managed device) Android app. One controller phone manages up to 5 twin phones — file transfer, remote actions, captures, lockdown, automation, real-time chat.

Which APK do I need?
APK	Role	When to install
app-mainline.apk	Controller (parent)	Install on YOUR phone — the one that controls other devices
app-twin.apk	Twin (managed device)	Install on the phone BEING managed
How to install
Download the APK to your phone
Open the file (Files app → Downloads → tap the APK)
Allow "Install from unknown sources" if prompted
Tap Install
Auto-update
If you already have Wifi Transfer installed, just open the app — it will automatically detect the new version and prompt you to install. No manual download needed.

Signing certificate
SHA-256: c44606046726b7d6b4dfce3c7a290e4acd4ae2e8900dfd35cd5fe58b72844f0c

Verify before installing:

keytool -print-cert -jarfile app-mainline.apk

text


The certificate fingerprint should match the SHA-256 above.

## Version history

| Version | Highlights |
|---|---|
| **v1.5.7** | Queue/tick timing, instant online check, Wi-Fi History Logger, Takeover Chat, 14 audit fixes, Capture Cloud Mirror (KV) |
| v1.5.0 | 16 new features: retry policy, result details, automation pause, file manager, apps extended, drag-to-pair, archive, mDNS, heatmap, remote touch, pair restore |
| v1.4.0 | UI redesign, MIUI-safe Wi-Fi settings, Telegram 4MB parts |
| v1.1.3 | Trusted baseline |

## Support

This is a private app — no public support. Contact the owner directly.
