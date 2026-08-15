# Yujin Portfolio — Firebase + Vercel No-Code Editor

This package uses the ACTUAL portfolio layout from the uploaded `index.html` and the ACTUAL visual editor from the uploaded `editor.html`.

## Firebase project

Project: `yujin-f6be5`

The Firebase web configuration supplied by the owner is already included in both pages.

## What is integrated

- Firebase Authentication (Email/Password) for the editor
- Cloud Firestore document: `sites/portfolio`
- `draftConfig` for saved drafts
- `publishedConfig` for the public portfolio
- Firebase Storage for uploaded portfolio project images
- Public `index.html` loads the published configuration from Firestore
- Editor live preview uses the real `index.html`
- LocalStorage remains as an offline fallback

## Firebase setup

1. In Firebase Console, enable Authentication → Sign-in method → Email/Password.
2. Create the admin user that will operate the editor.
3. Copy that user's UID.
4. Replace `REPLACE_WITH_YOUR_ADMIN_UID` in:
   - `firestore.rules`
   - `storage.rules`
5. Publish those rules.
6. Enable Firestore Database.
7. Enable Storage.

Do not open Firestore/Storage to all authenticated users. The rules in this package restrict writes to the one admin UID.

## Vercel

Deploy the folder to Vercel. The static site works without a build command.

Routes:
- `/` → public portfolio
- `/editor` → visual editor
- `/admin` → visual editor

## Editing flow

1. Open `/editor`.
2. Sign in with the Firebase admin account.
3. Change content/design.
4. Click **Save Draft**.
5. Click **Publish** when ready.
6. Visitors opening `/` load the published Firestore configuration.

## Security

The Firebase API key in a web app is not a secret. Security is provided by Firebase Authentication and Firestore/Storage Security Rules.

Do not put a service-account private key into this frontend project.


## Google Admin Login

The visual editor now supports **Continue with Google** and accepts these admin accounts:

- `eugene.aquila06@gmail.com`
- `yujinybwork@gmail.com`

In Firebase Console:

1. Go to **Authentication → Sign-in method**.
2. Enable **Google**.
3. Add your deployed Vercel domain under **Authentication → Settings → Authorized domains**.
4. Make sure the Google account `eugene.aquila06@gmail.com` is the Firebase user/admin account.
5. Keep the Firestore and Storage rules restricted to the admin UID.

The editor also checks the email client-side before loading the admin interface. The Firebase Security Rules remain the real protection for writes.
