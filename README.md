# maven-repo

Git backed Maven repository for personal projects — the successor to the Ivy layout `ivy-config` repository.

## Consuming

No checkout needed. Add the repository to a Gradle build:

```kotlin
repositories {
	mavenCentral()
	maven {
		url = uri("https://raw.githubusercontent.com/OllieMilton/maven-repo/main")
	}
}
```

## Publishing

No checkout needed here either. Bump `version` in the project's `build.gradle.kts` and run:

```
./gradlew publish
```

The build clones this repository into its build directory, publishes into the clone, then commits and pushes the result (commit message `Published group:artifact:version`). Push access via ssh is all that is required. To publish somewhere else (e.g. for testing) override the target with `-PmavenRepoGitUri=<uri>`.

Note that raw.githubusercontent.com caches responses for a few minutes, so a freshly published artefact can take a short while to become visible to consumers.

## Contents

| Group | Artifact | Notes |
|-------|----------|-------|
| `ollie.utils` | `utils` | github.com/OllieMilton/utils |
| `com.jaudiostream` | `jaudiostream` | github.com/OllieMilton/jaudio-stream |
| `serialiser` | `serialiser` | 1.29 seeded from ivy-config (2015 build, no current source project) |
