# quickref

A lightweight, git-friendly knowledge base for terminal and Neovim workflows.

quickref is designed for fast retrieval and low maintenance:
- Search-first from terminal
- Markdown notes with clean structure
- Fast note creation with date-based paths
- Optional Neovim integration for an editor-native workflow

## Features

- `qref` interactive picker for quickref files
- `qref <query>` content search and jump-to-line in Neovim
- `qref --help` opens the notes index
- `qnewref "title"` creates a dated note using a template
- `ref` and `qn` aliases (if configured in your shell)

## Repository Layout

```text
quickref/
├── bin/
│   ├── qref
│   ├── qnewref
│   └── ref
├── notes/
│   ├── index.md
│   └── ...
└── templates/
    └── note.md
```

## Requirements

- Neovim (`nvim`) required by `qref` and `qnewref`
- ripgrep (`rg`) required for search mode (`qref <query>`)
- fzf recommended for interactive selection (picker and search select)
- fd optional for faster file discovery in picker mode

## Quick Start

1. Ensure quickref bin directory is in PATH.
2. Run `qref` to open the picker.
3. Run `qnewref "some title"` to create and open a new dated note.

Optional shell aliases:

```sh
alias ref='qref'
alias qn='qnewref'
```

## CLI Usage

| Command | Behavior |
|---|---|
| `qref` | Interactive file picker (excludes `notes/index.md`) |
| `qref <text>` | Search notes and open selected match at exact line (excludes `notes/index.md`) |
| `qref --help` | Open `notes/index.md` |
| `qnewref "title"` | Create/open `notes/YYYY/MM/YYYY-MM-DD-title.md` |

### Examples

```sh
qref
qref docker
qref --help
qnewref "ssh troubleshooting"
```

## Neovim Integration

If your Neovim setup includes quickref mappings/commands, common actions are:

- `:QuickrefFiles` open quickref file search
- `:QuickrefGrep` grep within quickref notes
- `:QuickrefOpen` open this README
- `:QuickrefNew [title]` create/open a new dated note

Typical keymaps:

- `<leader>sq` quickref files
- `<leader>sQ` quickref grep
- `<leader>qo` open quickref README
- `<leader>qn` new quickref note

## Configuration

- Default root: `~/github/quickref`
- Override root: set `QUICKREF_DIR`

```sh
export QUICKREF_DIR="$HOME/github/quickref"
```

## Behavior Notes

- `notes/index.md` is intentionally excluded from normal picker and search results.
- Use `qref --help` when you want the index explicitly.

## Troubleshooting

- `nvim is required but not found in PATH`
  Install Neovim or ensure it is in PATH.
- `ripgrep (rg) is required for search mode`
  Install ripgrep.
- `fzf is required for interactive picker mode`
  Install fzf or use `qref <query>` mode.