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

# To fork and build your versions
First fork the repo, then depending on what you choose, it would be easy or not

## Github Actions
Nothing is required, as long as you have qouta you can make a release, it will pick it up and build for it

## CircleCI
1. Sign up to [CircleCI](https://circleci.com/)
2. When you fork the repo on GitHub, in CircleCI go to Projects and on the forked repo click Set Up, keep the option on "Select your config.yml file" to "Fatest" to use the config from the repo and click Set Up Project
3. After that, make a [GitHub Classic Token](https://github.com/settings/tokens/new) with the repo scope selected
4. Copy the token, then go back to your projects, click the 3 dots on your `paper-templates` fork, click "Project Settings" then go to "Environment Variables", click "Add" and name it `GH_TOKEN` or `GITHUB_TOKEN` (and its value is what you just copied)
5. You're done, now after you do a release of the version (or push it), it will do its job
