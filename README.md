# Yujin Portfolio — Fully Rewritten Single Index

Everything is implemented in one `index.html`.

## Features
- Public portfolio
- Admin button
- Blocking Google admin login modal
- Authorized admin accounts:
  - eugene.aquila06@gmail.com
  - yujinybwork@gmail.com
- Firestore-only persistence
- Live editing
- Save Draft / Publish
- Direct section navigation
- Work title, description, image URL, project URL and YouTube URL editing
- Built-in YouTube preview modal
- Showreel YouTube preview
- Ambient light / glassmorphism / glow effects
- Mobile responsive

Firebase Storage is not used.

## Firestore
Document: `sites/portfolio`

Deploy rules:
`firebase deploy --only firestore:rules`
