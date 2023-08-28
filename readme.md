<p align="center">
    <h2 align="center">Opulo for Neovim</h2>
</p>

<p align="center">Colors to protect your sanity while debugging</p>

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

## Palette

- Base: #1D212B
- Surface: #232A34
- Overlay: #29333E
- Text: #9ab8d7
- Subtle: #92d5e6
- Muted: #DCDCCC

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

We welcome and appreciate any help in creating a lovely experience for all.

- Get highlight groups under cursor via `:Inspect` in Neovim 0.9 or
  [nvim-treesitter/playground](https://github.com/nvim-treesitter/playground#show-treesitter-and-syntax-highlight-groups-under-the-cursor)
- [Palette reference by name](https://github.com/notjek1/opulo)
