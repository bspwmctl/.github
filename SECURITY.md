# Security Policy

## Supported versions

Only the latest release of [bspwmctl](https://github.com/bspwmctl/bspwmctl/releases) receives security fixes.

## Reporting a vulnerability

**Please do not report security issues in public issues, discussions or pull requests.**

Report them privately instead:

- **Preferred:** use GitHub's private reporting. Open the **Security** tab of the affected repository and click **Report a vulnerability**.
- **Or by email:** lukatinarelli@protonmail.com

Please include:

- What the issue is and where it is (file, command, config)
- Steps to reproduce it
- The bspwmctl version (`bspwmctl --version`) and your distribution

You will get an answer as soon as possible. Once the issue is confirmed, a fix will be released and you will be credited in the release notes, unless you prefer to stay anonymous.

## Scope

bspwmctl runs commands with `sudo` and writes to your home directory, so we take these especially seriously:

- Commands run with more privileges than needed
- Files written outside the expected locations
- Configs or scripts that execute untrusted code
