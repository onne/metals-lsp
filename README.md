# metals-lsp

Scala language server ([Metals](https://scalameta.org/metals/)) for Claude Code, providing code intelligence features like go-to-definition, find references, hover information, and refactoring.

## Supported Extensions
`.scala`, `.sc`, `.sbt`

## Installation

This plugin connects Claude Code to the Metals language server. You must install the `metals` binary separately and have it on your `PATH`.

### Requirements
- A JDK (Java 17 or later)
- A supported, importable build (sbt, Gradle, Maven, Mill, or Bazel). Metals
  bootstraps its build server (Bloop) automatically on first open — you do not
  install it yourself. Navigation and hover work via the presentation compiler
  even before import; compile diagnostics require the build to be imported.

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

## How it works

Metals serves two kinds of intelligence:

- **Presentation compiler** — hover, go-to-definition, find references, and
  completion. These work per-file and do not require a connected build server.
- **Build server (Bloop)** — project-wide compile diagnostics (type mismatches,
  missing implicits, unused imports). These are produced on file **save** for the
  module containing the file, and require the build to have been imported.

## More Information
- [Metals website](https://scalameta.org/metals/)
- [Metals GitHub repository](https://github.com/scalameta/metals)
