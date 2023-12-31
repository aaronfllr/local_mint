# Base Packages

Your Mint comes with [zsh](https://www.zsh.org/ "Welcome to Zsh") as a default shell, so we'll just configure it through plugins with [Oh My Zsh!](https://ohmyz.sh/ "Unleash your terminal like never before."). However, it also comes with minimalist Vim, which we will 'improve on.'

## The First Thing is First

Familiarize yourself with your shell - it'll be your best friend. The [Introductory Document](https://zsh.sourceforge.io/Intro/intro_toc.html "An Introduction to the Z Shell") contains the [**Startup Files**](https://zsh.sourceforge.io/Intro/intro_3.html#SEC3 "Z Shell Startup Files") section (3). We won't need to change any global `/etc/zsh/` configuration files, but we need to understand the conventions and purpose of the local user configs.

- `~/.zshenv` - sourced first, inanimate _(so no function calls)_, our environment variables like `GITHUB_TOKEN` go here.
- `~/.zprofile` - animate, sourced second before `.zshrc`, only common things like IDE, or JetBrains Toolbox `bin`s go here.
- `~/.zshrc` - sourced last, animate, is **THE** place for many our customizations.
- `~/.zlogin` - **ignore for now**, sourced first for login shell, should NEVER change the shell.
- `~/.zlogout` - **ignore for now**, cleanup for login shell.

## The Second Thing is Second: Understand your Package Manager!

All global configurations are in `/etc/`. Our main package manager interface is `apt`.  Instead of using a single village-style manifest file `/etc/apt/sources.list` use the daemon folder `/etc/apt/sources.list.d` and segregate sources groups into separate files, as it is now, out of the box (OOTB). 

_Add sources with `apt add-repository` instead or manually by a script we first examine well._

Examine the single file `/etc/apt/sources.list.d/official-package-repositories.list`, it should look something like this:


```
# Do not edit this file manually, use Software Sources instead.

deb http://packages.linuxmint.com victoria main upstream import backport #id:linuxmint_main

deb http://archive.ubuntu.com/ubuntu jammy main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu jammy-updates main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu jammy-backports main restricted universe multiverse

deb http://security.ubuntu.com/ubuntu/ jammy-security main restricted universe multiverse
```

### Update Sources and Upgrade Box

NOTE: How to become `root`:
```shell
sudo su -                   # become root; get out with exit
### Do lots of stuff here
exit
```

**IMPORTANT**: _It's best to just use `sudo` for occasional changes when necessary. For extensive changes becoming is fine with adequate planning and vigilance._

```shell
sudo su -                   # become root; get out with exit
apt update && apt full-upgrade -y && apt autoremove && apt autoclean
exit
```

### Install full Vim

```shell
sudo apt install vim
```

### Optionally Install Build Essentials for Kernel and driver patching

```shell
sudo su -
apt install build-essential module-assistant
m-a prepare
reboot
```