# metals-lsp

Scala language server ([Metals](https://scalameta.org/metals/)) for Claude Code, providing code intelligence features like go-to-definition, find references, hover information, and refactoring.

## Supported Extensions
`.scala`, `.sc`, `.sbt`

## Installation

This plugin connects Claude Code to the Metals language server. You must install the `metals` binary separately and have it on your `PATH`.

### Requirements
- A JDK (Java 17 or later)

### Install Metals

**Via Coursier (recommended)**
```bash
cs install metals
```

**Via Homebrew (macOS)**
```bash
brew install coursier/formulas/coursier && cs install metals
```

See the [Metals installation docs](https://scalameta.org/metals/docs/) for other methods.

Verify the binary is available:
```bash
metals --version
```

### Install the plugin

```
/plugin marketplace add onne/metals-lsp
/plugin install metals-lsp@metals-lsp
```

(Once accepted into the community marketplace, install with `/plugin install metals-lsp@claude-community`.)

## Verify

Open any `.scala` file in a build-imported Scala project. Claude Code will start Metals automatically on first use — the initial import can take up to 90 seconds. After that, hover, go-to-definition, and find-references work on Scala symbols.

If a call reports the server is still starting, wait a few seconds and retry — Metals is importing the build.

## More Information
- [Metals website](https://scalameta.org/metals/)
- [Metals GitHub repository](https://github.com/scalameta/metals)
