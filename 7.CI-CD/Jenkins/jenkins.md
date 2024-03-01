# Jenkins Interview questions

## 1. What is Jenkins?

Jenkins is an open-source automation server used for building, testing, and deploying software projects. It facilitates Continuous Integration (CI) and Continuous Delivery (CD) by automating the repetitive tasks involved in the software development process.

## 2. Which SCM tools does Jenkins support?

Jenkins supports various Source Code Management (SCM) tools, including Git, Subversion, Mercurial, CVS, Perforce, and more.

## 3. What is Groovy?

Groovy is a powerful, optionally typed and dynamic language for the Java Virtual Machine (JVM). In Jenkins, Groovy is used extensively for scripting tasks, defining pipelines, and configuring jobs.

## 4. Name the Jenkins suite's essential plugins.

Essential plugins for Jenkins include:

- Pipeline
- Git
- Maven
- Credentials
- Build Pipeline
- Blue Ocean
- GitHub

## 5. What are the ways to trigger a Jenkins job?

Jenkins jobs can be triggered in several ways, including:

- Manual trigger by a user
- Periodic builds at scheduled intervals
- Triggered by changes in the source code repository (e.g., SCM polling)
- Triggered by other jobs (upstream/downstream dependencies)
- Triggered by external events via webhooks or APIs

## 6. Name the types of pipelines in Jenkins.

There are two main types of pipelines in Jenkins:

- Scripted Pipeline
- Declarative Pipeline

## 7. What is meant by Blue Ocean when using Jenkins?

Blue Ocean is a modern and user-friendly interface for Jenkins that provides a visual and intuitive way to create, manage, and visualize Jenkins pipelines and projects.

## 8. What are the requirements for using Jenkins?

To use Jenkins, you need:

- A machine to host the Jenkins server (can be on-premises or cloud-based)
- Java Development Kit (JDK) installed on the server
- Sufficient memory and disk space for Jenkins and its plugins
- Network access for communication with source code repositories, build servers, and other systems

## 9. What is Jenkinsfile?

A Jenkinsfile is a text file written in Groovy syntax that defines the entire pipeline for a Jenkins job. It is checked into source control along with the project's source code and describes how the pipeline should be executed.

## 10. What are the system requirements to install Jenkins?

The system requirements to install Jenkins include:

- Operating System: Linux, Windows, macOS, or any Unix-like system
- Java Development Kit (JDK) version 8 or later
- Sufficient memory (recommended minimum of 256 MB RAM, but higher for production environments)
- Disk space for Jenkins installation and workspace
- Network connectivity for accessing plugins, repositories, and other resources

## 11. What are the steps included in a Jenkins pipeline?

A Jenkins pipeline typically includes the following steps:

1. Checkout source code from version control system
2. Build the project
3. Run automated tests
4. Perform static code analysis
5. Package the application
6. Deploy the application to a test environment
7. Run integration tests
8. Deploy the application to production (if tests pass)

## 12. Give Syntax for Declarative Jenkins Pipeline.

```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Build steps
            }
        }
        stage('Test') {
            steps {
                // Test steps
            }
        }
        stage('Deploy') {
            steps {
                // Deployment steps
            }
        }
    }
}
```

## 13. Write a simple Jenkins pipeline.

```grovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
            }
        }
    }
}

```

## 14. What is Continuous Integration?

Continuous Integration (CI) is a software development practice where developers regularly merge their code changes into a central repository, after which automated builds and tests are run. The goal is to detect and fix integration errors early in the development process.

## 15. What is Continuous Delivery?

Continuous Delivery (CD) is an extension of Continuous Integration where software is built, tested, and deployed to production environments automatically. The aim is to ensure that changes to the software can be released reliably and quickly at any time.

## 16. What is Continuous Deployment?

Continuous Deployment is the practice of automatically deploying every change that passes through the CI/CD pipeline to production environments without human intervention.

## 17. How can you start Jenkins manually?

Jenkins can be started manually by executing the startup command. For example, on Unix-like systems:

```bash
To start Jenkins: jenkins.exe start
To stop: jenkins.exe stop
to restart: jenkins.exe restart
```

## 18. What is the native scripting language used in Jenkins?

The native scripting language used in Jenkins is Groovy.

## 19. What are the credential types supported by Jenkins?

Jenkins supports various types of credentials, including:

- Username and password
- SSH username with private key
- Secret text
- Secret file
- Certificate
- Docker Host Certificate Authentication

## 20. What is Jenkins Job DSL?

Jenkins Job DSL (Domain-Specific Language) is a plugin that allows you to define Jenkins jobs programmatically using Groovy code. It provides a convenient way to manage and version control Jenkins job configurations.

## 21. How can you define the Control Flows in Pipeline?

Control flows in Jenkins Pipeline can be defined using conditional statements (e.g., `if`, `else`, `switch`), loops (e.g., `for`, `while`), and stages (e.g., `parallel`, `timeout`). These constructs help in controlling the flow of execution within a pipeline.

## 22. How do you start Jenkins?

Jenkins can be started by running the Jenkins WAR file using Java. For example:

```bash
 java -jar jenkins.war
```

## 23. How will you secure Jenkins?

Jenkins can be secured by enabling security features such as authentication, authorization, and encryption. This includes setting up user accounts with strong passwords, restricting access to sensitive Jenkins features, and configuring secure communication protocols.

## 24. What are the types of jobs or projects in Jenkins?

The types of jobs or projects in Jenkins include:

- Freestyle projects
- Pipeline projects
- Multi-configuration projects
- Maven projects
- GitHub organization projects
- Folder projects

## 25. Define the Agent.

An agent in Jenkins is a worker node that executes the steps of a pipeline or job. It can be a physical or virtual machine configured to run specific tasks and may have dependencies installed based on the requirements of the pipeline or job.

## 26. What is the relation between Hudson and Jenkins?

Jenkins is a fork of the Hudson project. After a dispute within the Hudson community, the majority of the developers decided to fork the project and continue its development under the name Jenkins.

## 27. What is the default port in Jenkins? And range of ports can be used? And what is the command to start Jenkins on a specific port number?

The default port in Jenkins is 8080. The range of ports that can be used varies depending on system configurations.(it can be 8080-8099) To start Jenkins on a specific port number, you can use the `--httpPort` option followed by the desired port number when starting Jenkins. For example:

```bash
java -jar jenkins.war --httpPort=8089
```

## 28. How to delete old builds automatically?

You can delete old builds automatically in Jenkins by configuring the "Discard Old Builds" option in the job configuration. You can specify criteria such as the number of builds to keep or how long to keep builds before they are automatically deleted.

## 29. How to install plugins? and custom plugins?

You can install plugins in Jenkins through the Jenkins web interface. Navigate to "Manage Jenkins" > "Manage Plugins" > "Available" tab, select the plugins you want to install, and click "Install without restart". To install custom plugins, you can upload the plugin file directly through the same interface.

## 30. How to run pipeline parallelly?

To run a pipeline in parallel in Jenkins, you can use the `parallel` directive within the pipeline script. This allows you to execute multiple stages or tasks concurrently, improving build efficiency and reducing overall build time.

## 31. How to run multibranch pipeline parallelly?

To run a multibranch pipeline in parallel in Jenkins, you can define parallel stages within each branch's Jenkinsfile. By leveraging the `parallel` directive and defining multiple branches with parallel execution, you can optimize the build process and achieve faster results.
