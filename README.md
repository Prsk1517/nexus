# NEXUS — Offline Everyday Utility Ecosystem

> **"Less tapping. Less searching. More doing."**

NEXUS is an offline-first, privacy-first Android utility ecosystem built with Kotlin, Jetpack Compose, Material Design 3, Room, DataStore, and Hilt.

## Core Guarantees
- **100% Offline**: No `INTERNET` permission in `AndroidManifest.xml`. No analytics, no ads, no trackers, no cloud dependencies.
- **Privacy-First**: All data is stored locally in Room (SQLite) and DataStore. Explicit user-controlled JSON backup/restore via Android Storage Access Framework.
- **Accessible & Responsive**: Material 3 design tokens, TalkBack semantics, 48dp minimum touch targets, and scalable typography.

## Requirements to Build
- **Android Studio**: Ladybug (2024.2.1) or newer
- **JDK**: 17
- **Android SDK**: Compile SDK 35, Min SDK 26

## Build Commands
```bash
./gradlew assembleDebug
./gradlew testDebugUnitTest
./gradlew connectedDebugAndroidTest
```
