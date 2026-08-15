# Yujin Portfolio — Visual Editor

This package uses the actual Yujin portfolio layout as the public site. The editor is a no-code control panel for that same page.

- `/` → `index.html`
- `/editor` → `editor.html`
- `/admin` → `editor.html`

The editor uses localStorage for saved design/content. The public page reads that configuration automatically. For shared publishing across devices, replace localStorage with a persistent backend.
