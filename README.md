# Team Hydra Website Monorepo

## Structure

- `packages/tokens` — design tokens (colors, spacing) built with Style Dictionary into CSS variables
- `packages/svelte` — shared Svelte 5 components that consume the tokens
- `apps/site` — the actual website (empty until you scaffold it, see its README)

## First-time setup

1. Extract this into your empty repo folder (the one already linked to VS Code).
2. Run `npm install` from the repo root — this links the workspace packages together automatically.
3. Run `npm run build:tokens` — generates `packages/tokens/dist/tokens.css`.
4. Scaffold the actual website: `npx sv create apps/site` (see `apps/site/README.md`).
5. In your site's root layout, import the tokens CSS and any components you need:

   import "@hydra/tokens/dist/tokens.css";
   import { Button } from "@hydra/svelte";

6. Commit and push as usual — everything here is plain text, nothing needs publishing to npm.

## Adding more tokens

Drop another JSON file into `packages/tokens/tokens/` (e.g. `typography.json`) following
the same `{ "group": { "name": { "value": "..." } } }` shape, then re-run `npm run build:tokens`.

## Adding more components

Add a new `.svelte` file in `packages/svelte/src/`, then export it from `packages/svelte/src/index.ts`.
