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
    <version>1.0.1</version> 
    <relativePath/> 
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

You don’t need to edit this parent POM yourself.  
However, to be able to use it in your projects, Maven must know how to access the GitHub Packages repository where this POM is stored.  
This requires a one-time configuration of your `settings.xml`.

### Step 1: Create or open your `settings.xml`
In IntelliJ: Right click on a `pom.xml` file in your project > Maven > Create/Open settings.xml
![createsettingsxml](images/createsettingsxml.png)

By default, the settings.xml is located in your Maven home directory under `.m2/settings.xml`.

### Step 2: Add your GitHub credentials
Edit your `settings.xml` and add the following snippet inside the `<settings>` element:

```xml
<servers>
  <server>
    <id>github</id>
    <username>YOUR_GITHUB_USERNAME</username>
    <password>YOUR_PERSONAL_ACCESS_TOKEN</password>
  </server>
</servers>
```

Replace YOUR_GITHUB_USERNAME with your GitHub username.

Replace YOUR_PERSONAL_ACCESS_TOKEN with a token you generated from GitHub:
- Go to https://github.com/settings/tokens
- Create a Personal Access Token (classic) with at least the **read:packages** scope.
- Expiration: today + 1 year
- Copy the token and use it as the password.

⚠️ Keep your token secret — do not commit it to GitHub or share it with others.

### Step 3: Verify
Now, when you build a project that uses this parent POM, Maven will automatically download it from GitHub Packages.