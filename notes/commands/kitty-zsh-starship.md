# Kitty + Zsh + Starship Quickref

Use with: `qref kitty`, `qref zsh`, `qref starship`

## Kitty Keybinds

`kitty_mod = Ctrl+Shift`

| Keys | Action |
|---|---|
| `Ctrl+Shift+Enter` | New window in current directory |
| `Ctrl+Shift+T` | New tab in current directory |
| `Ctrl+Shift+D` | Vertical split |
| `Ctrl+Shift+O` | Horizontal split |
| `Ctrl+Shift+H/J/K/L` | Move between splits |
| `Ctrl+Shift+W` | Close split/window |
| `Ctrl+Shift+Q` | Close tab |
| `Ctrl+Shift+,` / `Ctrl+Shift+.` | Previous / next tab |
| `Ctrl+Shift+Y` | URL picker |
| `Ctrl+Shift+F` | Toggle fullscreen |
| `Ctrl+Shift+R` | Reload kitty config |
| `Ctrl+Shift+=` / `Ctrl+Shift+-` | Font size up / down |

## Zsh Keybinds

| Keys | Action |
|---|---|
| `Ctrl+R` | Search history |
| `Up/Down` | Prefix-based history navigation |
| `Alt+B` / `Alt+F` | Move by word |
| `Ctrl+Left` / `Ctrl+Right` | Move by word |
| `Ctrl+W` | Delete previous word |
| `Ctrl+U` | Delete to line start |
| `Ctrl+K` | Delete to line end |
| `Ctrl+Y` | Paste deleted text |
| `Ctrl+X Ctrl+E` | Edit command in Neovim |
| `Ctrl+A` / `Ctrl+E` | Start / end of line |

## Useful Commands

- Reload Zsh: `source ~/.config/zsh/.zshrc`
- Reload Kitty: `Ctrl+Shift+R`
- Check Kitty config: `kitty --debug-config`

## Starship

- Config file: `~/.config/starship.toml`
- Check install: `command -v starship`
- Enable in Zsh:

```zsh
if command -v starship >/dev/null 2>&1; then
    eval "$(starship init zsh)"
fi
```
