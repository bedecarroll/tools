 # AGENTS

 ## Overview

 This repository hosts a static, client-side directory website listing command-line tools. All functionality runs entirely in the user's browser; there is no server-side code. Tools are defined by Markdown files, and the site generates an overview page that can be searched using the browser's built-in search.

 ## Repository Structure

 ```plaintext
 .
 ├── tool_readmes/              # Directory of tool Markdown files
 ├── scripts/
 │   └── generate-tools.js      # Generates tools.json from Markdown files
 ├── tools.json                 # Generated list of tools
 ├── src/
 │   ├── main.ts                # Loads tools.json and renders tool cards
 │   └── autocomplete.ts        # (Optional) Autocomplete widget
 ├── index.html                 # Entry point for the site
 ├── styles.css                 # Site styling
 ├── package.json               # NPM scripts: generate-tools, build, serve, serve:python
 ├── tsconfig.json              # TypeScript configuration
 ├── dist/                      # Compiled JS assets (generated)
 └── public/                    # Built static site (generated)
 ```

 ## Build & Development Workflow

 1. Install dependencies:
    ```bash
    npm install
    ```
 2. Generate the tools list and build the site:
    ```bash
    npm run build
    ```
 3. Serve the site locally:
    ```bash
    npm run serve
    # or
    npm run serve:python
    ```
 4. For iterative development, watch and rebuild on changes:
    ```bash
    npm run dev
    ```

 ## Guidelines for LLM Agents

 - Modify or add Markdown files in `tool_readmes/` to update tools.
 - Use `scripts/generate-tools.js` to regenerate `tools.json` whenever tool files change.
 - Client-side logic is in `src/`; changes here run in the browser.
 - Preserve the static, serverless design; do not introduce server-side dependencies.
 - After changes, run the build script and serve the site to verify output.
