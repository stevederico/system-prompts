# AGENTS

How I work with agentic coding assistants

| File | Description |
|------|-------------|
| **[AGENTS.md](AGENTS.md)** | Global — coding standards, stack preferences, deployment patterns, git workflow, and agent behavior rules |
| **[SETUP.md](SETUP.md)** | Dev environment — Ghostty, tmux, Zsh, micro/Zed, and how everything is wired together |

## How It Works

`AGENTS.md` is my global file. Coding Agent loads it at the start of every conversation across all projects. It defines:

- **Coding standards** — naming, error handling, accessibility, API safety
- **Stack** — React + Vite + Hono, Tailwind v4, shadcn/ui, Deno, SQLite
- **Agent behavior** — default to parallel teams, auto-commit, never echo requests
- **Git workflow** — version bumping, changelog format, selective staging
- **Dev validation** — headless browser CLI for visual QA after every change

## Stack

| Layer | Tools |
|-------|-------|
| Terminal | [Ghostty](https://github.com/ghostty-org/ghostty), [tmux](https://github.com/tmux/tmux), [micro](https://github.com/zyedidia/micro) |
| Editor | [Zed](https://github.com/zed-industries/zed) |
| Frontend | [React](https://github.com/facebook/react) 19, [Vite](https://github.com/vitejs/vite) 7, [Tailwind](https://github.com/tailwindlabs/tailwindcss) v4, [shadcn/ui](https://github.com/shadcn-ui/ui) |
| Backend | [Node.js](https://github.com/nodejs/node), [Hono](https://github.com/honojs/hono), [SQLite](https://github.com/sqlite/sqlite) |
| Runtime | [Deno](https://github.com/denoland/deno) |
| AI | Coding Agent with [Ahoy](https://github.com/stevederico/ahoy) for auto-focus and audio alert |

## Related Projects

- [skills](https://github.com/stevederico/skills) — Custom agent skills and subagents for Claude and other LLMs
- [ahoy](https://github.com/stevederico/ahoy) — Auto-focus and audio alert for multi-agent coding
- [skateboard](https://github.com/stevederico/skateboard) — React starter with auth, Stripe, shadcn, and SQLite
- [skateboard-ui](https://github.com/stevederico/skateboard-ui) — Web component library

---

Built by [Steve Derico](https://github.com/stevederico)
