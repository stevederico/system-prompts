# Dev Setup

How I like to code. Everything is symlinked from a single dotfiles repo so any machine is identical in minutes.

## Terminal: Ghostty

- Font: JetBrains Mono 14pt, thickened
- Theme: GitHub Dark, 92% opacity with background blur
- Tabs as titlebar, block cursor (no blink)
- Keybinds remap Cmd to Ctrl for micro editor compatibility
- `Cmd+N` creates new tmux window, `Cmd+B Space` opens tmux menu

## Multiplexer: tmux

- Always working inside a tmux session (`t` alias attaches or creates `dev`)
- Status bar at top, transparent, shows current path and command per window
- Windows auto-rename to current directory
- Mouse enabled for scrolling, resizing, clicking
- Pane borders: yellow active, dim inactive; heavy lines
- `Prefix Space` opens a quick menu for splits, windows, and session management
- 50k line scrollback

## Editor: Micro (terminal) / Zed (GUI)

- `$EDITOR=micro` for quick terminal edits, `$VISUAL=zed --wait` for everything else
- `code` is aliased to `zed`
- Micro uses GitHub Dark colorscheme
- Bat (cat replacement) also uses GitHub Dark theme

## Shell: Zsh

- Minimal prompt: `dirname %#` — just the current folder and a `%`
- Key aliases:
  - `d` — cd to Desktop
  - `gs` — git status + last 3 commits
  - `gp` — stage all, auto-generate commit message with Claude, push to master
  - `ds` — kill ports 8000/5173, then `deno run start`
  - `c` — launch Claude Code
  - `t` — attach to tmux session
  - `y` — yazi file manager
  - `ru` — deploy
  - `pup` — `deno outdated --update`
  - `clearports` — kill processes on common dev ports (3000, 8000, 5173, 5174)
- Zsh autosuggestions (Shift+Tab to accept)
- Zoxide for smart `cd`
- Tab completion with case-insensitive matching

## Git

- Default branch: `master`
- Editor: micro
- Global gitignore

## Package Management

- Deno for JS package management (never npm CLI)
- pip/uv for Python with supply-chain protections (`pip.conf`, `uv.toml`)
- Python virtual envs in `~/py-envs/` via `create_env` / `activate_env` helpers

## Dotfiles Sync

Everything lives in a single dotfiles repo. A `setup.sh` script symlinks all configs to their expected locations:

- `~/.zshrc` -> shell config
- `~/.gitconfig` -> git config
- `~/.tmux.conf` -> tmux config
- `~/.config/ghostty/` -> terminal config
- `~/.config/zed/` -> editor config
- `~/.config/micro/` -> terminal editor config
- `~/.claude/` -> AI agent config (CLAUDE.md, settings, hooks, commands, skills)

Run `setup.sh --doctor` to health-check all symlinks.

## Multi-Agent: Ahoy

When running multiple Claude Code sessions in parallel, [Ahoy](https://github.com/stevederico/ahoy) auto-focuses the right terminal tab when an agent needs input. Each session gets a unique name, emoji tab states show what each agent is doing, and voice alerts call out the agent name.

## Theme

GitHub Dark everywhere: Ghostty, micro, bat, Zed. Consistent dark background across all tools.
