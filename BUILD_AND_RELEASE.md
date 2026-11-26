# Build & Release Guide — NEXUS

## Prerequisites
- Android Studio Ladybug (2024.2.1) or newer
- JDK 17
- Android SDK 35 (Min SDK 26)

## Local Build & Test
```bash
cd /home/user/nexus
./gradlew testDebugUnitTest
./gradlew assembleDebug
./gradlew assembleRelease
```

## Signing Configuration
Never commit keystores or signing passwords to Git. Configure signing via environment variables or `keystore.properties` (excluded in `.gitignore`) before running `bundleRelease` for Google Play Console.

## CI/CD
`.github/workflows/build.yml` runs `testDebugUnitTest` and `assembleDebug` on every push/PR and uploads `nexus-debug-apk` as a workflow artifact.
