# PHP Coding Standards Fixer pre commit hook

A script to run [PHP Coding Standards Fixer](https://github.com/FriendsOfPhp/PHP-CS-Fixer) before committing code.

PHP Coding Standards Fixer is run quietly to avoid unnecessary noise when
committing code. If there are standards violations it is run again in verbose
mode to provide more information about the violations and stop the commit.

You can bypass the `pre-commit` with `git commit --no-verify`.

A full check is done if the PHP Coding Standards configuration or the Composer
dependencies lock file has changed, otherwise only changed files since the last
commit are checked.

## Installation

Create a Git hooks directory:

    mkdir ~/.githooks

Download the `pre-commit` hook to:

    ~/.githooks/pre-commit

Make sure the file is executable:

    chmod 744 ~/.githooks/pre-commit

Configure Git to use the hooks:

    git config --global core.hooksPath ~/.githooks
