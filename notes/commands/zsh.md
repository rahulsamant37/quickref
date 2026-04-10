# Zsh Quickref

Use with: `qref zsh`

## Core Commands

| Task | Command |
|---|---|
| Current path | `pwd` |
| List files | `ls -lah` |
| Previous directory | `cd -` |
| Make nested directory | `mkdir -p a/b/c` |
| Recursive copy | `cp -r src dst` |
| Move or rename | `mv old new` |
| Find command path | `which cmd` |
| Command type | `type cmd` |
| Search text | `rg "pattern"` |
| Reload zsh config | `source ~/.config/zsh/.zshrc` |

## Keybinds

| Key | Action |
|---|---|
| `Ctrl+R` | Reverse history search |
| `Up Arrow` | Previous history match for typed prefix |
| `Down Arrow` | Next history match for typed prefix |
| `Alt+B` | Back one word |
| `Alt+F` | Forward one word |
| `Ctrl+Left` | Back one word |
| `Ctrl+Right` | Forward one word |
| `Ctrl+W` | Delete previous word |
| `Ctrl+U` | Delete to line start |
| `Ctrl+K` | Delete to line end |
| `Ctrl+Y` | Paste deleted text |
| `Ctrl+X Ctrl+E` | Edit command in Neovim |
| `Ctrl+A` | Jump to line start |
| `Ctrl+E` | Jump to line end |

## Useful Helpers (Your Setup)

- `please` rerun previous command with `sudo`
- `hgrep <pattern>` search command history
- `mkcd <dir>` make directory and enter it
- `l`, `la`, `lsa` quick listings

## Useful Patterns

- `ls **/*.py`
- `echo *(.N)`
- `echo *(/)`
- `print -l **/*(.om[1,10])`
