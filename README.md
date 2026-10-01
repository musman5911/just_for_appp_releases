# 📲 Wifi Transfer Releases

Public APK distribution for the private **Wifi Transfer Controller ⇄ Twin** project.

[![Latest Release](https://img.shields.io/github/v/release/musman5911/just_for_appp_releases?logo=github)](https://github.com/musman5911/just_for_appp_releases/releases/latest)
[![Android 10+](https://img.shields.io/badge/Android-10%2B-3DDC84?logo=android)](https://developer.android.com/about/versions/android-10)

## Downloads

| APK | Install on |
|---|---|
| [app-mainline.apk](https://github.com/musman5911/just_for_appp_releases/releases/latest/download/app-mainline.apk) | Controller phone |
| [app-twin.apk](https://github.com/musman5911/just_for_appp_releases/releases/latest/download/app-twin.apk) | Managed/Twin phone |

All versioned releases are available on the [Releases](https://github.com/musman5911/just_for_appp_releases/releases) page.

## Automatic updates

Installed apps check the update manifest, download newer APKs when available, verify the published SHA-256, and prompt for installation.

## Verify the APK

Official release certificate:

~~~text
SHA-256:
c44606046726b7d6b4dfce3c7a290e4acd4ae2e8900dfd35cd5fe58b72844f0c
~~~

Windows:

~~~cmd
keytool -printcert -jarfile app-mainline.apk
~~~

Linux/macOS:

~~~bash
apksigner verify --print-certs app-mainline.apk
~~~

Do not install an APK whose certificate fingerprint does not match.

## Project

Source repository: https://github.com/musman5911/just_for_appp

This repository contains release APKs only.

## Security

Report security vulnerabilities privately. See [SECURITY.md](SECURITY.md).
