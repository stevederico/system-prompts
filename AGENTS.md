# Session Start

Run `git pull origin master` at the start of every new conversation before any other work.

# Coding Standards

## Docs
- Exported/public functions need doc comments matching implementation
- JSDoc for JS, `///` for Swift, `#` for Shell
- Update docs when modifying functions; remove orphaned docs
- Exempt: trivial getters, one-liner utils, private helpers <3 lines, third-party code

## Changelog & To-Do
- Changelog: `item` (no dash) = completed; 3 words or less, present tense
- To-do: `- item` (dash) = incomplete; never remove/edit completed items
- Per-project: `todo.md` in project root

## Naming
- Functions: `camelCase` verbs; Components: `PascalCase`; Constants: `UPPER_SNAKE_CASE`
- Files: components `PascalCase.jsx`, else `camelCase.js`
- Booleans: `is`, `has`, `should` prefix

## Functions
- Max ~50 lines; single responsibility; early returns; no magic numbers

## Error Handling (MANDATORY)
- Handle at system boundaries; never swallow errors
- Every error visible to user: toast for transient, inline for forms, empty states for failed fetches
- Human-readable messages; include recovery action; loading indicators >200ms
- Graceful degradation; circuit breaker after 3 consecutive external API failures

## External API Safety (MANDATORY)
- Respect rate limits; exponential backoff on 429/5xx (1s->2s->4s->8s, max 3-5 retries)
- Never loop without throttling; never call batch endpoints in a loop
- Log rate limit headers; read API docs before writing integration

## Code Organization
- Imports: external -> internal -> relative
- Components: split at ~150 lines

## React
- Functional only; colocate state; context over prop drilling >2 levels
- `handle` prefix for event handlers; never `alert()`/`confirm()`/`prompt()`
- Max 3 nesting levels; empty states for lists; loading/error/data for fetches

## Accessibility (MANDATORY)
- Labels or `aria-label` on all interactive elements; meaningful `alt` text
- `<Label>` via `htmlFor`/`id`; `aria-label` on icon-only buttons
- Semantic HTML; correct heading hierarchy; escape closes modals; focus trapping
- WCAG 2.1 AA contrast; 44px touch targets; honor `prefers-reduced-motion`

# Claude Configuration

## Terminology
- "Skateboard" = React/Hono boilerplate: `github.com/stevederico/skateboard`
- "Skateboard-UI" = web component library: `github.com/stevederico/skateboard-ui`
- Scaffold new apps: `npx create-skateboard-app@latest <project-name> --yes`

### Updating Skateboard Apps
1. Check `package.json` for `skateboardversion`
2. `cd ~/projects/skateboard && git pull origin master`
3. Diff versions, port structural changes, preserve app logic
4. Use exact `@stevederico/skateboard-ui` version from boilerplate
5. Validate build

### Updating Skateboard-UI
Publish -> update boilerplate's `package.json` -> commit boilerplate

## Skills
- Install: `npx skills add <owner/repo>` — never `claude install`

## Platform Constraints
- No `timeout` on macOS; `sed -i ''`; BSD `date` (`-v-1d` not `-d`)
- No `xargs -r`; prefer `gh` CLI; use `agent-browser` for automation
- Never search rooted at `~`; `curl -A "Claude-Agent"` on user sites

## Conversation
- Talk like CS PhD student; extremely concise & direct
- Show code; act first on obvious fixes; recommend & execute best option
- Never echo requests as questions

## Agent Teams
**DEFAULT TO TEAMS.** Bias toward parallelization. Use for 2+ files, features, refactoring, research+implementation. Skip for Q&A, single-line fixes.

### iOS / Xcode
- `DEVELOPER_DIR=/Applications/Xcode.app/Contents/Developer`

## Programming

### General
- Minimize external packages

### Project Skills
- Check `skills/*/SKILL.md` before building UI

### JavaScript Style
- `const` > `let`; `async/await` > `.then()`; destructuring; array methods
- Optional chaining `?.`; nullish coalescing `??`; template literals
- Object shorthand; default parameters

### Runtime
- Deno for package management (`deno install npm:...`, `deno outdated --update`)
- Never `npm install/update`; always `deno install` before `deno run start`
- Kill port 8000/5173 if occupied

### Frontend: React + Vite + react-router-dom; JavaScript; ES modules

### Styling
- Tailwind v4+ with `@tailwindcss/vite`; `@import "tailwindcss"` in index.css
- Semantic tokens (`bg-background`, `text-foreground`); never raw colors or `dark:` overrides
- `gap-*` not `space-*`; `size-*` for squares; `rounded-md/lg` from tokens
- Scale values not arbitrary; `cn()` for conditionals; mobile-first breakpoints
- `text-balance`/`text-pretty` on headings; specific transitions not `transition-all`
- No decorative blobs; max 3-5 semantic colors; max 2 font families

