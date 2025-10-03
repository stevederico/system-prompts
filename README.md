# Claude Configuration

## Conversation
- I am a software developer, talk to me like a Computer Science PHD Student
- Be extremely concise & direct in your responses
- Go step-by-step and process each change one at a time
- Try to use the least amount of external packages as possible
- Always show as much code as possible

## Programming

### Runtime & Package Management
- Use deno v2.5+ (NOT npm/node CLI for package management)
- Install packages: deno install npm:package-name
- Never run npm install
- Update deps: deno outdated --update
- Never run npm update
- You must Run deno install before you run deno run start or deno run dev
- Never start or stop dev servers (user handles this)
- Before you run the start script, make sure node_modules have been installed with deno install
- Make sure there is an alias to the package.json dev script called start. i.e. deno run start

### Frontend Stack
- Always use react version 19.2+
- Always use vite, version 7.1+
- Always use react-router-dom 7.9+
- Always use javascript
- Always use ES modules

### Styling & UI
- Always use tailwindcss v4+ with @tailwindcss/vite plugin
- Add `@import "tailwindcss"` to index.css
- Style using utility classes on elements, not central CSS
- Support dark mode with bg-background, bg-accent
- Never use postcss, autoprefixer, or tailwind.config.js

### Backend Stack
- Runtime: Node.js with Express v4.18+
- Always use nodejs for backend
- Always use express
- Prioritize sqlite for database, use mongodb if sqlite not available
- Always use mongodb npm package, never mongoose
- HTTP Client: Native fetch only
- Always use native fetch in js and nodejs

### Prohibited Tools & Practices
- Never use typescript
- never use @types packages
- Never use eslint or globals package
- Never use globals package
- Never add unit tests
- Never use require to import
- Never use mongoose, require(), PostCSS, autoprefixer, or tailwind.config.js
- Never run destructive commands (rm, mv, delete)
- Never run delete commands or move commands

## Sensitive Files
DO NOT read or modify:
- .env files
- *_/config/secrets.*
- *_/*.pem
- Any file containing API keys, tokens, or credentials
- Add .env to .gitignore

## Security Practices
- Never commit sensitive files
- Use environment variables for secrets
- Keep credentials out of logs and output
