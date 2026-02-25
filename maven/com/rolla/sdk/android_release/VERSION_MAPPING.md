# Maven Version Mapping

Rolla SDK Version: 0.1.1

To use this version in your Android project:
```kotlin
dependencies {
    // Use android_release - it includes flutter_release (Dart code) as a transitive dependency
    implementation("com.rolla.sdk:android_release:0.1.1")
}
```

## What's in each artifact?
- `android_release`: Native Android code (Bluetooth handlers, Pigeon APIs, etc.)
- `flutter_release`: Compiled Dart/Flutter code (automatically included via transitive dependency)

## Version History

Each SDK release creates version-specific Maven artifacts.
Browse available versions at: https://rolla-health-fitness.github.io/rolla-sdk-release-android/maven/com/rolla/sdk/android_release/

## Updating to Latest Version

1. Check the latest version in `maven-metadata.xml`
2. Update your `build.gradle.kts`:
   ```kotlin
   implementation("com.rolla.sdk:android_release:0.1.1")
   ```
3. Sync Gradle and rebuild

## Gradle Version Catalog

```toml
[versions]
rolla-sdk = "0.1.1"

[libraries]
rolla-sdk = { group = "com.rolla.sdk", name = "android_release", version.ref = "rolla-sdk" }
```
