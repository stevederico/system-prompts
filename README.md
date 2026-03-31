<h1 align="center" style="border-bottom: none; margin-bottom: 0;">System Prompts</h1>
<h3 align="center" style="margin-top: 0; font-weight: normal;">
  how I configure AI coding agents
</h3>

<p align="center">
  <a href="https://github.com/stevederico/ahoy">
    <img src="https://img.shields.io/badge/auto--focus-ahoy-blue" alt="Ahoy">
  </a>
  <a href="https://github.com/stevederico/skateboard">
    <img src="https://img.shields.io/badge/boilerplate-skateboard-green" alt="Skateboard">
  </a>
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
| Terminal | Ghostty, tmux, micro |
| Editor | [Zed](https://github.com/zed-industries/zed) |
| Frontend | React 19, Vite 7, Tailwind v4, shadcn/ui |
| Backend | Node.js, Hono, SQLite |
| Runtime | Deno |
| AI | Claude Code with [Ahoy](https://github.com/stevederico/ahoy) for multi-agent focus |

<br />

## Related Projects

- [ahoy](https://github.com/stevederico/ahoy) — Auto-focus terminal tabs across multi-agent sessions
- [skateboard](https://github.com/stevederico/skateboard) — React starter with auth, Stripe, shadcn, and SQLite
- [skateboard-ui](https://github.com/stevederico/skateboard-ui) — Web component library

<br />

---

<div align="center">
  <p>
    Built by <a href="https://github.com/stevederico">Steve Derico</a>
  </p>
</div>
