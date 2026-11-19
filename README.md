# Groovy Language Server

A [language server](https://microsoft.github.io/language-server-protocol/) for [Groovy](http://groovy-lang.org/). It is designed specifically for [Moonshine IDE](https://moonshine-ide.com), but it may work in other editors and environments.

The following language server protocol requests are currently supported:

- completion
- definition
- documentSymbol
- hover
- references
- rename
- signatureHelp
- symbol
- typeDefinition

The following configuration options are supported:

- groovy.java.home (`string` - sets a custom JDK path)
- groovy.classpath (`string[]` - sets a custom classpath to include _.jar_ files)

## Build

To build from the command line, run the following command:

```sh
./gradlew build
```

This will create _build/libs/groovy-language-server-all.jar_.

## Run

To run the language server, use the following command:

```sh
java -jar groovy-language-server-all.jar
```

Language server protocol messages are passed using standard I/O by default.

## Releases

Prebuilt packages are published to [GitHub Releases](https://github.com/jayChoa/groovy-language-server/releases). To publish a new release, push a tag whose name starts with `v`:

```sh
git tag v1.0.0
git push origin v1.0.0
```

The workflow then builds the project and attaches the following assets to the release:

- `groovy-language-server-all.jar` — the runnable language server (see [Run](#run))
- `groovy-*.vsix` — the VS Code extension
- `SHA256SUMS.txt` — checksums for the downloaded files

Release assets are downloaded directly from the release page; no build tools are required.

## Editors and IDEs

A sample language extension for Visual Studio Code is available in the _vscode-extension_ directory. There are no plans to release this extension to the VSCode Marketplace.

Instructions for setting up the language server in Sublime Text is available in the _sublime-text_ directory. Configuring the language server in other editors will likely be very similar.

Moonshine IDE natively provides a Grails project type that automatically configures the language server.
