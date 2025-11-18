<!-- .github/copilot-instructions.md - guidance for AI coding agents -->
# Copilot / AI agent instructions (concise)

Purpose: help an AI agent become productive quickly in this small Vue 3 + Vite app.

- Project entry & build
  - Entry: `index.html` loads `src/main.js` which mounts `App.vue` to `#app`.
  - Dev server: `npm run dev` (Vite). Default port: `5173` (open `http://localhost:5173`).
  - Build: `npm run build` and `npm run preview` to serve the built output.
  - Key files: `package.json`, `vite.config.js`, `index.html`, `src/main.js`.

- Tech stack & conventions (project-specific)
  - Vue 3 with `<script setup>` SFCs and the Composition API. Example: `src/components/HelloWorld.vue`.
  - Global styles: `src/style.css`. Component styles often use `scoped` in SFCs (see `App.vue`).
  - Assets in `public/` are served from the project root (e.g. `/vite.svg` used in `index.html` and `App.vue`). Files in `src/assets/` should be imported via relative paths.
  - `package.json` lists `vue` and `vuetify` as dependencies; Vuetify is present but not initialized in `main.js` — do not assume Vuetify components are wired unless you add the plugin setup.
  - Project uses ES modules (`"type": "module"` in `package.json`). Use `import`/`export`, not `require`.

- Code patterns to follow
  - Use Composition API idioms: `ref`, `reactive`, `defineProps` inside `<script setup>` (see `HelloWorld.vue`).
  - Keep single-file components small and place shared assets under `src/assets`.
  - HMR-friendly edits: editing SFCs (e.g., `components/HelloWorld.vue`) should trigger Vite HMR automatically.

- Integration & external dependencies
  - Vite + `@vitejs/plugin-vue` is used; plugin config lives in `vite.config.js`.
  - If you add Vuetify usage, update `src/main.js` to register Vuetify per its docs (this repo currently doesn't include that setup).

- Developer workflows & verification
  - Quick smoke test: run `npm install` (if needed) then `npm run dev` and open the app; change `src/components/HelloWorld.vue` to confirm HMR.
  - For builds, run `npm run build` then `npm run preview` to validate production output.
  - There are no automated tests configured; rely on manual verification and `dev` / `preview` runs.

- PR / change guidance (for AI-generated code)
  - Make minimally invasive changes; preserve `index.html` -> `src/main.js` mount pattern unless explicitly migrating.
  - When adding UI libraries (e.g., Vuetify), include initialization code in `src/main.js` and update `vite.config.js` only if required by the library.
  - Prefer small, focused commits with explanation and a brief manual test checklist (commands to run and files to edit to verify HMR/build).

- Examples & file references
  - Entrypoint: `index.html` -> `src/main.js` -> `App.vue`.
  - Example component: `src/components/HelloWorld.vue` (uses `defineProps`, `ref`, scoped styles).
  - Global styles: `src/style.css`.
  - Build config: `vite.config.js`.

If you find an existing `.github/copilot-instructions.md` or other agent guidance files, merge conservatively: preserve repo-specific commands and patterns, add any missing clarifications above, and avoid changing general contributing rules.

Questions? Ask the repo owner which UI library conventions they prefer (Vuetify usage, global component registration, or none) before adding framework-wide config.
