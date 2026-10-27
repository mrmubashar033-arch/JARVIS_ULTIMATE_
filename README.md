# JARVIS ULTIMATE — MASTER ENGINEERING PROMPT

## PROJECT
Upgrade my existing Android application into JARVIS ULTIMATE, an advanced personal AI voice assistant inspired by JARVIS and ChatGPT.

## 1. CRITICAL INSTRUCTIONS
Act as a senior Android engineer, Kotlin developer, AI architect, Android automation specialist, security engineer, and build engineer.

- Work directly inside my existing GitHub repository.
- Do not create a new project or replace the existing application.
- Inspect the source files, package names, Gradle configuration, Android SDK versions, dependencies, database schema, UI, permissions, and GitHub Actions workflow before making changes.
- Preserve the app identity and all working features.
- Make compatible, incremental changes. Do not delete working code unnecessarily.
- Implement real functionality in source files, not just a tutorial, mock-up, or pseudocode.
- Never claim a feature works unless the code and relevant tests support that claim.
- If a requirement is blocked by Android restrictions, missing credentials, hardware, or unavailable services, explain the limitation and implement a legitimate fallback.

## 2. ANDROID TECHNOLOGY
Prefer the existing compatible toolchain. Use Kotlin, AndroidX, Jetpack Compose where compatible, MVVM or clean architecture, Room, DataStore, coroutines, Flow, Android SpeechRecognizer, Android TextToSpeech, WorkManager, eligible foreground services, and GitHub Actions.

Do not upgrade Gradle, Kotlin, Android Gradle Plugin, SDK versions, or major dependencies without checking compatibility.

## 3. JARVIS AI BRAIN
Implement an assistant that answers questions naturally, solves calculations, translates, summarizes, writes, plans, and helps with daily tasks. Maintain conversational context from available history, handle follow-up questions, avoid repeating introductions or “System fully ready” after every message, admit uncertainty, and handle timeouts and network errors gracefully.

Support:
- An offline rules-based provider for basic commands.
- Optional local language models when compatible with the device.
- Optional online AI providers with secure user configuration.

Do not pretend a rules-based engine has full ChatGPT-level intelligence. Do not require a paid API just to build the app. Clearly distinguish offline features from those requiring a network or credentials. Never embed private API keys in source code, assets, Git history, or the APK.

## 4. VOICE CONVERSATION
Implement a voice-session state machine with IDLE, LISTENING, PROCESSING, SPEAKING, WAITING_FOR_FOLLOW_UP, PAUSED, and ERROR states.

- Start through a microphone button or a supported wake-word implementation.
- Support back-and-forth conversation without requiring the wake phrase before every sentence.
- Process recognized speech and speak responses through TextToSpeech.
- Resume listening after speaking only when continuous conversation is enabled and the user has not stopped or paused.
- Provide an obvious stop button.
- Handle silence, recognition errors, audio focus, microphone permission denial, and unavailable speech services.
- Prevent duplicate responses and overlapping recognition sessions.
- Display clear listening, thinking, speaking, and paused indicators.
- Support English, Urdu, Roman Urdu, and Hindi where the selected engines allow. Respond in the user's language when detection is reliable.
- Offer language and voice settings, including an available female voice when supported.
- Do not misrepresent ordinary speech recognition as always-on wake-word detection.

## 5. ANDROID PHONE ACTIONS
Implement validated tools for supported actions such as opening apps through intents, opening permitted Settings pages, adjusting volume, controlling the flashlight where supported, controlling media, creating notes, tasks, and reminders, and reporting capability and permission status.

Check hardware, Android version, permissions, and user authorization. Return structured success or failure results. Never claim an action succeeded when it failed. Do not bypass Android security, protected dialogs, lock-screen protections, or app sandboxing.

## 6. ACCESSIBILITY AND SCREEN-OFF BEHAVIOR
Accessibility automation must be optional and explicitly enabled by the user through Android Settings. Explain sensitive permissions. Do not secretly monitor screens, collect credentials, or bypass security protections.

Implement background voice behavior only where permitted by the Android version and system policies. Use the appropriate foreground service, notification, and permissions when required. Explain restrictions on background microphone access and screen wake behavior. Do not promise uninterrupted screen-off listening without verification.

## 7. MESSAGING AND CALLS
Use supported Android APIs, intents, or official integrations.

For WhatsApp or other messaging apps:
1. Identify the recipient unambiguously.
2. Clarify when multiple contacts match.
3. Prepare the exact message.
4. Show or speak the recipient and message and request confirmation before sending.
5. Use supported handoff or integration.
6. Report whether the message was prepared, handed off, or reliably confirmed sent.

Do not claim a message was sent merely because another app opened. Do not silently message contacts or place calls without authorization.

