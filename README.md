# quickref

A lightweight, git-friendly knowledge base for terminal and Neovim workflows.

quickref is built for one thing: fast capture and fast retrieval of personal reference notes without adding maintenance overhead.

## Highlights

- Search-first workflow from terminal (`qref <query>`)
- Interactive file picker for browsing notes (`qref`)
- Date-based note creation with stable paths (`qnewref "title"`)
- Markdown-first structure that stays easy to diff and review
- Optional Neovim-native command/keymap integration

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

- `bash` (scripts are Bash)
- `nvim` required by `qref`; used by `qnewref` when opening a created note
- `rg` (ripgrep) required for `qref <query>` mode
- `fzf` recommended for interactive selection
- `fd` optional for faster file discovery in picker mode

## Local Setup

1. Clone to your preferred path (example uses `~/github/quickref`):

```sh
git clone <your-repo-url> "$HOME/github/quickref"
cd "$HOME/github/quickref"
```

2. Ensure the scripts are executable:

```sh
chmod +x bin/qref bin/qnewref bin/ref
```

3. Add quickref to your shell environment (zsh example):

```sh
cat <<'EOF' >> ~/.zshrc
export QUICKREF_DIR="$HOME/github/quickref"
export PATH="$QUICKREF_DIR/bin:$PATH"

alias ref='qref'
alias qn='qnewref'
EOF

source ~/.zshrc
```

For Bash, use `~/.bashrc` instead of `~/.zshrc`.

4. Verify installation:

```sh
qref --help
qnewref "quickref setup test"
```

## CLI Usage

| Command | Behavior |
|---|---|
| `qref` | Interactive file picker (excludes `notes/index.md`) |
| `qref <text>` | Search notes and open selected match at exact line (excludes `notes/index.md`) |
| `qref --help` | Open `notes/index.md` |
| `qnewref "title"` | Create/open `notes/YYYY/MM/YYYY-MM-DD-title.md` |
| `ref` | Pass-through wrapper to `qref` |

### Examples

```sh
qref
qref docker compose
qref --help
qnewref "ssh troubleshooting"
```

## Configuration

### `QUICKREF_DIR`

- Default: `$HOME/github/quickref`
- Use this to point quickref to a different root path

```sh
export QUICKREF_DIR="$HOME/github/quickref"
```

### `QUICKREF_NO_OPEN`

Set this for non-interactive usage of `qnewref` (for scripts/automation):

```sh
QUICKREF_NO_OPEN=1 qnewref "release checklist"
```

## Behavior Notes

- `notes/index.md` is intentionally excluded from picker and search results.
- Use `qref --help` to open `notes/index.md` directly.
- In search mode without `fzf`, `qref` opens the first match automatically.

## Neovim Integration (Optional)

If your Neovim config defines quickref helpers, common patterns are:

- `:QuickrefFiles` to open quickref file search
- `:QuickrefGrep` to grep within quickref notes
- `:QuickrefOpen` to open this README
- `:QuickrefNew [title]` to create/open a dated note

Typical keymaps:

- `<leader>sq` quickref files
- `<leader>sQ` quickref grep
- `<leader>qo` quickref README
- `<leader>qn` new quickref note

## Troubleshooting

| Error | Cause | Fix |
|---|---|---|
| `quickref directory not found: ...` | `QUICKREF_DIR` is wrong or repo is missing | Set `QUICKREF_DIR` to the correct path |
| `nvim is required but not found in PATH` | Neovim is not installed or not on PATH | Install Neovim and confirm `nvim` is available |
| `ripgrep (rg) is required for search mode.` | `rg` is not installed | Install ripgrep |
| `fzf is required for interactive picker mode.` | `fzf` is not installed | Install `fzf` or use `qref <query>` |
