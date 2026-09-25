1. **Setup Android Project Foundation**:
   - Create a basic Android project structure using Gradle with Kotlin DSL.
   - Use AndroidX, Material 3, and Compose dependencies.
   - Configure Gradle files (settings.gradle.kts, build.gradle.kts, app/build.gradle.kts) and AndroidManifest.xml.
   - Add necessary permissions (Internet, Record Audio, Text-to-Speech).
2. **Setup Keystore and Secure Preferences**:
   - Implement an encrypted shared preferences mechanism using Android `EncryptedSharedPreferences` for secure API Key storage.
3. **Core Data layer (Room & Data classes)**:
   - Setup Room database to persist Conversation History and Memory storage.
   - Create entities, DAOs, and repository.
4. **Implement Gemini Client (Conversational AI + Tools)**:
   - Integrate the official Google Generative AI SDK for Android (if compatible with the needed features, such as function calling). Or make raw HTTP calls if specific streaming or function calling features are required and unsupported by the SDK.
   - Implement `GeminiClient` to handle chat and streaming where possible.
5. **Implement Audio Integration (Voice & TTS)**:
   - Use `SpeechRecognizer` for Voice Input (STT).
   - Use `TextToSpeech` (TTS) for Voice Output.
   - Create abstractions `SpeechRecognizerManager` and `TtsManager`.
6. **Implement Tool Registry and Core Tools**:
   - Create `ToolRegistry` to route function calls from Gemini.
   - Implement Android-safe tools: `open_app`, `web_search`, `save_memory`, `recall_memory`, `search_conversation`.
7. **Build JARVIS UI**:
   - Create modern Compose UI mimicking a futuristic assistant.
   - Implement Main screen (Assistant face/core, conversation list, input field, voice toggle).
   - Implement Settings screen (API key entry, permissions toggle, clear history).
8. **App Permissions & Security Flow**:
   - Ensure dynamic permission requests for RECORD_AUDIO.
   - Handle invalid API keys and display prompts to configure settings.
9. **Pre commit instructions**:
   - Complete pre-commit steps to make sure proper testing, verifications, reviews, and reflections are done.
10. **Build & Verify**:
    - Run the Android build to ensure `app-debug.apk` is generated.
    - Write a Final Report listing capabilities, tools, components, and APK path.
