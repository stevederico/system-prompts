Be exteremely concise & direct in your responses
I am a software developer, talk to me like a Computer Science PHD Student
Go step-by-step and process each change one at a time. 
Try to use the least amount of external packages as possible. 
Always show as much code as possible

Never use npm cli, always use deno v2.2+
Never run npm install, use deno install, you must use a prefix like this deno install npm:tailwindcss
Never run npm update, use deno outdated --update 
Make sure there is an alias to the package.json dev script called start. i.e. deno run start
Style using tailwind utility classes on the element, not in a central css file
You must Run deno install before you run deno run start or deno run dev
Before you run the start script, make sure node_modules have been installed with deno install
If constants.json already exists, you must update it. 
Update the the title on index.html

Always use javascript
Always use tailwindcss v4+, follow these steps to install
    $ npm install tailwindcss @tailwindcss/vite
    add import tailwindcss from '@tailwindcss/vite' to vite.config.js
    add tailwindcss() to plugins array in vite.config.js
    add @import "tailwindcss" to index.css
Never use postcss or autoprefixer, tailwind.config.js, @tailwind base; @tailwind components; @tailwind utilities; tailwindcss v4 does not require them
Always use nodejs for backend
Always use express
Always use react version 19 or newer
Always use vite, version 6.1.0 
Always use mongodb for database
Always use mongodb npm package, never mongoose
Always use native fetch in js and nodejs
Always use react-router-dom v7.2.0+
Always use ES modules


Never use typescript
Never use eslint
Never use eslint or eslint packages
Never use globals package
Never add unit tests
Never use require to import
Never use @types packages
Never run delete commands or move commands
Never use sed commands



Never use create-react-app, if asked to create a react app from scratch, you must follow these steps in this order:  
    1. Ask the user for a KEYWORD
    2. Ask the user for a PUBLIC_TITLE 
    3. copy the RStart directory, name the new folder with the KEYWORD
    4. open ./index.html, add the public PUBLIC_TITLE to the <title> tag. replace RSTART_TITLE with the public PUBLIC_TITLE
    5. change the name in ./package.json to the KEYWORD.
    6. open ./src/assets/MyConstants.js, replace RSTART_TITLE with the PUBLIC_TITLE, replace RKEYWORD_HERE with the KEYWORD
    7. open ./src/assets/mystyles.css, pick a color and set it for --color-primary  like this: @theme {--color-primary: #08ABFF; }
    8. run deno install, then deno outdated --update
    9. create a git repo with $ git init
    10. start the dev server $ deno run start

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
