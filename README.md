# Jenkins Java Build Lab

A small Java console program for practicing how to compile and run Java code in a Jenkins build. It prints a lab banner and a few status messages, making it easy to check a job's console output.

## What it does

`HelloJenkins.main()` prints six lines to standard output. The program takes no input, uses no external libraries, and does not create or modify files.

## Run locally

Install a Java Development Kit (JDK) and make sure both `javac` and `java` are available in your terminal. From the repository folder, run:

```sh
javac HelloJenkins.java
java HelloJenkins
```

The first command creates `HelloJenkins.class`. The second runs the program and prints:

```text
================================
     Jenkins Java Build Lab     
================================
Welcome to ICEM jenkins lab!
Java program executed successfully.
Build completed using Jenkins.
```

## Use with Jenkins

On a Jenkins agent with a JDK installed:

1. Create a Freestyle project and configure its Git source to check out this repository.
2. Add an **Execute shell** build step on Linux/macOS, or an **Execute Windows batch command** step on Windows.
3. Use the following commands to compile the file and run it only if compilation succeeds:

   ```sh
   javac HelloJenkins.java && java HelloJenkins
   ```

4. Run the job and open its console output to see the banner and messages.

Jenkins job configuration is not included in this repository; there is no `Jenkinsfile`, Maven configuration, or Gradle configuration.

## Files

| File | Purpose |
| --- | --- |
| `HelloJenkins.java` | The program's single class and `main()` entry point. |

## Scope

This is a compilation and execution exercise. There are no automated tests or application features beyond console output. All messages are fixed strings: the line saying the build completed using Jenkins appears even when the program runs locally. Use the job's actual result and process exit status to determine whether a Jenkins build succeeded.
