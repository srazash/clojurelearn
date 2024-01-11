# Learning Clojure

## Clojure Basics

(notes taken from: https://www.braveclojure.com/getting-started/)

Clojure projects are usually managed and built using Leiningen: http://leiningen.org/. Java is required, OpenJDK is recommended, as is using an LTS version.

Clojure itself is not required when using Leiningen, as it will pull down all required files including Clojure.

Clojure has an LSP: clojure-lsp

On Mac and Linux both Leiningen and clojure-lsp can be installed using Brew.

Leiningen is invoked with the `lein` command.

Creating a new project is done using: `lein new app <app-name>`. The app name you use will create a project directory of that name.

Once the project is created there is a basic 'Hello, world!' program ready to go.

`cd` into the project directory and run the app by executing `lein run`.

The 'Hello, world!' program is a full, valid app. It only prints a string to the screen but this ican be packaged and distributed as it is. As Clojure apps run on the JVM we compile to bytecode and package this in a JAR file.

To do this we run `lein uberjar`, which will produce a `target` directory and two JAR files:

- `<app-name>-0.1.0-SNAPSHOT.jar`, and;
- `<app-name>-0.1.0-SNAPSHOT-standalone.jar`

The standalone JAR can be shared and run on any computer with the JVM with no other Clojure tools.

This is run by executing: `java -jar /path/to/<app-name>-0.1.0-SNAPSHOT-standalone.jar`.

One of Clojure's best features is it's REPL, this can be ivoked by executing: `lein repl`.

Running this within a project directory sets the REPL's default namespace to that of the project, so you can call funcions from the project directly in the REPL. This is very useful for experimenting with how functions work and prototyping functionality against an existing codebase.

As an example, when using the REPL within a default new app project we can invoke the `-main` function like this:

```
<app-name>.core=> (-main)
Hello, world!
```

(`<app-name>.core=>` is the default prompt of the REPL when run within our project directory, reflecting our namespace.)