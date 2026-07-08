# nvim-config

Personal Neovim configuration using [lazy.nvim](https://github.com/folke/lazy.nvim).
Works on **macOS** and **Linux**.

## Features

- **Plugin manager**: [lazy.nvim](https://github.com/folke/lazy.nvim) — auto-bootstrapped, no manual install needed
- **Theme**: [Tokyo Night](https://github.com/folke/tokyonight.nvim) (`night` style)
- **Syntax highlighting**: [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter) v1.x via Neovim's built-in highlight engine
- **Pre-installed parsers**: `lua`, `pascal`, `c`, `python`, `bash`
- **Treesitter indentation** enabled for all supported filetypes

## Requirements

| Dependency | Min version | Purpose |
|---|---|---|
| [Neovim](https://neovim.io) | 0.9+ | Editor |
| [git](https://git-scm.com) | any | Plugin installation |
| [tree-sitter-cli](https://github.com/tree-sitter/tree-sitter) | any | Compile parsers from source |
| A [Nerd Font](https://www.nerdfonts.com) *(optional)* | any | Icons in the UI |

### macOS

```sh
brew install neovim git tree-sitter-cli
```

### Linux (Debian/Ubuntu)

```sh
sudo apt update && sudo apt install -y neovim git
# tree-sitter-cli via cargo (apt version is often outdated)
cargo install tree-sitter-cli
```

### Linux (Arch)

```sh
sudo pacman -S neovim git tree-sitter
```

## Installation

> If you have an existing config, back it up first:
> ```sh
> mv ~/.config/nvim ~/.config/nvim.bak
> ```

Clone the repo:

```sh
git clone git@github.com:ahmed-masud/nvim-config.git ~/.config/nvim
```

Open Neovim — lazy.nvim will automatically bootstrap itself and install all plugins:

```sh
nvim
```

Once inside, install the treesitter parsers:

```
:TSInstall lua pascal c python bash
```

## Usage

### Plugin management

| Command | Action |
|---|---|
| `:Lazy` | Open plugin manager UI |
| `:Lazy sync` | Update all plugins |
| `:Lazy install` | Install missing plugins |
| `:Lazy clean` | Remove unused plugins |

### Treesitter parsers

| Command | Action |
|---|---|
| `:TSInstall {lang}` | Install a parser (e.g. `:TSInstall go`) |
| `:TSUpdate` | Update all installed parsers |
| `:TSUninstall {lang}` | Remove a parser |
| `:checkhealth nvim-treesitter` | Verify parser status |

### Theme variants

The Tokyo Night theme has four styles. To switch, edit `init.lua` and change `style`:

```lua
require("tokyonight").setup({
  style = "night",   -- night | storm | moon | day
})
```

## Customisation

All configuration lives in `~/.config/nvim/init.lua`. After editing, reload with `:source %`
or simply restart Neovim.

## Updating

Pull the latest config and sync plugins:

```sh
cd ~/.config/nvim && git pull
```

Then inside Neovim:

```
:Lazy sync
:TSUpdate
```

## License

This project is licensed under the **MIT License**.

Copyright (c) 2026 ahmed-masud

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

See [LICENSE](LICENSE) for the full license file.
