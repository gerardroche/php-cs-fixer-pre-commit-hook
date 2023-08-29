# PHP-CS-Fixer Pre-Commit Hook

This script runs [PHP-CS-Fixer](https://github.com/PHP-CS-Fixer/PHP-CS-Fixer) before committing code.

The fixer is **run quietly** to avoid any output. If there are violations, it is run again in verbose mode to provide information about the violations.

Only **changed files** since the last commit are checked, unless configuration files that might impact all files are changed, in which case a full check is done.

This hook is invoked by `git commit`, and [can be bypassed](https://git-scm.com/docs/githooks#_pre_commit) using the `--no-verify` option.

```sh
git commit --no-verify
```

## Installation

Create the hooks directory:

```sh
mkdir ~/.githooks
```

Download or copy the `pre-commit` script to:

```sh
~/.githooks/pre-commit
```

Ensure the file is executable:

```sh
chmod 744 ~/.githooks/pre-commit
```

Configure the Git [hooks path](https://git-scm.com/docs/git-config#Documentation/git-config.txt-corehooksPath):

```sh
git config --global core.hooksPath ~/.githooks
```

## License

Released under the [GPL-3.0-or-later License](LICENSE).
