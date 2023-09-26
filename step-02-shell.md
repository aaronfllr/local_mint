# Shell: The primary IDE

NOTE: This is to be done to the 'base' user and every user specialized to a domain / customer.

## Install [Oh My Zsh](https://ohmyz.sh/ "Unleash your terminal like never before.") plugin management system

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

NOTE: zsh will intercept your `sh` call correctly

_We may need to log out._

## Configure plugins: `~/.zshrc`

This is the list of available plugins: https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins

By default, one gets enough to get started: `plugins=(git)`

## Suggested configuration: `~/.zshrc`

```shell
zstyle ':omz:update' mode auto      # update automatically without asking
zstyle ':omz:update' frequency 1    # Git pull every 1 day
COMPLETION_WAITING_DOTS="true"      # show dots while waiting for completion

export LANG=en_US.UTF-8             # forces default local lang
export ARCHFLAGS="-arch x86_64"     # force your default arch flag - CHECK YOURS

# Aliases - my example
alias zconf="vim ~/.zshrc"
alias zpl="ll ~/.oh-my-zsh/plugins"
# ... add your most frequently used shortcuts here ....
```