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

Publishing writes into a local checkout, then the new files are committed and pushed:

1. Clone this repository next to the project being published (e.g. `~/work/maven-repo`).
2. Bump `version` in the project's `build.gradle.kts` and run `./gradlew publish`.
3. Commit and push the new artefact directory here.

Note that raw.githubusercontent.com caches responses for a few minutes, so a freshly published artefact can take a short while to become visible to consumers.

## Contents

| Group | Artifact | Notes |
|-------|----------|-------|
| `ollie.utils` | `utils` | github.com/OllieMilton/utils |
| `com.jaudiostream` | `jaudiostream` | github.com/OllieMilton/jaudio-stream |
| `serialiser` | `serialiser` | 1.29 seeded from ivy-config (2015 build, no current source project) |
