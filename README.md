## Conversation
- Be extremely concise & direct in your responses
- I am a software developer, talk to me like a Computer Science PHD Student
- Go step-by-step and process each change one at a time. 
- Try to use the least amount of external packages as possible. 
- Always show as much code as possible

## Programming
- Never use npm cli, always use deno v2.2+
- Never run npm install, use deno install, you must use a prefix like this deno install npm:tailwindcss
- Never run npm update, use deno outdated --update 
- Make sure there is an alias to the package.json dev script called start. i.e. deno run start
- Style using tailwind utility classes on the element, not in a central css file
- You must Run deno install before you run deno run start or deno run dev
- Before you run the start script, make sure node_modules have been installed with deno install
- If constants.json already exists, you must update it. 
- Update the the title on index.html
- Always use javascript
- Always use tailwindcss v4+, follow these steps to install
    - $ npm install tailwindcss @tailwindcss/vite
    - add import tailwindcss from '@tailwindcss/vite' to vite.config.js
    - add tailwindcss() to plugins array in vite.config.js
    - add @import "tailwindcss" to index.css
- Never use postcss or autoprefixer, tailwind.config.js, @tailwind base; @tailwind components; @tailwind utilities; tailwindcss v4 does not require them
- Always support dark mode, use bg-background, bg-accent for components, and do not specify a text color.
- Always use nodejs for backend
- Always use express
- Always use react version 19 or newer
- Always use vite, version 6.1.0 
- Always use mongodb for database
- Always use mongodb npm package, never mongoose
- Always use native fetch in js and nodejs
- Always use react-router-dom v7.2.0+
- Always use ES modules
- Never use typescript
- Never use eslint
- Never use eslint or eslint packages
- Never use globals package
- Never add unit tests
- Never use require to import
- Never use @types packages
- Never run delete commands or move commands
- Never use sed commands
- when editing the _worklog or worklog file only use - aka dash to mark incomplete tasks. Do not use any symbol for completed tasks. At the end of the completed section, append a single line: Version: x.y.z. 


## Sensitive Files
DO NOT read or modify:
-   .env files
-   \*_/config/secrets._
-   \*_/_.pem
-   Any file containing API keys, tokens, or credentials
## Security Practices
-   Never commit sensitive files
-   Use environment variables for secrets
-   Keep credentials out of logs and output
