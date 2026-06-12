# Rolla SDK — Android

Android distribution repository for the Rolla Flutter SDK. Artifacts are served as a Maven repository via GitHub Pages.

**Latest version:** `0.1.18-test.257.1`

---

## Installation

### 1. Add Maven repositories to `settings.gradle.kts`

```kotlin
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()

        // Rolla SDK repository
        maven {
            url = uri("https://rolla-health-fitness.github.io/rolla-sdk-release-test-android/maven/")
        }

        // Flutter engine artifacts
        maven {
            url = uri("https://storage.googleapis.com/download.flutter.io")
        }

        // Mapbox SDK for maps
        maven {
            url = uri("https://api.mapbox.com/downloads/v2/releases/maven")
        }
    }
}
```

### 2. Add dependencies to `app/build.gradle.kts`

```kotlin
dependencies {
    // Core library desugaring (required by SDK)
    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:2.0.4")

    // Rolla SDK
    implementation("com.rolla.sdk:android_release:0.1.18-test.257.1")
}
```

Enable core library desugaring in the android block:

```kotlin
android {
    compileOptions {
        isCoreLibraryDesugaringEnabled = true
    }
}
```

### 3. Sync Project

Click "Sync Now" in the Gradle notification bar, or run:

```
./gradlew --refresh-dependencies
```

---

For detailed integration instructions see the [Android Integration Guide](https://github.com/Rolla-Health-Fitness/rolla-sdk-documentation/tree/dev/android).
