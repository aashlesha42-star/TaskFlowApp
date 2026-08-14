# TaskFlow — Modern To-Do List App

A professional, production-ready to-do list application built with **React Native + Expo**. Features a premium UI inspired by Notion, Todoist, and Microsoft To Do.

## Features

### Authentication
- Email & password sign up / login
- Google Sign-In (demo mode)
- Forgot password flow
- Protected dashboard routes
- User profile with avatar

### Tasks
- Create, edit, delete, duplicate tasks
- Mark complete / incomplete
- Pin important tasks
- Archive & restore
- Undo delete
- Priority levels (Low / Medium / High)
- Categories, tags, due dates & times
- Reminders
- Custom ordering

### Dashboard
- Welcome message with live date/time
- Stats: total, completed, pending, completion %, overdue, due today
- Weekly productivity chart
- Daily / weekly / monthly goal progress
- Streak counter & productivity score

### Search & Filters
- Live search across title, description, tags
- Filter by status, priority, category
- Sort by date, priority, alphabetical, custom order

### Calendar
- Month view with task indicators
- Day detail with task list

### Settings
- Light / Dark / System theme
- Profile editing (name, photo, password)
- Custom categories
- Goal configuration
- Notifications toggle
- Export CSV / Report
- Import CSV
- Backup & restore
- Download all data
- Delete account

### Extra
- Offline-first (AsyncStorage)
- Empty states & loading skeletons
- Smooth animations (Reanimated)
- Fully responsive mobile layout
- Keyboard shortcuts friendly forms

## Tech Stack

- React Native + Expo (SDK 52+)
- TypeScript
- React Navigation (Stack + Bottom Tabs)
- AsyncStorage (local persistence)
- React Native Reanimated
- date-fns
- Expo Vector Icons

## Project Structure

```
├── App.tsx
├── components/
│   ├── dashboard/     # Stat cards, charts, goals
│   ├── tasks/         # Task items, form, filters
│   └── ui/            # Button, Input, Card, Avatar, etc.
├── constants/         # Theme colors, default categories
├── context/           # Auth, Theme, Task providers
├── navigation/        # Navigators & types
├── screens/           # All app screens
├── types/             # TypeScript interfaces
└── utils/             # Helpers & storage
```

## Getting Started

```bash
# Install dependencies
npm install

# Start Expo
npm start

# Web
npm run web

# iOS / Android
npm run ios
npm run android
```

## Demo Login

1. Tap **Get Started** and create an account, or
2. Use **Continue with Google** for instant demo access

## Firebase Configuration (Optional Upgrade)

This app uses local AsyncStorage for full offline functionality. To connect Firebase:

1. Create a Firebase project at https://console.firebase.google.com
2. Enable Email/Password + Google auth
3. Create a Firestore database
4. Add your config to `firebase/config.ts`:

```ts
import { initializeApp } from 'firebase/app';
import { getAuth } from 'firebase/auth';
import { getFirestore } from 'firebase/firestore';

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID",
};

export const app = initializeApp(firebaseConfig);
export const auth = getAuth(app);
export const db = getFirestore(app);
```

5. Replace AuthContext / TaskContext storage calls with Firebase SDK methods.

## Deployment

### Vercel (Web)

```bash
npx expo export --platform all
# Deploy dist/ folder to Vercel
```

### Firebase Hosting

```bash
npx expo export --platform web
firebase init hosting  # set public directory to dist
firebase deploy
```

### EAS Build (Native)

```bash
npx eas build --platform all
```

## License

MIT
