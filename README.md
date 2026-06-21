# Midnight Blue

A cool, deep-navy theme. Soft cool-white text on a dark navy background (`#1A1F2B`),
with a saturated palette that keeps blue and cyan distinct. Designed to be shared
between a terminal (Ghostty) and Neovim from a **single source of truth**.

![bg #1A1F2B · fg #E6EAF2](https://img.shields.io/badge/bg-%231A1F2B-1A1F2B)
![fg #E6EAF2](https://img.shields.io/badge/fg-%23E6EAF2-E6EAF2)

## Ghostty

Copy the theme file into Ghostty's themes directory and reference it by name:

```sh
mkdir -p ~/.config/ghostty/themes
cp themes/midnight-blue ~/.config/ghostty/themes/midnight-blue
```

Then in `~/.config/ghostty/config`:

```
theme = midnight-blue
```

Reload Ghostty (`Cmd+Shift+,`) or restart it.

## Neovim

Two ways to use it — pick one.

### A. Truecolor colorscheme (recommended)

Install this repo as a plugin and load the colorscheme. You get the full palette in
truecolor, so Treesitter/LSP highlighting stays rich.

`lazy.nvim`:

```lua
{ 'AshminJayson/midnight-blue-theme', lazy = false, priority = 1000,
  config = function() vim.cmd.colorscheme 'midnight-blue' end }
```

`vim.pack` (Neovim 0.12+):

```lua
vim.pack.add { 'https://github.com/AshminJayson/midnight-blue-theme' }
vim.cmd.colorscheme 'midnight-blue'
```

For a transparent background (inherit the terminal's), set this before loading:

```lua
vim.g.midnight_blue_transparent = true
```

### B. Palette sync, no plugin

Since the theme is also defined by the terminal's 16-color palette, you can let Neovim
render straight from Ghostty instead of loading a colorscheme:

```lua
vim.opt.termguicolors = false
```

Neovim then inherits Midnight Blue's colors directly from Ghostty — one source of truth.
Tradeoff: 16-color syntax instead of truecolor (Treesitter detail flattens).

## Palette

| Role | Normal | Bright |
|------|--------|--------|
| black   | `#39414F` | `#5A6478` |
| red     | `#FF6B6B` | `#FF8B8B` |
| green   | `#8CE0A0` | `#A6E8B4` |
| yellow  | `#FFD479` | `#FFE3A3` |
| blue    | `#6FA8FF` | `#9CC4FF` |
| magenta | `#C792EA` | `#DDB0F6` |
| cyan    | `#56C9D6` | `#8BE9F0` |
| white   | `#D8DEE9` | `#FFFFFF` |

Background `#1A1F2B` · Foreground `#E6EAF2` · Cursor `#8FB6E8` · Selection `#33508A`
