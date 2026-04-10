# quickref

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Shell: Bash](https://img.shields.io/badge/shell-bash-121011.svg?logo=gnu-bash)](https://www.gnu.org/software/bash/)
[![Editor: Neovim](https://img.shields.io/badge/editor-neovim-57A143.svg?logo=neovim&logoColor=white)](https://neovim.io/)
[![Search: ripgrep](https://img.shields.io/badge/search-ripgrep-CF242E.svg?logo=ripgrep&logoColor=white)](https://github.com/BurntSushi/ripgrep)
[![Fuzzy Finder: fzf](https://img.shields.io/badge/fuzzy%20finder-fzf-0E8A16.svg)](https://github.com/junegunn/fzf)
[![Notes: Markdown](https://img.shields.io/badge/notes-markdown-000000.svg?logo=markdown)](https://www.markdownguide.org/)

A lightweight, git-friendly knowledge base for terminal and Neovim workflows.

quickref is optimized for one workflow: capture knowledge quickly, then retrieve it in seconds without leaving your terminal.

## Table of Contents

- [Why quickref](#why-quickref)
- [Features](#features)
- [Repository Layout](#repository-layout)
- [Requirements](#requirements)
- [Local Setup](#local-setup)
- [Usage](#usage)
- [Configuration](#configuration)
- [Neovim Integration (Optional)](#neovim-integration-optional)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Why quickref

- Search-first access from terminal.
- Markdown notes that stay clean in Git history.
- Predictable, date-based file paths for long-term organization.
- Minimal dependencies and zero database lock-in.

## Features

- `qref` interactive picker for quick browsing.
- `qref <query>` full-text search and jump to exact line in Neovim.
- `qref --help` opens `notes/index.md` as your navigation hub.
- `qnewref "title"` creates/open a dated note from template.
- `ref` wrapper script for a shorter command.

## Repository Layout

```text
quickref/
|-- bin/
|   |-- qref
|   |-- qnewref
|   `-- ref
|-- notes/
|   |-- index.md
|   `-- ...
`-- templates/
    `-- note.md
```

## Requirements

- `bash` (all scripts use Bash)
- `nvim` required by `qref`; used by `qnewref` when opening notes interactively
- `rg` (ripgrep) required for `qref <query>` mode
- `fzf` recommended for interactive selection
- `fd` optional for faster file discovery in picker mode

## Local Setup

1. Clone and enter the repository:

```sh
git clone <your-repo-url> "$HOME/github/quickref"
cd "$HOME/github/quickref"
```

2. Ensure scripts are executable:

```sh
chmod +x bin/qref bin/qnewref bin/ref
```

3. Configure shell environment.

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

4. Verify installation:

```sh
qref --help
qnewref "quickref setup test"
```

## Usage

| Command | Behavior |
|---|---|
| `qref` | Interactive file picker (excludes `notes/index.md`) |
| `qref <text>` | Search notes and open selected match at exact line (excludes `notes/index.md`) |
| `qref --help` | Open `notes/index.md` |
| `qnewref "title"` | Create/open `notes/YYYY/MM/YYYY-MM-DD-title.md` |
| `ref` | Pass-through wrapper to `qref` |

Examples:

```sh
qref
qref docker compose
qref --help
qnewref "ssh troubleshooting"
```

## Configuration

### `QUICKREF_DIR`

- Default: `$HOME/github/quickref`
- Override to move quickref root elsewhere

```sh
export QUICKREF_DIR="$HOME/github/quickref"
```

### `QUICKREF_NO_OPEN`

Use for script-driven note creation without opening Neovim:

```sh
QUICKREF_NO_OPEN=1 qnewref "release checklist"
```

## Neovim Integration (Optional)

If your Neovim config defines quickref helpers, common patterns are:

- `:QuickrefFiles` open quickref file search
- `:QuickrefGrep` grep quickref notes
- `:QuickrefOpen` open this README
- `:QuickrefNew [title]` create/open dated note

Typical keymaps:

- `<leader>sq` quickref files
- `<leader>sQ` quickref grep
- `<leader>qo` open quickref README
- `<leader>qn` new quickref note

## Troubleshooting

| Error | Cause | Fix |
|---|---|---|
| `quickref directory not found: ...` | `QUICKREF_DIR` is wrong or the repository is missing | Set `QUICKREF_DIR` to the correct path |
| `nvim is required but not found in PATH` | Neovim is not installed or unavailable in PATH | Install Neovim and confirm `nvim` resolves |
| `ripgrep (rg) is required for search mode.` | `rg` is not installed | Install ripgrep |
| `fzf is required for interactive picker mode.` | `fzf` is not installed | Install `fzf` or use `qref <query>` |

## Contributing

Contributions are welcome.

- Keep notes and scripts simple and portable.
- Preserve current CLI behavior unless changes are clearly documented.
- Use small, focused pull requests.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
