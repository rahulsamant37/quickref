# Neovim Quickref

Use with: `qref neovim`

## Core Commands

| Task | Command |
|---|---|
| Open file | `:e path/to/file` |
| Save | `:w` |
| Save and quit | `:wq` |
| Quit | `:q` |
| Force quit | `:q!` |
| List buffers | `:buffers` |
| Split horizontal | `:split` |
| Split vertical | `:vsplit` |
| Replace all | `:%s/old/new/g` |
| Replace with confirm | `:%s/old/new/gc` |

## Most Used Keys

| Key | Action |
|---|---|
| `h j k l` | Move cursor |
| `w b e` | Word motions |
| `0 ^ $` | Start and end of line |
| `gg G` | Top and bottom of file |
| `i a o` | Insert modes |
| `dd yy p` | Cut, copy, paste |
| `u` | Undo |
| `Ctrl+R` | Redo |
| `/text` `n` `N` | Search and navigate results |

## Buffer Keybinds (Your Setup)

| Key | Action |
|---|---|
| `<leader>be` | New empty buffer |
| `<leader>bl` | List buffers |
| `<leader>bn` | Next buffer |
| `<leader>bp` | Previous buffer |
| `<leader>bb` | Last buffer |
| `<leader>bd` | Delete current buffer |
| `<S-l>` / `]b` | Next buffer |
| `<S-h>` / `[b` | Previous buffer |

## Window Movement

- `Ctrl+W W`
- `Ctrl+W H`
- `Ctrl+W J`
- `Ctrl+W K`
- `Ctrl+W L`

## Macro Basics

1. `qa`
2. do edits
3. `q`
4. `@a`
5. `10@a`
