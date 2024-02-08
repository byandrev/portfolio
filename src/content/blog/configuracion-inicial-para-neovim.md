---
title: "Configuración inicial para Neovim"
description: ""
pubDate: "Feb 07 2024"
heroImage: "/blog-placeholder-3.jpg"
tags: neovim,vim,dotfiles
---

Neovim es una versión moderna y renovada del editor de texto Vim.
Aunque Neovim viene con una configuración básica que funciona bien para la mayoría de los usuarios, personalizarlo puede llevar tu experiencia al siguiente nivel. 
En este artículo, exploraremos una configuración mínima que puedes implementar para mejorar tu flujo de trabajo en Neovim.


## Configuración básica

Comencemos con algunos ajustes básicos que afectarán la codificación de archivos y la sintaxis.

```lua
vim.scriptencoding = "utf-8"
vim.opt.encoding = "utf-8"
vim.opt.fileencoding = "utf-8"
vim.opt.syntax = "enable"

```

Estos ajustes garantizan que Neovim maneje correctamente los caracteres UTF-8 y habilite la sintaxis para resaltar la sintaxis del código.

## Backups

Es crucial manejar cómo Neovim maneja los respaldos de archivos para evitar la creación de archivos innecesarios. Establecer estas opciones puede ayudar:

```lua
vim.opt.backup = false
vim.opt.swapfile = false
vim.opt.writebackup = false 
```

Esto deshabilita la creación de archivos de respaldo y archivos de intercambio, lo que puede ser útil para mantener limpio tu espacio de trabajo.

## Atajos de teclado

Crear atajos de teclado puede mejorar enormemente tu eficiencia en Neovim. Aquí hay algunas asignaciones de teclas útiles:

```lua
local options = { noremap = true }

-- Establecer el líder de teclas como el espacio
vim.g.mapleader = " "

-- Cambiar entre paneles usando Ctrl + h/j/k/l
vim.api.nvim_set_keymap("n", "<C-h>", "<C-w>h", options)
vim.api.nvim_set_keymap("n", "<C-j>", "<C-w>j", options)
vim.api.nvim_set_keymap("n", "<C-k>", "<C-w>k", options)
vim.api.nvim_set_keymap("n", "<C-l>", "<C-w>l", options)

-- Dividir la ventana verticalmente con <leader>sv
vim.api.nvim_set_keymap("n", "<leader>sv", ":vsplit<CR>", options)

-- Salir de modo insertar con 'jk'
vim.api.nvim_set_keymap("i", ",,", "<ESC>", options)

-- Guardar y salir con <leader>w y <leader>q
vim.api.nvim_set_keymap("n", "<leader>w", ":w<CR>", options)
vim.api.nvim_set_keymap("n", "<leader>q", ":q<CR>", options)
vim.api.nvim_set_keymap("n", "<leader>wq", ":wq<CR>", options)
```


## Configuración de plugins

Finalmente, considera utilizar la biblioteca lazy.nvim para cargar tus plugins de forma diferida y optimizar el tiempo de inicio de Neovim. Aquí está cómo configurarlo:


```lua
local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"

if not vim.loop.fs_stat(lazypath) then
  vim.fn.system({
    "git",
    "clone",
    "--filter=blob:none",
    "https://github.com/folke/lazy.nvim.git",
    "--branch=stable",
    lazypath,
  })
end

vim.opt.rtp:prepend(lazypath)

require("lazy").setup({
	spec = {
		{ import = "plugins" },
	},
	
	debug = false
})
```

Con lazy.nvim, tus plugins se cargarán solo cuando los necesites, lo que puede acelerar significativamente el tiempo de inicio de Neovim.

Puedes visitar el siguiente repositorio donde esta la configuración [https://github.com/byandrev/minimal-neovim-config](https://github.com/byandrev/minimal-neovim-config).


## Conclusiones

Personalizar Neovim puede llevar tiempo y experimentación, pero con una configuración mínima como esta, puedes mejorar rápidamente tu flujo de trabajo y productividad.
