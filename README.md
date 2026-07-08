# nvim-config

Personal Neovim configuration using [lazy.nvim](https://github.com/folke/lazy.nvim).

## Features

- **Plugin manager**: lazy.nvim (auto-bootstrapped)
- **Theme**: Tokyo Night (night style)
- **Syntax highlighting**: nvim-treesitter v1.x with Neovim built-in highlight engine
- **Parsers**: lua, pascal, c, python, bash (more installable via `:TSInstall <lang>`)

## Requirements

### macOS

```sh
brew install neovim git tree-sitter-cli
```

### Linux (Debian/Ubuntu)

```sh
sudo apt update && sudo apt install -y neovim git
# tree-sitter-cli via cargo (apt package may be outdated)
cargo install tree-sitter-cli
```

### Linux (Arch)

```sh
sudo pacman -S neovim git tree-sitter
```

> **Note:** Neovim >= 0.9 is required for the built-in treesitter highlight engine.

## Install

```sh
git clone git@github.com:ahmed-masud/nvim-config.git ~/.config/nvim
```

Then open Neovim — lazy.nvim will auto-install all plugins on first launch.

To install treesitter parsers after first launch:

```
:TSInstall lua pascal c python bash
```

## Updating

```sh
cd ~/.config/nvim && git pull
```

Then inside Neovim: `:Lazy sync`
