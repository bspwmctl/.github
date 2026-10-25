# Contributing to bspwmctl

Thank you for your interest in contributing! Every contribution helps, whether it is a bug report, a fix, a test on a new distro or an improvement to the docs.

This guide applies to every repository in the [bspwmctl organization](https://github.com/bspwmctl). Please also read our [Code of Conduct](CODE_OF_CONDUCT.md).

## Repositories

| Repository | What lives there |
|------------|------------------|
| [bspwmctl](https://github.com/bspwmctl/bspwmctl) | The command-line tool and its default configs |
| [docs](https://github.com/bspwmctl/docs) | The documentation site, [bspwmctl.github.io/docs](https://bspwmctl.github.io/docs/) |
| [themes](https://github.com/bspwmctl/themes) | Community themes *(coming soon)* |
| [scripts](https://github.com/bspwmctl/scripts) | Community scripts *(coming soon)* |

## Ways to contribute

| If you want to... | then... |
|-------------------|---------|
| report a **bug** | open a [bug report](https://github.com/bspwmctl/bspwmctl/issues/new?template=bug_report.yml) |
| suggest a **feature** | open a [feature request](https://github.com/bspwmctl/bspwmctl/issues/new?template=feature_request.yml) |
| report a **documentation** problem | open an [issue in docs](https://github.com/bspwmctl/docs/issues/new?template=documentation.yml) |
| ask a **question** | start a [discussion](https://github.com/bspwmctl/bspwmctl/discussions) |
| report a **security** issue | follow the [security policy](SECURITY.md), never a public issue |
| **test** on your distro | install it and tell us how it went, even if everything works |
| contribute **code or docs** | follow the steps below |

## Making changes

1. **Open or pick an issue first.** For anything bigger than a small fix, let's agree on the approach before you spend time on it. Comment on the issue so nobody duplicates your work.
2. **Fork** the repository and create a branch:
   ```bash
   git checkout -b feature/short-description
   ```
3. **Make your changes**, following the guidelines below.
4. **Commit** with a short message that starts with a verb:
   ```
   Add: restore command
   Fix: backups not created on Arch
   Update: polybar colors
   Remove: unused polybar module
   ```
5. **Open a pull request** against `main` and fill in the template. Link the issue it solves (`Closes #42`).

## Guidelines for bspwmctl

- **Bash** with `set -Eeuo pipefail`, 2-space indentation, and the `log` / `success` / `warn` / `die` helpers for output.
- **Run the checks** before opening a pull request:
  ```bash
  bash -n bspwmctl
  shellcheck --severity=warning bspwmctl
  ```
  GitHub Actions runs them too, builds the `.deb`, `.rpm` and Arch packages, and test-installs them on Ubuntu, Debian, Fedora and Arch.
- **Test in a VM or a container**, never on your daily machine: `bspwmctl install` installs packages and replaces configs.
- **Packages:** if you add one, check that it exists with that name in Debian/Ubuntu, Arch and Fedora. Names often differ.
- **Default configs** must work on any machine: no hardcoded monitors, network interfaces, home paths or programs that bspwmctl doesn't install.
- **Changelog:** add your change to the `Unreleased` section of `CHANGELOG.md`.

## Guidelines for the docs

The site uses [docsify](https://docsify.js.org/), so pages are plain Markdown. To preview your changes locally:

```bash
cd docs
python3 -m http.server 3000
# open http://localhost:3000
```

Keep the docs in sync with the tool: if a command, option or keybinding changes in bspwmctl, update the docs in the same release.

## Questions

Not sure about something? Ask in [Discussions](https://github.com/bspwmctl/bspwmctl/discussions) or in your pull request. There are no silly questions.
