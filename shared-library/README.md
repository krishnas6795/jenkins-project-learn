# Shared Library

## Description:

A Jenkins Shared Library is a feature of Jenkins that allows you to define common code and functionality that can be shared across multiple Jenkins pipelines. Instead of duplicating code in each pipeline script, you can centralize it in a shared library, making maintenance and updates easier.

## Here's how it generally works:

1. Create Shared Library: You create a shared library in Jenkins by defining a Git repository containing the code that you want to share.

1. Define Functions: Inside the shared library repository, you organize your code into Groovy scripts. These scripts typically define functions or classes that can be reused across your Jenkins pipelines.

1. Configure Jenkins: In the Jenkins web interface, you configure Jenkins to use your shared library by specifying the repository URL and optionally a branch, tag, or specific commit.

1. Use in Pipelines: In your Jenkins pipeline scripts, you import and use the functions or classes defined in your shared library. Jenkins automatically loads the shared library code and makes it available to your pipelines.

### Here's a basic example of how you might use a shared library in a Jenkins pipeline:

```groovy
// Jenkinsfile

// Import shared library
@Library('my-shared-library') _

// Use shared library function
mySharedLibraryFunction()
```

### And here's an example of what the shared library code might look like:

```groovy
// vars/mySharedLibraryFunction.groovy

def call() {
    echo 'Hello from my shared library function!'
}
```

In this example, mySharedLibraryFunction is a function defined in the shared library, and we're using it in our Jenkins pipeline script.

## Advantages

Shared libraries are useful for encapsulating common logic such as build steps, deployment procedures, testing functions, and more. They promote code reuse, improve maintainability, and help ensure consistency across your Jenkins pipelines.
