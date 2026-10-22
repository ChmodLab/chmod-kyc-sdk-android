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
    defaultConfig {
        minSdk = 24
    }
    compileOptions {
        isCoreLibraryDesugaringEnabled = true
        sourceCompatibility = JavaVersion.VERSION_11
        targetCompatibility = JavaVersion.VERSION_11
    }
}

dependencies {
    // VERSION: the latest one in com/chmod/kyc/chmod-kyc-sdk-android/maven-metadata.xml.
    implementation("com.chmod.kyc:chmod-kyc-sdk-android:VERSION")
    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:2.1.4")
}
```

It needs Android 7.0 (API 24) or later and core library desugaring. Gradle takes the liveness module
the SDK depends on from this same repository. The SDK's manifest declares the camera, location and
internet permissions, and the flow asks for them when it needs them: there is nothing to add.

Each version is published once and never replaced. This repository is written by chmod's release
pipeline: don't edit it by hand.
