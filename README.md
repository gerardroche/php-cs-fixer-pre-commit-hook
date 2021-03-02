# Git Hooks

## Installation

This will install the hooks globally and will be used by all repositories.


Clone the repository to `~/.githooks`:

    git clone https://github.com/gerardroche/githooks.git ~/.githooks

Configure Git:

    git config --global core.hooksPath ~/.githooks

Done.

## Configuration

For verbose messages when hooks are run set a system environment variable e.g. set it in your `~/.bashrc` file:

    PRE_COMMIT_PHP_CS_FIXER_VERBOSE=1

Or for less verbosity:

    PRE_COMMIT_PHP_CS_FIXER_VERBOSE=0
