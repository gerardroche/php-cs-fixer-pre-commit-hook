# PHP Coding Standards Fixer Pre Commit Hook

## Installation

Create a Git hooks directory:

    mkdir ~/.githooks

Download the `pre-commit` hook to:

    ~/.githooks/pre-commit

Make sure the file is executable:

    chmod 744 ~/.githooks/pre-commit

Configure Git to use the hooks:

    git config --global core.hooksPath ~/.githooks
