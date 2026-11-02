# LINE 12 — Public Android update distribution

This repository is the **public, read-only distribution endpoint** for the 12라인 불출 플래너 Android app.

- Private app source: `totemismsuhak-cmd/12LINE` (not mirrored here)
- Release manifest: `latest.json` (will only be published when a correctly signed, installable APK exists)
- Signed packages: `apk/line12-vX.Y.apk`
- Manifest/API URLs use HTTPS and don't require a GitHub login.
- `latest.json` must include monotonically increasing `versionCode`, `versionName`, `notes`, `apkUrl`, and a verified `sha256` of the APK.
- Do **not** commit private signing keys, passwords, access tokens, or user work records.

## Release lifecycle
Build the app in the private repo → sign with the same certificate used for V4.1 → verify package ID and APK SHA-256 → publish APK here → publish `latest.json` **last**. The app checks the public manifest, verifies the downloaded APK SHA-256, and asks Android to install it with user confirmation. App installation and existing-data preservation still require testing on-device.

**Current state:** Bootstrap repository set up. No public update has been published yet. Keep V4.1 installed until a signed V4.2 APK is ready and verified.
