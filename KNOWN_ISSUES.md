# Known Issues & Limitations

1. **Sandbox Build Environment**: The initial development sandbox lacked JDK 17 and Android SDK 35, so Gradle compilation and unit tests must be executed in Android Studio or via `.github/workflows/build.yml`.
2. **Physical Device & Instrumented Tests**: Compose UI tests and physical-device TalkBack/gesture verification are pending execution on an Android emulator or physical device.
3. **Database Migrations**: Currently at `version = 1`. Any future schema change must add an explicit `Migration(1, 2)` and Room migration test before release.
