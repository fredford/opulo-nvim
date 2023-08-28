<p align="center">
    <h2 align="center">Opulo for Neovim</h2>
</p>

<p align="center">Colors to protect your sanity while debugging</p>

## Description

This was a fork of the [Rose-Pine neovim theme](https://github.com/rose-pine/neovim), using the colors from the [Opulo theme](https://github.com/notjek1/opulo) to help blend into a more vibrant mix of the two.

## Install

**[Paq](https://github.com/savq/paq-nvim)**

```lua
require('paq')({
  { 'fredford/opulo-nvim', as = 'opulo' }
})
```

**[lazy.nvim](https://github.com/folke/lazy.nvim)**

```lua
require("lazy").setup({
  { 'fredford/opulo-nvim', as = 'opulo'  }
})
```

**[packer.nvim](https://github.com/wbthomason/packer.nvim)**

```lua
require('packer').startup(function(use)
  use({ 'fredford/opulo-nvim', as = 'opulo' })
end)
```

Set the colorscheme:

```lua
vim.cmd.colorscheme("opulo")

```

## Palette

If you want to modify the colors, you can do so in `lua/opulo/palette.lua`, the naming is from Rose-Pine and not the actual colors.

- Base: #1D212B
- Surface: #232A34
- Overlay: #29333E
- Text: #9AB8D7
- Subtle: #92D5E6
- Muted: #DCDCCC
- Love: #FF97B1
- Gold: #DCA3A3
- Rose: #DCDCCC
- Pine: #FF758E
- Foam: #60B48A
- Iris: #BD91FF
- Highlight_Low: #232A34
- Highlight_Mid: #2F3C47
- Highlight_High: #405763

## Options

> Options should be set **before** colorscheme

Variant respects `vim.o.background`, using dawn when light and `dark_variant`
when dark

```lua
require('rose-pine').setup({
	--- @usage 'auto'|'main'|'moon'|'dawn'
	variant = 'auto',
	--- @usage 'main'|'moon'|'dawn'
	dark_variant = 'main',
	bold_vert_split = false,
	dim_nc_background = false,
	disable_background = false,
	disable_float_background = false,
	disable_italics = false,

	--- @usage string hex value or named color from rosepinetheme.com/palette
	groups = {
		background = 'base',
		background_nc = '_experimental_nc',
		panel = 'surface',
		panel_nc = 'base',
		border = 'highlight_med',
		comment = 'muted',
		link = 'iris',
		punctuation = 'subtle',

		error = 'love',
		hint = 'iris',
		info = 'foam',
		warn = 'gold',

		headings = {
			h1 = 'iris',
			h2 = 'foam',
			h3 = 'rose',
			h4 = 'gold',
			h5 = 'pine',
			h6 = 'foam',
		}
		-- or set all headings at once
		-- headings = 'subtle'
	},

	-- Change specific vim highlight groups
	-- https://github.com/rose-pine/neovim/wiki/Recipes
	highlight_groups = {
		ColorColumn = { bg = 'rose' },

		-- Blend colours against the "base" background
		CursorLine = { bg = 'foam', blend = 10 },
		StatusLine = { fg = 'love', bg = 'love', blend = 10 },

		-- By default each group adds to the existing config.
		-- If you only want to set what is written in this config exactly,
		-- you can set the inherit option:
		Search = { bg = 'gold', inherit = false },
	}
})

-- Set colorscheme after options
vim.cmd('colorscheme opulo')
```

## Contributing

We welcome and appreciate any help in creating a lovely experience for all. If you want to change it or improve the theme feel free to make changes and submit a PR.

- Get highlight groups under cursor via `:Inspect` in Neovim 0.9 or
  [nvim-treesitter/playground](https://github.com/nvim-treesitter/playground#show-treesitter-and-syntax-highlight-groups-under-the-cursor)
- [Palette reference by name](https://github.com/notjek1/opulo)
