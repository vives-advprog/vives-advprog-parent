# Publishing New Versions

Students don’t need to, and cannot, edit this parent POM. Only the repository maintainers can do that.
However, to publish a new version (e.g., when a new Java LTS or library version is released), follow these steps:

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