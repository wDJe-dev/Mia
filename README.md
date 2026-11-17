# Mia — improved Android project

This is an upgraded version of the supplied Mia app, prepared for Android packaging with Capacitor.

## Improvements
- Android-native speech-recognition and text-to-speech bridges, with browser fallback.
- Conversation history is saved locally and restored after reopening.
- New Chat clears the transcript while keeping saved memories.
- Settings includes an AI connection test.
- Clearer connection and microphone status, accessibility improvements, and Android metadata.
- Practice trading remains simulated only; it cannot place real orders.

## Build APK locally
Requires Node.js, Java 17, Android Studio and Android SDK.

```bash
npm install
npm run build
npx cap add android
npx cap sync android
```

Open the generated `android/` folder in Android Studio and select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.

## Build APK using GitHub Actions
Push this project to a GitHub repository. The included `.github/workflows/android-apk.yml` workflow builds a debug APK on push or manual dispatch. Download `mia-debug-apk` from the workflow run's Artifacts section.

## First launch
Open Settings, paste your own Groq API key, and select **Test AI connection**. The key is stored locally and sent to Groq for AI requests. Do not share a device profile with your key entered.

## Notes
- Voice recognition requires microphone permission and an Android speech service.
- The included APK workflow produces a debug build for testing. Sign a release build with your own key before distribution.
- The trading tab is paper-trading simulation only, not investment advice or real trading.
