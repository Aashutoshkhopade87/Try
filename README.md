# TezWeb

TezWeb is a React + Vite + TypeScript + Tailwind app for quickly creating small-business websites.

## Local setup

```bash
npm install
npm run dev
```

## Firebase setup (required for real auth + Firestore persistence)

1. Create a Firebase project in [Firebase Console](https://console.firebase.google.com/).
2. Enable **Authentication** providers:
   - Phone
   - Email/Password
3. Enable **Cloud Firestore** in production or test mode.
4. In Firebase project settings, create a Web app and copy config values.
5. Create `.env.local` in project root:

```bash
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your-project-id
VITE_FIREBASE_STORAGE_BUCKET=your-project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=123456789
VITE_FIREBASE_APP_ID=1:123456789:web:abc123
```

6. Add your local origin (`http://localhost:5173`) to Authorized domains in Firebase Auth.
7. Start app: `npm run dev`.

## Firestore collections used

- `users/{uid}`: user profile/session metadata.
- `websites/{websiteId}`: generated websites persisted from local app state.

On first Firestore read for a logged-in user, existing localStorage websites are migrated into Firestore automatically.

## Commands

```bash
npm run dev
npm run build
npm run lint
```
