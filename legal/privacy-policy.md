# Privacy Policy — CodeCourse

**Effective:** August 17, 2025 &nbsp;|&nbsp; **Last Updated:** August 30, 2026 &nbsp;|&nbsp; **App:** CodeCourse (`com.wewithall.codecourse`) &nbsp;|&nbsp; **Developer:** We With All 4 Students

---

## 1. Overview

CodeCourse is built with privacy as a core principle. This Privacy Policy explains what data the app collects, how it's used, and your rights. **In short: we collect no personal data, no analytics, no tracking, and no accounts are required.**

## 2. Data We Collect

### 2.1 Data Stored Locally on Your Device Only

The following data is stored **exclusively on your device** using Android's local storage (DataStore / SharedPreferences / Room database). It never leaves your phone:

- **Course Progress:** Which lessons you've completed, quiz scores, challenge stars earned
- **App Preferences:** Theme (light/dark/system), narration speed, reminder time, notification settings
- **User Profile (Optional):** Display name and avatar for certificates (entered manually, stored locally)
- **Certificates Generated:** PDF/PNG certificates you create (saved to your Downloads or app folder)
- **Streaks & XP:** Local gamification counters
- **Downloaded Content:** Lesson audio (TTS) cached for offline playback

### 2.2 Data We Do NOT Collect

- ❌ No personal identifiers (name, email, phone, contacts)
- ❌ No device identifiers (advertising ID, Android ID, IMEI)
- ❌ No location data (GPS, coarse location, network location)
- ❌ No usage analytics, crash reports, or telemetry
- ❌ No network traffic monitoring
- ❌ No account creation, login, or authentication
- ❌ No third-party SDKs for analytics (Firebase, Amplitude, Mixpanel, etc.)
- ❌ No advertising identifiers or ad networks

## 3. Network Communication

CodeCourse makes **only one optional network call**:

| Feature | Network Call | Data Sent | Purpose |
|---|---|---|---|
| **Code Runner** | HTTPS POST to `https://emkc.org/api/v2/piston/execute` | Code snippet + language + stdin (user-provided only) | Execute code in sandboxed cloud runner |

**Key points about the Code Runner:**

