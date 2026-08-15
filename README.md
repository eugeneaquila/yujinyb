# Yujin Portfolio — Vercel Ready

## Files

- `index.html` — public portfolio
- `editor.html` — no-code editor
- `vercel.json` — Vercel routing and headers
- `yujin-portfolio-default.json` — starter configuration

## Deploy to Vercel

This is a static site and does not require a build command or framework. Import this folder into Vercel as a project and deploy from the project root.

The public page is `/`. The no-code editor is `/editor` (with `/admin` as an alias).

## Important about saving

The current editor stores customizations in the browser's `localStorage`. That means it is excellent for local editing and previews, but it does **not** create a shared database or publish changes to every visitor automatically. A Vercel deployment is static unless you add a persistence layer.

For a true multi-device CMS where you change the site once and every visitor sees the update, the next step is a Vercel/Supabase-backed editor.
