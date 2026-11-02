# HomeFit Pro v5.0 — Offline-First Biomechanical Fitness & Clinical Nutrition Engine

![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-Material_3-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white)
![Room SQLite](https://img.shields.io/badge/Room_SQLite-2.7.0-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Offline--First_%7C_Zero--Cloud-10B981?style=for-the-badge)
![Codebase](https://img.shields.io/badge/Codebase-71_Files_%7C_20.6K%2B_LOC-F59E0B?style=for-the-badge)
![Version](https://img.shields.io/badge/Release-v5.0-38BDF8?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-22C55E?style=for-the-badge)

**HomeFit Pro v5.0** is an open-source, privacy-first, zero-cloud Android fitness and clinical nutrition platform built entirely in **Kotlin** and **Jetpack Compose**. Engineered across **71 modular source files (20,600+ lines of code)**, it combines real-time 2.5D/3D procedural biomechanical rendering, deterministic coaching heuristics, clinical metabolic equations, and full bilingual (**English & Bengali**) accessibility without requiring external servers, user accounts, or telemetry trackers.

---

## Why HomeFit Matters to the Open-Source Ecosystem

Most modern mobile health applications lock essential biometric calculators, exercise kinematics, and personal health logs behind proprietary cloud paywalls and invasive data-harvesting pipelines. **HomeFit Pro v5.0** solves this by providing a self-contained, auditable, and deterministic mobile health engine:

1. **100% Offline-First & Zero-Cloud Privacy:** Every biometric profile, weight log, hydration record, and custom workout routine resides strictly on-device inside a local **Room SQLite v4** database (`HomeFitDatabase`), with full user-controlled JSON portability (`LocalBackupManager`).
2. **Procedural Biomechanical Visualization (Zero Heavy Assets):** Instead of bundling hundreds of megabytes of video files, `ExerciseAnimationVisualizer` renders **27 distinct multi-joint humanoid exercise animations** at 60 FPS using mathematical forward/inverse kinematics and real-time muscle activation heatmaps on Jetpack Compose `Canvas`.
3. **Bilingual Health Democratization (EN / BN):** Built-in localization (`HomeFitStrings` & `TranslationManager`) pairs clinical fitness science with region-accessible nutrition (`BudgetDietPlans` & `FoodDatabaseData`), empowering underserved communities with scientifically accurate health tooling in both English and Bengali.

---

## Quick Audit Note for Reviewers

> **Important Note for OpenAI Codex Reviewers & Codebase Auditors:**
> Alongside the standard Android Gradle project tree, the entire **71-file, 20,691-line codebase**—complete with a numbered file tree index, Gradle configurations, Room SQLite entities/DAOs, domain engines, and Compose UI screens—has been consolidated into **[`HomeFit_Complete_Project_Code.md`](./HomeFit_Complete_Project_Code.md)** in the root of this repository for rapid, single-file inspection and automated static analysis.

---

## Core Engines & Technical Highlights

### 1. Procedural Biomechanical Animation Engine (`ExerciseAnimationVisualizer.kt`)
- **27 Real-Time Kinematic Routines:** Dedicated mathematical joint-interpolation pipelines covering Chest, Arms, Core/Abs, Legs, Back, and HIIT/Cardio movements (`PUSH_UP`, `DIAMOND_PUSHUP`, `CHAIR_DIPS`, `BICYCLE_CRUNCHES`, `PISTOL/BODYWEIGHT_SQUATS`, `BURPEES`, `COBRA_STRETCH`, etc.).
- **Live Muscle Activation Heatmaps:** Dynamically illuminates primary and secondary muscle groups (Pectoralis Major, Rectus Abdominis, Latissimus Dorsi, Quadriceps, Triceps Brachii) synchronized with the concentric and eccentric phases of each repetition.
- **Interactive Viewport Controls:** Supports pinch-to-zoom (`detectTransformGestures`), pan inspection, cadence pause/resume, and bilingual anatomical target callouts.

### 2. Deterministic Smart Coaching & Adaptive Planning (`SmartCoachEngine.kt`, `WorkoutRecommendationEngine.kt`, `SmartPlanGenerator.kt`)
- **`SmartCoachEngine`:** Evaluates multi-variable user telemetry—including active workout streaks, days elapsed since last training or weight log, daily water intake, and cumulative session volume—to synthesize context-aware coaching directives (`CoachTipType`).
- **`WorkoutRecommendationEngine` & `SmartPlanGenerator`:** Deterministically generates progressive-overload training splits and Tabata/HIIT circuits tailored to the user's goal (`weight_loss`, `muscle_gain`, `fitness`), experience tier (`beginner`, `intermediate`, `advanced`), weekly frequency, and available home equipment (`none`, `chair_towel`, `dumbbells`).

### 3. Clinical Biometrics, Hydration & Nutrition (`HealthCalculations.kt`, `BudgetDietPlans.kt`, `FoodDatabaseData.kt`)
- **`HealthCalculations`:** Implements the **Mifflin-St Jeor Equation** for Basal Metabolic Rate (BMR), activity-adjusted Total Daily Energy Expenditure (TDEE), goal-calibrated caloric targets, and macronutrient splits (Protein, Carbohydrates, Fats).
- **Scientific Hydration Formula:** Computes personalized daily fluid requirements in milliliters and 250ml glasses using baseline body mass (`weightKg * 35ml`), training frequency sweat compensation, age modifiers, and goal adjustments.
- **`BudgetDietPlans` & `FoodDatabaseData`:** Provides structured, cost-effective daily meal blueprints and a searchable bilingual food macro database for real-time daily calorie and protein logging (`NutritionLogEntity`).

### 4. Active Workout Player, Voice Synthesis & Audio Ducking (`ActiveWorkoutPlayerScreen.kt`, `AudioFeedbackManager.kt`, `WorkoutMusicManager.kt`)
- **State-Driven Session Engine (`ActiveWorkoutSession`):** Manages `PREPARE`, `EXERCISE`, `REST`, and `COMPLETED` phases with wake-lock management (`FLAG_KEEP_SCREEN_ON`), live calorie burn estimation, and interactive sequence checklists.
- **`AudioFeedbackManager` & `WorkoutMusicManager`:** Pairs offline Text-to-Speech (TTS) rep counting and phase announcements with synthesized offline workout beats (`OfflineBeatPreset`) and custom local audio tracks (`SavedMusicTrackEntity`), featuring automatic volume ducking during voice cues.

### 5. Resilient Local Persistence & Portable Backups (`HomeFitDatabase.kt`, `RoomStorageService.kt`, `LocalBackupManager.kt`)
- **Schema Evolution & Migrations:** Implements Room SQLite version 4 with explicit, non-destructive SQL migrations (`MIGRATION_1_2`, `MIGRATION_2_3`, `MIGRATION_3_4`) across 9 relational entities (`UserProfileEntity`, `WorkoutLogEntity`, `WeightLogEntity`, `WaterLogEntity`, `FavoriteExerciseEntity`, `CustomWorkoutEntity`, `NutritionLogEntity`, `SavedMusicTrackEntity`, `ChallengeProgressEntity`).
- **`LocalBackupManager`:** Enables full offline data sovereignty via structured JSON export and transactional restore of all user logs, custom workouts, and challenge progress.

---

## System Architecture & Tech Stack

    +-------------------------------------------------------------------------+
    |                     UI Layer (Jetpack Compose / M3)                     |
    |  +----------------------+ +----------------------+ +-----------------+  |
    |  | ExerciseAnimation    | | ActiveWorkoutPlayer  | | MainAppScreen   |  |
    |  | Visualizer (27 3D)   | | & WorkoutMusicSheet  | | (5 Core Tabs)   |  |
    |  +----------+-----------+ +----------+-----------+ +--------+--------+  |
    +-------------|------------------------|----------------------|-----------+
                  |                        |                      |
    +-------------v------------------------v----------------------v-----------+
    |                 State & Domain Layer (HomeFitViewModel)                 |
    |  +----------------------+ +----------------------+ +-----------------+  |
    |  | SmartCoachEngine &   | | HealthCalculations   | | AudioFeedback & |  |
    |  | PlanGenerators       | | (BMR/TDEE/Hydration) | | MusicManager    |  |
    |  +----------+-----------+ +----------+-----------+ +--------+--------+  |
    +-------------|------------------------|----------------------|-----------+
                  |                        |                      |
    +-------------v------------------------v----------------------v-----------+
    |                  Data & Persistence Layer (Offline-First)               |
    |  +----------------------+ +----------------------+ +-----------------+  |
    |  | RoomStorageService   | | HomeFitDatabase      | | LocalBackup     |  |
    |  | (Reactive Flows)     | | (SQLite v4 + DAOs)   | | Manager (JSON)  |  |
    |  +----------------------+ +----------------------+ +-----------------+  |
    +-------------------------------------------------------------------------+

| Layer / Domain | Technology / Implementation |
| :--- | :--- |
| **Language & Concurrency** | Kotlin 2.2.10, Kotlin Coroutines, Reactive `StateFlow` & `Flow` |
| **UI Framework** | Jetpack Compose (BOM 2024.09.00), Material Design 3, Custom 2D/3D `Canvas` |
| **Architecture Pattern** | Clean MVVM (Model-View-ViewModel) with Unidirectional Data Flow (UDF) |
| **Local Persistence** | AndroidX Room SQLite 2.7.0 (KSP 2.3.5), Custom Schema Migrations (v1 -> v4) |
| **Audio & Telemetry** | Android TTS (`TextToSpeech`), `AudioTrack` Beat Synthesizer, `MediaPlayer` |
| **Build & Target SDK** | Android Gradle Plugin (AGP) 9.1.1, Compile/Target SDK 36, Min SDK 26, Java 17 |
| **Testing Infrastructure** | JUnit 4, Robolectric Local JVM Testing (`ExampleRobolectricTest.kt`) |

---

## Repository Module Overview

- `app/src/main/java/com/example/MainActivity.kt` — Application entry point, ViewModel factory wiring, and top-level screen router.
- `app/src/main/java/com/example/ui/HomeFitViewModel.kt` — Central reactive state holder (`HomeFitUiState`) orchestrating all 9 database flows, workout timers, and biometric recalculations.
- `app/src/main/java/com/example/ui/components/animation/ExerciseAnimationVisualizer.kt` — 2,260+ line procedural biomechanical humanoid renderer and muscle heatmap engine.
- `app/src/main/java/com/example/domain/` — Pure Kotlin business logic:
  - `calculations/HealthCalculations.kt` — BMR, TDEE, BMI, macro splits, and scientific hydration math.
  - `coach/SmartCoachEngine.kt` — Behavioral streak and hydration evaluation rules.
  - `recommendation/WorkoutRecommendationEngine.kt` & `SmartPlanGenerator.kt` — Adaptive routine builders.
  - `service/StorageService.kt` — Domain repository contract.
- `app/src/main/java/com/example/data/` — Offline persistence and seed catalogs:
  - `local/HomeFitDatabase.kt`, `dao/`, `entity/` — Room SQLite database, DAOs, and 9 entities.
  - `repository/RoomStorageService.kt` — Reactive Flow implementation of `StorageService`.
  - `backup/LocalBackupManager.kt` — JSON serialization/deserialization for user data portability.
  - `seed/ExerciseLibraryData.kt`, `FoodDatabaseData.kt`, `BudgetDietPlans.kt` — Bilingual exercise and nutrition catalogs.
- `app/src/main/java/com/example/core/` — Cross-cutting services:
  - `audio/AudioFeedbackManager.kt` & `WorkoutMusicManager.kt` — Voice synthesis and audio ducking.
  - `i18n/HomeFitStrings.kt` — Complete English and Bengali string tables.
- `HomeFit_Complete_Project_Code.md` — Single-file comprehensive bundle of all 71 project files for rapid auditing.

---

## Roadmap (Powered by OpenAI Codex & API Ecosystem)

As **HomeFit Pro** scales to support a broader global open-source community, our upcoming engineering milestones are centered around **OpenAI Codex** and **Codex Security**:

1. **Automated Vulnerability Auditing via Codex Security:**
   - Continuous static analysis and fuzzing of `LocalBackupManager` JSON import/restore pipelines to prevent deserialization and SQL injection vectors.
   - Automated auditing of Android URI permission grants and media file handling in `WorkoutMusicManager` across community pull requests.
   - Memory-leak detection and coroutine lifecycle verification across long-running `ActiveWorkoutPlayerScreen` sessions.
2. **Next-Generation AI Coaching & Macro Adaptation (OpenAI API):**
   - Evolving `SmartCoachEngine`, `SmartPlanGenerator`, and `BudgetDietPlans` with optional, privacy-preserving OpenAI structured outputs for hyper-personalized injury-aware exercise substitutions and culturally tailored nutrition planning.
3. **CI/CD Test Generation & Bilingual Localization QA:**
   - Leveraging Codex in CI/CD pipelines to expand Robolectric unit test coverage (`HealthCalculations`, `RoomStorageService` migrations, and `HomeFitViewModel` state transitions), automate PR reviews, and validate bilingual (EN/BN) string parity in `HomeFitStrings`.

---

## Getting Started & Building From Source

### Prerequisites
- **Android Studio** Ladybug / Meerkat or newer (AGP 9.1.1 compatible)
- **JDK 17** configured as the Gradle JVM
- **Android SDK 36** (Min SDK 26 / Android 8.0+)

### Build Steps
1. Clone the repository to your local machine:
   `git clone https://github.com/ishanxczsx2023/HomeFit.git`
2. Open the project root directory in Android Studio and allow Gradle to sync dependencies via `gradle/libs.versions.toml`.
3. Compile and install the debug APK on a connected device or emulator:
   `gradle :app:assembleDebug`
4. Alternatively, you can directly install the pre-built `HomeFit_v5.0.apk` included in the root directory or export the APK directly from the in-app **Profile** tab.

---

## Maintainer & Governance

- **Primary Maintainer & Lead Architect:** **Iftekhar Ahmed**
- **GitHub:** [@ishanxczsx2023](https://github.com/ishanxczsx2023)

As the sole Primary Maintainer managing all 71 files and 20,600+ lines of Kotlin/Compose code, community contributions, bug reports, and security audits are warmly welcomed. Please open an issue or submit a pull request for any enhancements.

---

## License

This project is open-source software licensed under the **MIT License**. Free to use, study, modify, and distribute with attribution.
