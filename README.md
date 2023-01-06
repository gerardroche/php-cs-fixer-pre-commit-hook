# PHP Coding Standards Fixer pre-commit hook

A script to run [PHP Coding Standards Fixer](https://github.com/PHP-CS-Fixer/PHP-CS-Fixer) before committing code.

The fixer is run **quietly** to avoid unnecessary noise when committing code. If there are violations it is run again in verbose mode to provide more information about the violations in the commit.

A full check is executed if the configuration or the Composer lock file has changed, otherwise only changed files since the last commit are checked.

This hook is invoked by git-commit, and [can be bypassed](https://git-scm.com/docs/githooks#_pre_commit) with the --no-verify option.

```
git commit --no-verify
```

## Installation

Create a Git hooks directory:

    mkdir ~/.githooks

Download the `pre-commit` hook to:

    ~/.githooks/pre-commit

Make sure the file is executable:

    chmod 744 ~/.githooks/pre-commit

Configure the Git [hooks path](https://git-scm.com/docs/git-config#Documentation/git-config.txt-corehooksPath):

    git config --global core.hooksPath ~/.githooks

Done!
