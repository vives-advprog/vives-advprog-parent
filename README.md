# VIVES AdvProg Parent POM

## Overview
This repository contains the **parent Maven POM** for all Advanced Programming projects.
It centralizes common configurations such as:

- Java version (currently set to Java 25)  
- Compiler plugin configuration  
- Shared testing dependencies (JUnit, AssertJ)  
- Dependency management  

By using this parent POM, you can centralize version management, streamline the development process for all your Java projects, ensure consistent standards, and simplify updates.
Whenever a new Java LTS or library version is released, you only need to update this parent POM, and all projects can benefit from the changes by updating the parent version.

---

## How to Use in Your Project

In your project’s `pom.xml`, declare this parent:

```xml
<parent>
    <groupId>be.vives.advprog</groupId>
    <artifactId>parent</artifactId>
    <version>1.0.1</version> <!-- use the latest release -->
    <relativePath/> <!-- fetch from GitHub Packages -->
</parent>
```
Then you can add project-specific dependencies and plugins as needed.
The Java version, compiler settings, and common test libraries are automatically inherited.

---

## Publishing New Versions

1. Update the `pom.xml` in this repository:
   - Change the Java version if needed (e.g., `25` → `26`)
   - Update or add dependencies as required
   - Increase the version number (e.g., `1.0.1` → `1.0.2`)

2. Commit your changes:

```bash
git add pom.xml
git commit -m "Update parent POM for Java 25 and dependencies"
```

3. Tag the new version:

```bash
git tag v1.0.2
git push origin main --tags
```

4. GitHub Actions will automatically deploy the new version to GitHub Packages.

    Students can then use the new version in their projects by updating the `<version>` in their parent declaration.

## Notes for Students

You do not need to clone or install this repository locally.

Simply reference the latest version in your project POM.

Always check for the latest parent version before starting a new assignment to ensure your project uses the latest Java version and dependencies.
