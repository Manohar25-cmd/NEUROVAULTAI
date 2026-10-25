<div align="center">

# 🧠 NeuroVault AI

**Your Intelligent On-Device Companion for Health, Deep Focus & Cognitive Life Optimization**

[![Version](https://img.shields.io/badge/Version-1.1.3_(Build_15)-7c3aed?style=for-the-badge&logo=android)](https://github.com/Manohar630/NEUROVAULTAI)
[![Android](https://img.shields.io/badge/Platform-Android_6.0+_(API_23--35)-34d399?style=for-the-badge&logo=android)](https://github.com/Manohar630/NEUROVAULTAI)
[![React](https://img.shields.io/badge/React-19.2-61dafb?style=for-the-badge&logo=react)](https://react.dev)
[![Capacitor](https://img.shields.io/badge/Capacitor-8.5-119EFF?style=for-the-badge&logo=capacitor)](https://capacitorjs.com)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.3-38bdf8?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com)
[![Privacy](https://img.shields.io/badge/Privacy-100%25_Offline_/_Zero_Cloud-fbbf24?style=for-the-badge&logo=shield)](https://github.com/Manohar630/NEUROVAULTAI)
[![License](https://img.shields.io/badge/License-MIT-gray?style=for-the-badge)](LICENSE)

<br/>

> **Zero Cloud Telemetry. No Accounts. No Server Subscriptions.**  
> All biometric metrics, app activity, and personal habits remain encrypted and strictly stored on your physical device.

<br/>

</div>

---

## 📖 Table of Contents

- [✨ Overview](#-overview)
- [🌟 Key Pillars \& Feature Matrix](#-key-pillars--feature-matrix)
- [🏗️ System Architecture](#️-system-architecture)
- [🔐 Privacy, Security \& Data Safety](#-privacy-security--data-safety)
- [📱 Android Permissions Reference](#-android-permissions-reference)
- [📁 Project Structure](#-project-structure)
- [🚀 Quickstart \& Developer Setup](#-quickstart--developer-setup)
- [🧪 Testing \& Quality Gates](#-testing--quality-gates)
- [📦 Build \& Release Pipeline](#-build--release-pipeline)
- [🛡️ Git Safety Checklist](#️-git-safety-checklist)
- [👨‍💻 Author \& Credits](#-author--credits)

---

## ✨ Overview

**NeuroVault AI** is a state-of-the-art personal wellness and cognitive productivity hub engineered for Android. Built with **React 19**, **TypeScript**, **Capacitor 8**, and an ultra-lean native Java background service, it bridges raw device sensors directly to rich local dashboards without external cloud dependencies.

Traditional wellness apps monetize your biometric logs and upload sensitive app usage telemetry to remote cloud servers. **NeuroVault AI is 100% local-first**:
- Computes your holistic daily health index (**NeuroScore™**) directly on device.
- Leverages Android's hardware step sensor and accelerometer fallback with peak detection.
- Passively detects circadian sleep cycles using pure `UsageStatsManager` inactivity gap heuristics (zero battery drain).
- Enforces deep work focus through native app overlay blocking for 200+ distraction apps.
- Persists data across app uninstalls via native `NvStorage` (Android SharedPreferences) mirror.

---

## 🌟 Key Pillars & Feature Matrix

### 1. 🧠 Cognitive & Wellness Index (NeuroScore™)
- **Composite NeuroScore Algorithm:** Multi-factor daily score (0–100) balanced across Sleep (25%), Steps (25%), Focus (20%), Hydration (15%), and Screen Time (15%).
- **Academic Grading:** Instant A+, A, B, C, D, or F wellness score tier with visual color indicators.
- **5-Axis Radar Chart:** Interactive SVG spider chart visualizing daily wellness balance across all 5 dimensions.
- **90-Day Calendar Heatmap:** Tri-state interactive activity grid (NeuroScore, Steps, Sleep) displaying long-term habit consistency.
- **Pearson Correlation Engine:** Computes automated on-device statistical correlations (e.g., *“High screen time correlates with 28% lower sleep score”*).
- **Predictive Energy & Bedtime Insights:** Circadian prediction curve indicating expected afternoon slumps, focus momentum, and bedtime fatigue.

### 2. 🚶 Physical Activity & Hardware Sensor Tracking
- **Hardware Step Counter:** Direct hook into Android's low-power hardware step counter (`Sensor.TYPE_STEP_COUNTER`).
- **Accelerometer Fallback Engine:** Linear acceleration analysis with peak detection when step sensor hardware is busy.
- **Wearable Deduplication Multiplier:** Configurable 1.0x–3.0x step multiplier to eliminate duplicate counts from Wear OS devices.
- **10-Step Walk Calibration:** Interactive calibration wizard to fine-tune personal stride length and accelerometer sensitivity.
- **GPS Speed Suppression:** Optional vehicle motion filter to eliminate false steps recorded while driving or riding transit.

### 3. 🌙 Zero-Sensor Circadian Sleep Detection
- **Schedule-Based Gap Analysis:** Calculates sleep by inspecting `UsageStatsManager` inactivity gaps ($\ge 4$ hours) strictly within the user's configured bedtime window.
- **Zero Sensor Overhead:** No active microphones, no battery-draining accelerometer loops, and no SQLite bloat.
- **Sleep Quality Score:** 0–100 score analyzing sleep duration against configured target, schedule regularity, and pre-sleep screen activity.
- **Bedtime Countdown:** Live dashboard countdown badge alerting users as their optimal bedtime window approaches.

### 4. ⏱️ Deep Work & Focus Engine
- **Configurable Pomodoro Timer:** 25/5 Classic, 50/10 Ultra, or customizable sessions ranging from 5 to 120 minutes.
- **Wall-Clock Resilience:** Focus session timing persists seamlessly even if the app process is terminated by Android battery optimizations.
- **Native Distraction Blocker:** Full-screen purple Zen Mode overlay that locks out distracting apps during active sessions (with phone call exemptions).
- **200+ App Categorizer:** Instant classification of top global and Indian apps (Social, Games, Entertainment, Productivity, Utility).
- **Focus Streak Counter:** Dedicated streak tracking that rewards consecutive days of deep focus work.

### 5. 🧘 Mindful Habits & Daily Wellness
- **5 Evidence-Based Breathing Exercises:**
  - *Box Breathing (4-4-4-4)*: Navy SEAL focus and stress reset.
  - *4-7-8 Relax*: Rapid parasympathetic nervous system activation for sleep prep.
  - *Physiological Sigh (2-1-4)*: Dual-inhalation acute anxiety reduction.
  - *Square Breathing*: Balanced autonomic regulation.
  - *5-5-10 De-stress*: Extended exhale for deep relaxation.
- **Hydration Tracker:** Interactive 8-glass water grid with one-tap logging, haptic feedback, and hydration reminders.
- **Mood & Energy Check-in:** 5-tier emoji mood logging with 14-day overlay charts against sleep and focus metrics.
- **Goals & Task Management:** Priority-sorted task lists, deadlines, overdue notifications, and confetti celebrations upon completion.

### 6. 🎙️ On-Device AI Voice Agent
- **Native Speech Recognition:** Built on `@capacitor-community/speech-recognition` with real-time partial transcription.
- **Zero-Cloud Intent Parsing:** Rule-based natural language intent engine that resolves queries locally (e.g., *"How is my sleep today?"*, *"Log 2 glasses of water"*, *"Start focus timer"*).
- **Voice-Guided Navigation:** Voice commands seamlessly route you directly to Stats, Tasks, Focus, or Settings.

### 7. 🎮 Gamification, Quests & Living Themes
- **20-Level XP Progression:** Earn XP for every logged glass of water, completed focus sprint, and achieved sleep target.
- **5 Daily Quests:** Fresh daily challenges with claimable rewards to cultivate balanced daily routines.
- **12 Unlockable Achievement Badges:** High-resolution badges (First Step, 10K Walker, Sleep Hero, Focus Master, etc.) with shareable social cards.
- **9 Handcrafted Color Schemes:**
  - 🟣 Violet Dream (Default Cosmic)
  - 🔵 Ocean Blue
  - 🟢 Emerald Vitality
  - 🌸 Rose Gold
  - 🟡 Warm Amber
  - 🌌 Cosmic Deep Space
  - 📟 Matrix Green
  - ☀️ Solaris Neon
  - 💖 Cyberpink

---

## 🏗️ System Architecture

```
┌────────────────────────────────────────────────────────────────────────┐
│                        USER HARDWARE (ANDROID)                         │
│  Hardware Step Sensor • Accelerometer • UsageStats • Location (Speed)   │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   ANDROID NATIVE SERVICE LAYER (JAVA)                  │
│                                                                        │
│   TrackingService.java (Foreground Service — 60s background cycle)      │
│   ├── Step Counter + Linear Peak Detection Fallback                    │
│   ├── Circadian Sleep Gap Analysis (UsageStatsManager >= 4h gap)       │
│   ├── Vehicle Motion Filter (Speed Threshold > 25 km/h)                │
│   ├── App Blocker Window (SYSTEM_ALERT_WINDOW Focus Overlay)           │
│   └── BootReceiver.java (Auto-resumes service on device reboot)        │
│                                                                        │
│   NvStorage.java (Native SharedPreferences Key-Value Mirror)           │
│   NeuroWidget.java (Android Lock Screen & Home Screen Widget)          │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
                          Capacitor 8 Bridge
                (NeuroTrackerPlugin.java / NvStoragePlugin.java)
                                   │
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     FRONTEND APPLICATION (REACT 19)                    │
│                                                                        │
│   App.tsx (Screen State Machine & Route Orchestration)                 │
│   ├── useAppInitialization.ts (3-Second Polling & Sync Orchestrator)   │
│   ├── storage.ts (Local Storage CRUD + NvStorage Native Sync)          │
│   ├── aiEngine.ts (NeuroScore Formula, Correlations & Predictions)     │
│   ├── themeEngine.ts (Dynamic CSS Custom Property Variable Injection)   │
│   └── Zustand Store (Reactive Global UI State)                         │
│                                                                        │
│   UI Components: Framer Motion 13 • Tailwind CSS v4 • Lucide Icons     │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 🔐 Privacy, Security & Data Safety

NeuroVault AI was architected from line one with an uncompromising **local-first privacy pledge**:

1. **Zero External Data Transmission:** No personal data, biometric info, health metrics, or application usage statistics ever leave your handset.
2. **No Accounts or Identification:** You are never asked to register, log in, or provide phone numbers or OAuth credentials.
3. **Google Play Store Data Safety Compliance:**
   - **Data Collection:** **NO** (Google Play defines collection as transmitting data off the device).
   - **Data Sharing:** **NO**.
   - **Network Usage:** The `INTERNET` permission is required strictly by the Capacitor WebView runtime to render internal assets.
4. **Storage Quota & Auto-Pruning:**
   - Daily logs older than 90 days are automatically pruned to keep total storage well under the 5MB browser budget.
   - AI voice chat logs older than 500 messages are pruned automatically.
5. **Data Portability:**
   - One-tap export to structured **CSV** (7-day or 30-day).
   - One-tap export to formatted **A4 PDF Wellness Reports** via `jsPDF`.
   - Complete local backup and restore.

---

## 📱 Android Permissions Reference

| Permission | Category | Purpose | User Disclosure |
|---|---|---|---|
| `PACKAGE_USAGE_STATS` | Special Access | Measures real screen time and categorizes app usage | User is redirected to system settings with visual guide |
| `ACTIVITY_RECOGNITION` | Runtime | Accesses hardware step counter and physical motion | In-app prompt upon enabling step tracking |
| `FOREGROUND_SERVICE` | Normal | Maintains continuous background step and sleep tracking | Persistent notification showing live step status |
| `FOREGROUND_SERVICE_HEALTH` | Android 14+ | Official Android declaration for health/step sensor sync | Explicit declaration in Play Store submission |
| `FOREGROUND_SERVICE_SPECIAL_USE` | Android 14+ | Distraction blocking overlay during active focus sprints | Declared in manifest with video demo rationale |
| `SYSTEM_ALERT_WINDOW` | Special Access | Renders the purple Zen Mode focus overlay on blocked apps | Explicit toggle with direct settings shortcut |
| `POST_NOTIFICATIONS` | Runtime | Daily morning briefing, hydration pings, and bedtime alert | Prompts on onboarding |
| `SCHEDULE_EXACT_ALARM` | Special Access | Triggers timely bedtime and morning briefing notifications | Graceful fallback if exact alarms are disabled |
| `RECORD_AUDIO` | Runtime | Enables hands-free AI voice queries | Microphone access used strictly while mic button is pressed |
| `RECEIVE_BOOT_COMPLETED` | Normal | Restarts tracking service after device power cycle | Runs silently on boot |

---

## 📁 Project Structure

```
NEUROVAULTAI/
├── android/                             # Android Studio native project
│   ├── app/
│   │   ├── src/main/AndroidManifest.xml # Permissions & service declarations
│   │   └── src/main/java/com/neurovault/app/
│   │       ├── MainActivity.java        # Capacitor bridge initialization
│   │       ├── TrackingService.java     # Persistent foreground tracking engine
│   │       ├── NeuroTrackerPlugin.java  # 42 Capacitor-to-Java bridge methods
│   │       ├── NvStoragePlugin.java     # Native SharedPreferences bridge
│   │       ├── ScreenReceiver.java      # BroadcastReceiver for display on/off
│   │       ├── ActivityRecognitionReceiver.java # Motion classifier
│   │       ├── BootReceiver.java        # Reboot auto-start receiver
│   │       └── NeuroWidget.java         # Home screen and lock screen widget
│   └── build.gradle                     # Android Gradle build configuration
├── public/                              # Static public assets & icons
├── src/                                 # React 19 application source
│   ├── assets/                          # App logos & branding graphics
│   ├── components/                      # Reusable UI components
│   │   ├── BottomNav.tsx                # Dynamic themed 5-tab navigation bar
│   │   ├── CalendarHeatmap.tsx          # 90-day interactive habits grid
│   │   ├── PredictiveInsightsCard.tsx   # Energy, focus & fatigue forecasts
│   │   ├── RadarChart.tsx               # 5-axis SVG Spider Radar visualization
│   │   ├── ShareCard.tsx                # Native progress image generator (html2canvas)
│   │   ├── SleepScoreCard.tsx           # Sleep ring with sub-score breakdowns
│   │   └── ThemeSelector.tsx            # 9-theme bottom-sheet picker
│   ├── hooks/                           # Custom React hooks
│   │   ├── useAppInitialization.ts      # Native sync, polling & quota pruning
│   │   └── useTracking.ts               # LiveData sensor hook with web demo mode
│   ├── plugins/                         # TypeScript interfaces for Capacitor
│   │   ├── NeuroTracker.ts              # Bridge method definitions
│   │   └── NvStorage.ts                 # Storage mirror definitions
│   ├── screens/                         # Top-level screen views
│   │   ├── HomeScreen.tsx               # Live NeuroScore ring, quests, daily summary
│   │   ├── StatsScreen.tsx              # Deep analytics, trends, correlations, radar
│   │   ├── FocusScreen.tsx              # Pomodoro timer, Zen overlay, streak tracking
│   │   ├── TasksScreen.tsx              # Priority task manager with tap-to-focus
│   │   ├── GoalsScreen.tsx              # Long-term habit milestones & celebrations
│   │   ├── BreathingScreen.tsx          # 5 guided breathwork animations
│   │   ├── AgentScreen.tsx              # Hands-free AI voice assistant
│   │   └── ProfileScreen.tsx            # CSV/PDF export, themes, data manager
│   ├── utils/                           # Pure computational utilities
│   │   ├── aiEngine.ts                  # NeuroScore calculation & Pearson math
│   │   ├── appCategorizer.ts            # 200+ app regex categorization
│   │   ├── csvExport.ts                 # CSV formatting utility
│   │   ├── pdfExport.ts                 # jsPDF A4 report generator
│   │   ├── sleepScore.ts                # Circadian sleep scoring model
│   │   ├── storage.ts                   # LocalStorage CRUD & native synchronization
│   │   └── themeEngine.ts               # CSS variable injector
│   ├── App.tsx                          # Root router & screen state coordinator
│   └── main.tsx                         # Entry point & theme initializer
├── scripts/                             # Build, verification & screenshot scripts
│   ├── freshness-gate.cjs               # Automated build artifact freshness validator
│   ├── generate-feature-graphic.cjs     # 1024x500 Play Store feature graphic creator
│   └── run-gradle.cjs                   # Cross-platform Gradle wrapper orchestrator
├── tests/                               # Test suites
│   ├── app.spec.ts                      # Playwright E2E smoke tests
│   ├── navigation.spec.ts               # Playwright multi-screen navigation tests
│   └── crash-hardening.spec.ts          # Playwright recovery & stress tests
├── capacitor.config.ts                  # Capacitor framework configuration
├── vite.config.ts                       # Vite 8 bundling & Tailwind integration
└── package.json                         # Dependencies and build scripts
```

---

## 🚀 Quickstart & Developer Setup

### Prerequisites
- **Node.js**: `20.x` or higher (LTS recommended)
- **Java Development Kit (JDK)**: `17` or higher
- **Android Studio**: Ladybug / Hedgehog or newer with Android SDK Platform 34/35
- **Git**

### 1. Clone & Install Dependencies
```bash
git clone https://github.com/Manohar630/NEUROVAULTAI.git
cd NEUROVAULTAI
npm install
```

### 2. Run Local Web Dev Server
Experience the complete frontend with simulated sensor data in your browser:
```bash
npm run dev
```
Open [http://localhost:5173](http://localhost:5173) in your browser.

### 3. Type Checking & Code Quality
```bash
# Validate strict TypeScript types without emitting code
npm run typecheck

# Run ESLint validation
npm run lint
```

---

## 🧪 Testing & Quality Gates

NeuroVault AI features a multi-tiered testing suite to guarantee stability before production builds:

### Run Unit Tests (Vitest)
Executes mathematical verification of the NeuroScore algorithm, circadian gap calculations, and XP rewards:
```bash
npm run test:unit
```

### Run End-to-End Tests (Playwright)
Executes automated browser tests across desktop and mobile form factors (iPhone SE, Pixel, 1080p):
```bash
npm run test
```

Interactive Playwright UI mode:
```bash
npm run test:ui
```

---

## 📦 Build & Release Pipeline

The repository includes custom automation scripts to ensure that Android builds never bundle stale JavaScript assets.

### Build Android Debug APK
Compiles the web bundle, syncs Capacitor, and generates an installable debug APK:
```bash
npm run build:android
```

Install directly onto a connected physical Android device or emulator via ADB:
```bash
npm run adb:install
```

### Build Production Release Android App Bundle (AAB)
Compiles an optimized bundle ready for upload to Google Play Console:
```bash
npm run build:release
```
Artifact generated at:  
`android/app/build/outputs/bundle/release/app-release.aab`

### Build Production Release Standalone APK
```bash
npm run build:apk
```
Artifact generated at:  
`android/app/build/outputs/apk/release/app-release.apk`

---

## 🛡️ Git Safety Checklist

To protect developer keys and sensitive information when pushing updates to GitHub, follow these standard practices:

- [x] **Keystore & Signatures:** `release.keystore`, `*.jks`, and `key.properties` are listed in `.gitignore` and **must never** be forced into git (`git add -f`).
- [x] **Credentials & Secrets:** Plaintext passwords and credential PDF generators are excluded from git.
- [x] **Tester PII:** Tester email lists (`testers.csv`) are strictly ignored.
- [x] **Large Binary Archives:** Backup zip archives (`*.zip`) and build outputs (`dist/`, `build/`, `.apk`, `.aab`) are excluded to keep git repositories clean and fast.

### Recommended Safe Push Commands
```bash
# 1. Review what is staged (ensure no .keystore or key.properties appear)
git status

# 2. Stage verified code changes
git add README.md .gitignore

# 3. Commit with a clear semantic message
git commit -m "docs: publish comprehensive A-to-Z production README"

# 4. Safely push to your repository
git push origin <your-branch-name>
```

---

## 👨‍💻 Author & Credits

- **Developer & Creator:** **Manohar** ([@Manohar630](https://github.com/Manohar630))
- **Email Contact:** [smanohar33733@gmail.com](mailto:smanohar33733@gmail.com)
- **Design Inspiration:** *Project K — Cognitive Wellness Engineering*

---

<div align="center">
  <sub>NeuroVault AI is designed and maintained by Manohar. Built with ❤️ for on-device health and focus.</sub>
</div>
