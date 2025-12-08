# Paper Plugin Templates

Basic Paper Plugin generator with nothing apart from the files, no sort of bloat

The files were generated with [IntelliJ IDEA](https://www.jetbrains.com/idea/download) using the [Minecraft Development](https://plugins.jetbrains.com/plugin/8327-minecraft-development) Plugin

# To download:

To use the latest version of the game, fork the repo, or use the [releases](https://github.com/huhuhuhuheh/paper-template/releases) tab by looking at the correct game version

when downloading (or forking), make sure to use the right folder (or zip) structure, this template generates one for Java and one for Kotlin for what it keeps best for you

## Note

Depending what you choose, if you want to change to an version with an earlier java, you must update the Java Version of the ToolChain. the releases tab should (in case where minecraft updates what java is required) will automatically have the right java version

(Kotlin - Inside Line 31)

```java
val targetJavaVersion = 21
kotlin {
    jvmToolchain(targetJavaVersion)
}
```

(Java - Inside Line 30)

```java
def targetJavaVersion = 21
java {
    def javaVersion = JavaVersion.toVersion(targetJavaVersion)
    sourceCompatibility = javaVersion
    targetCompatibility = javaVersion
    if (JavaVersion.current() < javaVersion) {
        toolchain.languageVersion = JavaLanguageVersion.of(targetJavaVersion)
    }
}
```
