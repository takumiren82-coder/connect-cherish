## Goal
Copy the full contents of `github.com/takumiren82-coder/project-bloom` into this project so it runs in the preview.

## What I found
The repo is public and uses the exact same stack as this project (TanStack Start + React 19 + Tailwind v4 + shadcn/ui), so it can be copied over 1:1. It contains ~150 files: all routes (home, auth, library, reader, article, profile, hub with chat/gallery/reels/status), components, hooks, lib utilities, assets, and a Supabase integration folder.

## Steps
1. Download the repo archive and copy every file into this project, overwriting the placeholder home page, `__root.tsx`, `router.tsx`, `styles.css`, `src/server.ts`, `src/start.ts`, config files, `public/` assets and `src/assets/` images.
2. Replace `package.json` dependencies with the repo's list and install them (adds `@supabase/supabase-js`, radix packages, recharts, embla, sonner, vaul, etc.).
3. Let the router regenerate its route tree, then flush the dev server and load the preview.
4. Screenshot the running app to confirm it renders, and fix any import/build errors that surface from the copy.

## Technical note
The repo's code talks to a backend (Supabase client + auth middleware + a public API route). The original project's backend credentials belong to that other project and won't be carried over. So the UI will run in preview, but any login/data features will be inert until backend is enabled here. Two options once the clone is up:
- Leave it UI-only for now (fastest, matches "just clone and open").
- Enable Lovable Cloud on this project and recreate the database schema so data features work again — this needs the original schema, which isn't in the repo unless a `supabase/migrations` folder exists (I'll check during the copy).

I'll do the clone first and report which of the two applies.