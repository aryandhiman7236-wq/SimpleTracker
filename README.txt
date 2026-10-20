HABITLY — FIXED FIREBASE LOGIN VERSION

Files required in the same folder:
- index.html
- style.css
- configure.js
- app.js

Fix applied:
- configure.js now assigns window.firebaseConfig, which app.js reads.
- This fixes the duplicate top-level `const firebaseConfig` syntax error and lets the auth screen initialize.

Firebase setup:
1. Firebase Console > Authentication > Sign-in method > enable Email/Password.
2. Firebase Console > Authentication > Settings > Authorized domains: ensure localhost or your hosting domain is listed.
3. Open the folder with a local web server (VS Code Live Server is fine), or deploy to Firebase Hosting/GitHub Pages. Avoid opening index.html directly with file:// for testing Firebase Auth.
4. Sign up once, then sign in with that account.

Login persistence:
Firebase's default browser persistence is LOCAL. Once signed in, refreshing/reopening the app keeps the user signed in until they log out (or clear browser site data). The login/signup screen appears when signed out. This is intentional and matches the requested “stay logged in until logout” behavior.

Data note:
Habit tracking is currently stored in this browser's localStorage. Firebase Auth authenticates users, but this version does not yet sync habit data to Firestore.
