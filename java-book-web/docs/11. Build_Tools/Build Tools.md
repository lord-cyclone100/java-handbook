# Java Build Tools: Maven & Gradle

## Navigation
- [Introduction](#introduction)
- [Apache Maven](#apache-maven)
    - [Maven Basics](#maven-basics)
    - [Maven Lifecycle](#maven-lifecycle)
    - [Dependency Management](#dependency-management)
- [Gradle](#gradle)
    - [Gradle Basics](#gradle-basics)
    - [Gradle Build Lifecycle](#gradle-build-lifecycle)
    - [Dependency Management](#gradle-dependency-management)
- [Comparison: Maven vs. Gradle](#comparison-maven-vs-gradle)
- [Best Practices](#best-practices)
- [Resources](#resources)

---

## Introduction
Java build tools automate compilation, testing, packaging, and deployment. **Maven** and **Gradle** are two widely used build automation tools in Java projects. They manage dependencies, streamline builds, and integrate with CI/CD pipelines.

---

## Apache Maven
### Maven Basics
Maven is a project management and build automation tool based on **POM (Project Object Model)**.

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" 
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>demo-app</artifactId>
    <version>1.0-SNAPSHOT</version>
</project>
```
**Explanation:**
- `<groupId>`: Unique identifier for a project (e.g., company domain).
- `<artifactId>`: Name of the project artifact.
- `<version>`: Versioning information.

### Maven Lifecycle
Maven follows a predefined build lifecycle:
1. **clean** - Removes previous build artifacts.
2. **compile** - Compiles the source code.
3. **test** - Runs unit tests.
4. **package** - Creates a JAR/WAR file.
5. **install** - Installs the package in the local repository.
6. **deploy** - Publishes the package to a remote repository.

### Dependency Management
Maven manages dependencies via **Maven Central Repository**:
```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
        <version>2.7.4</version>
    </dependency>
</dependencies>
```
**Explanation:**
- Dependencies are defined in the `<dependencies>` section of the `pom.xml` file.
- Maven resolves and downloads the required JAR files automatically.

---

## Gradle
### Gradle Basics
Gradle uses a **Groovy** or **Kotlin**-based DSL instead of XML.

**Example: `build.gradle`**
```groovy
plugins {
    id 'java'
}

group 'com.example'
version '1.0-SNAPSHOT'

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-web:2.7.4'
}
```
**Explanation:**
- **`plugins`**: Defines plugins such as `java`.
- **`repositories`**: Specifies repositories for dependency resolution.
- **`dependencies`**: Declares dependencies required by the project.

### Gradle Build Lifecycle
Gradle uses **task-based execution** instead of a fixed lifecycle.
- `gradle build` → Compiles, tests, and packages the application.
- `gradle clean` → Cleans previous builds.
- `gradle test` → Runs unit tests.
- `gradle run` → Runs the application.

### Dependency Management
Gradle manages dependencies in a **`dependencies`** block:
```groovy
dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-web:2.7.4'
    testImplementation 'junit:junit:4.13.2'
}
```

---

## Comparison: Maven vs. Gradle
| Feature         | Maven                            | Gradle                          |
|---------------|--------------------------------|--------------------------------|
| Language      | XML (`pom.xml`)                 | Groovy/Kotlin (`build.gradle`) |
| Speed        | Slower due to sequential tasks  | Faster with incremental builds |
| Lifecycle    | Fixed lifecycle phases         | Task-based execution          |
| Dependency Management | Central Repository | Flexible dependency resolution |
| Configuration | Declarative (XML)             | Scriptable (Groovy/Kotlin)    |

---

## Best Practices
- Use **Maven** for simple, structured projects.
- Use **Gradle** for large, performance-sensitive builds.
- Avoid unnecessary dependencies to reduce build times.
- Leverage caching in Gradle to improve performance.
- Use dependency versions carefully to avoid conflicts.
- Implement CI/CD integration for automated builds.

---

## Resources
- **Maven Documentation** → [Documentation](https://maven.apache.org/) || [Tutorial](https://www.baeldung.com/maven)
- **Gradle Documentation** → [Documentation](https://gradle.org/) || [Tutorial](https://www.baeldung.com/gradle)
- **YouTube Tutorial** → [YouTube](https://youtu.be/s6W2R1Z3wd4?feature=shared)

