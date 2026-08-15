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
