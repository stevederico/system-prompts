<h1 align="center" style="border-bottom: none; margin-bottom: 0;">AGENTS</h1>
<h3 align="center" style="margin-top: 0; font-weight: normal;">
  how I configure AI coding agents
</h3>

<p align="center">
  <a href="https://github.com/stevederico/ahoy">ahoy</a> — auto-focus and audio alert for multi-agent coding · <a href="https://github.com/stevederico/skateboard">skateboard</a> — react starter kit
</p>

<br />

## What's Here

| File | Description |
|------|-------------|
| **[AGENTS.md](AGENTS.md)** | Global `CLAUDE.md` — coding standards, stack preferences, deployment patterns, git workflow, and agent behavior rules |
| **[SETUP.md](SETUP.md)** | Dev environment — Ghostty, tmux, Zsh, micro/Zed, and how everything is wired together |

<br />

## How It Works

`AGENTS.md` is my global `CLAUDE.md` file. Claude Code loads it at the start of every conversation across all projects. It defines:

- **Coding standards** — naming, error handling, accessibility, API safety
- **Stack** — React + Vite + Hono, Tailwind v4, shadcn/ui, Deno, SQLite
- **Agent behavior** — default to parallel teams, auto-commit, never echo requests
- **Git workflow** — version bumping, changelog format, selective staging
- **Dev validation** — headless browser CLI for visual QA after every change

<br />

## Stack

| Layer | Tools |
|-------|-------|
| Terminal | [Ghostty](https://github.com/ghostty-org/ghostty), [tmux](https://github.com/tmux/tmux), [micro](https://github.com/zyedidia/micro) |
| Editor | [Zed](https://github.com/zed-industries/zed) |
| Frontend | [React](https://github.com/facebook/react) 19, [Vite](https://github.com/vitejs/vite) 7, [Tailwind](https://github.com/tailwindlabs/tailwindcss) v4, [shadcn/ui](https://github.com/shadcn-ui/ui) |
| Backend | [Node.js](https://github.com/nodejs/node), [Hono](https://github.com/honojs/hono), [SQLite](https://github.com/sqlite/sqlite) |
| Runtime | [Deno](https://github.com/denoland/deno) |
| AI | Claude Code with [Ahoy](https://github.com/stevederico/ahoy) for auto-focus and audio alert |

<br />

## Related Projects

- [ahoy](https://github.com/stevederico/ahoy) — Auto-focus and audio alert for multi-agent coding
- [skateboard](https://github.com/stevederico/skateboard) — React starter with auth, Stripe, shadcn, and SQLite
- [skateboard-ui](https://github.com/stevederico/skateboard-ui) — Web component library

<br />

---

<div align="center">
  <p>
    Built by <a href="https://github.com/stevederico">Steve Derico</a>
  </p>
</div>
