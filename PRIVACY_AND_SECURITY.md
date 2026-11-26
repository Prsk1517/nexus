# Privacy & Security Audit — NEXUS

## 1. Strict Offline Verification
- `AndroidManifest.xml` declares **zero** `INTERNET` or `ACCESS_NETWORK_STATE` permissions.
- No analytics, advertising, crash reporting, or cloud SDKs are included in `gradle/libs.versions.toml` or `app/build.gradle.kts`.
- QR code generation uses `com.google.zxing:core` (Apache-2.0) 100% locally on-device.

## 2. Local Storage & Backup Behavior
- **App Sandbox**: Room (`nexus_local.db`) and DataStore (`nexus_preferences.preferences_pb`) are stored in private app-internal storage.
- **Android Auto-Backup**: Explicitly disabled (`android:allowBackup="false"`, `data_extraction_rules.xml` excludes `root`, `database`, `sharedpref`, `file`) so user data is never silently uploaded to cloud backup services.
- **User-Controlled Export/Import**: Uses Android Storage Access Framework (`CreateDocument` / `OpenDocument`). Exported JSON files are unencrypted plaintext; users are warned in Settings to store backups securely.

## 3. Input & Share Validation
- Incoming `ACTION_SEND` (`text/plain`) intents are length-capped (`5000` chars) and require explicit user confirmation in the Save dialog before persisting.
- JSON backup imports validate `schemaVersion == 1` and execute inside a single Room `@Transaction` to prevent partial/corrupted imports.
