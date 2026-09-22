# WalkWins

An Android app that turns your daily steps into real rewards. Walk, track your progress, and cash in — steps convert into coins that can be withdrawn or redeemed for gift vouchers.

## Features

- **Step tracking** — reads live step counts off the device pedometer and shows daily progress against a goal (default 3,000, adjustable up to 20,000 via a slider or quick presets), plus a rough calorie estimate.
- **Weekly overview** — a 7-day ring chart on the home screen shows how each day stacks up against your goal, with local caching so it survives app restarts and spotty connections.
- **Coins & earnings** — lifetime steps are converted into an earnings balance using a level-based multiplier, so the longer you stick with it the more each step is worth.
- **Leveling system** — 11 levels from "Beginner Walker" up to "Walking God" based on total lifetime steps, each unlocking a better coin rate, with a level-up modal when you cross a threshold.
- **Boost windows** — steps taken during sunrise (4–7 AM) or sunset (5:30–7 PM) windows earn double, with a badge on the home screen showing when a boost is active.
- **Daily challenges** — join a randomly generated step challenge for a small coin entry fee and earn a payout on completion; can be abandoned early if you change your mind.
- **Watch-to-earn** — short video ads can be watched for coins, with a daily cap and a bonus for hitting it, plus milestone ads that unlock every 3,000 lifetime steps.
- **Leaderboard** — a live daily leaderboard ranks users by steps walked that day, with medal treatment for the top three.
- **Walk map** — GPS-based live location tracking on an embedded Leaflet map, with start/stop trail recording and the ability to screenshot and share your route.
- **Rewards & withdrawals** — redeem earnings for gift vouchers at fixed tiers, or request a cash withdrawal via UPI/phone with a transaction history log.
- **Mood-based music** — a small in-app music player with mood presets (Calm, Happy, Inspire) plus time-of-day options that show up automatically around sunrise and sunset.
- **Referrals** — every user gets a referral code and earns bonus coins for people they bring in.
- **Push notifications** — a Firebase Cloud Function generates personalized motivational nudges (via Gemini) based on a user's progress and goals, sent through FCM.
- **Auth & profile** — email/password login and signup, with an editable daily step goal, referral stats, and account deletion.

## Tech stack

- **React Native 0.79 + Expo SDK 53**, written in TypeScript, using Expo Router for file-based navigation
- **expo-sensors** (Pedometer) for step counting, **expo-location** for GPS tracking
- **react-native-webview** + Leaflet.js for the in-app map
- **Firebase** — Auth, Firestore (user data, daily step records, transactions), Cloud Messaging, and Cloud Functions for the backend
- **Google Gemini API** (via Cloud Functions) for generating notification copy
- **react-native-reanimated**, **react-native-svg**, **expo-linear-gradient**, and **@shopify/react-native-skia** for the animated UI (progress rings, gradients, background effects)
- **AsyncStorage** for offline step caching and recovery
- A native Android Kotlin module (`com.walkwins.stepservice`) scaffolded for a background step-counting foreground service — present in the project but not yet wired up; step tracking currently runs through `expo-sensors`

---

**Ankit Singh**
[LinkedIn](https://www.linkedin.com/in/ankit-singh-117925249/)
