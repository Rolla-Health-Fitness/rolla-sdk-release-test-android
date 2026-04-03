# Rolla SDK — Android

Android distribution repository for the Rolla Flutter SDK. Artifacts are served as a Maven repository via GitHub Pages.

**Current version:** `0.1.1`

---

## Installation

### 1. Add repositories in `settings.gradle.kts`

```kotlin
dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()

        // Rolla SDK Maven repository (includes bundled ucrop)
        maven {
            url = uri("https://rolla-health-fitness.github.io/rolla-sdk-release-android/maven/")
            name = "Rolla SDK"
        }

        // Flutter engine artifacts
        maven {
            url = uri("https://storage.googleapis.com/download.flutter.io")
            name = "Flutter Engine"
        }

        // Mapbox SDK for maps (public, no token needed)
        maven {
            url = uri("https://api.mapbox.com/downloads/v2/releases/maven")
            name = "Mapbox"
        }
    }
}
```

### 2. Enable core library desugaring in `app/build.gradle.kts`

Required by `flutter_local_notifications`:

```kotlin
android {
    compileOptions {
        isCoreLibraryDesugaringEnabled = true
    }
}
```

### 3. Add dependencies in `app/build.gradle.kts`

```kotlin
dependencies {
    // Core library desugaring - required by flutter_local_notifications
    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:2.0.4")

    // Rolla SDK - android_release includes flutter_release (Dart code) as a transitive dependency
    implementation("com.rolla.sdk:android_release:0.1.1")
}
```

---

For detailed integration instructions see [ANDROID_INTEGRATION.md](https://github.com/Rolla-Health-Fitness/rolla-sdk/blob/dev/ANDROID_INTEGRATION.md).
