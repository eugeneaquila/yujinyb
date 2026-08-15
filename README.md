# Yujin Portfolio — No-Code Editor

## Files

- `index.html` — public portfolio
- `editor.html` — visual no-code editor
- `vercel.json` — Vercel routing
- `yujin-portfolio-default.json` — starter configuration
- `builder-config.json` — builder metadata

## Use locally

Open `editor.html` in a browser. Edit the portfolio using the controls and use the live preview.

## Vercel

Upload this folder/project to Vercel.

- `/` → public portfolio
- `/editor` → visual editor
- `/admin` → visual editor

## Important

The editor stores the current configuration in the browser's localStorage. This means the editor is completely static and requires no backend, but changes made in one browser are not automatically published to other visitors.

For a shared production CMS, replace the localStorage layer with a persistent database such as Supabase.
