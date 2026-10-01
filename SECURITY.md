# Security Policy

This repository distributes signed Wifi Transfer APK releases.

## Reporting

**Do not report security vulnerabilities through public issues or pull requests.**

Use GitHub's private security reporting/advisory mechanism when available. If it is unavailable, contact the project owner privately through GitHub.

Include the affected release, impact, reproduction steps and relevant evidence. Remove passwords, tokens, pairing codes and personal data.

## APK authenticity

Official release certificate:

~~~text
SHA-256:
c44606046726b7d6b4dfce3c7a290e4acd4ae2e8900dfd35cd5fe58b72844f0c
~~~

If an APK certificate does not match this fingerprint, do not install it.

## Release integrity

Versioned releases are produced from tags in the private source repository. APK hashes are published with each release. Signing keys and server credentials are never stored here.

Application security issues should be reported through the private source repository's security process:

https://github.com/musman5911/just_for_appp/security
