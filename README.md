# LINE12 — Android update distribution

Public distribution endpoint for the personal LINE12 dispatch planner.

- Current released version and SHA-256: [latest.json](latest.json)
- Signed APKs: `apk/line12-vX.Y.apk`
- Publication status: [status.json](status.json)
- Android checks `latest.json`, downloads the APK via HTTPS, verifies SHA-256, then requests **user-confirmed** installation.

## Release rules

The source repository is private. A signed release is produced by its protected GitHub Actions workflow using the original signing certificate. The workflow checks package ID and certificate, uploads the signed APK, and **publishes the manifest last**. Do not upload a manifest for an unavailable APK.

The owner must approve installation in Android. Existing records should survive signed in-place updates because the package identity and WebView storage origin are preserved, but on-device verification and backup are recommended.

Never publish signing keys, passwords, access tokens, or real work records here. Release information only; no private source code.
