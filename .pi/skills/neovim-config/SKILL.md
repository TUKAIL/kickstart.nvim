---
name: neovim-config
description: Guidance for working in this Neovim configuration. Use when reading or modifying files under this project, especially plugin setup in init.lua.
---

# Neovim Config

This project is a personal Neovim configuration rooted at `/root/.config/nvim`.

## Key Rule

Do not assume `lazy.nvim` or any external plugin manager.

This config uses Neovim's built-in plugin manager: `vim.pack`.

When working on plugin-related tasks:
1. Read `init.lua` first.
2. Follow the existing `vim.pack.add(...)` and `require(...).setup(...)` patterns already present in the file.
3. Prefer matching the local style instead of introducing a new plugin layout.
4. Before mentioning plugin-manager choices to the user, verify whether the request actually requires that detail.

## Project Notes

- Main config entrypoint: `init.lua`
- Optional custom plugin modules live under `lua/custom/plugins/`
- This repository started from Kickstart, but plugin installation and configuration should be treated according to the current local code, not generic Kickstart assumptions.

## Working Style

For Neovim/plugin edits in this project:
- keep changes small and local
- inspect nearby code before editing
- preserve existing keymap and setup style
- avoid redundant explanation about plugin managers unless the user asks
