yum install maven
"yum remove maven for unistall"

If you're asking for the **basic steps to use Apache Maven**, here's a simple workflow:

### 1. Install Maven

* Install the **JDK** first.
* Download Maven from the official site:

  * [Apache Maven](https://maven.apache.org/?utm_source=chatgpt.com)
* Verify installation:

```bash
mvn -version
```

### 2. Create a Maven Project

Generate a new project using an archetype:

```bash
**mvn archetype:generate** \
  -DgroupId=com.example \
  -DartifactId=my-app \
  -DarchetypeArtifactId=maven-archetype-quickstart \
  -DinteractiveMode=false
```

This creates a project structure like:

```
my-app
│
├── pom.xml
└── src
    ├── main
    │   └── java
    └── test
        └── java
```

### 3. Understand `pom.xml`

The `pom.xml` file is Maven's configuration file.

Example:

```xml
<project>
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>my-app</artifactId>
    <version>1.0</version>

    <dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.13.2</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```

### 4. Compile the Project

```bash
mvn compile
```

Compiles source code and places `.class` files in the `target` directory.

### 5. Run Tests

```bash
mvn test
```

Executes unit tests.

### 6. Package the Application

```bash
mvn package
```

Creates a JAR/WAR file in the `target` directory.

Example output:

```
target/my-app-1.0.jar
```

### 7. Clean Build Artifacts

```bash
mvn clean
```

Deletes the `target` directory.

### 8. Install to Local Repository

```bash
mvn install
```

Builds the project and installs the artifact into your local Maven repository (`~/.m2/repository`).

### Common Maven Commands

| Command               | Purpose                     |
| --------------------- | --------------------------- |
| `mvn clean`           | Remove previous build files |
| `mvn compile`         | Compile source code         |
| `mvn test`            | Run tests                   |
| `mvn package`         | Create JAR/WAR              |
| `mvn install`         | Install artifact locally    |
| `mvn dependency:tree` | Show dependency hierarchy   |
| `mvn spring-boot:run` | Run Spring Boot application |

### Typical Daily Workflow

```bash
mvn clean
mvn compile
mvn test
mvn package
```

Or simply:

```bash
mvn clean install
```

which performs the entire build lifecycle and installs the artifact locally.