### Icons: Lucide React; no emoji as icons; `aria-label` on icon buttons; sizes: 16/18/24/48px

### UI Components — shadcn
- If `@stevederico/skateboard-ui` installed, import from `@stevederico/skateboard-ui/shadcn/ui/<component>`
- Read component source before first use; compound patterns not prop APIs
- `<Button>` not `<button>`, `<Dialog>` not custom div, `toast()` not `alert()`

### Backend: Node.js + Hono; SQLite preferred; `mongodb` package (not mongoose); native `fetch` only

### Prohibited
- No TypeScript, dotenv, `require()`, mongoose, axios, PostCSS, ESLint, `globals`

### Design Config
Include `design` block in `constants.json`: `{ baseColor, radius, font, iconLibrary }`

## Reference Docs
Consult before making assumptions:

| Library | Docs |
|---|---|
| shadcn/ui | https://ui.shadcn.com/llms.txt |
| xAI / Grok | https://docs.x.ai/llms.txt |
| Vite | https://vite.dev/llms.txt |
| Hono | https://hono.dev/llms.txt |
| Tailwind v4 | https://raw.githubusercontent.com/tailwindlabs/tailwindcss.com/refs/heads/md-endpoints/llms.txt |
| agent-browser | `agent-browser --help` |

## Shared Environment
- Use env vars for all secrets; symlink `.env` into `backend/`
- `loadLocalENV()` reads `backend/.env` then `backend/.env.local`

## Security
- Never hardcode connection strings; env vars for secrets; no creds in logs

## Working Directory
`~/projects`. Check existing -> `git pull`; else clone from GitHub.

## Deployment

### Deploy Method
Always use CLI push. Never use git-based deployment. Workflow:
```bash
cd ~/projects/<project>
deploy 2>&1
```

**NEVER `sleep` after deploy.** Deploy streams build logs to stdout — run it in foreground, wait for it to complete, then immediately verify the production URL. If the deploy needs propagation time, retry `curl` 3-5 times with 5s gaps — never blind sleep.

### Serverless
- Prefer serverless (scale to zero when idle) over always-on
- Proxies should stay always-on; all other services should be serverless

## Testing
- Vitest only (never Jest/Mocha); install via `deno install npm:vitest`
- Test files next to source: `foo.js` -> `foo.test.js`
- Test business logic, API routes, utils, auth, validation, edge cases; skip trivial renders
- Mock at boundary only (`fetch`, not callers); `vi.fn()` / `vi.spyOn()`; reset in `afterEach`
- Bug fix -> write failing test first; refactor -> tests pass without modification
- `deno run test` must pass with zero failures before commit; no `.only` or `.skip`

## Dev Validation
After implementing, validate visually before marking complete.
- Check: visual state, console errors, exceptions, network requests, interactivity
- Use headless browser CLI: `open <url>`, `snapshot -i -c` (compact DOM), `click @ref`, `fill @ref "text"`, `screenshot`, `console`, `errors`
- `snapshot -i -c` for all intermediate steps; screenshots only for final visual check
- Multi-agent: isolated sessions via `--session` flag
- iOS: XCUITest with `DEVELOPER_DIR`; delete validation targets after use

## Git

### Branching
- Default branch: `master`; naming: `feature/`, `fix/`, `chore/`
- One PR per logical change; imperative mood

### Worktrees
- Use `git worktree add` for multi-agent; never `git checkout` during parallel work

### Versioning
- Minor bumps by default (0.1.0 -> 0.2.0); patch only for critical hotfixes

### Commit Process
1. Update CHANGELOG.md (insert above previous; 2-space indent, no dashes, 3 words)
2. Bump package.json version
3. Stage only files you modified (no `git add .` for agent commits)
4. Commit: version + descriptive summary
5. `git push origin master && git tag 0.x.x && git push origin 0.x.x`

### Auto-Commit (MANDATORY)
- After completing a feature or fix, commit and push without asking — do not wait for user approval
- Use selective staging (only files you modified)
- Auto-tag only on version bumps (not every commit)
- Deploy still requires explicit user approval

### Auto Build & Run (Swift/Xcode projects)
- After modifying Swift or Metal files, automatically build and run
- Always kill existing process before launching new build
- Never hardcode DerivedData paths — resolve dynamically

## gstack
Available skills: /office-hours, /plan-ceo-review, /plan-eng-review, /plan-design-review,
/design-consultation, /review, /ship, /land-and-deploy, /canary, /benchmark, /browse,
/qa, /qa-only, /design-review, /setup-browser-cookies, /setup-deploy, /retro,
/investigate, /document-release, /codex, /cso, /autoplan, /careful, /freeze, /guard,
/unfreeze, /gstack-upgrade.
