# Yujin Portfolio — Firebase + Vercel Clean Package

This package keeps the actual portfolio/editor pages and moves Firebase configuration
into one shared `firebase-config.js` file.

## Routes

- `/` — public portfolio
- `/editor` — protected visual editor
- `/admin` — protected visual editor

## Admin Google accounts

- eugene.aquila06@gmail.com
- yujinybwork@gmail.com

## Firebase setup

1. Firebase Console → Authentication → Sign-in method → enable Google.
2. Add your Vercel domain under Authentication → Settings → Authorized domains.
3. Make sure both admin Google accounts are Firebase Authentication users.
4. Set the Firestore and Storage rules to the correct admin UID(s).
5. If you see `auth/invalid-api-key`, replace the values in `firebase-config.js` with the
   current Web App config from Firebase Console → Project settings → Your apps.

## Important

The Firebase web API key is client-side configuration and is expected to be present in
the frontend. Do not put a Firebase service-account private key in this package.

The editor uses Firebase Authentication, Firestore, and Storage. The public site only
loads the published portfolio configuration.

## Deploy

Upload this folder to Vercel. No build step is required.
