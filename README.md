# Yujin Portfolio — Firestore Only

Current portfolio/editor package with the existing ambient light, glassmorphism and glow effects.

## Firebase services

- Firebase Authentication
- Cloud Firestore
- No Firebase Storage

## Admin accounts

- eugene.aquila06@gmail.com
- yujinybwork@gmail.com

## Firestore document

`sites/portfolio`

## Firestore Rules

```js
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /sites/portfolio {
      allow read: if true;
      allow create, update, delete: if request.auth != null
        && request.auth.token.email in [
          "eugene.aquila06@gmail.com",
          "yujinybwork@gmail.com"
        ];
    }

    match /{document=**} {
      allow read, write: if false;
    }
  }
}
```

Deploy with:

```bash
firebase deploy --only firestore:rules
```

Firebase Storage is intentionally not included. Image fields should use external image URLs.


## Editor improvements

The editor now supports:
- Profile name / logo editing
- Footer name editing
- Per-project descriptions
- Per-project YouTube URLs
- Click-to-preview YouTube videos in a glassmorphism modal
- Showreel YouTube preview
- Image URLs without Firebase Storage


## Quick section navigation

The editor now has a sticky quick-navigation bar with direct buttons for:

Identity, Hero, About, Works, Services, Process, Showreel, Contact, and Appearance.

Clicking a button smoothly scrolls directly to that section.