- Only triggered when you explicitly tap "Run Code" in a lesson or challenge
- No metadata, no device info, no user identity sent
- You can use the app 100% offline — all lessons, quizzes, TTS narration, and certificates work without internet
- The Piston API is a public open-source code execution service; see their privacy policy at [github.com/engineer-man/piston](https://github.com/engineer-man/piston)

**No other network requests are made by the app.**

## 4. Permissions

| Permission | Required? | Reason |
|---|---|---|
| `INTERNET` | Yes | Only for optional Code Runner (Piston API) |
| `POST_NOTIFICATIONS` | Yes (Android 13+, runtime) | Daily learning reminder (user-enabled) |
| `ACCESS_NETWORK_STATE` | Yes | Checks for a working connection before attempting the Code Runner network call |
| `FOREGROUND_SERVICE` | Yes | Used by the WorkManager library so the daily reminder can be scheduled and delivered reliably |
| `RECEIVE_BOOT_COMPLETED` | Yes | Re-schedules the daily reminder after the device restarts, if enabled |
| `WAKE_LOCK` | Yes | Used by WorkManager to briefly wake the device to schedule/deliver the reminder |
| `READ_EXTERNAL_STORAGE` / `WRITE_EXTERNAL_STORAGE` | No | Not used (certificates saved via MediaStore) |
| `RECORD_AUDIO` | No | Not used (TTS is local synthesis) |
| `CAMERA` | No | Not used |
| `SCHEDULE_EXACT_ALARM` | No | Not requested — reminder timing uses WorkManager's standard (inexact) scheduling, not exact alarms |

**Only one permission requires your explicit runtime approval: `POST_NOTIFICATIONS`** (Android 13 and above), for the optional daily reminder. All other permissions listed above are "normal" permissions that Android grants automatically at install time and do not prompt you.

## 5. Data Retention & Deletion

- All local data persists until you uninstall the app or clear app data in Android Settings
- You can reset all progress anytime: **Settings → Reset Progress** (deletes local database)
- Certificates you saved to Downloads remain after uninstall (user-owned files)
- No server-side data exists to delete

## 6. Children's Privacy

CodeCourse is designed for learners of all ages, including children under 13. Because we collect **no personal data**, COPPA and GDPR-K do not apply. The app is safe for classroom and home use without parental consent for data collection (since there is none).

## 7. Third-Party Services

| Service | Purpose | Data Shared |
|---|---|---|
| **Piston API** (emkc.org) | Code execution | Only the code you choose to run |
| **Google Play** | App distribution, updates | Standard Play Console data (install country, device model, Android version) — controlled by Google, not us |
| **System TTS** (optional fallback) | Voice narration | None (on-device) |

We do **not** use: Firebase, Google Analytics, Crashlytics, Adjust, AppsFlyer, Meta SDK, Unity Ads, or any other third-party SDK.

## 8. Your Rights

Since we hold no personal data on our servers, there is no "account" to delete or "data" to export from us. Your data lives on your device. You can:

- **View all local data:** Settings → Export Progress (JSON)
- **Delete all local data:** Settings → Reset Progress, or uninstall the app
- **Opt out of reminders:** Turn off "Daily Reminder" in Settings
- **Use fully offline:** Disable internet for the app via Android Settings → Apps → CodeCourse → Data usage → Background data / Unrestricted data

## 9. Security

- All local storage uses Android's sandboxed storage (no world-readable files)
- Network call (Code Runner) uses HTTPS with certificate pinning not required (public API)
- No encryption keys stored — no sensitive data to encrypt
- App is not debuggable in release builds (`android:debuggable="false"`)

## 10. International Transfers

No data leaves your device except the optional Code Runner call to Piston API (hosted in the US). If you are in the EU/UK/India, you may disable the Code Runner by using the app offline.

## 11. Changes to This Policy

We may update this policy for:

- New app features (e.g., if we add cloud sync in future — **opt-in only**)
- Legal requirement changes
- Clarity improvements

Updates will be posted in the app (Settings → Legal → Privacy Policy) and the `CHANGELOG.md` in the app repository. Continued use after changes constitutes acceptance.

> **August 30, 2026 revision:** corrected the Permissions table (Section 4) to accurately reflect `ACCESS_NETWORK_STATE`, `FOREGROUND_SERVICE`, `RECEIVE_BOOT_COMPLETED`, and `WAKE_LOCK`, which are declared and used to support the daily reminder feature via WorkManager; removed `SCHEDULE_EXACT_ALARM`, which is not requested; and added the in-app support phone number to Section 12. Verified against app build v1.3.1 (versionCode 14).

## 12. Contact

**We With All 4 Students**

- 📧 privacy@wewithall.com
- 📞 8792381530
- 🌐 [https://wewithall.com](https://wewithall.com)
- 📱 Instagram: [@wewithall4ever](https://instagram.com/wewithall4ever)

For data protection inquiries, email **privacy@wewithall.com** with subject "Privacy Policy — CodeCourse".

## 13. Summary (TL;DR)

| Question | Answer |
|---|---|
| Do you collect my personal info? | **No** |
| Do you track me? | **No** |
| Do I need an account? | **No** |
| Does the app work offline? | **Yes, 100%** |
| Is my data sold? | **No — we have none to sell** |
| Can I delete my data? | **Yes — uninstall or Settings → Reset Progress** |
| Is it safe for kids? | **Yes — no data collection at all** |

*This policy is written in plain language, not legalese. If something is unclear, email us.*

---

CodeCourse by **We With All 4 Students** &nbsp;|&nbsp; 📧 privacy@wewithall.com &nbsp;|&nbsp; 📞 8792381530 &nbsp;|&nbsp; 🌐 [wewithall.com](https://wewithall.com) &nbsp;|&nbsp; 📱 [@wewithall4ever](https://instagram.com/wewithall4ever)

*Last updated: August 30, 2026*
