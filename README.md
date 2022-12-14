# terminal-setup

A project for storing dot files and terminal configuration.

## Add Custom Aliases

Within the `.aliases` file are a bunch of customisable aliases which are sourced on prompt start up.

You should then source these aliases from your `~/.zshrc` file like so:

`source ~/.aliases`

## Install Oh my ZSH

Run the below to install ZSH:

`sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

## Install Zsh Plugins

Run the below to download the syntax highlighting plugin:

`git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`

Run the below to download the auto-suggestions plugin:

`git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`

Then enable the plugins like so in the `~/.zshrc`:

```txt
plugins=(
        git
        zsh-syntax-highlighting
        zsh-autosuggestions
)
```

## Install Bash Completion

In order to get bash completion when hitting `=> Tab`, you can add the following to the end of your `~/.zshrc`

```bash
autoload bashcompinit && bashcompinit
autoload -Uz compinit && compinit
complete -C '/usr/local/bin/aws_completer' aws
```

## Install Brew

Run the following to install homebrew:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

The add the following line to your `~/.zshrc`

eval "$(/opt/homebrew/bin/brew shellenv)"

## Install Starship

Run the below to install starship:

`brew install starship`

Copy the `startship.toml` to `~/.config/starship.toml`

Once installed add the following to your `~/.zshrc`:

`eval "$(starship init zsh)"`
