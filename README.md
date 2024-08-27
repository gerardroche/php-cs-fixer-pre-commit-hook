# PHP-CS-Fixer Pre-Commit Hook

Run [PHP-CS-Fixer](https://github.com/PHP-CS-Fixer/PHP-CS-Fixer) before committing code in a Git pre-commit hook.

The fixer runs quietly without making changes to your files, but will stop and print analysis upon first file that needs to be fixed. Only changed files since the last commit are checked, unless configuration files have changed, in which case the fixer runs a full check.

The hook is invoked by `git commit`, and can be bypassed [using the `--no-verify`](https://git-scm.com/docs/githooks#_pre_commit) option:

```sh
git commit --no-verify
```

## Environment variables

- `PHP_CS_FIXER_IGNORE_ENV=1`
- `XDEBUG_MODE=off`

## Installation

Run the installer.

```sh
./install
```

You'll thank me later ;)

### Manual installation

Create the hooks directory and set the [Git hooks path](https://git-scm.com/docs/git-config#Documentation/git-config.txt-corehooksPath).

```sh
mkdir ~/.githooks && git config --global core.hooksPath ~/.githooks
```

Download, copy, or symlink the `pre-commit` script to `~/.githooks/pre-commit-php` and ensure the file is executable. The installer symlinks the script into the githooks folder.

```sh
chmod 744 ~/.githooks/pre-commit-php
```

Create a pre-commit script that calls the php-cs-fixer pre-commit and any local pre-commit script if it exits.

```sh
#!/bin/sh

if [ -f ~/.githooks/pre-commit-php ]; then
    exec ~/.githooks/pre-commit-php
fi

if [ -f .git/hooks/pre-commit ]; then
    exec .git/hooks/pre-commit
fi
```

## License

Released under the [GPL-3.0-or-later License](LICENSE).
