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

## Motion Tips

Use `f<char>` when you want to land exactly on the character
Use `t<char>` when you want to position just before the character

## Your Run and Compile Commands

| Task | Command |
|---|---|
| Compile and run current C/C++/Java/Rust file | `:R` |
| Compile/check current C/C++/Java/Rust file | `:RCompile` |
| C/C++ compile and run (CP workflow) | `:CPRun` |
| C/C++ compile only (CP workflow) | `:CPCompile` |
| C/C++ interactive run (CP workflow) | `:CPRunInteractive` |

Notes:

- `:R` on Rust uses `cargo run --bin <target>` if inside a Cargo project (auto-detected from current file when possible), otherwise `rustc` for single-file Rust.
- If a Cargo workspace has multiple binaries and target inference is ambiguous, Neovim prompts you to select a binary.
- `:RCompile` on Rust uses `cargo check` in Cargo projects, otherwise a `rustc` compile check.

## CP Keybinds You Already Have (C/C++ Buffers)

| Key | Action |
|---|---|
| `<F5>` / `<leader>cr` | Compile and run |
| `<F9>` / `<leader>cc` | Compile only |
| `<F6>` / `<leader>ci` | Run with custom input |
| `<F7>` / `<leader>r` | Interactive run |
| `<leader>t` / `<leader>ct` | Create/open test files |
| `<leader>cd` | Compare output with expected |
| `<leader>x` | Delete generated CP artifacts |

## Rust Keybinds (Rust Buffers)

| Key | Action |
|---|---|
| `<F5>` / `<leader>cr` | Compile and run (`:R`) |
| `<F9>` / `<leader>cc` | Compile/check (`:RCompile`) |

## How To Discover Commands and Keybinds Fast

| What you want | Command |
|---|---|
| List all user commands | `:command` |
| Check one command definition | `:command R` |
| See where a command was last set | `:verbose command R` |
| Search commands interactively | `:Telescope commands` |
| Search keymaps interactively | `:Telescope keymaps` |
| Show all normal-mode maps | `:nmap` |
| Inspect one mapping | `:nmap <leader>r` |
| See mapping source file/line | `:verbose nmap <leader>r` |

Also useful in your setup:

- `:help :command`
- `:help map-listing`
- `:help :verbose`