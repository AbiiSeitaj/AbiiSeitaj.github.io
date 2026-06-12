# CmdCrafter

CmdCrafter is a static command builder for Linux shell workflows. It helps users compose commands, inspect common flags, add arguments, and connect commands into pipelines without installing a backend or build toolchain.

## Features

- Searchable command catalog for common Linux administration commands.
- Workflow presets for common command shapes such as disk usage, service errors, endpoint checks, and match counting.
- Click-to-toggle flags with short descriptions.
- Argument inputs tailored to each command.
- Pipeline builder for chaining commands with `|`.
- Token-level explanations for commands, flags, arguments, and pipe connectors.
- Light and dark themes persisted in the browser.
- Copy-ready command output.

## Run locally

Open `index.html` directly in a browser. No package manager, build step, or server is required.

## Deploy

This repository is ready for GitHub Pages because the app is a single static HTML file. Deploy from the `main` branch and serve the repository root.

## Project structure

```text
index.html   Static app, styles, command registry, and browser-side logic
README.md    Repository documentation
```

## Extension points

The command registry is exposed through `window.CmdCrafter`. The legacy `window.ShellCrafter` alias remains available for compatibility. Additional commands can be registered at runtime with:

```js
window.CmdCrafter.registerCommand({
  name: "example",
  full: "describe the command",
  flags: [
    { f: "-v", d: "Enable verbose output" }
  ],
  arg: { placeholder: "target", label: "TARGET" }
});
```
