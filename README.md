# quickref

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Shell: Bash](https://img.shields.io/badge/shell-bash-121011.svg?logo=gnu-bash)](https://www.gnu.org/software/bash/)
[![Editor: Neovim](https://img.shields.io/badge/editor-neovim-57A143.svg?logo=neovim&logoColor=white)](https://neovim.io/)
[![Search: ripgrep](https://img.shields.io/badge/search-ripgrep-CF242E.svg?logo=ripgrep&logoColor=white)](https://github.com/BurntSushi/ripgrep)
[![Fuzzy Finder: fzf](https://img.shields.io/badge/fuzzy%20finder-fzf-0E8A16.svg)](https://github.com/junegunn/fzf)
[![Notes: Markdown](https://img.shields.io/badge/notes-markdown-000000.svg?logo=markdown)](https://www.markdownguide.org/)

A terminal-first knowledge base for developers who want fast note capture and retrieval with plain Markdown files.

## Overview

quickref is a lightweight Bash toolkit that turns a folder of Markdown notes into a fast, searchable reference system. It is designed for people who already live in the terminal and want information in seconds.

Instead of introducing a new app, database, or sync format, quickref works directly with files you own. Your notes stay portable, readable, and easy to version with Git.

The workflow is intentionally simple: use `qnewref` to create structured dated notes, then use `qref` to find and open what you need quickly. If you prefer shorter commands, `ref` is a thin wrapper around `qref`.

This makes quickref a good fit for engineering notes, incident runbooks, setup snippets, and recurring debugging commands where speed and low friction matter.

## Table of Contents

- [Overview](#overview)
- [Why quickref](#why-quickref)
- [Features](#features)
- [Philosophy](#philosophy)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Neovim Integration (Optional)](#neovim-integration-optional)
- [Performance](#performance)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Why quickref

- Fast retrieval from terminal with one command.
- Low cognitive load: plain files, simple scripts, predictable behavior.
- No database layer, no migration concerns, no vendor lock-in.
- Git-friendly workflow for history, diffs, and backups.
- Easy to script and automate in your existing shell environment.

## Features

- Interactive note picker with preview.
- Full-text search via ripgrep and jump to first matching line.
- Date-based note creation with clean slugs.
- Optional non-interactive mode for scripts and automation.
- Configurable note root and UI behavior through environment variables.
- Neovim-first editing with terminal-native flow.

## Philosophy

- Keep notes as files, not records in a hidden store.
- Prefer speed and clarity over feature bloat.
- Make the default path useful, then allow opt-in customization.

## Project Structure

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

- `bash` (all scripts use Bash)
- `nvim` required by `qref`; used by `qnewref` when opening notes interactively
- `rg` (ripgrep) required for `qref <query>` mode
- `fzf` recommended for interactive selection
- `fd` optional for faster file discovery in picker mode

## Installation

1. Clone and enter the repository:

```sh
git clone <your-repo-url> "$HOME/github/quickref"
cd "$HOME/github/quickref"
```

2. Ensure scripts are executable:

```sh
chmod +x bin/qref bin/qnewref bin/ref
```

3. Configure your shell environment.

Zsh:

```sh
cat <<'EOF' >> ~/.zshrc
export QUICKREF_DIR="$HOME/github/quickref"
export PATH="$QUICKREF_DIR/bin:$PATH"

alias ref='qref'
alias qn='qnewref'
EOF

source ~/.zshrc
```

Bash:

```sh
cat <<'EOF' >> ~/.bashrc
export QUICKREF_DIR="$HOME/github/quickref"
export PATH="$QUICKREF_DIR/bin:$PATH"

alias ref='qref'
alias qn='qnewref'
EOF

source ~/.bashrc
```

4. Verify:

```sh
qref --help
qnewref "quickref setup test"
```

## Usage

| Command | Behavior |
|---|---|
| `qref` | Interactive note picker from `notes/` (excludes `notes/index.md`) |
| `qref <text>` | Search in `notes/`, let you choose a matching markdown file with preview, then open it |
| `qref stl` | Open `notes/commands/cpp-stl/index.md` |
| `qref stl-list` | Print supported STL quick-access topics |
| `qref vector` | Jump to the `vector` section in STL quick reference |
| `qref --help` | Open `notes/index.md` |
| `qnewref "title"` | Create/open `notes/YYYY/MM/YYYY-MM-DD-title.md` |
| `ref` | Pass-through wrapper to `qref` |

Real-world examples:

```sh
# Find Docker networking notes and open at first hit
qref docker network

# Create a dated incident note
qnewref "postgres timeout incident"

# Script-friendly search output (do not open Neovim)
QUICKREF_NO_OPEN=1 qref ssh tunnel
```

## Configuration

| Variable | Default | Purpose |
|---|---|---|
| `QUICKREF_DIR` | `$HOME/github/quickref` | Root directory for quickref |
| `QUICKREF_NOTES_DIR` | `$QUICKREF_DIR/notes` | Notes directory used by `qref` |
| `QUICKREF_NO_FZF` | `0` | Disable fzf and auto-pick first file/match |
| `QUICKREF_NO_PREVIEW` | `0` | Disable split preview in fzf |
| `QUICKREF_NO_OPEN` | `0` | Print path (or path:line) instead of opening Neovim |

Examples:

```sh
export QUICKREF_DIR="$HOME/github/quickref"
export QUICKREF_NOTES_DIR="$HOME/github/quickref/notes"

QUICKREF_NO_FZF=1 qref dijkstra
QUICKREF_NO_PREVIEW=1 qref "kernel panic"
QUICKREF_NO_OPEN=1 qnewref "release checklist"
```

Note: `qnewref` currently writes new notes under `$QUICKREF_DIR/notes`.

## Neovim Integration (Optional)

If your Neovim config exposes quickref commands, typical usage is:

- `:QuickrefFiles` to browse notes
- `:QuickrefGrep` to search notes
- `:QuickrefOpen` to open the project README
- `:QuickrefNew [title]` to create a new dated note

Typical keymaps:

- `<leader>sq` browse notes
- `<leader>sQ` grep notes
- `<leader>qo` open quickref README
- `<leader>qn` create note

## Performance

| Task | quickref | Traditional Notes |
|---|---|---|
| Open note | Instant | Slower |
| Search | ripgrep (fast) | Often slower |
| Setup | Minimal | Heavier |

Optional chart snippet:

```md
![Performance](assets/metrics.png)
```

> quickref focuses on speed and minimal overhead for everyday workflows.

## Troubleshooting

| Error | Cause | Fix |
|---|---|---|
| `quickref directory not found: ...` | `QUICKREF_DIR` is wrong or the repository is missing | Set `QUICKREF_DIR` to the correct path |
| `quickref notes directory not found: ...` | `QUICKREF_NOTES_DIR` points to a missing directory | Create the directory or fix `QUICKREF_NOTES_DIR` |
| `nvim is required but not found in PATH` | Neovim is not installed or unavailable in PATH | Install Neovim and confirm `nvim` resolves |
| `ripgrep (rg) is required for search mode.` | `rg` is not installed | Install ripgrep |
| `No matches for: ...` | Query did not match any notes | Broaden your query or create a new note |
| `No note files found under: ...` | Notes directory is empty | Add notes or verify your notes path |

## Contributing

Contributions are welcome and appreciated.

- Keep changes simple, portable, and easy to review.
- Preserve CLI behavior unless you clearly document changes.
- Prefer small, focused pull requests.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
