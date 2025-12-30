# Documentation of Gradle Module Metadata, Attributes, and Rules

The Gradle [dependency resolution algorithm](https://docs.gradle.org/current/userguide/variant_aware_resolution.html#sec:abm-algorithm) is complex. 

This repository aims to document how different attributes are used so that best practices can emerge.

If you are a plugin author, please contribute to this repository by documenting how your plugin uses attributes.

## Known attributes

### From Gradle
- `org.gradle.usage`
  - [Source code](https://github.com/gradle/gradle/blob/master/subprojects/core-api/src/main/java/org/gradle/api/attributes/Usage.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/Usage.html)
  - Setting this attribute is strongly recommended.
  - Known values
    - `java-runtime`
    - `java-api`
    - `kotlin-metadata`
    - `kotlin-api`
- `org.gradle.category` 
  - [Source code](https://github.com/gradle/gradle/blob/master/subprojects/core-api/src/main/java/org/gradle/api/attributes/Category.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/Category.html)
  - Known values
    - `documentation`
    - `library`
- `org.gradle.dependency.bundling`
  - [Source code](https://github.com/gradle/gradle/blob/master/subprojects/core-api/src/main/java/org/gradle/api/attributes/Bundling.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/Bundling.html)
  - Known values
    - `external`
- `org.gradle.docstype`
  - [Source code](https://github.com/gradle/gradle/blob/master/subprojects/core-api/src/main/java/org/gradle/api/attributes/DocsType.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/DocsType.html)
- `org.gradle.libraryelements`
  - [Source code](https://github.com/gradle/gradle/blob/master/subprojects/core-api/src/main/java/org/gradle/api/attributes/LibraryElements.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/LibraryElements.html)
  - Known values
    - `aar`
    - `jar`
- `org.gradle.jvm.environment`
  - [Source code](https://github.com/gradle/gradle/blob/master/platforms/jvm/jvm-services/src/main/java/org/gradle/api/attributes/java/TargetJvmEnvironment.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/java/TargetJvmEnvironment.html)
  - Known values
    - `android`
    - `standard-jvm`
    - `non-jvm`
- `org.gradle.jvm.version`
  - [Source code](https://github.com/gradle/gradle/blob/master/subprojects/core-api/src/main/java/org/gradle/api/attributes/java/TargetJvmVersion.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/java/TargetJvmVersion.html)
- `org.gradle.docstype`
  - [Source code](https://github.com/gradle/gradle/blob/master/subprojects/core-api/src/main/java/org/gradle/api/attributes/DocsType.java)
  - [Documentation](https://docs.gradle.org/nightly/javadoc/org/gradle/api/attributes/DocsType.html)
  - Known values
    - `sources`

### From Kotlin Gradle Plugin
- `org.jetbrains.kotlin.platform.type`
  - [Source code](https://github.com/JetBrains/kotlin/blob/master/libraries/tools/kotlin-gradle-plugin-api/src/common/kotlin/org/jetbrains/kotlin/gradle/plugin/KotlinPlatformType.kt) 
  - Known values
    - `common`
    - `native`
    - `js`
    - `jvm`
    - `wasm`
- `org.jetbrains.kotlin.native.target`
  - [Source code](https://github.com/JetBrains/kotlin/blob/master/libraries/tools/kotlin-gradle-plugin/src/common/kotlin/org/jetbrains/kotlin/gradle/targets/native/KotlinNativeTarget.kt)
  - Known values
    - `android_arm32`
    - `android_arm64`
    - `android_x64`
    - `android_x86`
    - `ios_arm64`
    - `ios_simulator_arm64`
    - `ios_x64`
    - `linux_arm64`
    - `linux_x64`
    - `macos_arm64`
    - `macos_x64`
    - `mingw_x64`
    - `tvos_arm64`
    - `tvos_simulator_arm64`
    - `tvos_x64`
    - `watchos_arm32`
    - `watchos_arm64`
    - `watchos_device_arm64`
    - `watchos_simulator_arm64`
    - `watchos_x64`
- `org.jetbrains.kotlin.js.compiler`
  - [Source code](https://github.com/JetBrains/kotlin/blob/master/libraries/tools/kotlin-gradle-plugin/src/common/kotlin/org/jetbrains/kotlin/gradle/targets/js/KotlinJsCompilerAttribute.kt)
  - Known values
    - `ir`
- `org.jetbrains.kotlin.wasm.target`
  - [Source code](https://github.com/JetBrains/kotlin/blob/master/libraries/tools/kotlin-gradle-plugin/src/common/kotlin/org/jetbrains/kotlin/gradle/targets/js/KotlinWasmCompilerAttribute.kt)
  - Known values
    - `js`
    - `wasi`

### From Kotlin Resources Plugin
- `dev.opensavvy.resources`
  - [Source code](https://gitlab.com/opensavvy/automation/kotlin-js-resources/-/blob/main/shared/src/main/kotlin/Attributes.kt)
  - [Documentation](https://kotlin-resources.opensavvy.dev/)
  - Known values
    - `Regular`
  - Must be used alongside
    - `org.gradle.category`
    - `org.gradle.libraryelements`
    - `org.jetbrains.kotlin.platform.type`
    - `org.jetbrains.kotlin.native.target`
