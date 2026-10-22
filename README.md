# chmod KYC SDK for Android

Compiled releases of the chmod KYC SDK for Android, as a Maven repository. Installing it needs no
GitHub account or token.

```kotlin
// settings.gradle.kts
dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()
        maven { url = uri("https://raw.githubusercontent.com/ChmodLab/chmod-kyc-sdk-android/main") }
    }
}

// app/build.gradle.kts
android {
    compileOptions {
        isCoreLibraryDesugaringEnabled = true
    }
}

dependencies {
    implementation("com.chmod.kyc:chmod-kyc-sdk-android:VERSION")
    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:2.1.4")
}
```

Each version is published once and never replaced.

This repository is written by chmod's release pipeline: don't edit it by hand.
