# basic-gradle-template

Basic gradle template with subprojects, deployable to Heroku as separate dyno processes.

## What's included?

1. Gradle Plugins
    - application plugin
    - shadowjar plugin
2. Code Style
    - checkstyle
    - findbugs
    - pmd
3. General Libraries
    - guava
    - junit
    - mockito
    - log4j2 via slf4j
4. Multi-Project Gradle Setup
    - see: [settings.gradle](settings.gradle)
5. Heroku Deployment
    - see: [Procfile](Procfile), [stage.gradle](gradle/heroku/stage.gradle)

## Development

### Building

```
$ ./gradlew clean build
```

### Testing

```
$ ./gradlew clean test
```

### Building Deployment Artifacts

```
$ ./gradlew clean stage
```

### Running

Use the Gradle `application` plugin. However, `./gradlew run` will run applications in lexicographical order.
Instead, explicitly specify which subproject to run:

```
$ ./gradlew template-core:run
$ ./gradlew template-server:run
```
