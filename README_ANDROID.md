# Mark LIV - Android Port

This project is a native Android port of the Mark LIV cross-platform assistant, designed using modern Android architecture.

## Architecture

- **Language:** Kotlin
- **UI Toolkit:** Jetpack Compose, Material 3
- **Local Database:** Room Database (used for Memory and Conversation persistence)
- **AI Integration:** Google Generative AI SDK for Android (Gemini Flash 1.5)
- **Audio:** Native Android `SpeechRecognizer` and `TextToSpeech`
- **Security:** `EncryptedSharedPreferences` via AndroidX Security for storing the Gemini API key

## Ported Features

- **Gemini Chat:** Conversational reasoning utilizing native API integration with proper schema mapping (`FunctionType.OBJECT`).
- **Voice & TTS:** Voice input via Speech Recognizer and spoken responses via TTS, visually synced to the UI.
- **Memory Management:** Integrated SQLite memory recall and save using Room database and a native `MemoryTool`.
- **App Launcher:** An intent-driven App Launcher capability using `OpenAppTool` leveraging Android's PackageManager.
- **Tool Registry:** The `ToolRegistry` enforces boundaries and acts as the gatekeeper for Gemini tool usage on Android.
- **Animated Core UI:** A futuristic Jetpack Compose UI pulsing dynamically to listening/speaking states.

## Features Restricted/Replaced

- **Face/Avatar UI:** Replaced with the `AnimatedCore` Jetpack Compose UI component natively.
- **System Control (Power/WiFi/Hardware):** Not implemented to remain within standard unrooted Android capabilities and permissions.
- **Wake Word:** The background PyAudio local wake-word stream was restricted for strict permission safety. Relying on the manual mic button instead.
- **Desktop/Mouse Control:** Completely replaced with standard native intents.

## Build Instructions (Local)

Due to Maven rate limiting in the automated sandbox environment, please compile this project locally using Android Studio.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/AliRahman786/mark-liv-android-jarvis.git
   cd mark-liv-android-jarvis
   git checkout fix-build-tools
   ```
2. **Open in Android Studio:**
   - Launch Android Studio and select "Open".
   - Select the `mark-liv-android-jarvis` directory.
   - Wait for Gradle to sync dependencies locally.

3. **Build the APK:**
   - In Android Studio, go to `Build > Build Bundle(s) / APK(s) > Build APK(s)`.
   - Alternatively, via command-line: `./gradlew assembleDebug`
   - The output will be located at `app/build/outputs/apk/debug/app-debug.apk`.

## Security Measures

- The Gemini API key is stored securely in `EncryptedSharedPreferences`.
- Permissions requested natively: `INTERNET` and `RECORD_AUDIO`.
- A dynamic permission prompt handles microphone access securely before recording starts.
