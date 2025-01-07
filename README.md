# Advanced Programming Project Parent POM

This project contains the Parent POM for all project in Advanced Programming managing common dependencies, plugins, and configurations across multiple Maven projects. 
By using this parent POM, you can centralize version management and streamline the development process for all your Java projects.

## How to Use

### 1. Clone this Repository

Clone the repository to your local machine using the following command:

```bash
git clone https://github.com/vives-advprog/advprog-project-parent.git
cd advprog-project-parent
```

### 2. Install the Parent POM Locally
After cloning, you need to install the Parent POM into your local Maven repository. This makes it accessible to all your child projects on your machine:
    
```bash 
mvn install
```
This command adds the Parent POM to your local `.m2` Maven repository. It allows child projects to reference it using its `groupId`, `artifactId`, and `version`.