## 8. MEMORY AND HISTORY
Use Room or the existing database architecture for conversation history, timestamps, saved preferences, notes, tasks, and reminders. Add search where practical. Provide controls to view, delete, disable, and clear stored information. Respect deletion and disablement. Do not store passwords, private API keys, or unnecessary sensitive data. Add proper database migrations and preserve existing user data.

## 9. PRODUCTIVITY AND RESEARCH
Implement persistent notes, checklists, tasks, due dates, reminders, and notifications using suitable Android scheduling APIs. Account for notification permissions, battery restrictions, reboot behavior, and exact-alarm restrictions. Do not claim a reminder was scheduled unless the operation succeeds.

Provide optional web research through a configured legitimate provider. Summarize sources, retain source URLs, distinguish evidence from inference, and report unavailable providers honestly. Do not invent search results or claim live research when no provider is configured.

## 10. UI
Preserve the existing design where practical. Improve it with a polished futuristic JARVIS-inspired interface: dark theme, subtle blue accents, animated orb or equivalent, prominent microphone, clear voice states, readable chat, conversation history, language and provider settings, privacy and permission controls, continuous-conversation toggle, and an obvious stop button. Keep it responsive and accessible, including on lower-end devices.

## 11. SECURITY
- Request permissions only when needed and explain their purpose.
- Never secretly record audio.
- Do not upload audio, contacts, messages, or conversations without the relevant feature, disclosure, and authorization.
- Never expose secrets in logs.
- Use HTTPS.
- Validate AI-generated tool requests against a strict allowlist.
- Require confirmation for sensitive, irreversible, financial, communication, or privacy-impacting actions.
- Treat AI output as untrusted input.
- Fail safely when permissions are denied.

## 12. ARCHITECTURE
Inspect the existing architecture and reuse compatible components. Create or improve components as appropriate, such as AssistantViewModel, ConversationRepository, VoiceSessionManager, SpeechRecognitionManager, TextToSpeechManager, AIProvider, OfflineAIProvider, OptionalOnlineAIProvider, ToolDefinition, ToolRequest, ToolExecutor, ToolResult, AndroidActionDispatcher, PermissionManager, MemoryRepository, ReminderRepository, and CapabilityChecker.

Do not duplicate existing classes unnecessarily. Keep UI, business logic, data persistence, AI providers, and platform actions separate. Use typed models, lifecycle-aware coroutines, and structured logging without secrets.

## 13. TESTING AND GITHUB ACTIONS
Inspect and update the existing workflow instead of creating duplicate workflows unnecessarily.

- Check out the repository.
- Set up a compatible JDK.
- Configure Gradle caching where appropriate.
- Run available unit tests and static analysis.
- Build the debug APK.
- Verify that the APK exists and is nonzero in size.
- Upload the APK using a supported GitHub Actions artifact-upload action.
- Report failures clearly.

Test voice state transitions, duplicate recognition prevention, provider errors, tool validation, database persistence and migrations, permission denial, reminders, and action results. Mark device-only checks as requiring real-device verification. Never claim skipped or failed tests passed.

## 14. IMPLEMENTATION ORDER
1. Inspect the repository and summarize the existing app.
2. Establish a working baseline build.
3. Preserve app identity and working features.
4. Stabilize architecture, data models, and migrations.
5. Implement conversation handling and offline commands.
6. Implement voice sessions and TextToSpeech.
7. Add optional AI providers and secure configuration.
8. Add authorized Android tools.
9. Add memory, notes, tasks, reminders, and research where supported.
10. Add optional messaging and accessibility workflows.
11. Complete tests, static analysis, APK build, and artifact upload.
12. Report completed features, limitations, changed files, test results, and APK location.

Do not stop at writing a plan when repository editing and build tools are available. Implement and validate changes.

## 15. FINAL ACCEPTANCE CRITERIA
- The existing Android project remains intact.
- Changes are implemented in actual source files.
- The project builds successfully, or the exact blocking error is reported.
- The debug APK is produced and uploaded when the build succeeds.
- Offline capabilities are genuine and accurately described.
- Voice interaction matches verified device capabilities.
- Tool execution is validated and reports truthful results.
- Sensitive actions have appropriate authorization.
- Database upgrades preserve user data.
- No private credentials are committed or embedded in the APK.
- Unsupported features and real-device testing requirements are documented.

## FINAL COMMAND
Inspect and upgrade my existing GitHub Android repository into JARVIS ULTIMATE. Make minimal, compatible, production-minded changes. Implement real functionality instead of mock responses. Preserve existing features. Test the changes, build the APK using GitHub Actions, upload the APK artifact, and provide an honest implementation and validation report. Do not invent completed features, successful tests, or build results.
