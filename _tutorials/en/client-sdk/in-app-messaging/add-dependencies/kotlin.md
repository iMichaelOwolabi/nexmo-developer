---
title: Add dependencies
description: In this step you add external dependencies
---

# Add dependencies

## Add Nexmo

You need to add a custom Maven URL repository to your Gradle configuration. Add the following `maven` block inside `allprojects` block in the project-level `build.gradle` file:

```screenshot
image: public/screenshots/tutorials/client-sdk/android-shared/project-level-build-gradle-file.png
```

```groovy
allprojects {
    repositories {
        google()
        jcenter()
        
        maven {
            url "https://artifactory.ess-dev.com/artifactory/gradle-dev-local"
        }
    }
}
```

Now add the Client SDK to the project. Add the following dependency in the module level `build.gradle` file.:

```screenshot
image: public/screenshots/tutorials/client-sdk/android-shared/module-level-build-gradle-file.png
```

```groovy
dependencies {
    // ...

    implementation 'com.nexmo.android:client-sdk:2.8.0'
}
```

## Add Navigation component

To navigate between screens you will use [Navigation component](https://developer.android.com/guide/navigation).

To add navigation component dependency define a variable `ext.android_navigation_version` containing version in project-level `build.gradle` file:

```screenshot
image: public/screenshots/tutorials/client-sdk/android-shared/project-level-build-gradle-file.png
```

```groovy
buildscript {
    ext.android_navigation_version = '2.3.2'

    // ...
}
```

In the same file, add a dependency for the Gradle `Safe Args` plugin. This provides type safety when navigating and passing data between destinations.

Add a new `classpath` in the `dependencies` block:

```groovy
dependencies {
    // ...

    classpath "androidx.navigation:navigation-safe-args-gradle-plugin:$android_navigation_version"
}
```

Add `Safe Args` plugin in the module level `build.gradle` file:

```screenshot
image: public/screenshots/tutorials/client-sdk/android-shared/module-level-build-gradle-file.png
```

```groovy
plugins {
    // ...
    id 'androidx.navigation.safeargs.kotlin'
}
```

In the same file, add navigation component dependencies:

```groovy
dependencies {
    // ...

    implementation "androidx.navigation:navigation-fragment-ktx:$android_navigation_version"
    implementation "androidx.navigation:navigation-ui-ktx:$android_navigation_version"
}
```

Click the `Sync project with Gradle Files` icon to make sure build scripts have been correctly configured:

```screenshot
image: public/screenshots/tutorials/client-sdk/android-shared/sync-project-wth-gradle-files.png
```
