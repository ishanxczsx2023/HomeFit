# HomeFit Pro v5.0 — Complete Android Project Codebase

এই সিঙ্গেল কমপ্রিহেনসিভ ফাইলটিতে **HomeFit Pro v5.0** অ্যাপ্লিকেশন প্রজেক্টের সম্পূর্ণ সোর্স কোড, Gradle কনফিগারেশন, XML রিসোর্স এবং ডাটাবেস ফাইলগুলো একত্রে সাজানো আছে।

## সূচিপত্র (Project File Tree - Total 71 Files)

1. `build.gradle.kts`
2. `gradle.properties`
3. `metadata.json`
4. `settings.gradle.kts`
5. `app/build.gradle.kts`
6. `app/proguard-rules.pro`
7. `app/src/androidTest/java/com/example/ExampleInstrumentedTest.kt`
8. `app/src/main/AndroidManifest.xml`
9. `app/src/main/java/com/example/MainActivity.kt`
10. `app/src/main/java/com/example/core/audio/AudioFeedbackManager.kt`
11. `app/src/main/java/com/example/core/audio/WorkoutMusicManager.kt`
12. `app/src/main/java/com/example/core/i18n/HomeFitStrings.kt`
13. `app/src/main/java/com/example/data/backup/LocalBackupManager.kt`
14. `app/src/main/java/com/example/data/local/HomeFitDatabase.kt`
15. `app/src/main/java/com/example/data/local/dao/LogDao.kt`
16. `app/src/main/java/com/example/data/local/dao/UserDao.kt`
17. `app/src/main/java/com/example/data/local/dao/WorkoutDao.kt`
18. `app/src/main/java/com/example/data/local/entity/CustomWorkoutEntities.kt`
19. `app/src/main/java/com/example/data/local/entity/LogEntities.kt`
20. `app/src/main/java/com/example/data/local/entity/UserProfileEntity.kt`
21. `app/src/main/java/com/example/data/repository/RoomStorageService.kt`
22. `app/src/main/java/com/example/data/seed/BudgetDietPlans.kt`
23. `app/src/main/java/com/example/data/seed/ExerciseLibraryData.kt`
24. `app/src/main/java/com/example/data/seed/FoodDatabaseData.kt`
25. `app/src/main/java/com/example/domain/calculations/HealthCalculations.kt`
26. `app/src/main/java/com/example/domain/coach/SmartCoachEngine.kt`
27. `app/src/main/java/com/example/domain/model/ActiveWorkoutSession.kt`
28. `app/src/main/java/com/example/domain/model/ExerciseModels.kt`
29. `app/src/main/java/com/example/domain/model/UserProfile.kt`
30. `app/src/main/java/com/example/domain/recommendation/SmartPlanGenerator.kt`
31. `app/src/main/java/com/example/domain/recommendation/WorkoutRecommendationEngine.kt`
32. `app/src/main/java/com/example/domain/service/StorageService.kt`
33. `app/src/main/java/com/example/ui/HomeFitViewModel.kt`
34. `app/src/main/java/com/example/ui/components/HomeFitComponents.kt`
35. `app/src/main/java/com/example/ui/components/ProSubscriptionComponents.kt`
36. `app/src/main/java/com/example/ui/components/animation/ExerciseAnimationVisualizer.kt`
37. `app/src/main/java/com/example/ui/components/charts/AnalyticsCharts.kt`
38. `app/src/main/java/com/example/ui/screens/diet/DietScreen.kt`
39. `app/src/main/java/com/example/ui/screens/home/HomeWidgets.kt`
40. `app/src/main/java/com/example/ui/screens/main/MainAppScreen.kt`
41. `app/src/main/java/com/example/ui/screens/onboarding/HealthDisclaimerScreen.kt`
42. `app/src/main/java/com/example/ui/screens/onboarding/NameInputScreen.kt`
43. `app/src/main/java/com/example/ui/screens/onboarding/ProfileSetupScreen.kt`
44. `app/src/main/java/com/example/ui/screens/onboarding/WelcomeSlidesScreen.kt`
45. `app/src/main/java/com/example/ui/screens/player/ActiveWorkoutPlayerScreen.kt`
46. `app/src/main/java/com/example/ui/screens/player/WorkoutCardShareHelper.kt`
47. `app/src/main/java/com/example/ui/screens/player/WorkoutCompletionScreen.kt`
48. `app/src/main/java/com/example/ui/screens/player/WorkoutMusicSheet.kt`
49. `app/src/main/java/com/example/ui/screens/profile/ProfileScreen.kt`
50. `app/src/main/java/com/example/ui/screens/progress/ProgressScreen.kt`
51. `app/src/main/java/com/example/ui/screens/splash/SplashScreen.kt`
52. `app/src/main/java/com/example/ui/screens/workouts/ChallengesAndTabataContent.kt`
53. `app/src/main/java/com/example/ui/screens/workouts/WorkoutPreviewScreen.kt`
54. `app/src/main/java/com/example/ui/screens/workouts/WorkoutsScreen.kt`
55. `app/src/main/java/com/example/ui/theme/Color.kt`
56. `app/src/main/java/com/example/ui/theme/Theme.kt`
57. `app/src/main/java/com/example/ui/theme/Type.kt`
58. `app/src/main/res/drawable/ic_launcher_background.xml`
59. `app/src/main/res/drawable/ic_launcher_foreground.xml`
60. `app/src/main/res/mipmap-anydpi-v26/ic_launcher.xml`
61. `app/src/main/res/mipmap-anydpi-v26/ic_launcher_round.xml`
62. `app/src/main/res/values/colors.xml`
63. `app/src/main/res/values/strings.xml`
64. `app/src/main/res/values/themes.xml`
65. `app/src/main/res/xml/backup_rules.xml`
66. `app/src/main/res/xml/data_extraction_rules.xml`
67. `app/src/main/res/xml/file_paths.xml`
68. `app/src/test/java/com/example/ExampleRobolectricTest.kt`
69. `app/src/test/java/com/example/ExampleUnitTest.kt`
70. `gradle/libs.versions.toml`
71. `gradle/wrapper/gradle-wrapper.properties`

---

## FILE: `build.gradle.kts`

```kotlin
// Top-level build file where you can add configuration options common to all sub-projects/modules.
plugins {
    alias(libs.plugins.android.application) apply false
    alias(libs.plugins.kotlin.compose) apply false
    alias(libs.plugins.ksp) apply false
}
```

---

## FILE: `gradle.properties`

```properties
org.gradle.jvmargs=-Xmx2048m -XX:MaxMetaspaceSize=512m -XX:+UseG1GC
android.useAndroidX=true
```

---

## FILE: `metadata.json`

```json
{
  "name": "HomeFit",
  "description": "HomeFit Pro - Dark Luxury Gym & Home Workouts with 3D Anatomical Mannequin Animations, IshanX10 VIP Unlocked, Dynamic Hydration & Macro Nutrition.",
  "requestFramePermissions": [],
  "majorCapabilities": ["MAJOR_CAPABILITY_SERVER_SIDE_GEMINI_API"]
}
```

---

## FILE: `settings.gradle.kts`

```kotlin
pluginManagement {
    repositories {
        google {
            content {
                includeGroupByRegex("com\\.android.*")
                includeGroupByRegex("com\\.google.*")
                includeGroupByRegex("androidx.*")
            }
        }
        mavenCentral()
        gradlePluginPortal()
    }
}
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}

rootProject.name = "HomeFit"
include(":app")
```

---

## FILE: `app/build.gradle.kts`

```kotlin
plugins {
    alias(libs.plugins.android.application)
    alias(libs.plugins.kotlin.compose)
    alias(libs.plugins.ksp)
}

android {
    namespace = "com.example"
    compileSdk = 36

    defaultConfig {
        applicationId = "com.aistudio.homefit.ishan"
        minSdk = 26
        targetSdk = 36
        versionCode = 5
        versionName = "5.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
    }

    signingConfigs {
        create("release") {
            storeFile = file("${rootDir}/debug.keystore")
            storePassword = "android"
            keyAlias = "androiddebugkey"
            keyPassword = "android"
        }
        getByName("debug") {
            storeFile = file("${rootDir}/debug.keystore")
            storePassword = "android"
            keyAlias = "androiddebugkey"
            keyPassword = "android"
        }
    }

    buildTypes {
        release {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
            signingConfig = signingConfigs.getByName("release")
        }
        debug {
            signingConfig = signingConfigs.getByName("debug")
        }
    }

    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_17
        targetCompatibility = JavaVersion.VERSION_17
    }

    buildFeatures {
        compose = true
    }
}

dependencies {
    implementation(libs.androidx.core.ktx)
    implementation(libs.androidx.lifecycle.runtime.ktx)
    implementation(libs.androidx.lifecycle.viewmodel.compose)
    implementation(libs.androidx.activity.compose)
    implementation(platform(libs.androidx.compose.bom))
    implementation(libs.androidx.ui)
    implementation(libs.androidx.ui.graphics)
    implementation(libs.androidx.ui.tooling.preview)
    implementation(libs.androidx.material3)
    implementation(libs.androidx.material.icons.extended)

    // Room Database
    implementation(libs.androidx.room.runtime)
    implementation(libs.androidx.room.ktx)
    ksp(libs.androidx.room.compiler)

    debugImplementation(libs.androidx.ui.tooling)
}
```

---

## FILE: `app/proguard-rules.pro`

```pro
# Add project specific ProGuard rules here.
# You can control the set of applied configuration files using the
# proguardFiles setting in build.gradle.
#
# For more details, see
#   http://developer.android.com/guide/developing/tools/proguard.html

# If your project uses WebView with JS, uncomment the following
# and specify the fully qualified class name to the JavaScript interface
# class:
#-keepclassmembers class fqcn.of.javascript.interface.for.webview {
#   public *;
#}

# Uncomment this to preserve the line number information for
# debugging stack traces.
#-keepattributes SourceFile,LineNumberTable

# If you keep the line number information, uncomment this to
# hide the original source file name.
#-renamesourcefileattribute SourceFile
```

---

## FILE: `app/src/androidTest/java/com/example/ExampleInstrumentedTest.kt`

```kotlin
package com.example

import androidx.test.ext.junit.runners.AndroidJUnit4
import androidx.test.platform.app.InstrumentationRegistry
import org.junit.Assert.*
import org.junit.Test
import org.junit.runner.RunWith

/**
 * Instrumented test, which will execute on an Android device.
 *
 * See [testing documentation](http://d.android.com/tools/testing).
 */
@RunWith(AndroidJUnit4::class)
class ExampleInstrumentedTest {
  @Test
  fun useAppContext() {
    // Context of the app under test.
    val appContext = InstrumentationRegistry.getInstrumentation().targetContext
    assertEquals(BuildConfig.APPLICATION_ID, appContext.packageName)
  }
}
```

---

## FILE: `app/src/main/AndroidManifest.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.ApexGym">
        <activity
            android:name=".MainActivity"
            android:exported="true"
            android:windowSoftInputMode="adjustResize"
            android:theme="@style/Theme.ApexGym">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

---

## FILE: `app/src/main/java/com/example/MainActivity.kt`

```kotlin
package com.example

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.enableEdgeToEdge
import androidx.activity.viewModels
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.lifecycle.ViewModel
import androidx.lifecycle.ViewModelProvider
import com.example.core.audio.AudioFeedbackManager
import com.example.core.audio.WorkoutMusicManager
import com.example.core.i18n.Language
import com.example.data.local.HomeFitDatabase
import com.example.data.repository.RoomStorageService
import com.example.ui.AppScreen
import com.example.ui.HomeFitViewModel
import com.example.ui.components.MainTab
import com.example.ui.components.ProSubscriptionDialog
import com.example.ui.screens.main.MainAppScreen
import com.example.ui.screens.onboarding.HealthDisclaimerScreen
import com.example.ui.screens.onboarding.NameInputScreen
import com.example.ui.screens.onboarding.ProfileSetupScreen
import com.example.ui.screens.onboarding.WelcomeSlidesScreen
import com.example.ui.screens.player.ActiveWorkoutPlayerScreen
import com.example.ui.screens.player.WorkoutCompletionScreen
import com.example.ui.screens.splash.SplashScreen
import com.example.ui.screens.workouts.WorkoutPreviewScreen
import com.example.ui.theme.HomeFitTheme

class MainActivity : ComponentActivity() {

    private val viewModel: HomeFitViewModel by viewModels {
        object : ViewModelProvider.Factory {
            @Suppress("UNCHECKED_CAST")
            override fun <T : ViewModel> create(modelClass: Class<T>): T {
                val db = HomeFitDatabase.getDatabase(applicationContext)
                val storage = RoomStorageService(db)
                val audio = AudioFeedbackManager(applicationContext)
                val music = WorkoutMusicManager(applicationContext)
                return HomeFitViewModel(storage, audio, music) as T
            }
        }
    }

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()

        setContent {
            val uiState by viewModel.uiState.collectAsState()
            val activeSession by viewModel.activeWorkoutSessionFlow.collectAsState()
            val musicState by viewModel.musicStateFlow.collectAsState()

            HomeFitTheme(darkTheme = uiState.isDarkMode) {
                // Pro Dialog if open
                if (uiState.isProDialogOpen) {
                    ProSubscriptionDialog(
                        isProSubscribed = uiState.isProSubscribed,
                        selectedLanguage = uiState.selectedLanguage,
                        errorMessage = uiState.proCodeError,
                        successMessage = uiState.proActivationMessage,
                        onRedeemCode = { code -> viewModel.redeemSecretProCode(code) },
                        onDeactivatePro = { viewModel.deactivateProSubscription() },
                        onDismiss = { viewModel.closeProDialog() }
                    )
                }

                when (val screen = uiState.currentScreen) {
                    is AppScreen.Splash -> {
                        SplashScreen(
                            strings = uiState.strings,
                            onFinished = { viewModel.onSplashFinished() }
                        )
                    }
                    is AppScreen.WelcomeSlides -> {
                        WelcomeSlidesScreen(
                            currentSlide = screen.slideIndex,
                            strings = uiState.strings,
                            onSlideChange = { viewModel.setWelcomeSlide(it) },
                            onFinishSlides = { viewModel.skipToNameInput() },
                            onBack = { viewModel.navigateBack() },
                            isProSubscribed = uiState.isProSubscribed,
                            selectedLanguage = uiState.selectedLanguage,
                            onOpenProDialog = { viewModel.openProDialog() }
                        )
                    }
                    is AppScreen.NameInput -> {
                        NameInputScreen(
                            name = uiState.nameInput,
                            errorMessage = uiState.nameError,
                            strings = uiState.strings,
                            onNameChange = { viewModel.onNameChange(it) },
                            onSubmit = { viewModel.submitName() },
                            onBack = { viewModel.navigateBack() }
                        )
                    }
                    is AppScreen.ProfileSetup -> {
                        ProfileSetupScreen(
                            age = uiState.ageInput,
                            heightCm = uiState.heightInput,
                            weightKg = uiState.weightInput,
                            gender = uiState.genderInput,
                            goal = uiState.goalInput,
                            level = uiState.levelInput,
                            daysPerWeek = uiState.daysInput,
                            equipment = uiState.equipmentInput,
                            liveBmi = uiState.liveBmi,
                            liveBmiCategory = uiState.liveBmiCategory,
                            liveCalories = uiState.liveDailyCalories,
                            strings = uiState.strings,
                            onAgeChange = { viewModel.updateAge(it) },
                            onHeightChange = { viewModel.updateHeight(it) },
                            onWeightChange = { viewModel.updateWeight(it) },
                            onGenderChange = { viewModel.updateGender(it) },
                            onGoalChange = { viewModel.updateGoal(it) },
                            onLevelChange = { viewModel.updateFitnessLevel(it) },
                            onDaysChange = { viewModel.updateWorkoutDays(it) },
                            onEquipmentChange = { viewModel.updateEquipment(it) },
                            onProceed = { viewModel.proceedToDisclaimer() },
                            onBack = { viewModel.navigateBack() }
                        )
                    }
                    is AppScreen.HealthDisclaimer -> {
                        HealthDisclaimerScreen(
                            disclaimerAccepted = uiState.disclaimerAccepted,
                            strings = uiState.strings,
                            onAcceptChanged = { viewModel.setDisclaimerAccepted(it) },
                            onConfirm = { viewModel.completeOnboardingAndSave() },
                            onBack = { viewModel.navigateBack() }
                        )
                    }
                    is AppScreen.MainApp -> {
                        MainAppScreen(
                            currentTab = screen.currentTab,
                            userProfile = uiState.userProfile,
                            recommendedWorkout = uiState.recommendedWorkout,
                            todayCaloriesBurned = uiState.todayCaloriesBurned,
                            todayCaloriesGoal = uiState.todayCaloriesGoal,
                            todayWaterGlasses = uiState.todayWaterGlasses,
                            todayWaterGoal = uiState.todayWaterGoal,
                            todaySteps = uiState.todaySteps,
                            todayStepsGoal = uiState.todayStepsGoal,
                            streakDays = uiState.streakDays,
                            dailyIntakeCaloriesGoal = uiState.liveDailyCalories,
                            todayWaterGoalMl = uiState.todayWaterGoalMl,
                            smartCoachTip = uiState.smartCoachTip,
                            completedWeekDays = uiState.completedWeekDays,
                            isStepDialogOpen = uiState.isStepDialogOpen,
                            isWeightDialogOpen = uiState.isWeightDialogOpen,
                            favoriteExerciseIds = uiState.favoriteExerciseIds,
                            customWorkouts = uiState.customWorkouts,
                            weightLogs = uiState.weightLogs,
                            waterLogs = uiState.waterLogs,
                            workoutLogs = uiState.workoutLogs,
                            todayNutritionLogs = uiState.todayNutritionLogs,
                            savedMusicTracks = uiState.savedMusicTracks,
                            challengeProgressList = uiState.challengeProgressList,
                            voiceRepCounterEnabled = uiState.voiceRepCounterEnabled,
                            musicState = musicState,
                            selectedLanguage = uiState.selectedLanguage,
                            isDarkMode = uiState.isDarkMode,
                            strings = uiState.strings,
                            onTabSelected = { viewModel.selectTab(it) },
                            onToggleLanguage = { viewModel.toggleLanguage() },
                            onToggleTheme = { viewModel.toggleTheme() },
                            onAddWaterGlass = { viewModel.addWaterGlass() },
                            onRemoveWaterGlass = { viewModel.removeWaterGlass() },
                            onOpenStepDialog = { viewModel.openStepDialog() },
                            onCloseStepDialog = { viewModel.closeStepDialog() },
                            onSaveSteps = { viewModel.saveSteps(it) },
                            onOpenWeightDialog = { viewModel.openWeightDialog() },
                            onCloseWeightDialog = { viewModel.closeWeightDialog() },
                            onSaveWeight = { viewModel.saveWeightLog(it) },
                            onToggleFavorite = { viewModel.toggleFavorite(it) },
                            onSaveCustomWorkout = { title, ids, dur, rest -> viewModel.saveCustomWorkout(title, ids, dur, rest) },
                            onDeleteCustomWorkout = { viewModel.deleteCustomWorkout(it) },
                            onStartWorkout = { viewModel.startRecommendedWorkout() },
                            onStartWorkoutPlan = { viewModel.startWorkoutPlan(it) },
                            onToggleChallengeDay = { id, day -> viewModel.toggleChallengeDay(id, day) },
                            onToggleVoiceRepCounter = { viewModel.toggleVoiceRepCounter() },
                            onStartTabataSession = { title, desc, w, r, c, ex -> viewModel.startTabataSession(title, desc, w, r, c, ex) },
                            onLogNutritionItem = { nameBn, nameEn, cal, p, c, f -> viewModel.logNutritionItem(nameBn, nameEn, cal, p, c, f) },
                            onDeleteNutritionLog = { viewModel.deleteNutritionLog(it) },
                            onSelectBeatPreset = { viewModel.selectBeatPreset(it) },
                            onPlayMusicTrack = { viewModel.playMusicTrack(it) },
                            onToggleMusicPlayPause = { viewModel.toggleMusicPlayPause() },
                            onNextMusicTrack = { viewModel.nextMusicTrack() },
                            onMusicVolumeChange = { viewModel.setMusicVolume(it) },
                            onAddMusicTrack = { uri, title -> viewModel.addMusicTrack(uri, title) },
                            onDeleteMusicTrack = { viewModel.deleteMusicTrack(it) },
                            onExportBackup = { viewModel.exportBackupJson() },
                            onImportBackup = { viewModel.importBackupJson(it) },
                            onSaveProfile = { n, a, h, w, g, l -> viewModel.updateUserProfile(n, a, h, w, g, l) },
                            onResetAllData = { viewModel.resetAllData() },
                            isProSubscribed = uiState.isProSubscribed,
                            onOpenProDialog = { viewModel.openProDialog() }
                        )
                    }
                    is AppScreen.WorkoutPreview -> {
                        WorkoutPreviewScreen(
                            plan = screen.plan,
                            selectedLanguage = uiState.selectedLanguage,
                            strings = uiState.strings,
                            onStartWorkout = { viewModel.startWorkoutPlan(screen.plan) },
                            onExerciseClick = { /* preview */ },
                            onBrowseOtherWorkouts = { viewModel.selectTab(MainTab.WORKOUTS) },
                            onBack = { viewModel.navigateBack() }
                        )
                    }
                    is AppScreen.ActivePlayer -> {
                        val session = activeSession
                        if (session != null) {
                            ActiveWorkoutPlayerScreen(
                                session = session,
                                selectedLanguage = uiState.selectedLanguage,
                                strings = uiState.strings,
                                onPlayPauseToggle = { viewModel.togglePlayPause() },
                                onSkipNext = { viewModel.skipNextExercise() },
                                onPrevious = { viewModel.previousExercise() },
                                onRestartCurrent = { viewModel.restartCurrentExercise() },
                                onToggleMute = { viewModel.toggleMute() },
                                onSkipRest = { viewModel.skipRest() },
                                onExitWorkout = { viewModel.exitWorkout() },
                                musicState = musicState,
                                savedMusicTracks = uiState.savedMusicTracks,
                                voiceRepCounterEnabled = uiState.voiceRepCounterEnabled,
                                onToggleVoiceRepCounter = { viewModel.toggleVoiceRepCounter() },
                                onToggleMusicPlayPause = { viewModel.toggleMusicPlayPause() },
                                onNextMusicTrack = { viewModel.nextMusicTrack() },
                                onAddMusicTrack = { uri, title -> viewModel.addMusicTrack(uri, title) },
                                onDeleteMusicTrack = { viewModel.deleteMusicTrack(it) },
                                onPlayMusicTrack = { viewModel.playMusicTrack(it) },
                                onSelectBeatPreset = { viewModel.selectBeatPreset(it) },
                                onMusicVolumeChange = { viewModel.setMusicVolume(it) }
                            )
                        } else {
                            viewModel.selectTab(MainTab.HOME)
                        }
                    }
                    is AppScreen.WorkoutCompleted -> {
                        val planTitle = if (uiState.selectedLanguage == Language.BENGALI) {
                            screen.session.plan.titleBn
                        } else {
                            screen.session.plan.titleEn
                        }
                        WorkoutCompletionScreen(
                            planTitle = planTitle,
                            totalSeconds = screen.session.totalElapsedSeconds,
                            caloriesBurned = screen.session.totalCaloriesBurned,
                            exercisesCompletedCount = screen.session.completedExercisesCount,
                            selectedLanguage = uiState.selectedLanguage,
                            strings = uiState.strings,
                            userName = uiState.userProfile?.name ?: "",
                            streakDays = uiState.streakDays,
                            onFinish = { viewModel.finishCompletedWorkout() }
                        )
                    }
                }
            }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/core/audio/AudioFeedbackManager.kt`

```kotlin
package com.example.core.audio

import android.content.Context
import android.media.AudioManager
import android.media.ToneGenerator
import android.os.Build
import android.os.VibrationEffect
import android.os.Vibrator
import android.os.VibratorManager
import android.speech.tts.TextToSpeech
import android.speech.tts.UtteranceProgressListener
import com.example.core.i18n.Language
import kotlinx.coroutines.CoroutineScope
import kotlinx.coroutines.Dispatchers
import kotlinx.coroutines.Job
import kotlinx.coroutines.SupervisorJob
import kotlinx.coroutines.delay
import kotlinx.coroutines.launch
import java.util.Locale

class AudioFeedbackManager(
    private val context: Context,
    var onDuckingChange: ((Boolean) -> Unit)? = null
) : TextToSpeech.OnInitListener {

    private val scope = CoroutineScope(SupervisorJob() + Dispatchers.Main)
    private var duckResetJob: Job? = null

    private var tts: TextToSpeech? = null
    private var isTtsReady = false
    private var toneGenerator: ToneGenerator? = null
    private val vibrator: Vibrator? = if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.S) {
        val vibratorManager = context.getSystemService(Context.VIBRATOR_MANAGER_SERVICE) as? VibratorManager
        vibratorManager?.defaultVibrator
    } else {
        @Suppress("DEPRECATION")
        context.getSystemService(Context.VIBRATOR_SERVICE) as? Vibrator
    }

    var isSoundEnabled: Boolean = true

    private val bengaliNumbers = listOf(
        "", "এক", "দুই", "তিন", "চার", "পাঁচ", "ছয়", "সাত", "আট", "নয়", "দশ",
        "এগারো", "বারো", "তেরো", "চৌদ্দ", "পনেরো", "ষোলো", "সতেরো", "আঠারো", "উনিশ", "বিশ",
        "একুশ", "বাইশ", "তেইশ", "চব্বিশ", "পঁচিশ", "ছাব্বিশ", "সাতাশ", "আটাশ", "ঊনত্রিশ", "ত্রিশ"
    )

    init {
        try {
            tts = TextToSpeech(context, this)
            toneGenerator = ToneGenerator(AudioManager.STREAM_MUSIC, 90)
        } catch (_: Exception) {
        }
    }

    override fun onInit(status: Int) {
        if (status == TextToSpeech.SUCCESS) {
            isTtsReady = true
            tts?.setOnUtteranceProgressListener(object : UtteranceProgressListener() {
                override fun onStart(utteranceId: String?) {
                    onDuckingChange?.invoke(true)
                }

                override fun onDone(utteranceId: String?) {
                    onDuckingChange?.invoke(false)
                }

                @Deprecated("Deprecated in Java")
                override fun onError(utteranceId: String?) {
                    onDuckingChange?.invoke(false)
                }
            })
        }
    }

    private fun triggerTemporaryDuck(durationMs: Long) {
        onDuckingChange?.invoke(true)
        duckResetJob?.cancel()
        duckResetJob = scope.launch {
            delay(durationMs)
            onDuckingChange?.invoke(false)
        }
    }

    fun speak(textBn: String, textEn: String, lang: Language) {
        if (!isSoundEnabled) return

        val textToSpeak = if (lang == Language.BENGALI) textBn else textEn
        val targetLocale = if (lang == Language.BENGALI) Locale.forLanguageTag("bn-BD") else Locale.US

        triggerTemporaryDuck(1800L)

        if (isTtsReady && tts != null) {
            val supported = tts?.isLanguageAvailable(targetLocale)
            if (supported != TextToSpeech.LANG_NOT_SUPPORTED && supported != TextToSpeech.LANG_MISSING_DATA) {
                tts?.language = targetLocale
                tts?.speak(textToSpeak, TextToSpeech.QUEUE_FLUSH, null, "homefit_tts_${System.currentTimeMillis()}")
                return
            } else if (lang == Language.BENGALI) {
                // Fallback to English voice if device lacks Bengali TTS voice pack
                tts?.language = Locale.US
                tts?.speak(textEn, TextToSpeech.QUEUE_FLUSH, null, "homefit_tts_${System.currentTimeMillis()}")
                return
            }
        }
        // Fallback tone if TTS unavailable
        playToneBeep()
    }

    fun speakRepCount(repNumber: Int, lang: Language) {
        if (!isSoundEnabled) return
        val bnWord = if (repNumber in 1 until bengaliNumbers.size) bengaliNumbers[repNumber] else repNumber.toString()
        val enWord = repNumber.toString()
        try {
            toneGenerator?.startTone(ToneGenerator.TONE_PROP_ACK, 90)
        } catch (_: Exception) {
        }
        speak(bnWord, enWord, lang)
    }

    fun playToneBeep() {
        if (!isSoundEnabled) return
        try {
            toneGenerator?.startTone(ToneGenerator.TONE_PROP_BEEP, 140)
        } catch (_: Exception) {
        }
    }

    fun playToneStart() {
        if (!isSoundEnabled) return
        triggerTemporaryDuck(550L)
        scope.launch {
            try {
                toneGenerator?.startTone(ToneGenerator.TONE_PROP_BEEP2, 160)
                delay(180L)
                toneGenerator?.startTone(ToneGenerator.TONE_PROP_PROMPT, 280)
            } catch (_: Exception) {
            }
        }
    }

    fun playToneHalfway() {
        if (!isSoundEnabled) return
        triggerTemporaryDuck(400L)
        try {
            toneGenerator?.startTone(ToneGenerator.TONE_SUP_CONFIRM, 240)
        } catch (_: Exception) {
        }
    }

    fun playToneFinish() {
        if (!isSoundEnabled) return
        triggerTemporaryDuck(950L)
        scope.launch {
            try {
                toneGenerator?.startTone(ToneGenerator.TONE_PROP_BEEP, 150)
                delay(170L)
                toneGenerator?.startTone(ToneGenerator.TONE_PROP_PROMPT, 180)
                delay(200L)
                toneGenerator?.startTone(ToneGenerator.TONE_CDMA_ALERT_CALL_GUARD, 480)
            } catch (_: Exception) {
            }
        }
    }

    fun vibrateShort() {
        if (!isSoundEnabled) return
        try {
            if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
                vibrator?.vibrate(VibrationEffect.createOneShot(90, VibrationEffect.DEFAULT_AMPLITUDE))
            } else {
                @Suppress("DEPRECATION")
                vibrator?.vibrate(90)
            }
        } catch (_: Exception) {
        }
    }

    fun vibrateMedium() {
        if (!isSoundEnabled) return
        try {
            if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
                vibrator?.vibrate(VibrationEffect.createOneShot(240, VibrationEffect.DEFAULT_AMPLITUDE))
            } else {
                @Suppress("DEPRECATION")
                vibrator?.vibrate(240)
            }
        } catch (_: Exception) {
        }
    }

    fun release() {
        try {
            duckResetJob?.cancel()
            tts?.stop()
            tts?.shutdown()
            toneGenerator?.release()
        } catch (_: Exception) {
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/core/audio/WorkoutMusicManager.kt`

```kotlin
package com.example.core.audio

import android.content.Context
import android.media.AudioAttributes
import android.media.AudioFormat
import android.media.AudioTrack
import android.media.MediaPlayer
import android.net.Uri
import com.example.data.local.entity.SavedMusicTrackEntity
import kotlinx.coroutines.CoroutineScope
import kotlinx.coroutines.Dispatchers
import kotlinx.coroutines.Job
import kotlinx.coroutines.SupervisorJob
import kotlinx.coroutines.flow.MutableStateFlow
import kotlinx.coroutines.flow.StateFlow
import kotlinx.coroutines.flow.asStateFlow
import kotlinx.coroutines.flow.update
import kotlinx.coroutines.isActive
import kotlinx.coroutines.launch
import kotlin.math.PI
import kotlin.math.exp
import kotlin.math.sin

enum class OfflineBeatPreset(
    val id: String,
    val titleBn: String,
    val titleEn: String,
    val bpm: Int
) {
    NONE("none", "বন্ধ (Off)", "Off", 0),
    HIIT_128("hiit_128", "হাই-এনার্জি জিম বিট (128 BPM)", "High-Energy Gym Beat (128 BPM)", 128),
    POWER_110("power_110", "পাওয়ার স্ট্রেংথ রিদম (110 BPM)", "Power Strength Rhythm (110 BPM)", 110),
    FLOW_85("flow_85", "ফোকাস ও স্ট্রেচ পালস (85 BPM)", "Focus & Mobility Pulse (85 BPM)", 85)
}

data class WorkoutMusicState(
    val isPlaying: Boolean = false,
    val isDucked: Boolean = false,
    val currentTrackId: Long? = null,
    val currentTrackTitle: String? = null,
    val activeBeatPreset: OfflineBeatPreset = OfflineBeatPreset.NONE,
    val volume: Float = 0.85f
)

class WorkoutMusicManager(private val context: Context) {

    private val scope = CoroutineScope(SupervisorJob() + Dispatchers.Default)
    private var mediaPlayer: MediaPlayer? = null
    private var synthJob: Job? = null
    private var playlist: List<SavedMusicTrackEntity> = emptyList()

    private val _musicState = MutableStateFlow(WorkoutMusicState())
    val musicState: StateFlow<WorkoutMusicState> = _musicState.asStateFlow()

    fun updatePlaylist(tracks: List<SavedMusicTrackEntity>) {
        playlist = tracks
        val currentId = _musicState.value.currentTrackId
        if (currentId != null && tracks.none { it.id == currentId }) {
            stopAll()
        }
    }

    fun playLocalTrack(track: SavedMusicTrackEntity) {
        stopSynthBeat()
        releaseMediaPlayer()

        try {
            val uri = Uri.parse(track.uriString)
            val player = MediaPlayer().apply {
                setAudioAttributes(
                    AudioAttributes.Builder()
                        .setContentType(AudioAttributes.CONTENT_TYPE_MUSIC)
                        .setUsage(AudioAttributes.USAGE_MEDIA)
                        .build()
                )
                setDataSource(context, uri)
                isLooping = false
                setOnCompletionListener {
                    playNextLocalTrack()
                }
                prepare()
                val effVol = effectiveVolume()
                setVolume(effVol, effVol)
                start()
            }
            mediaPlayer = player
            _musicState.update {
                it.copy(
                    isPlaying = true,
                    currentTrackId = track.id,
                    currentTrackTitle = track.title,
                    activeBeatPreset = OfflineBeatPreset.NONE
                )
            }
        } catch (_: Exception) {
            // Fallback to built-in beat if URI is no longer accessible
            playBeatPreset(OfflineBeatPreset.HIIT_128)
        }
    }

    fun playNextLocalTrack() {
        if (playlist.isEmpty()) return
        val currentId = _musicState.value.currentTrackId
        val idx = playlist.indexOfFirst { it.id == currentId }
        val nextTrack = if (idx in 0 until playlist.size - 1) {
            playlist[idx + 1]
        } else {
            playlist.first()
        }
        playLocalTrack(nextTrack)
    }

    fun playPreviousLocalTrack() {
        if (playlist.isEmpty()) return
        val currentId = _musicState.value.currentTrackId
        val idx = playlist.indexOfFirst { it.id == currentId }
        val prevTrack = if (idx > 0) {
            playlist[idx - 1]
        } else {
            playlist.last()
        }
        playLocalTrack(prevTrack)
    }

    fun playBeatPreset(preset: OfflineBeatPreset) {
        if (preset == OfflineBeatPreset.NONE) {
            stopAll()
            return
        }
        releaseMediaPlayer()
        stopSynthBeat()

        _musicState.update {
            it.copy(
                isPlaying = true,
                currentTrackId = null,
                currentTrackTitle = preset.titleBn,
                activeBeatPreset = preset
            )
        }
        startSynthLoop(preset)
    }

    fun togglePlayPause() {
        val state = _musicState.value
        if (state.isPlaying) {
            pause()
        } else {
            resume()
        }
    }

    fun pause() {
        try {
            if (mediaPlayer?.isPlaying == true) {
                mediaPlayer?.pause()
            }
        } catch (_: Exception) {
        }
        stopSynthBeat()
        _musicState.update { it.copy(isPlaying = false) }
    }

    fun resume() {
        val state = _musicState.value
        if (state.activeBeatPreset != OfflineBeatPreset.NONE) {
            _musicState.update { it.copy(isPlaying = true) }
            startSynthLoop(state.activeBeatPreset)
        } else if (mediaPlayer != null) {
            try {
                val effVol = effectiveVolume()
                mediaPlayer?.setVolume(effVol, effVol)
                mediaPlayer?.start()
                _musicState.update { it.copy(isPlaying = true) }
            } catch (_: Exception) {
            }
        } else if (playlist.isNotEmpty()) {
            playLocalTrack(playlist.first())
        } else {
            playBeatPreset(OfflineBeatPreset.HIIT_128)
        }
    }

    fun setDucking(isDucked: Boolean) {
        _musicState.update { it.copy(isDucked = isDucked) }
        applyCurrentVolume()
    }

    fun setVolume(volume: Float) {
        _musicState.update { it.copy(volume = volume.coerceIn(0f, 1f)) }
        applyCurrentVolume()
    }

    private fun effectiveVolume(): Float {
        val state = _musicState.value
        return if (state.isDucked) state.volume * 0.22f else state.volume
    }

    private fun applyCurrentVolume() {
        try {
            val vol = effectiveVolume()
            mediaPlayer?.setVolume(vol, vol)
        } catch (_: Exception) {
        }
    }

    private fun startSynthLoop(preset: OfflineBeatPreset) {
        synthJob?.cancel()
        synthJob = scope.launch {
            val sampleRate = 22050
            val stepDurationSec = 60.0 / (preset.bpm.coerceAtLeast(60) * 4.0) // 16th note
            val samplesPerStep = (sampleRate * stepDurationSec).toInt().coerceAtLeast(512)
            val buffer = ShortArray(samplesPerStep)

            var audioTrack: AudioTrack? = null
            try {
                val minBufSize = AudioTrack.getMinBufferSize(
                    sampleRate,
                    AudioFormat.CHANNEL_OUT_MONO,
                    AudioFormat.ENCODING_PCM_16BIT
                ).coerceAtLeast(samplesPerStep * 2)

                audioTrack = AudioTrack.Builder()
                    .setAudioAttributes(
                        AudioAttributes.Builder()
                            .setUsage(AudioAttributes.USAGE_MEDIA)
                            .setContentType(AudioAttributes.CONTENT_TYPE_MUSIC)
                            .build()
                    )
                    .setAudioFormat(
                        AudioFormat.Builder()
                            .setEncoding(AudioFormat.ENCODING_PCM_16BIT)
                            .setSampleRate(sampleRate)
                            .setChannelMask(AudioFormat.CHANNEL_OUT_MONO)
                            .build()
                    )
                    .setBufferSizeInBytes(minBufSize)
                    .setTransferMode(AudioTrack.MODE_STREAM)
                    .build()

                audioTrack.play()

                var step = 0
                val bassFreqsHiit = doubleArrayOf(110.0, 110.0, 130.81, 146.83)
                val bassFreqsPower = doubleArrayOf(82.41, 82.41, 98.0, 92.5)
                val flowChords = doubleArrayOf(220.0, 261.63, 329.63, 196.0)

                while (isActive && _musicState.value.isPlaying && _musicState.value.activeBeatPreset == preset) {
                    val stepInBar = step % 16
                    val barIndex = (step / 16) % 4
                    val gain = effectiveVolume().toDouble()

                    val isKick = when (preset) {
                        OfflineBeatPreset.HIIT_128 -> stepInBar == 0 || stepInBar == 4 || stepInBar == 8 || stepInBar == 12
                        OfflineBeatPreset.POWER_110 -> stepInBar == 0 || stepInBar == 6 || stepInBar == 8 || stepInBar == 14
                        OfflineBeatPreset.FLOW_85 -> stepInBar == 0 || stepInBar == 8
                        else -> false
                    }
                    val isSnare = when (preset) {
                        OfflineBeatPreset.HIIT_128, OfflineBeatPreset.POWER_110 -> stepInBar == 4 || stepInBar == 12
                        OfflineBeatPreset.FLOW_85 -> stepInBar == 12
                        else -> false
                    }
                    val isHat = preset != OfflineBeatPreset.FLOW_85 && (stepInBar % 2 == 0)

                    val noteFreq = when (preset) {
                        OfflineBeatPreset.HIIT_128 -> bassFreqsHiit[barIndex] * if (stepInBar % 4 == 2) 1.5 else 1.0
                        OfflineBeatPreset.POWER_110 -> bassFreqsPower[barIndex]
                        OfflineBeatPreset.FLOW_85 -> flowChords[(stepInBar / 4) % 4]
                        else -> 110.0
                    }

                    for (i in 0 until samplesPerStep) {
                        val t = i.toDouble() / sampleRate
                        var sample = 0.0

                        if (isKick) {
                            // Pitch-dropping punchy kick drum
                            val kickFreq = 135.0 * exp(-t * 28.0) + 42.0
                            val kickEnv = exp(-t * 14.0)
                            sample += sin(2.0 * PI * kickFreq * t) * kickEnv * 0.65
                        }

                        if (isSnare) {
                            // Crisp snare burst
                            val snareEnv = exp(-t * 24.0)
                            val pseudoNoise = sin(2.0 * PI * 431.0 * t * (1.0 + sin(2.0 * PI * 179.0 * t)))
                            sample += pseudoNoise * snareEnv * 0.35
                        }

                        if (isHat) {
                            // Metallic hi-hat tick
                            val hatEnv = exp(-t * 48.0)
                            val hatWave = sin(2.0 * PI * 3200.0 * t) * sin(2.0 * PI * 5100.0 * t)
                            sample += hatWave * hatEnv * 0.18
                        }

                        // Synth bass / harmonic pulse
                        val synthEnv = if (preset == OfflineBeatPreset.FLOW_85) {
                            exp(-t * 4.5) * 0.30
                        } else {
                            exp(-t * 10.0) * 0.28
                        }
                        val synthWave = sin(2.0 * PI * noteFreq * t) + 0.3 * sin(4.0 * PI * noteFreq * t)
                        sample += synthWave * synthEnv

                        val scaled = (sample * gain * 26000.0).toInt().coerceIn(Short.MIN_VALUE.toInt(), Short.MAX_VALUE.toInt())
                        buffer[i] = scaled.toShort()
                    }

                    audioTrack.write(buffer, 0, samplesPerStep)
                    step++
                }
            } catch (_: Exception) {
            } finally {
                try {
                    audioTrack?.stop()
                    audioTrack?.release()
                } catch (_: Exception) {
                }
            }
        }
    }

    private fun stopSynthBeat() {
        synthJob?.cancel()
        synthJob = null
    }

    private fun releaseMediaPlayer() {
        try {
            mediaPlayer?.stop()
        } catch (_: Exception) {
        }
        try {
            mediaPlayer?.release()
        } catch (_: Exception) {
        }
        mediaPlayer = null
    }

    fun stopAll() {
        stopSynthBeat()
        releaseMediaPlayer()
        _musicState.update {
            it.copy(
                isPlaying = false,
                activeBeatPreset = OfflineBeatPreset.NONE
            )
        }
    }

    fun release() {
        stopAll()
    }
}
```

---

## FILE: `app/src/main/java/com/example/core/i18n/HomeFitStrings.kt`

```kotlin
package com.example.core.i18n

enum class Language(val code: String, val displayName: String) {
    BENGALI("bn", "বাংলা"),
    ENGLISH("en", "English")
}

data class AppStrings(
    // App & Common
    val appName: String,
    val appTagline: String,
    val continueBtn: String,
    val nextBtn: String,
    val backBtn: String,
    val skipBtn: String,
    val getStartedBtn: String,
    val saveBtn: String,
    val cancelBtn: String,
    val deleteBtn: String,

    // Splash
    val splashLoading: String,
    val splashSubtitle: String,

    // Welcome Slides
    val slide1Title: String,
    val slide1Desc: String,
    val slide2Title: String,
    val slide2Desc: String,
    val slide3Title: String,
    val slide3Desc: String,

    // Name Onboarding
    val nameTitle: String,
    val nameSubtitle: String,
    val namePlaceholder: String,
    val nameErrorEmpty: String,
    val nameErrorTooShort: String,

    // Profile Setup
    val profileTitle: String,
    val profileSubtitle: String,
    val ageLabel: String,
    val heightLabel: String,
    val weightLabel: String,
    val genderLabel: String,
    val genderMale: String,
    val genderFemale: String,
    val genderOther: String,
    val goalLabel: String,
    val goalWeightLoss: String,
    val goalMuscleBuilding: String,
    val goalGeneralFitness: String,
    val levelLabel: String,
    val levelBeginner: String,
    val levelIntermediate: String,
    val levelAdvanced: String,
    val daysPerWeekLabel: String,
    val daysUnit: String,
    val equipmentLabel: String,
    val equipNone: String,
    val equipBasic: String,
    val equipFull: String,

    // Metrics & Validation
    val liveMetricsTitle: String,
    val bmiLabel: String,
    val bmiUnderweight: String,
    val bmiNormal: String,
    val bmiOverweight: String,
    val bmiObese: String,
    val estCaloriesLabel: String,
    val estCaloriesNote: String,

    // Disclaimer
    val disclaimerTitle: String,
    val disclaimerWarning: String,
    val disclaimerBody: String,
    val disclaimerCheckbox: String,
    val disclaimerConfirmBtn: String,

    // Bottom Navigation
    val navHome: String,
    val navWorkouts: String,
    val navProgress: String,
    val navDiet: String,
    val navProfile: String,

    // Home Greetings
    val greetingMorning: String,
    val greetingAfternoon: String,
    val greetingLateAfternoon: String,
    val greetingEvening: String,
    val greetingNight: String,
    val phase1FoundationReady: String,
    val phase1Summary: String,

    // Phase 2 Smart Home Strings
    val todayWorkoutTitle: String,
    val startWorkoutBtn: String,
    val whyRecommended: String,
    val minutesUnit: String,
    val caloriesUnit: String,
    val exercisesUnit: String,
    val intensityLabel: String,

    val progressRingTitle: String,
    val streakTitle: String,
    val streakDaysUnit: String,
    val caloriesBurnedToday: String,
    val caloriesGoalLabel: String,

    val waterTrackerTitle: String,
    val waterGlassesUnit: String,
    val waterAddBtn: String,
    val waterUndoBtn: String,
    val waterTargetLabel: String,

    val stepTrackerTitle: String,
    val stepGoalUnit: String,
    val stepManualLogBtn: String,
    val stepSensorActive: String,
    val stepManualActive: String,
    val stepInputDialogTitle: String,
    val stepInputHint: String,

    val smartCoachTitle: String,
    val quickActionsTitle: String,
    val quick5Min: String,
    val quick10Min: String,
    val quick15Min: String,
    val logWeightTitle: String,
    val logWeightHint: String,
    val customWorkoutTitle: String,

    val weeklyCalendarTitle: String,
    val dayMon: String,
    val dayTue: String,
    val dayWed: String,
    val dayThu: String,
    val dayFri: String,
    val daySat: String,
    val daySun: String,
    val statusCompleted: String,
    val statusRest: String,
    val statusToday: String,

    // Settings
    val settingsTitle: String,
    val languageSetting: String,
    val themeSetting: String,
    val themeDark: String,
    val themeLight: String,
    val resetDataBtn: String,
    val resetConfirmTitle: String,
    val resetConfirmBody: String
)

object TranslationManager {
    val BengaliStrings = AppStrings(
        appName = "HomeFit",
        appTagline = "এলিট বায়োমেকানিক্স ও পারফরম্যান্স স্টুডিও",
        continueBtn = "পরবর্তী ধাপে এগিয়ে যান",
        nextBtn = "পরবর্তী প্রিভিউ",
        backBtn = "পেছনে",
        skipBtn = "সরাসরি সেটআপ",
        getStartedBtn = "এলিট ফিটনেস জার্নি শুরু করুন",
        saveBtn = "সংরক্ষণ করুন",
        cancelBtn = "বাতিল",
        deleteBtn = "মুছে ফেলুন",

        splashLoading = "সায়েন্টিফিক বায়োমেট্রিক ইঞ্জিন প্রস্তুত হচ্ছে...",
        splashSubtitle = "প্রাইভেট জিম স্টুডিও • ৩ডি মাসল অ্যানাটমি • ক্লিনিক্যাল নিউট্রিশন",

        slide1Title = "প্রাইভেট জিম ও হোম পারফরম্যান্স স্টুডিও",
        slide1Desc = "জিমের ডাম্বেল হোক বা ঘরের ফ্রি-হ্যান্ড ট্রেনিং—৩ডি মাসল অ্যানাটমি ও রিয়েল-টাইম জয়েন্ট অ্যাঙ্গেল গাইডের সাহায্যে প্রতিটি রেপ করুন নিখুঁত ফর্মে।",
        slide2Title = "ক্লিনিক্যাল BMR, TDEE ও হাইড্রেশন ইঞ্জিন",
        slide2Desc = "সবার জন্য গড়পড়তা ২ লিটার পানি বা ফেক ডেটা নয়! আপনার বয়স, ওজন (২৫–১৫০ কেজি) ও ঘামের হার অনুযায়ী প্রতি মিলিলিটার পানি ও প্রোটিনের নিখুঁত হিসাব।",
        slide3Title = "১০০% অফলাইন প্রাইভেসি ও প্রো অডিও বিটস",
        slide3Desc = "নিজের পছন্দের গান সেভ করে অটো-ডাকিং ভয়েস কোচের সাথে অনুশীলন করুন। ইন্টারনেট ছাড়াই আপনার সব বায়োমেট্রিক ডেটা থাকবে আপনার ফোনে সুরক্ষিত।",

        nameTitle = "অ্যাথলেট প্রোফাইল আইডেন্টিটি",
        nameSubtitle = "আপনার নাম বা ডাকনাম লিখুন—আপনার ব্যক্তিগত ট্রেনিং ড্যাশবোর্ড ও ভয়েস কোচ এই নামে আপনাকে সম্বোধন করবে।",
        namePlaceholder = "আপনার নাম লিখুন (যেমন: আরিয়ান / রাফি)",
        nameErrorEmpty = "অনুগ্রহ করে আপনার নাম লিখুন",
        nameErrorTooShort = "নাম কমপক্ষে ২ অক্ষরের হতে হবে",

        profileTitle = "বায়োমেট্রিক ও মেটাবলিক ক্যালিব্রেশন",
        profileSubtitle = "আপনার বয়স, ওজন ও ট্রেনিং লক্ষ্য অনুযায়ী সঠিক BMR, TDEE, প্রোটিন এবং পানির লক্ষ্যমাত্রা (ml/L) নির্ধারণ করুন।",
        ageLabel = "বয়স (বছর)",
        heightLabel = "উচ্চতা (সেমি)",
        weightLabel = "শরীরের ওজন (কেজি)",
        genderLabel = "জৈবিক মেটাবলিক প্রোফাইল",
        genderMale = "পুরুষ",
        genderFemale = "মহিলা",
        genderOther = "অন্যান্য",
        goalLabel = "প্রধান ট্রেনিং লক্ষ্য",
        goalWeightLoss = "ফ্যাট লস ও লিন শেপ",
        goalMuscleBuilding = "হাইপারট্রফি ও পেশি গঠন",
        goalGeneralFitness = "অ্যাথলেটিক স্ট্যামিনা ও ফিটনেস",
        levelLabel = "বর্তমান ট্রেনিং অভিজ্ঞতা",
        levelBeginner = "ফাউন্ডেশন (বিগিনার)",
        levelIntermediate = "অ্যাথলেটিক (ইন্টারমিডিয়েট)",
        levelAdvanced = "প্রো স্টুডিও (অ্যাডভান্সড)",
        daysPerWeekLabel = "সাপ্তাহিক ট্রেনিং সেশন",
        daysUnit = "দিন/সপ্তাহ",
        equipmentLabel = "উপলব্ধ ট্রেনিং সরঞ্জাম",
        equipNone = "বডি-ওয়েট (সরঞ্জাম ছাড়া)",
        equipBasic = "হোম বেসিক (চেয়ার/রেজিস্ট্যান্স)",
        equipFull = "জিম স্টুডিও (ডাম্বেল/বারবেল/ম্যাট)",

        liveMetricsTitle = "লাইভ ক্লিনিক্যাল বায়োমেট্রিক রিপোর্ট",
        bmiLabel = "বডি মাস ইনডেক্স (BMI)",
        bmiUnderweight = "কম ওজন (পুষ্টি বৃদ্ধি প্রয়োজন)",
        bmiNormal = "আদর্শ অ্যাথলেটিক রেঞ্জ",
        bmiOverweight = "অতিরিক্ত ওজন (ফ্যাট লস রেঞ্জ)",
        bmiObese = "উচ্চ ওজন (মেটাবলিক কেয়ার)",
        estCaloriesLabel = "দৈনিক ক্যালরি ও মেটাবলিক লক্ষ্য (TDEE)",
        estCaloriesNote = "Mifflin-St Jeor স্পোর্টস সায়েন্স সূত্র ও আপনার ওজন অনুযায়ী হিসাবকৃত।",

        disclaimerTitle = "বায়োমেকানিক্যাল নিরাপত্তা ও অঙ্গীকার",
        disclaimerWarning = "প্রফেশনাল ট্রেনিং প্রোটোকল",
        disclaimerBody = "HomeFit Pro আপনার শারীরিক তথ্যের ভিত্তিতে বৈজ্ঞানিক ওয়ার্কআউট ও পুষ্টি গাইড প্রদান করে। যেকোনো হাই-ইনটেনসিটি সেশন শুরুর আগে পর্যাপ্ত ওয়ার্ম-আপ করুন। শারীরিক অসুস্থতা, জয়েন্টে তীব্র ব্যথা বা মাথা ঘোরা অনুভব করলে অনুশীলন স্থগিত রেখে বিশেষজ্ঞ চিকিৎসকের পরামর্শ নিন।",
        disclaimerCheckbox = "আমি ট্রেনিং প্রোটোকল ও নিরাপত্তা নির্দেশনা পড়েছি এবং সম্মত আছি।",
        disclaimerConfirmBtn = "স্টুডিও ড্যাশবোর্ডে প্রবেশ করুন",

        navHome = "স্টুডিও",
        navWorkouts = "ওয়ার্কআউট",
        navProgress = "অ্যানালিটিক্স",
        navDiet = "নিউট্রিশন",
        navProfile = "প্রোফাইল",

        greetingMorning = "শুভ সকাল, চ্যাম্পিয়ন",
        greetingAfternoon = "শুভ দুপুর, অ্যাথলেট",
        greetingLateAfternoon = "শুভ বিকেল, প্রো",
        greetingEvening = "শুভ সন্ধ্যা, চ্যাম্পিয়ন",
        greetingNight = "শুভ রাত্রি, রিকভারি মোড",
        phase1FoundationReady = "সিস্টেম প্রস্তুত",
        phase1Summary = "সকল মডিউল সক্রিয় রয়েছে।",

        todayWorkoutTitle = "আজকের সিগনেচার ট্রেনিং সেশন",
        startWorkoutBtn = "সেশন প্রিভিউ ও শুরু করুন",
        whyRecommended = "বায়োমেট্রিক রিকমেন্ডেশন বিশ্লেষণ",
        minutesUnit = "মিনিট",
        caloriesUnit = "ক্যালরি",
        exercisesUnit = "টি এক্সারসাইজ",
        intensityLabel = "ইনটেনসিটি",

        progressRingTitle = "ডেইলি বায়োমেট্রিক টেলিমেট্রি",
        streakTitle = "অ্যাক্টিভ স্ট্রিক",
        streakDaysUnit = "দিন",
        caloriesBurnedToday = "ওয়ার্কআউট বার্ন",
        caloriesGoalLabel = "লক্ষ্য",

        waterTrackerTitle = "প্রিসিশন হাইড্রেশন ট্র্যাকার",
        waterGlassesUnit = "গ্লাস (২৫০ মি.লি.)",
        waterAddBtn = "+২৫০ মি.লি. পান করুন",
        waterUndoBtn = "-২৫০ মি.লি.",
        waterTargetLabel = "বৈজ্ঞানিক হাইড্রেশন লক্ষ্যমাত্রা",

        stepTrackerTitle = "ডেইলি অ্যাক্টিভ স্টেপস",
        stepGoalUnit = "স্টেপ",
        stepManualLogBtn = "স্টেপ আপডেট",
        stepSensorActive = "লাইভ সেন্সর সিঙ্ক",
        stepManualActive = "অফলাইন স্টেপ রেকর্ড",
        stepInputDialogTitle = "আজকের স্টেপ সংখ্যা রেকর্ড করুন",
        stepInputHint = "স্টেপ সংখ্যা লিখুন (যেমন: 6500)",

        smartCoachTitle = "এআই বায়োমেকানিক্যাল কোচ ব্রিফিং",
        quickActionsTitle = "ইন্সট্যান্ট স্টুডিও অ্যাকশন",
        quick5Min = "৫ মিনিট মেটাবলিক বুস্ট",
        quick10Min = "১০ মিনিট কোর স্কাল্পট",
        quick15Min = "১৫ মিনিট ফুল-বডি পাওয়ার",
        logWeightTitle = "ওজন ক্যালিব্রেশন",
        logWeightHint = "বর্তমান ওজন (কেজি)",
        customWorkoutTitle = "কাস্টম সেশন বিল্ডার",

        weeklyCalendarTitle = "সাপ্তাহিক ট্রেনিং ক্যালেন্ডার",
        dayMon = "সোম",
        dayTue = "মঙ্গল",
        dayWed = "বুধ",
        dayThu = "বৃহঃ",
        dayFri = "শুক্র",
        daySat = "শনি",
        daySun = "রবি",
        statusCompleted = "সম্পন্ন",
        statusRest = "বিশ্রাম",
        statusToday = "আজ",

        settingsTitle = "স্টুডিও সেটিংস ও বায়োমেট্রিক কনফিগারেশন",
        languageSetting = "ইন্টারফেস ভাষা (Language)",
        themeSetting = "স্টুডিও ভিজ্যুয়াল থিম",
        themeDark = "ডার্ক লাক্সারি জিম",
        themeLight = "লাইট স্টুডিও",
        resetDataBtn = "সমস্ত ডেটা রিসেট করে নতুন প্রোফাইল খুলুন",
        resetConfirmTitle = "প্রোফাইল ও ডেটা রিসেট করবেন?",
        resetConfirmBody = "ডিভাইসে সংরক্ষিত সমস্ত ওয়ার্কআউট লগ, ওজন ও হাইড্রেশন রেকর্ড স্থায়ীভাবে মুছে যাবে এবং নতুন করে বায়োমেট্রিক সেটআপ শুরু হবে।"
    )

    val EnglishStrings = AppStrings(
        appName = "HomeFit",
        appTagline = "Elite Biomechanics & Performance Studio",
        continueBtn = "Proceed to Next Step",
        nextBtn = "Next Preview",
        backBtn = "Back",
        skipBtn = "Fast-Track Setup",
        getStartedBtn = "Begin Your Elite Fitness Journey",
        saveBtn = "Save Changes",
        cancelBtn = "Cancel",
        deleteBtn = "Delete",

        splashLoading = "Calibrating Clinical Biometrics Engine...",
        splashSubtitle = "Private Gym Studio • 3D Muscle Anatomy • Clinical Nutrition",

        slide1Title = "Private Gym & Home Performance Studio",
        slide1Desc = "Whether training with gym dumbbells or bodyweight at home—master every rep with 3D-shaded muscle anatomy and real-time biomechanical alignment cues.",
        slide2Title = "Clinical BMR, TDEE & Hydration Engine",
        slide2Desc = "Zero fake data or generic 2-liter rules. Precision daily hydration (in ml & Liters), protein synthesis, and metabolic targets tailored to your exact weight (25–150 kg) and age.",
        slide3Title = "100% Offline Privacy & Pro Gym Beats",
        slide3Desc = "Import your favorite workout tracks with intelligent voice-coach audio ducking. All biometric telemetry stays 100% private on your device.",

        nameTitle = "Athlete Profile Identity",
        nameSubtitle = "Enter the name your personal training studio and voice coach will use during sessions.",
        namePlaceholder = "Enter your name (e.g. Aryan / Rafi)",
        nameErrorEmpty = "Please enter your athlete name",
        nameErrorTooShort = "Name must be at least 2 characters",

        profileTitle = "Biometric & Metabolic Calibration",
        profileSubtitle = "Configure your physical parameters to compute your clinical BMR, TDEE, protein synthesis, and exact daily water need (ml/L).",
        ageLabel = "Age (years)",
        heightLabel = "Height (cm)",
        weightLabel = "Body Weight (kg)",
        genderLabel = "Biological Metabolic Profile",
        genderMale = "Male",
        genderFemale = "Female",
        genderOther = "Other",
        goalLabel = "Primary Training Objective",
        goalWeightLoss = "Fat Loss & Lean Definition",
        goalMuscleBuilding = "Hypertrophy & Muscle Gain",
        goalGeneralFitness = "Athletic Stamina & Conditioning",
        levelLabel = "Current Training Experience",
        levelBeginner = "Foundation (Beginner)",
        levelIntermediate = "Athletic (Intermediate)",
        levelAdvanced = "Pro Studio (Advanced)",
        daysPerWeekLabel = "Weekly Training Frequency",
        daysUnit = "days/wk",
        equipmentLabel = "Available Training Equipment",
        equipNone = "Bodyweight Only (Zero Gear)",
        equipBasic = "Home Essentials (Chair/Bands)",
        equipFull = "Gym Studio (Dumbbells/Barbell/Mat)",

        liveMetricsTitle = "Live Clinical Biometric Report",
        bmiLabel = "Body Mass Index (BMI)",
        bmiUnderweight = "Underweight (Mass Support Needed)",
        bmiNormal = "Optimal Athletic Range",
        bmiOverweight = "Elevated Mass (Cut Phase)",
        bmiObese = "High Mass (Metabolic Conditioning)",
        estCaloriesLabel = "Daily Calorie & Metabolic Target (TDEE)",
        estCaloriesNote = "Calculated via Mifflin-St Jeor equation & weight-specific hydration science.",

        disclaimerTitle = "Biomechanical Safety Protocol",
        disclaimerWarning = "Clinical Training Advisory",
        disclaimerBody = "HomeFit Pro calculates exercise intensity and nutrition from sports science formulas. Always warm up before high-intensity intervals. Stop immediately if you experience sharp joint pain, dizziness, or chest discomfort.",
        disclaimerCheckbox = "I have reviewed and accept the biomechanical safety protocol.",
        disclaimerConfirmBtn = "Enter Studio Dashboard",

        navHome = "Studio",
        navWorkouts = "Workouts",
        navProgress = "Analytics",
        navDiet = "Nutrition",
        navProfile = "Profile",

        greetingMorning = "Good Morning, Champion",
        greetingAfternoon = "Good Afternoon, Athlete",
        greetingLateAfternoon = "Good Evening, Pro",
        greetingEvening = "Good Evening, Champion",
        greetingNight = "Night Recovery Mode",
        phase1FoundationReady = "System Calibrated",
        phase1Summary = "All studio modules are active.",

        todayWorkoutTitle = "Today's Signature Training Session",
        startWorkoutBtn = "Preview & Launch Session",
        whyRecommended = "Biometric Recommendation Analysis",
        minutesUnit = "min",
        caloriesUnit = "kcal",
        exercisesUnit = "exercises",
        intensityLabel = "Intensity",

        progressRingTitle = "Daily Biometric Telemetry",
        streakTitle = "Active Streak",
        streakDaysUnit = "Days",
        caloriesBurnedToday = "Workout Burn",
        caloriesGoalLabel = "Target",

        waterTrackerTitle = "Precision Hydration Studio",
        waterGlassesUnit = "glasses (250 ml)",
        waterAddBtn = "+250 ml Glass",
        waterUndoBtn = "-250 ml",
        waterTargetLabel = "Clinical Hydration Target",

        stepTrackerTitle = "Daily Active Steps",
        stepGoalUnit = "steps",
        stepManualLogBtn = "Update Steps",
        stepSensorActive = "Live Sensor Sync",
        stepManualActive = "Offline Step Record",
        stepInputDialogTitle = "Record Today's Step Count",
        stepInputHint = "Enter step count (e.g. 6500)",

        smartCoachTitle = "Biomechanical Coach Briefing",
        quickActionsTitle = "Instant Studio Sessions",
        quick5Min = "5-Min Metabolic Boost",
        quick10Min = "10-Min Core Sculpt",
        quick15Min = "15-Min Full-Body Power",
        logWeightTitle = "Calibrate Weight",
        logWeightHint = "Current weight in kg",
        customWorkoutTitle = "Custom Routine Builder",

        weeklyCalendarTitle = "Weekly Training Consistency",
        dayMon = "Mon",
        dayTue = "Tue",
        dayWed = "Wed",
        dayThu = "Thu",
        dayFri = "Fri",
        daySat = "Sat",
        daySun = "Sun",
        statusCompleted = "Done",
        statusRest = "Rest",
        statusToday = "Today",

        settingsTitle = "Studio Settings & Biometric Calibration",
        languageSetting = "Interface Language",
        themeSetting = "Studio Visual Theme",
        themeDark = "Dark Luxury Gym",
        themeLight = "Light Studio",
        resetDataBtn = "Reset All Telemetry & Re-Calibrate Profile",
        resetConfirmTitle = "Reset all profile telemetry?",
        resetConfirmBody = "All workout logs, weight history, and custom routines will be permanently cleared and biometric onboarding will restart."
    )

    fun get(lang: Language): AppStrings = when (lang) {
        Language.BENGALI -> BengaliStrings
        Language.ENGLISH -> EnglishStrings
    }
}
```

---

## FILE: `app/src/main/java/com/example/data/backup/LocalBackupManager.kt`

```kotlin
package com.example.data.backup

import androidx.room.withTransaction
import com.example.data.local.HomeFitDatabase
import com.example.data.local.entity.ChallengeProgressEntity
import com.example.data.local.entity.CustomWorkoutEntity
import com.example.data.local.entity.FavoriteExerciseEntity
import com.example.data.local.entity.NutritionLogEntity
import com.example.data.local.entity.SavedMusicTrackEntity
import com.example.data.local.entity.UserProfileEntity
import com.example.data.local.entity.WaterLogEntity
import com.example.data.local.entity.WeightLogEntity
import com.example.data.local.entity.WorkoutLogEntity
import org.json.JSONArray
import org.json.JSONObject

class LocalBackupManager(private val database: HomeFitDatabase) {

    private val userDao = database.userDao()
    private val logDao = database.logDao()
    private val workoutDao = database.workoutDao()

    suspend fun exportDataToJson(): String {
        val root = JSONObject()
        root.put("version", 2)
        root.put("exportedAtMillis", System.currentTimeMillis())

        // User Profile
        val user = userDao.getUserProfile()
        if (user != null) {
            val userJson = JSONObject().apply {
                put("id", user.id)
                put("name", user.name)
                put("age", user.age)
                put("heightCm", user.heightCm.toDouble())
                put("weightKg", user.weightKg.toDouble())
                put("gender", user.gender)
                put("goal", user.goal)
                put("fitnessLevel", user.fitnessLevel)
                put("workoutDaysPerWeek", user.workoutDaysPerWeek)
                put("equipment", user.equipment)
                put("preferredLanguage", user.preferredLanguage)
                put("isDarkMode", user.isDarkMode)
                put("isOnboardingCompleted", user.isOnboardingCompleted)
            }
            root.put("userProfile", userJson)
        }

        // Workout Logs
        val workouts = logDao.getAllWorkoutLogsOnce()
        val workoutsArray = JSONArray()
        for (w in workouts) {
            val wJson = JSONObject().apply {
                put("id", w.id)
                put("workoutTitle", w.workoutTitle)
                put("durationSeconds", w.durationSeconds)
                put("caloriesBurned", w.caloriesBurned)
                put("exercisesCompleted", w.exercisesCompleted)
                put("completedAtMillis", w.completedAtMillis)
            }
            workoutsArray.put(wJson)
        }
        root.put("workouts", workoutsArray)

        // Weight Logs
        val weights = logDao.getAllWeightLogsOnce()
        val weightsArray = JSONArray()
        for (wt in weights) {
            val wtJson = JSONObject().apply {
                put("id", wt.id)
                put("weightKg", wt.weightKg.toDouble())
                put("loggedAtMillis", wt.loggedAtMillis)
            }
            weightsArray.put(wtJson)
        }
        root.put("weights", weightsArray)

        // Water Logs
        val waters = logDao.getAllWaterLogsOnce()
        val watersArray = JSONArray()
        for (wt in waters) {
            val wtJson = JSONObject().apply {
                put("id", wt.id)
                put("glassesCount", wt.glassesCount)
                put("dateIso", wt.dateIso)
            }
            watersArray.put(wtJson)
        }
        root.put("waters", watersArray)

        // Favorites
        val favs = workoutDao.getAllFavoriteIdsOnce()
        val favsArray = JSONArray()
        favs.forEach { favsArray.put(it) }
        root.put("favorites", favsArray)

        // Custom Workouts
        val customs = workoutDao.getAllCustomWorkoutsOnce()
        val customsArray = JSONArray()
        for (c in customs) {
            val cJson = JSONObject().apply {
                put("id", c.id)
                put("title", c.title)
                put("exerciseIdsCsv", c.exerciseIdsCsv)
                put("durationSecondsPerExercise", c.durationSecondsPerExercise)
                put("restSeconds", c.restSeconds)
                put("createdAtMillis", c.createdAtMillis)
            }
            customsArray.put(cJson)
        }
        root.put("customWorkouts", customsArray)

        // Daily Nutrition Logs
        val nutritions = logDao.getAllNutritionLogsOnce()
        val nutritionsArray = JSONArray()
        for (n in nutritions) {
            val nJson = JSONObject().apply {
                put("id", n.id)
                put("dateIso", n.dateIso)
                put("foodNameBn", n.foodNameBn)
                put("foodNameEn", n.foodNameEn)
                put("calories", n.calories)
                put("proteinGrams", n.proteinGrams.toDouble())
                put("carbsGrams", n.carbsGrams.toDouble())
                put("fatGrams", n.fatGrams.toDouble())
                put("loggedAtMillis", n.loggedAtMillis)
            }
            nutritionsArray.put(nJson)
        }
        root.put("nutritionLogs", nutritionsArray)

        // Saved Music Tracks
        val tracks = logDao.getAllMusicTracksOnce()
        val tracksArray = JSONArray()
        for (t in tracks) {
            val tJson = JSONObject().apply {
                put("id", t.id)
                put("uriString", t.uriString)
                put("title", t.title)
                put("addedAtMillis", t.addedAtMillis)
            }
            tracksArray.put(tJson)
        }
        root.put("musicTracks", tracksArray)

        // Challenge Progress
        val challenges = logDao.getAllChallengeProgressOnce()
        val challengesArray = JSONArray()
        for (ch in challenges) {
            val chJson = JSONObject().apply {
                put("challengeId", ch.challengeId)
                put("completedDaysCsv", ch.completedDaysCsv)
                put("updatedAtMillis", ch.updatedAtMillis)
            }
            challengesArray.put(chJson)
        }
        root.put("challengeProgress", challengesArray)

        return root.toString(2)
    }

    suspend fun importDataFromJson(jsonString: String): Boolean {
        return try {
            val root = JSONObject(jsonString)

            database.withTransaction {
                // User Profile
                if (root.has("userProfile") && !root.isNull("userProfile")) {
                    val u = root.getJSONObject("userProfile")
                    val entity = UserProfileEntity(
                        id = u.optInt("id", 1),
                        name = u.optString("name", "User"),
                        age = u.optInt("age", 24),
                        heightCm = u.optDouble("heightCm", 170.0).toFloat(),
                        weightKg = u.optDouble("weightKg", 65.0).toFloat(),
                        gender = u.optString("gender", "male"),
                        goal = u.optString("goal", "fitness"),
                        fitnessLevel = u.optString("fitnessLevel", "beginner"),
                        workoutDaysPerWeek = u.optInt("workoutDaysPerWeek", 4),
                        equipment = u.optString("equipment", "none"),
                        preferredLanguage = u.optString("preferredLanguage", "bn"),
                        isDarkMode = u.optBoolean("isDarkMode", true),
                        isOnboardingCompleted = u.optBoolean("isOnboardingCompleted", true)
                    )
                    userDao.saveUserProfile(entity)
                }

                // Workouts
                if (root.has("workouts")) {
                    val arr = root.getJSONArray("workouts")
                    for (i in 0 until arr.length()) {
                        val w = arr.getJSONObject(i)
                        logDao.insertWorkoutLog(
                            WorkoutLogEntity(
                                id = w.optLong("id", 0L),
                                workoutTitle = w.optString("workoutTitle", "Workout"),
                                durationSeconds = w.optInt("durationSeconds", 600),
                                caloriesBurned = w.optInt("caloriesBurned", 100),
                                exercisesCompleted = w.optInt("exercisesCompleted", 5),
                                completedAtMillis = w.optLong("completedAtMillis", System.currentTimeMillis())
                            )
                        )
                    }
                }

                // Weights
                if (root.has("weights")) {
                    val arr = root.getJSONArray("weights")
                    for (i in 0 until arr.length()) {
                        val wt = arr.getJSONObject(i)
                        logDao.insertWeightLog(
                            WeightLogEntity(
                                id = wt.optLong("id", 0L),
                                weightKg = wt.optDouble("weightKg", 65.0).toFloat(),
                                loggedAtMillis = wt.optLong("loggedAtMillis", System.currentTimeMillis())
                            )
                        )
                    }
                }

                // Waters
                if (root.has("waters")) {
                    val arr = root.getJSONArray("waters")
                    for (i in 0 until arr.length()) {
                        val wt = arr.getJSONObject(i)
                        logDao.insertWaterLog(
                            WaterLogEntity(
                                id = wt.optLong("id", 0L),
                                glassesCount = wt.optInt("glassesCount", 0),
                                dateIso = wt.optString("dateIso", "2026-10-01")
                            )
                        )
                    }
                }

                // Favorites
                if (root.has("favorites")) {
                    val arr = root.getJSONArray("favorites")
                    for (i in 0 until arr.length()) {
                        val favId = arr.getString(i)
                        workoutDao.addFavorite(FavoriteExerciseEntity(exerciseId = favId))
                    }
                }

                // Custom Workouts
                if (root.has("customWorkouts")) {
                    val arr = root.getJSONArray("customWorkouts")
                    for (i in 0 until arr.length()) {
                        val c = arr.getJSONObject(i)
                        workoutDao.insertCustomWorkout(
                            CustomWorkoutEntity(
                                id = c.optLong("id", 0L),
                                title = c.optString("title", "Custom"),
                                exerciseIdsCsv = c.optString("exerciseIdsCsv", ""),
                                durationSecondsPerExercise = c.optInt("durationSecondsPerExercise", 30),
                                restSeconds = c.optInt("restSeconds", 15),
                                createdAtMillis = c.optLong("createdAtMillis", System.currentTimeMillis())
                            )
                        )
                    }
                }

                // Nutrition Logs
                if (root.has("nutritionLogs")) {
                    val arr = root.getJSONArray("nutritionLogs")
                    for (i in 0 until arr.length()) {
                        val n = arr.getJSONObject(i)
                        logDao.insertNutritionLog(
                            NutritionLogEntity(
                                id = n.optLong("id", 0L),
                                dateIso = n.optString("dateIso", "2026-10-01"),
                                foodNameBn = n.optString("foodNameBn", "খাবার"),
                                foodNameEn = n.optString("foodNameEn", "Food"),
                                calories = n.optInt("calories", 100),
                                proteinGrams = n.optDouble("proteinGrams", 5.0).toFloat(),
                                carbsGrams = n.optDouble("carbsGrams", 10.0).toFloat(),
                                fatGrams = n.optDouble("fatGrams", 2.0).toFloat(),
                                loggedAtMillis = n.optLong("loggedAtMillis", System.currentTimeMillis())
                            )
                        )
                    }
                }

                // Music Tracks
                if (root.has("musicTracks")) {
                    val arr = root.getJSONArray("musicTracks")
                    for (i in 0 until arr.length()) {
                        val t = arr.getJSONObject(i)
                        logDao.insertMusicTrack(
                            SavedMusicTrackEntity(
                                id = t.optLong("id", 0L),
                                uriString = t.optString("uriString", ""),
                                title = t.optString("title", "Track"),
                                addedAtMillis = t.optLong("addedAtMillis", System.currentTimeMillis())
                            )
                        )
                    }
                }

                // Challenge Progress
                if (root.has("challengeProgress")) {
                    val arr = root.getJSONArray("challengeProgress")
                    for (i in 0 until arr.length()) {
                        val ch = arr.getJSONObject(i)
                        logDao.upsertChallengeProgress(
                            ChallengeProgressEntity(
                                challengeId = ch.optString("challengeId", "full_body_30"),
                                completedDaysCsv = ch.optString("completedDaysCsv", ""),
                                updatedAtMillis = ch.optLong("updatedAtMillis", System.currentTimeMillis())
                            )
                        )
                    }
                }
            }
            true
        } catch (_: Exception) {
            false
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/data/local/HomeFitDatabase.kt`

```kotlin
package com.example.data.local

import android.content.Context
import androidx.room.Database
import androidx.room.Room
import androidx.room.RoomDatabase
import androidx.room.migration.Migration
import androidx.sqlite.db.SupportSQLiteDatabase
import com.example.data.local.dao.LogDao
import com.example.data.local.dao.UserDao
import com.example.data.local.dao.WorkoutDao
import com.example.data.local.entity.ChallengeProgressEntity
import com.example.data.local.entity.CustomWorkoutEntity
import com.example.data.local.entity.FavoriteExerciseEntity
import com.example.data.local.entity.NutritionLogEntity
import com.example.data.local.entity.SavedMusicTrackEntity
import com.example.data.local.entity.UserProfileEntity
import com.example.data.local.entity.WaterLogEntity
import com.example.data.local.entity.WeightLogEntity
import com.example.data.local.entity.WorkoutLogEntity

@Database(
    entities = [
        UserProfileEntity::class,
        WorkoutLogEntity::class,
        WeightLogEntity::class,
        WaterLogEntity::class,
        FavoriteExerciseEntity::class,
        CustomWorkoutEntity::class,
        NutritionLogEntity::class,
        SavedMusicTrackEntity::class,
        ChallengeProgressEntity::class
    ],
    version = 4,
    exportSchema = false
)
abstract class HomeFitDatabase : RoomDatabase() {
    abstract fun userDao(): UserDao
    abstract fun logDao(): LogDao
    abstract fun workoutDao(): WorkoutDao

    companion object {
        @Volatile
        private var INSTANCE: HomeFitDatabase? = null

        val MIGRATION_1_2 = object : Migration(1, 2) {
            override fun migrate(db: SupportSQLiteDatabase) {
                db.execSQL("CREATE TABLE IF NOT EXISTS `favorite_exercises` (`exerciseId` TEXT NOT NULL, `savedAtMillis` INTEGER NOT NULL, PRIMARY KEY(`exerciseId`))")
                db.execSQL("CREATE TABLE IF NOT EXISTS `custom_workouts` (`id` INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, `title` TEXT NOT NULL, `exerciseIdsCsv` TEXT NOT NULL, `durationMinutes` INTEGER NOT NULL, `restSecondsBetween` INTEGER NOT NULL, `createdAtMillis` INTEGER NOT NULL)")
            }
        }

        val MIGRATION_2_3 = object : Migration(2, 3) {
            override fun migrate(db: SupportSQLiteDatabase) {
                db.execSQL("CREATE INDEX IF NOT EXISTS `index_workout_logs_completedAtMillis` ON `workout_logs` (`completedAtMillis`)")
                db.execSQL("CREATE INDEX IF NOT EXISTS `index_weight_logs_loggedAtMillis` ON `weight_logs` (`loggedAtMillis`)")
                db.execSQL("DELETE FROM `water_logs` WHERE id NOT IN (SELECT MAX(id) FROM `water_logs` GROUP BY `dateIso`)")
                db.execSQL("CREATE UNIQUE INDEX IF NOT EXISTS `index_water_logs_dateIso` ON `water_logs` (`dateIso`)")
            }
        }

        val MIGRATION_3_4 = object : Migration(3, 4) {
            override fun migrate(db: SupportSQLiteDatabase) {
                db.execSQL(
                    "CREATE TABLE IF NOT EXISTS `daily_nutrition_logs` (`id` INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, `dateIso` TEXT NOT NULL, `foodNameBn` TEXT NOT NULL, `foodNameEn` TEXT NOT NULL, `calories` INTEGER NOT NULL, `proteinGrams` REAL NOT NULL, `carbsGrams` REAL NOT NULL, `fatGrams` REAL NOT NULL, `loggedAtMillis` INTEGER NOT NULL)"
                )
                db.execSQL(
                    "CREATE INDEX IF NOT EXISTS `index_daily_nutrition_logs_dateIso` ON `daily_nutrition_logs` (`dateIso`)"
                )
                db.execSQL(
                    "CREATE TABLE IF NOT EXISTS `saved_music_tracks` (`id` INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, `uriString` TEXT NOT NULL, `title` TEXT NOT NULL, `addedAtMillis` INTEGER NOT NULL)"
                )
                db.execSQL(
                    "CREATE TABLE IF NOT EXISTS `challenge_progress` (`challengeId` TEXT NOT NULL, `completedDaysCsv` TEXT NOT NULL, `updatedAtMillis` INTEGER NOT NULL, PRIMARY KEY(`challengeId`))"
                )
            }
        }

        fun getDatabase(context: Context): HomeFitDatabase {
            return INSTANCE ?: synchronized(this) {
                val instance = Room.databaseBuilder(
                    context.applicationContext,
                    HomeFitDatabase::class.java,
                    "homefit_offline.db"
                )
                    .addMigrations(MIGRATION_1_2, MIGRATION_2_3, MIGRATION_3_4)
                    .build()
                INSTANCE = instance
                instance
            }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/data/local/dao/LogDao.kt`

```kotlin
package com.example.data.local.dao

import androidx.room.Dao
import androidx.room.Insert
import androidx.room.OnConflictStrategy
import androidx.room.Query
import com.example.data.local.entity.ChallengeProgressEntity
import com.example.data.local.entity.NutritionLogEntity
import com.example.data.local.entity.SavedMusicTrackEntity
import com.example.data.local.entity.WaterLogEntity
import com.example.data.local.entity.WeightLogEntity
import com.example.data.local.entity.WorkoutLogEntity
import kotlinx.coroutines.flow.Flow

@Dao
interface LogDao {
    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun insertWorkoutLog(log: WorkoutLogEntity): Long

    @Query("SELECT * FROM workout_logs ORDER BY completedAtMillis DESC")
    fun getAllWorkoutLogsFlow(): Flow<List<WorkoutLogEntity>>

    @Query("SELECT * FROM workout_logs ORDER BY completedAtMillis DESC LIMIT 1")
    suspend fun getLatestWorkoutLog(): WorkoutLogEntity?

    @Query("SELECT COUNT(*) FROM workout_logs")
    suspend fun getWorkoutCount(): Int

    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun insertWeightLog(log: WeightLogEntity): Long

    @Query("SELECT * FROM weight_logs ORDER BY loggedAtMillis DESC")
    fun getAllWeightLogsFlow(): Flow<List<WeightLogEntity>>

    @Query("SELECT * FROM weight_logs ORDER BY loggedAtMillis DESC LIMIT 1")
    suspend fun getLatestWeightLog(): WeightLogEntity?

    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun insertWaterLog(log: WaterLogEntity): Long

    @Query("SELECT * FROM water_logs WHERE dateIso = :dateIso LIMIT 1")
    fun getWaterLogForDate(dateIso: String): Flow<WaterLogEntity?>

    @Query("SELECT * FROM water_logs WHERE dateIso = :dateIso LIMIT 1")
    suspend fun getWaterLogForDateOnce(dateIso: String): WaterLogEntity?

    @Query("SELECT * FROM water_logs ORDER BY dateIso DESC")
    fun getAllWaterLogsFlow(): Flow<List<WaterLogEntity>>

    @Query("SELECT * FROM workout_logs ORDER BY completedAtMillis DESC")
    suspend fun getAllWorkoutLogsOnce(): List<WorkoutLogEntity>

    @Query("SELECT * FROM weight_logs ORDER BY loggedAtMillis DESC")
    suspend fun getAllWeightLogsOnce(): List<WeightLogEntity>

    @Query("SELECT * FROM water_logs ORDER BY dateIso DESC")
    suspend fun getAllWaterLogsOnce(): List<WaterLogEntity>

    // Daily Nutrition Logs
    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun insertNutritionLog(log: NutritionLogEntity): Long

    @Query("SELECT * FROM daily_nutrition_logs WHERE dateIso = :dateIso ORDER BY loggedAtMillis DESC")
    fun getNutritionLogsForDateFlow(dateIso: String): Flow<List<NutritionLogEntity>>

    @Query("SELECT * FROM daily_nutrition_logs ORDER BY loggedAtMillis DESC")
    fun getAllNutritionLogsFlow(): Flow<List<NutritionLogEntity>>

    @Query("SELECT * FROM daily_nutrition_logs ORDER BY loggedAtMillis DESC")
    suspend fun getAllNutritionLogsOnce(): List<NutritionLogEntity>

    @Query("DELETE FROM daily_nutrition_logs WHERE id = :id")
    suspend fun deleteNutritionLog(id: Long)

    @Query("DELETE FROM daily_nutrition_logs")
    suspend fun clearNutritionLogs()

    // Saved Music Tracks
    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun insertMusicTrack(track: SavedMusicTrackEntity): Long

    @Query("SELECT * FROM saved_music_tracks ORDER BY addedAtMillis DESC")
    fun getAllMusicTracksFlow(): Flow<List<SavedMusicTrackEntity>>

    @Query("SELECT * FROM saved_music_tracks ORDER BY addedAtMillis DESC")
    suspend fun getAllMusicTracksOnce(): List<SavedMusicTrackEntity>

    @Query("DELETE FROM saved_music_tracks WHERE id = :id")
    suspend fun deleteMusicTrack(id: Long)

    @Query("DELETE FROM saved_music_tracks")
    suspend fun clearMusicTracks()

    // 30-Day Challenge Progress
    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun upsertChallengeProgress(progress: ChallengeProgressEntity)

    @Query("SELECT * FROM challenge_progress WHERE challengeId = :challengeId LIMIT 1")
    suspend fun getChallengeProgressOnce(challengeId: String): ChallengeProgressEntity?

    @Query("SELECT * FROM challenge_progress")
    fun getAllChallengeProgressFlow(): Flow<List<ChallengeProgressEntity>>

    @Query("SELECT * FROM challenge_progress")
    suspend fun getAllChallengeProgressOnce(): List<ChallengeProgressEntity>

    @Query("DELETE FROM challenge_progress")
    suspend fun clearChallengeProgress()

    @Query("DELETE FROM workout_logs")
    suspend fun clearWorkoutLogs()

    @Query("DELETE FROM weight_logs")
    suspend fun clearWeightLogs()

    @Query("DELETE FROM water_logs")
    suspend fun clearWaterLogs()
}
```

---

## FILE: `app/src/main/java/com/example/data/local/dao/UserDao.kt`

```kotlin
package com.example.data.local.dao

import androidx.room.Dao
import androidx.room.Insert
import androidx.room.OnConflictStrategy
import androidx.room.Query
import com.example.data.local.entity.UserProfileEntity
import kotlinx.coroutines.flow.Flow

@Dao
interface UserDao {
    @Query("SELECT * FROM user_profile WHERE id = 1 LIMIT 1")
    fun getUserProfileFlow(): Flow<UserProfileEntity?>

    @Query("SELECT * FROM user_profile WHERE id = 1 LIMIT 1")
    suspend fun getUserProfile(): UserProfileEntity?

    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun saveUserProfile(profile: UserProfileEntity)

    @Query("UPDATE user_profile SET preferredLanguage = :language WHERE id = 1")
    suspend fun updateLanguage(language: String)

    @Query("UPDATE user_profile SET isDarkMode = :isDarkMode WHERE id = 1")
    suspend fun updateTheme(isDarkMode: Boolean)

    @Query("DELETE FROM user_profile")
    suspend fun deleteUserProfile()
}
```

---

## FILE: `app/src/main/java/com/example/data/local/dao/WorkoutDao.kt`

```kotlin
package com.example.data.local.dao

import androidx.room.Dao
import androidx.room.Insert
import androidx.room.OnConflictStrategy
import androidx.room.Query
import com.example.data.local.entity.CustomWorkoutEntity
import com.example.data.local.entity.FavoriteExerciseEntity
import kotlinx.coroutines.flow.Flow

@Dao
interface WorkoutDao {
    // Favorites
    @Query("SELECT exerciseId FROM favorite_exercises")
    fun getAllFavoriteIdsFlow(): Flow<List<String>>

    @Query("SELECT exerciseId FROM favorite_exercises")
    suspend fun getAllFavoriteIdsOnce(): List<String>

    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun addFavorite(fav: FavoriteExerciseEntity)

    @Query("DELETE FROM favorite_exercises WHERE exerciseId = :exerciseId")
    suspend fun removeFavorite(exerciseId: String)

    @Query("SELECT COUNT(*) FROM favorite_exercises WHERE exerciseId = :exerciseId")
    suspend fun isFavorite(exerciseId: String): Int

    // Custom Workouts
    @Query("SELECT * FROM custom_workouts ORDER BY createdAtMillis DESC")
    fun getAllCustomWorkoutsFlow(): Flow<List<CustomWorkoutEntity>>

    @Query("SELECT * FROM custom_workouts ORDER BY createdAtMillis DESC")
    suspend fun getAllCustomWorkoutsOnce(): List<CustomWorkoutEntity>

    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun insertCustomWorkout(workout: CustomWorkoutEntity): Long

    @Query("DELETE FROM custom_workouts WHERE id = :id")
    suspend fun deleteCustomWorkout(id: Long)

    @Query("DELETE FROM favorite_exercises")
    suspend fun clearFavorites()

    @Query("DELETE FROM custom_workouts")
    suspend fun clearCustomWorkouts()
}
```

---

## FILE: `app/src/main/java/com/example/data/local/entity/CustomWorkoutEntities.kt`

```kotlin
package com.example.data.local.entity

import androidx.room.Entity
import androidx.room.PrimaryKey

@Entity(tableName = "favorite_exercises")
data class FavoriteExerciseEntity(
    @PrimaryKey val exerciseId: String,
    val addedAtMillis: Long = System.currentTimeMillis()
)

@Entity(tableName = "custom_workouts")
data class CustomWorkoutEntity(
    @PrimaryKey(autoGenerate = true) val id: Long = 0,
    val title: String,
    val exerciseIdsCsv: String,
    val durationSecondsPerExercise: Int = 30,
    val restSeconds: Int = 15,
    val createdAtMillis: Long = System.currentTimeMillis()
)
```

---

## FILE: `app/src/main/java/com/example/data/local/entity/LogEntities.kt`

```kotlin
package com.example.data.local.entity

import androidx.room.Entity
import androidx.room.Index
import androidx.room.PrimaryKey

@Entity(
    tableName = "workout_logs",
    indices = [Index(value = ["completedAtMillis"], name = "index_workout_logs_completedAtMillis")]
)
data class WorkoutLogEntity(
    @PrimaryKey(autoGenerate = true) val id: Long = 0,
    val workoutTitle: String,
    val durationSeconds: Int,
    val caloriesBurned: Int,
    val exercisesCompleted: Int,
    val completedAtMillis: Long = System.currentTimeMillis()
)

@Entity(
    tableName = "weight_logs",
    indices = [Index(value = ["loggedAtMillis"], name = "index_weight_logs_loggedAtMillis")]
)
data class WeightLogEntity(
    @PrimaryKey(autoGenerate = true) val id: Long = 0,
    val weightKg: Float,
    val loggedAtMillis: Long = System.currentTimeMillis()
)

@Entity(
    tableName = "water_logs",
    indices = [Index(value = ["dateIso"], unique = true, name = "index_water_logs_dateIso")]
)
data class WaterLogEntity(
    @PrimaryKey(autoGenerate = true) val id: Long = 0,
    val glassesCount: Int,
    val dateIso: String
)

@Entity(
    tableName = "daily_nutrition_logs",
    indices = [Index(value = ["dateIso"], name = "index_daily_nutrition_logs_dateIso")]
)
data class NutritionLogEntity(
    @PrimaryKey(autoGenerate = true) val id: Long = 0,
    val dateIso: String,
    val foodNameBn: String,
    val foodNameEn: String,
    val calories: Int,
    val proteinGrams: Float,
    val carbsGrams: Float = 0f,
    val fatGrams: Float = 0f,
    val loggedAtMillis: Long = System.currentTimeMillis()
)

@Entity(tableName = "saved_music_tracks")
data class SavedMusicTrackEntity(
    @PrimaryKey(autoGenerate = true) val id: Long = 0,
    val uriString: String,
    val title: String,
    val addedAtMillis: Long = System.currentTimeMillis()
)

@Entity(tableName = "challenge_progress")
data class ChallengeProgressEntity(
    @PrimaryKey val challengeId: String,
    val completedDaysCsv: String,
    val updatedAtMillis: Long = System.currentTimeMillis()
)

```

---

## FILE: `app/src/main/java/com/example/data/local/entity/UserProfileEntity.kt`

```kotlin
package com.example.data.local.entity

import androidx.room.Entity
import androidx.room.PrimaryKey

@Entity(tableName = "user_profile")
data class UserProfileEntity(
    @PrimaryKey val id: Int = 1,
    val name: String,
    val age: Int,
    val heightCm: Float,
    val weightKg: Float,
    val gender: String,
    val goal: String,
    val fitnessLevel: String,
    val workoutDaysPerWeek: Int,
    val equipment: String,
    val preferredLanguage: String = "bn",
    val isDarkMode: Boolean = true,
    val isOnboardingCompleted: Boolean = false,
    val createdAtMillis: Long = System.currentTimeMillis()
)
```

---

## FILE: `app/src/main/java/com/example/data/repository/RoomStorageService.kt`

```kotlin
package com.example.data.repository

import com.example.data.backup.LocalBackupManager
import com.example.data.local.HomeFitDatabase
import com.example.data.local.entity.ChallengeProgressEntity
import com.example.data.local.entity.CustomWorkoutEntity
import com.example.data.local.entity.FavoriteExerciseEntity
import com.example.data.local.entity.NutritionLogEntity
import com.example.data.local.entity.SavedMusicTrackEntity
import com.example.data.local.entity.UserProfileEntity
import com.example.data.local.entity.WaterLogEntity
import com.example.data.local.entity.WeightLogEntity
import com.example.data.local.entity.WorkoutLogEntity
import com.example.domain.model.UserProfile
import com.example.domain.service.StorageService
import kotlinx.coroutines.flow.Flow
import kotlinx.coroutines.flow.firstOrNull
import kotlinx.coroutines.flow.map
import java.util.Calendar
import java.util.concurrent.TimeUnit

class RoomStorageService(private val database: HomeFitDatabase) : StorageService {

    private val userDao = database.userDao()
    private val logDao = database.logDao()
    private val workoutDao = database.workoutDao()
    private val backupManager = LocalBackupManager(database)

    override fun getUserProfileFlow(): Flow<UserProfile?> {
        return userDao.getUserProfileFlow().map { entity ->
            entity?.toDomainModel()
        }
    }

    override suspend fun getUserProfile(): UserProfile? {
        return userDao.getUserProfile()?.toDomainModel()
    }

    override suspend fun saveUserProfile(profile: UserProfile) {
        userDao.saveUserProfile(profile.toEntity())
    }

    override suspend fun updateLanguage(langCode: String) {
        userDao.updateLanguage(langCode)
    }

    override suspend fun updateTheme(isDarkMode: Boolean) {
        userDao.updateTheme(isDarkMode)
    }

    override suspend fun markOnboardingComplete() {
        val current = userDao.getUserProfile()
        if (current != null) {
            userDao.saveUserProfile(current.copy(isOnboardingCompleted = true))
        }
    }

    override fun getTodayWaterGlassesFlow(dateIso: String): Flow<Int> {
        return logDao.getWaterLogForDate(dateIso).map { entity ->
            entity?.glassesCount ?: 0
        }
    }

    override fun getAllWaterLogsFlow(): Flow<List<WaterLogEntity>> {
        return logDao.getAllWaterLogsFlow()
    }

    override suspend fun addWaterGlass(dateIso: String): Int {
        val current = logDao.getWaterLogForDateOnce(dateIso)
        val newCount = (current?.glassesCount ?: 0) + 1
        logDao.insertWaterLog(
            WaterLogEntity(
                id = current?.id ?: 0,
                glassesCount = newCount,
                dateIso = dateIso
            )
        )
        return newCount
    }

    override suspend fun removeWaterGlass(dateIso: String): Int {
        val current = logDao.getWaterLogForDateOnce(dateIso) ?: return 0
        val newCount = (current.glassesCount - 1).coerceAtLeast(0)
        logDao.insertWaterLog(current.copy(glassesCount = newCount))
        return newCount
    }

    override fun getLatestWeightFlow(): Flow<Float?> {
        return logDao.getAllWeightLogsFlow().map { logs ->
            logs.firstOrNull()?.weightKg
        }
    }

    override fun getAllWeightLogsFlow(): Flow<List<WeightLogEntity>> {
        return logDao.getAllWeightLogsFlow()
    }

    override suspend fun logWeight(weightKg: Float) {
        logDao.insertWeightLog(
            WeightLogEntity(
                weightKg = weightKg,
                loggedAtMillis = System.currentTimeMillis()
            )
        )
        val currentProfile = userDao.getUserProfile()
        if (currentProfile != null) {
            userDao.saveUserProfile(currentProfile.copy(weightKg = weightKg))
        }
    }

    override fun getTodayCaloriesBurnedFlow(): Flow<Int> {
        val startOfDay = getStartOfDayMillis()
        return logDao.getAllWorkoutLogsFlow().map { logs ->
            logs.filter { it.completedAtMillis >= startOfDay }
                .sumOf { it.caloriesBurned }
        }
    }

    override fun getAllWorkoutLogsFlow(): Flow<List<WorkoutLogEntity>> {
        return logDao.getAllWorkoutLogsFlow()
    }

    override suspend fun saveWorkoutLog(
        title: String,
        durationSeconds: Int,
        caloriesBurned: Int,
        exercisesCompleted: Int
    ): Long {
        return logDao.insertWorkoutLog(
            WorkoutLogEntity(
                workoutTitle = title,
                durationSeconds = durationSeconds,
                caloriesBurned = caloriesBurned,
                exercisesCompleted = exercisesCompleted,
                completedAtMillis = System.currentTimeMillis()
            )
        )
    }

    override suspend fun getWorkoutStreak(): Int {
        val logs = logDao.getAllWorkoutLogsFlow().firstOrNull() ?: emptyList()
        if (logs.isEmpty()) return 0

        val distinctDays = logs.map { getDayEpoch(it.completedAtMillis) }
            .distinct()
            .sortedDescending()

        val todayEpoch = getDayEpoch(System.currentTimeMillis())
        var streak = 0
        var expectedEpoch = todayEpoch

        if (distinctDays.firstOrNull() == todayEpoch) {
            expectedEpoch = todayEpoch
        } else if (distinctDays.firstOrNull() == todayEpoch - 1) {
            expectedEpoch = todayEpoch - 1
        } else {
            return 0
        }

        for (day in distinctDays) {
            if (day == expectedEpoch) {
                streak++
                expectedEpoch--
            } else {
                break
            }
        }
        return streak
    }

    override suspend fun getTotalCompletedWorkouts(): Int {
        return logDao.getWorkoutCount()
    }

    companion object {
        private const val PRO_SUBSCRIPTION_KEY = "__pro_sub_ishanx10__"
    }

    // Favorites & Custom Workouts
    override fun getFavoriteExerciseIdsFlow(): Flow<List<String>> {
        return workoutDao.getAllFavoriteIdsFlow().map { ids ->
            ids.filter { it != PRO_SUBSCRIPTION_KEY }
        }
    }

    override fun isProSubscribedFlow(): Flow<Boolean> {
        return workoutDao.getAllFavoriteIdsFlow().map { ids ->
            ids.contains(PRO_SUBSCRIPTION_KEY)
        }
    }

    override suspend fun setProSubscribed(enabled: Boolean) {
        if (enabled) {
            workoutDao.addFavorite(FavoriteExerciseEntity(exerciseId = PRO_SUBSCRIPTION_KEY))
        } else {
            workoutDao.removeFavorite(PRO_SUBSCRIPTION_KEY)
        }
    }

    override suspend fun toggleFavoriteExercise(exerciseId: String): Boolean {
        val isFav = workoutDao.isFavorite(exerciseId) > 0
        return if (isFav) {
            workoutDao.removeFavorite(exerciseId)
            false
        } else {
            workoutDao.addFavorite(FavoriteExerciseEntity(exerciseId = exerciseId))
            true
        }
    }

    override fun getCustomWorkoutsFlow(): Flow<List<CustomWorkoutEntity>> {
        return workoutDao.getAllCustomWorkoutsFlow()
    }

    override suspend fun saveCustomWorkout(
        title: String,
        exerciseIds: List<String>,
        durationSec: Int,
        restSec: Int
    ): Long {
        val entity = CustomWorkoutEntity(
            title = title,
            exerciseIdsCsv = exerciseIds.joinToString(","),
            durationSecondsPerExercise = durationSec,
            restSeconds = restSec
        )
        return workoutDao.insertCustomWorkout(entity)
    }

    override suspend fun deleteCustomWorkout(id: Long) {
        workoutDao.deleteCustomWorkout(id)
    }

    // Daily Nutrition Logs
    override fun getNutritionLogsForDateFlow(dateIso: String): Flow<List<NutritionLogEntity>> {
        return logDao.getNutritionLogsForDateFlow(dateIso)
    }

    override suspend fun logNutritionItem(
        dateIso: String,
        foodNameBn: String,
        foodNameEn: String,
        calories: Int,
        proteinGrams: Float,
        carbsGrams: Float,
        fatGrams: Float
    ): Long {
        return logDao.insertNutritionLog(
            NutritionLogEntity(
                dateIso = dateIso,
                foodNameBn = foodNameBn,
                foodNameEn = foodNameEn,
                calories = calories,
                proteinGrams = proteinGrams,
                carbsGrams = carbsGrams,
                fatGrams = fatGrams,
                loggedAtMillis = System.currentTimeMillis()
            )
        )
    }

    override suspend fun deleteNutritionLog(id: Long) {
        logDao.deleteNutritionLog(id)
    }

    // Saved Music Tracks
    override fun getSavedMusicTracksFlow(): Flow<List<SavedMusicTrackEntity>> {
        return logDao.getAllMusicTracksFlow()
    }

    override suspend fun saveMusicTrack(uriString: String, title: String): Long {
        return logDao.insertMusicTrack(
            SavedMusicTrackEntity(
                uriString = uriString,
                title = title,
                addedAtMillis = System.currentTimeMillis()
            )
        )
    }

    override suspend fun deleteMusicTrack(id: Long) {
        logDao.deleteMusicTrack(id)
    }

    // 30-Day Challenge Progress
    override fun getAllChallengeProgressFlow(): Flow<List<ChallengeProgressEntity>> {
        return logDao.getAllChallengeProgressFlow()
    }

    override suspend fun toggleChallengeDay(challengeId: String, dayNumber: Int) {
        val current = logDao.getChallengeProgressOnce(challengeId)
        val existingDays = current?.completedDaysCsv
            ?.split(",")
            ?.mapNotNull { it.trim().toIntOrNull() }
            ?.toMutableSet()
            ?: mutableSetOf()

        if (existingDays.contains(dayNumber)) {
            existingDays.remove(dayNumber)
        } else {
            existingDays.add(dayNumber)
        }

        val updatedCsv = existingDays.sorted().joinToString(",")
        logDao.upsertChallengeProgress(
            ChallengeProgressEntity(
                challengeId = challengeId,
                completedDaysCsv = updatedCsv,
                updatedAtMillis = System.currentTimeMillis()
            )
        )
    }

    // Local JSON Backup & Restore
    override suspend fun exportBackupJson(): String {
        return backupManager.exportDataToJson()
    }

    override suspend fun importBackupJson(json: String): Boolean {
        return backupManager.importDataFromJson(json)
    }

    override suspend fun deleteAllData(): Boolean {
        return try {
            userDao.deleteUserProfile()
            logDao.clearWorkoutLogs()
            logDao.clearWeightLogs()
            logDao.clearWaterLogs()
            logDao.clearNutritionLogs()
            logDao.clearMusicTracks()
            logDao.clearChallengeProgress()
            workoutDao.clearFavorites()
            workoutDao.clearCustomWorkouts()
            true
        } catch (e: Exception) {
            false
        }
    }

    private fun getStartOfDayMillis(): Long {
        val calendar = Calendar.getInstance().apply {
            set(Calendar.HOUR_OF_DAY, 0)
            set(Calendar.MINUTE, 0)
            set(Calendar.SECOND, 0)
            set(Calendar.MILLISECOND, 0)
        }
        return calendar.timeInMillis
    }

    private fun getDayEpoch(millis: Long): Long {
        return TimeUnit.MILLISECONDS.toDays(millis)
    }

    private fun UserProfileEntity.toDomainModel(): UserProfile {
        return UserProfile(
            id = this.id,
            name = this.name,
            age = this.age,
            heightCm = this.heightCm,
            weightKg = this.weightKg,
            gender = this.gender,
            goal = this.goal,
            fitnessLevel = this.fitnessLevel,
            workoutDaysPerWeek = this.workoutDaysPerWeek,
            equipment = this.equipment,
            preferredLanguage = this.preferredLanguage,
            isDarkMode = this.isDarkMode,
            isOnboardingCompleted = this.isOnboardingCompleted
        )
    }

    private fun UserProfile.toEntity(): UserProfileEntity {
        return UserProfileEntity(
            id = this.id,
            name = this.name,
            age = this.age,
            heightCm = this.heightCm,
            weightKg = this.weightKg,
            gender = this.gender,
            goal = this.goal,
            fitnessLevel = this.fitnessLevel,
            workoutDaysPerWeek = this.workoutDaysPerWeek,
            equipment = this.equipment,
            preferredLanguage = this.preferredLanguage,
            isDarkMode = this.isDarkMode,
            isOnboardingCompleted = this.isOnboardingCompleted
        )
    }
}
```

---

## FILE: `app/src/main/java/com/example/data/seed/BudgetDietPlans.kt`

```kotlin
package com.example.data.seed

data class MealItem(
    val timeBn: String,
    val timeEn: String,
    val titleBn: String,
    val titleEn: String,
    val itemsBn: List<String>,
    val itemsEn: List<String>,
    val approxProtein: String
)

data class DietPlanModel(
    val id: String,
    val titleBn: String,
    val titleEn: String,
    val targetBn: String,
    val targetEn: String,
    val dailyBudgetEstimateBn: String,
    val dailyBudgetEstimateEn: String,
    val totalProteinEstimate: String,
    val descriptionBn: String,
    val descriptionEn: String,
    val meals: List<MealItem>
)

object BudgetDietPlans {

    val studentBudgetPlan = DietPlanModel(
        id = "student_budget",
        titleBn = "ছাত্র ও ব্যাচেলর হাই-প্রোটিন বাজেট ডায়েট",
        titleEn = "Student / Bachelor Budget Protein Diet",
        targetBn = "স্বল্প খরচে ৭০-৮৫ গ্রাম দৈনিক প্রোটিন নিশ্চিতকরণ",
        targetEn = "70-85g daily protein on a minimal budget",
        dailyBudgetEstimateBn = "প্রতিদিন মাত্র ৫০-৮০ টাকা অতিরিক্ত",
        dailyBudgetEstimateEn = "Only 50-80 BDT extra per day",
        totalProteinEstimate = "৭৫-৮৫ গ্রাম",
        descriptionBn = "কোনো দামি প্রোটিন পাউডার বা সাপ্লিমেন্ট ছাড়া সাধারণ দেশীয় ডিম, ডাল, ছোলা ও চিনাবাদাম দিয়ে তৈরি বাস্তবসম্মত প্ল্যান।",
        descriptionEn = "Realistic meal plan using local eggs, lentils, chickpeas, and peanuts without expensive protein powders.",
        meals = listOf(
            MealItem(
                timeBn = "সকাল (নাস্তা)",
                timeEn = "Morning (Breakfast)",
                titleBn = "ডিম ও রুটি / ছোলা বুট",
                titleEn = "Eggs & Roti / Boiled Chickpeas",
                itemsBn = listOf(
                    "২টি সিদ্ধ ডিম (একটি কুসুম সহ, একটি সাদা অংশ)",
                    "২টি লাল আটার রুটি অথবা ১ বাটি সিদ্ধ ছোলা",
                    "১ কাপ চিনি ছাড়া লাল চা / পানি"
                ),
                itemsEn = listOf(
                    "2 Boiled eggs (1 whole, 1 white)",
                    "2 Whole wheat rotis or 1 bowl boiled chickpeas",
                    "1 cup black tea or water"
                ),
                approxProtein = "১৮-২০ গ্রাম"
            ),
            MealItem(
                timeBn = "দুপুর (লাঞ্চ)",
                timeEn = "Afternoon (Lunch)",
                titleBn = "ভাত, ঘন ডাল ও মাছ/ডিম",
                titleEn = "Rice, Thick Dal & Fish/Egg",
                itemsBn = listOf(
                    "১ প্লেট ভাত (পরিমিত পরিমাণ)",
                    "১ বড় বাটি ঘন মসুর ডাল (পাতলা পানির মতো নয়)",
                    "১ টুকরো সাধারণ মাছ (রুই/তেলাপিয়া) অথবা ১টি ওমলেট",
                    "প্রচুর সবুজ শাকসবজি বা শসা"
                ),
                itemsEn = listOf(
                    "1 plate cooked rice (measured)",
                    "1 large bowl of thick dal",
                    "1 piece fish or 1 egg",
                    "Plenty of leafy greens or cucumber salad"
                ),
                approxProtein = "২৫-২৮ গ্রাম"
            ),
            MealItem(
                timeBn = "বিকাল (স্ন্যাকস)",
                timeEn = "Evening (Snacks)",
                titleBn = "চিনাবাদাম ও কলা",
                titleEn = "Roasted Peanuts & Banana",
                itemsBn = listOf(
                    "১ মুঠো ভাজা চিনাবাদাম (১০-১৫ টাকার)",
                    "১টি বাংলা কলা",
                    "পর্যাপ্ত পানি"
                ),
                itemsEn = listOf(
                    "1 handful roasted peanuts",
                    "1 medium banana",
                    "Fresh water"
                ),
                approxProtein = "৮-১০ গ্রাম"
            ),
            MealItem(
                timeBn = "রাত (ডিনার)",
                timeEn = "Night (Dinner)",
                titleBn = "রুটি/ভাত, ডাল ও ডিম/মুরগি",
                titleEn = "Roti/Rice, Dal & Egg/Chicken",
                itemsBn = listOf(
                    "২টি লাল আটার রুটি (অথবা আধা প্লেট ভাত)",
                    "১ বাটি ঘন ডাল অথবা ১ টুকরো মুরগির মাংস",
                    "১ বাটি ঘরে পাতা টক দই (হজমে দারুণ সহায়ক)"
                ),
                itemsEn = listOf(
                    "2 whole wheat rotis or half plate rice",
                    "1 bowl thick dal or 1 chicken piece",
                    "1 small cup sour curd"
                ),
                approxProtein = "২২-২৫ গ্রাম"
            )
        )
    )

    val familyBalancedPlan = DietPlanModel(
        id = "family_balanced",
        titleBn = "পারিবারিক দেশীয় সুষম খাদ্য পরিকল্পনা",
        titleEn = "Family Balanced Nutrition Plan",
        targetBn = "সুস্থ ওজন নিয়ন্ত্রণ ও পারিবারিক পুষ্টি নিশ্চিতকরণ",
        targetEn = "Healthy weight control and balanced family nutrition",
        dailyBudgetEstimateBn = "স্বাভাবিক পারিবারিক বাজারের ভেতরেই",
        dailyBudgetEstimateEn = "Within normal family grocery budget",
        totalProteinEstimate = "৬৫-৭৫ গ্রাম",
        descriptionBn = "পরিবারের সবার সাথে একই খাবার খেয়ে কেবল তেল ও ভাতের অনুপাত কমিয়ে প্রোটিন ও সবজি বাড়ানোর টেকসই পদ্ধতি।",
        descriptionEn = "Sustainable family eating by reducing cooking oil and rice while increasing dal, vegetables, and fish.",
        meals = listOf(
            MealItem(
                timeBn = "সকালের নাস্তা",
                timeEn = "Breakfast",
                titleBn = "রুটি, ডিম পোচ ও সবজি ভাজি",
                titleEn = "Roti, Egg & Mixed Vegetables",
                itemsBn = listOf(
                    "২টি লাল আটার রুটি",
                    "১টি ডিমের পোচ (কম তেলে)",
                    "১ বাটি পেঁপে বা পটল ভাজি (কম তেলে রান্না)"
                ),
                itemsEn = listOf(
                    "2 Whole wheat rotis",
                    "1 lightly fried egg",
                    "1 bowl mixed vegetable curry"
                ),
                approxProtein = "১৪-১৬ গ্রাম"
            ),
            MealItem(
                timeBn = "দুপুরের খাবার",
                timeEn = "Lunch",
                titleBn = "ভাত, তাজা দেশি মাছ, ডাল ও সালাদ",
                titleEn = "Rice, Fresh Fish, Dal & Salad",
                itemsBn = listOf(
                    "১ প্লেট পরিমিত ভাত",
                    "১ বড় টুকরো দেশি মাছ",
                    "১ বাটি ডাল ও প্রচুর শসা-টমেটো সালাদ"
                ),
                itemsEn = listOf(
                    "1 measured plate of rice",
                    "1 large piece of fresh fish",
                    "1 bowl of dal with cucumber salad"
                ),
                approxProtein = "২৪-২৭ গ্রাম"
            ),
            MealItem(
                timeBn = "রাতের খাবার",
                timeEn = "Dinner",
                titleBn = "হালকা রুটি, মুরগি/মাছ ও স্যুপ",
                titleEn = "Light Roti, Chicken/Fish & Soup",
                itemsBn = listOf(
                    "১-২টি নরম রুটি",
                    "মুরগির মাংসের ঝোল বা ডাল",
                    "১টি ছোট বাটি টক দই"
                ),
                itemsEn = listOf(
                    "1-2 Soft rotis",
                    "Chicken curry or thick dal",
                    "1 small cup sour curd"
                ),
                approxProtein = "২০-২৩ গ্রাম"
            )
        )
    )

    val prePostWorkoutTipsBn = listOf(
        "ওয়ার্কআউটের ৩০-৪৫ মিনিট আগে: ১টি কলা ও ১ গ্লাস পানি অথবা ১ মুঠো চিনাবাদাম খান। এটি রক্তে গ্লুকোজ সরবরাহ বজায় রাখবে।",
        "কখনই ভরা পেটে ব্যায়াম করবেন না: ভারী খাবার খাওয়ার অন্তত ২ ঘণ্টা পর ব্যায়াম করুন।",
        "ওয়ার্কআউটের ৩০-৪৫ মিনিটের মধ্যে: মাংসপেশির রিকভারির জন্য দ্রুত প্রোটিন দরকার। ২টি সিদ্ধ ডিম অথবা ১ গ্লাস ছাতুর শরবত সবচেয়ে সেরা।"
    )

    val prePostWorkoutTipsEn = listOf(
        "30-45 mins Pre-workout: 1 banana and a glass of water, or a handful of peanuts for sustained energy.",
        "Never exercise on a full stomach: Wait at least 2 hours after a heavy meal.",
        "Within 30-45 mins Post-workout: Muscles need quick protein. 2 boiled eggs or a glass of chhatu drink is ideal."
    )

    val hydrationTipsBn = listOf(
        "সকালে ঘুম থেকে উঠেই মুখ ধুয়ে ১ গ্লাস সাধারণ পানি পান করুন।",
        "প্রতিটি ওয়ার্কআউট সেশনের আগে ১ গ্লাস এবং ব্যায়ামের ফাঁকে ছোট ছোট চুমুক দিন।",
        "প্রস্রাবের হালকা খড় রং নির্দেশ করে আপনার শরীর সঠিকভাবে হাইড্রেটেড আছে।",
        "কফি বা অতিরিক্ত মিষ্টি চা পানি শূন্যতা বাড়ায়, তাই এগুলো পরিমিত পান করুন।"
    )

    val hydrationTipsEn = listOf(
        "Drink 1 glass of water immediately upon waking up.",
        "Take small sips of water during workouts to avoid cramping.",
        "Pale light-yellow urine indicates optimal hydration.",
        "Limit excess sweet tea or coffee as they promote dehydration."
    )

    val sleepRecoveryTipsBn = listOf(
        "পেশি ব্যায়াম করার সময় বাড়ে না, বরং ঘুমানোর সময় রিকভার হয়ে শক্ত হয়।",
        "প্রতিদিন ৭-৮ ঘণ্টা নিরবচ্ছিন্ন ঘুম নিশ্চিত করুন।",
        "ঘুমানোর ৩০ মিনিট আগে মোবাইল বা উজ্জ্বল স্ক্রিনের ব্যবহার বন্ধ রাখুন।",
        "রোজ নির্দিষ্ট সময়ে ঘুমাতে যান এবং নির্দিষ্ট সময়ে ঘুম থেকে উঠুন।"
    )

    val sleepRecoveryTipsEn = listOf(
        "Muscles don't grow during workouts; they repair and grow during deep sleep.",
        "Aim for 7-8 hours of uninterrupted sleep every night.",
        "Turn off smartphone screens 30 minutes before bedtime.",
        "Maintain consistent sleep and wake-up times every day."
    )
}
```

---

## FILE: `app/src/main/java/com/example/data/seed/ExerciseLibraryData.kt`

```kotlin
package com.example.data.seed

import com.example.domain.model.Exercise
import com.example.domain.model.ExerciseCategory
import com.example.domain.model.WorkoutPlan

object ExerciseLibraryData {

    val allExercises: List<Exercise> = listOf(
        // --- 1. CHEST ---
        Exercise(
            id = "push_up",
            nameBn = "স্ট্যান্ডার্ড পুশ-আপ",
            nameEn = "Standard Push-Up",
            category = ExerciseCategory.CHEST,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "বুকের মাংসপেশি (Pectorals)",
            targetMusclesEn = "Pectoralis Major",
            secondaryMusclesBn = "ট্রাইসেপস ও সামনের কাঁধ",
            secondaryMusclesEn = "Triceps, Anterior Deltoids, Core",
            instructionsBn = listOf(
                "হাতের তালু কাঁধের চেয়ে সামান্য চওড়া রেখে মেঝেতে রাখুন।",
                "শরীরকে মাথা থেকে পা পর্যন্ত এক সরলরেখায় টানটান রাখুন।",
                "কনুই ৪৫ ডিগ্রি কোণে বাঁকিয়ে বুক মেঝে ছোঁয়ার কাছাকাছি নামান।",
                "বুকের পেশিতে চাপ দিয়ে শুরুর অবস্থানে ফিরে আসুন।"
            ),
            instructionsEn = listOf(
                "Place your palms on the floor slightly wider than shoulder-width.",
                "Maintain a rigid straight line from head to heels.",
                "Lower your chest until it nearly grazes the floor with elbows at 45 degrees.",
                "Push firmly through your chest to return to the starting plank position."
            ),
            formTipsBn = listOf("পেটের মাংসপেশি শক্ত রাখুন", "কোমর অতিরিক্ত ঝুলিয়ে দেবেন না"),
            formTipsEn = listOf("Brace your core tight", "Avoid sagging your lower back"),
            commonMistakesBn = listOf("কনুই শরীর থেকে ৯০ ডিগ্রি বাইরে ছড়িয়ে দেওয়া", "ঘাড় অতিরিক্ত নিচু রাখা"),
            commonMistakesEn = listOf("Flaring elbows out at 90 degrees", "Dropping head forward"),
            defaultDurationSeconds = 35,
            defaultReps = 12
        ),
        Exercise(
            id = "chair_incline_pushup",
            nameBn = "চেয়ার ইনক্লাইন পুশ-আপ",
            nameEn = "Chair Incline Push-Up",
            category = ExerciseCategory.CHEST,
            difficulty = "beginner",
            equipmentRequired = "chair",
            targetMusclesBn = "বুকের নিচের অংশ (Lower Chest)",
            targetMusclesEn = "Lower Pectorals",
            secondaryMusclesBn = "ট্রাইসেপস ও কাঁধ",
            secondaryMusclesEn = "Triceps & Front Delts",
            instructionsBn = listOf(
                "একটি শক্ত ও অনড় চেয়ারের ওপর দুই হাত রেখে সোজা হন।",
                "শরীর সোজা রেখে বুক চেয়ারের দিকে নামান।",
                "ধীরে ধীরে পুশ করে আগের অবস্থানে ফিরে আসুন।"
            ),
            instructionsEn = listOf(
                "Place hands firmly on a sturdy, non-slip household chair.",
                "Keep core tight and lower your chest towards the chair edge.",
                "Push back smoothly to full arm extension."
            ),
            formTipsBn = listOf("চেয়ারটি যাতে মেঝের ওপর না পিছলে যায় নিশ্চিত করুন"),
            formTipsEn = listOf("Ensure the chair is stable and placed against a wall or non-slip mat"),
            commonMistakesBn = listOf("ঢিলেঢালা চেয়ার ব্যবহার করা"),
            commonMistakesEn = listOf("Using an unstable wheeled or rocking chair"),
            defaultDurationSeconds = 30,
            defaultReps = 12,
            safetyNoticeBn = "সতর্কতা: চাকাযুক্ত বা হালকা প্লাস্টিকের চেয়ার ব্যবহার করবেন না। চেয়ারটি দেয়ালের সাথে ঠেস দিয়ে রাখুন।",
            safetyNoticeEn = "Safety Warning: Never use a rolling or flimsy chair. Place chair against a solid wall."
        ),
        Exercise(
            id = "wide_pushup",
            nameBn = "ওয়াইড গ্রিপ পুশ-আপ",
            nameEn = "Wide Grip Push-Up",
            category = ExerciseCategory.CHEST,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "বুকের বাইরের অংশ (Outer Chest)",
            targetMusclesEn = "Outer Pectorals",
            secondaryMusclesBn = "কাঁধ",
            secondaryMusclesEn = "Anterior Deltoids",
            instructionsBn = listOf(
                "কাঁধের চেয়ে আরও বেশ খানিকটা চওড়া করে হাত মেঝেতে রাখুন।",
                "বুক প্রসারিত করে নিচে নামুন এবং নিয়ন্ত্রণ বজায় রাখুন।"
            ),
            instructionsEn = listOf(
                "Set hands significantly wider than shoulder-width.",
                "Lower down with full chest stretch and press back up."
            ),
            formTipsBn = listOf("বুকের প্রসারণ গভীরভাবে অনুভব করুন"),
            formTipsEn = listOf("Focus on the stretch across your chest plates"),
            commonMistakesBn = listOf("অর্ধেক নেমে ফিরে আসা"),
            commonMistakesEn = listOf("Short range of motion"),
            defaultDurationSeconds = 35,
            defaultReps = 12
        ),
        Exercise(
            id = "water_bottle_floor_press",
            nameBn = "ফ্লোর চেস্ট প্রেস (বোতল সহ)",
            nameEn = "Floor Chest Press (Bottle)",
            category = ExerciseCategory.CHEST,
            difficulty = "beginner",
            equipmentRequired = "water_bottle",
            targetMusclesBn = "বুকের কেন্দ্রভাগ ও পেশি",
            targetMusclesEn = "Mid Chest & Pectorals",
            secondaryMusclesBn = "ট্রাইসেপস",
            secondaryMusclesEn = "Triceps",
            instructionsBn = listOf(
                "মেঝেতে পিঠ ঠেকিয়ে শুয়ে পড়ুন এবং দুই হাতে দুটি পানির বোতল ধরুন।",
                "কনুই মেঝেতে ছুঁয়ে বোতল দুটিকে সোজা উপরে তুলুন এবং বুকের পেশি চেপে ধরুন।"
            ),
            instructionsEn = listOf(
                "Lie flat on the floor holding two equal water bottles.",
                "Press the bottles upwards until arms are extended, squeezing your chest."
            ),
            formTipsBn = listOf("দুটি বোতলে সমান পরিমাণ পানি রাখুন"),
            formTipsEn = listOf("Ensure both bottles have equal weight and a dry, firm grip"),
            commonMistakesBn = listOf("হাত কাঁপিয়ে দ্রুত নামানো"),
            commonMistakesEn = listOf("Dropping bottles abruptly onto the chest"),
            defaultDurationSeconds = 40,
            defaultReps = 15
        ),

        // --- 2. ARMS ---
        Exercise(
            id = "chair_dips",
            nameBn = "চেয়ার ট্রাইসেপস ডিপস",
            nameEn = "Chair Triceps Dips",
            category = ExerciseCategory.ARMS,
            difficulty = "beginner",
            equipmentRequired = "chair",
            targetMusclesBn = "ট্রাইসেপস (হাতের পেছনের মাংস)",
            targetMusclesEn = "Triceps Brachii",
            secondaryMusclesBn = "সামনের কাঁধ ও বুকের উপরের অংশ",
            secondaryMusclesEn = "Anterior Deltoids & Upper Chest",
            instructionsBn = listOf(
                "চেয়ারের প্রান্তে দুই হাত রেখে বসুন এবং কোমর সামনে এগিয়ে আনুন।",
                "কনুই ৯০ ডিগ্রি পর্যন্ত ভাঁজ করে শরীর নিচে নামান।",
                "ট্রাইসেপসে শক্তি প্রয়োগ করে শরীরকে উপরে তুলুন।"
            ),
            instructionsEn = listOf(
                "Grip the front edge of a sturdy chair with knuckles facing forward.",
                "Slide your hips off the chair and bend elbows to 90 degrees.",
                "Engage triceps strongly to push back to starting height."
            ),
            formTipsBn = listOf("পিঠ চেয়ারের খুব কাছাকাছি রাখুন"),
            formTipsEn = listOf("Keep your back close to the edge of the chair"),
            commonMistakesBn = listOf("কনুই অতিরিক্ত পেছনে ছড়ানো", "কাঁধ কানের কাছে কুঁচকে রাখা"),
            commonMistakesEn = listOf("Drifting too far from the chair", "Shrugging shoulders into neck"),
            defaultDurationSeconds = 30,
            defaultReps = 12,
            safetyNoticeBn = "সতর্কতা: নিশ্চিত করুন চেয়ারটি পিছলে যাচ্ছে না।",
            safetyNoticeEn = "Ensure chair is completely stable on non-slip ground."
        ),
        Exercise(
            id = "towel_bicep_curl",
            nameBn = "তোয়ালে আইসোমেট্রিক বাইসেপ কার্ল",
            nameEn = "Towel Isometric Bicep Curl",
            category = ExerciseCategory.ARMS,
            difficulty = "beginner",
            equipmentRequired = "towel",
            targetMusclesBn = "বাইসেপস (হাতের সামনের পেশি)",
            targetMusclesEn = "Biceps Brachii",
            secondaryMusclesBn = "ফোরআর্মস ও গ্রিপ শক্তি",
            secondaryMusclesEn = "Forearms & Grip",
            instructionsBn = listOf(
                "একটি তোয়ালের মাঝে এক পা দিয়ে মাড়িয়ে দাঁড়ান।",
                "দুই হাত দিয়ে তোয়ালের দুই প্রান্ত শক্ত করে ধরুন।",
                "কনুই কোমর বরাবর রেখে বুক বরাবর সর্বশক্তি দিয়ে উপরের দিকে টানুন।"
            ),
            instructionsEn = listOf(
                "Step one foot firmly over the center of a strong towel.",
                "Grip both ends with palms facing up.",
                "Curl upward against the immovable tension of your foot, squeezing biceps."
            ),
            formTipsBn = listOf("টান ধরে রাখার সময় স্বাভাবিকভাবে শ্বাস নিন"),
            formTipsEn = listOf("Breathe consistently while maintaining maximal contraction"),
            commonMistakesBn = listOf("পিঠ বাঁকা করে টান দেওয়া"),
            commonMistakesEn = listOf("Arching lower spine backwards"),
            defaultDurationSeconds = 30,
            defaultReps = 10
        ),
        Exercise(
            id = "diamond_pushup",
            nameBn = "ডায়মন্ড পুশ-আপ",
            nameEn = "Diamond Push-Up",
            category = ExerciseCategory.ARMS,
            difficulty = "advanced",
            equipmentRequired = "none",
            targetMusclesBn = "ট্রাইসেপস ও বুকের কেন্দ্র",
            targetMusclesEn = "Triceps & Inner Chest",
            secondaryMusclesBn = "কাঁধ ও কোর",
            secondaryMusclesEn = "Deltoids & Core",
            instructionsBn = listOf(
                "দুই হাতের বুড়ো আঙুল ও তর্জনী একসাথে মিলিয়ে হীরার আকৃতি (Diamond) বানান।",
                "শরীর সোজা রেখে বুক হাতের ওপর নামান এবং ট্রাইসেপসের শক্তিতে ঠেলে তুলুন।"
            ),
            instructionsEn = listOf(
                "Place hands together under chest so thumbs and index fingers form a diamond.",
                "Lower your chest down smoothly and press up focusing purely on triceps."
            ),
            formTipsBn = listOf("অতিরিক্ত কঠিন লাগলে হাঁটু মেঝেতে রেখে করতে পারেন"),
            formTipsEn = listOf("Drop to knees if full leverage puts undue wrist pressure"),
            commonMistakesBn = listOf("হাতের ওপর অতিরিক্ত ওজন ফেলে কবজি বাঁকানো"),
            commonMistakesEn = listOf("Excessive wrist flexion"),
            defaultDurationSeconds = 30,
            defaultReps = 8
        ),
        Exercise(
            id = "plank_shoulder_taps",
            nameBn = "প্ল্যাঙ্ক শোল্ডার ট্যাপস",
            nameEn = "Plank Shoulder Taps",
            category = ExerciseCategory.ARMS,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "কাঁধ, ট্রাইসেপস ও স্ট্যাবিলিটি",
            targetMusclesEn = "Deltoids, Triceps & Anti-Rotational Core",
            secondaryMusclesBn = "পেটের কোর পেশি",
            secondaryMusclesEn = "Obliques & Rectus Abdominis",
            instructionsBn = listOf(
                "উঁচু পুশ-আপ প্ল্যাঙ্ক পজিশনে যান।",
                "কোমর না দুলিয়ে ডান হাত দিয়ে বাম কাঁধ স্পর্শ করুন।",
                "এরপর বাম হাত দিয়ে ডান কাঁধ স্পর্শ করুন।"
            ),
            instructionsEn = listOf(
                "Begin in a high push-up plank position with feet hip-width.",
                "Tap your left shoulder with your right hand while keeping hips rock-steady.",
                "Alternate sides with controlled cadence."
            ),
            formTipsBn = listOf("কোমর ডানে-বামে অতিরিক্ত নাড়াবেন না"),
            formTipsEn = listOf("Keep hips level with minimal side-to-side sway"),
            commonMistakesBn = listOf("কোমর ঝুলিয়ে দেওয়া বা খুব দ্রুত হাত নাড়ানো"),
            commonMistakesEn = listOf("Twisting hips aggressively"),
            defaultDurationSeconds = 40,
            defaultReps = 16
        ),

        // --- 3. ABS & CORE ---
        Exercise(
            id = "classic_crunches",
            nameBn = "ক্লাসিক ক্রাঞ্চেস",
            nameEn = "Classic Crunches",
            category = ExerciseCategory.ABS_CORE,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "পেটের উপরের অংশ (Upper Abs)",
            targetMusclesEn = "Upper Rectus Abdominis",
            secondaryMusclesBn = "মধ্য কোর",
            secondaryMusclesEn = "Transverse Abdominis",
            instructionsBn = listOf(
                "মেঝেতে পিঠ ঠেকিয়ে হাঁটু ভাঁজ করে শুয়ে পড়ুন।",
                "হাত কানের পাশে বা বুকে রাখুন।",
                "পেটের পেশি সংকুচিত করে কাঁধ মেঝে থেকে কয়েক ইঞ্চি তুলুন।"
            ),
            instructionsEn = listOf(
                "Lie on your back with knees bent and feet flat on the floor.",
                "Place fingertips lightly behind ears without pulling neck.",
                "Contract abdominals to lift shoulder blades 3-4 inches off the mat."
            ),
            formTipsBn = listOf("ঘাড় টেনে তুলবেন না, পেটে শক্তি দিন"),
            formTipsEn = listOf("Do not pull on your neck; lead with your ribs to hips"),
            commonMistakesBn = listOf("ঘাড়ের ওপর চাপ দেওয়া", "পুরো শরীর তুলে ফেলা"),
            commonMistakesEn = listOf("Yanking the neck forward"),
            defaultDurationSeconds = 35,
            defaultReps = 15
        ),
        Exercise(
            id = "bicycle_crunches",
            nameBn = "বাইসাইকেল ক্রাঞ্চেস",
            nameEn = "Bicycle Crunches",
            category = ExerciseCategory.ABS_CORE,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "পাশের পেট (Obliques) ও কোর",
            targetMusclesEn = "Internal & External Obliques",
            secondaryMusclesBn = "লোয়ার অ্যাবস",
            secondaryMusclesEn = "Lower Abs & Hip Flexors",
            instructionsBn = listOf(
                "পিঠের ওপর শুয়ে পা তুলে সাইকেল চালানোর ভঙ্গিতে নাড়ান।",
                "ডান কনুই দিয়ে বাম হাঁটু এবং বাম কনুই দিয়ে ডান হাঁটু স্পর্শের চেষ্টা করুন।"
            ),
            instructionsEn = listOf(
                "Lie on your back, knees elevated in tabletop position.",
                "Alternate bringing opposite elbow to opposite knee with a smooth pedal stroke."
            ),
            formTipsBn = listOf("ধীরস্থির ও নিয়ন্ত্রিত গতিতে করুন"),
            formTipsEn = listOf("Move with deliberate control rather than fast jerks"),
            commonMistakesBn = listOf("খুব দ্রুত এলোমেলো পা ছোড়া"),
            commonMistakesEn = listOf("Rushing without full abdominal twist"),
            defaultDurationSeconds = 40,
            defaultReps = 20
        ),
        Exercise(
            id = "plank_hold",
            nameBn = "স্ট্যান্ডার্ড প্ল্যাঙ্ক",
            nameEn = "Standard Forearm Plank",
            category = ExerciseCategory.ABS_CORE,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "সম্পূর্ণ কোর ও স্পাইনাল স্ট্যাবিলিটি",
            targetMusclesEn = "Full Core & Transverse Abdominis",
            secondaryMusclesBn = "কাঁধ, গ্লুটস ও কোয়াডস",
            secondaryMusclesEn = "Shoulders, Glutes & Quadriceps",
            instructionsBn = listOf(
                "কনুইয়ের ওপর ভর দিয়ে শরীর সোজা রেখে মেঝে থেকে উপরে উঠুন।",
                "পেট, কোমর ও নিতম্ব শক্ত করে এক সরলরেখায় ধরে রাখুন।"
            ),
            instructionsEn = listOf(
                "Rest on forearms with elbows directly under shoulders.",
                "Engage abs, glutes and quads to keep your entire body in a straight plank."
            ),
            formTipsBn = listOf("শ্বাস ধরে রাখবেন না, স্বাভাবিক শ্বাস নিন"),
            formTipsEn = listOf("Breathe continuously and pull belly button toward spine"),
            commonMistakesBn = listOf("কোমর নিচে ঝুলে যাওয়া বা খুব উঁচুতে তোলা"),
            commonMistakesEn = listOf("Sagging hips or piking up into a triangle"),
            defaultDurationSeconds = 45,
            defaultReps = 1
        ),
        Exercise(
            id = "mountain_climbers",
            nameBn = "মাউন্টেন ক্লাইম্বার্স",
            nameEn = "Mountain Climbers",
            category = ExerciseCategory.ABS_CORE,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "কোর ও কার্ডিও মেটাবলিজম",
            targetMusclesEn = "Core & Cardiovascular Conditioning",
            secondaryMusclesBn = "কাঁধ ও পা",
            secondaryMusclesEn = "Shoulders & Hip Flexors",
            instructionsBn = listOf(
                "হাই প্ল্যাঙ্ক অবস্থানে যান।",
                "একটি হাঁটু দ্রুত বুকের কাছে টানুন, তারপর দ্রুত পা পরিবর্তন করুন।"
            ),
            instructionsEn = listOf(
                "Start in push-up plank. Drive one knee toward chest, then alternate dynamically."
            ),
            formTipsBn = listOf("হাত মেঝের ওপর স্থির রাখুন"),
            formTipsEn = listOf("Keep hands firmly planted and back flat"),
            commonMistakesBn = listOf("কোমর মাত্রাতিরিক্ত লাফানো"),
            commonMistakesEn = listOf("Bouncing hips high in the air"),
            defaultDurationSeconds = 35,
            defaultReps = 24
        ),
        Exercise(
            id = "leg_raises",
            nameBn = "লায়িং লেগ রেইজেস",
            nameEn = "Lying Leg Raises",
            category = ExerciseCategory.ABS_CORE,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "পেটের নিচের অংশ (Lower Abs)",
            targetMusclesEn = "Lower Rectus Abdominis",
            secondaryMusclesBn = "হিপ ফ্লেক্সরস",
            secondaryMusclesEn = "Hip Flexors",
            instructionsBn = listOf(
                "মেঝেতে শুয়ে হাত নিতম্বের নিচে রাখুন।",
                "পা সোজা রেখে ৯০ ডিগ্রি পর্যন্ত উপরে তুলুন এবং ধীরে ধীরে নামান।"
            ),
            instructionsEn = listOf(
                "Lie flat with hands under hips for lower back support.",
                "Raise straight legs to 90 degrees, then lower slowly without touching floor."
            ),
            formTipsBn = listOf("লোয়ার ব্যাক মেঝের সাথে চেপে রাখুন"),
            formTipsEn = listOf("Keep lower back glued flat to the floor throughout"),
            commonMistakesBn = listOf("লোয়ার ব্যাক উঁচু করে ফেলা"),
            commonMistakesEn = listOf("Arching the lumbar spine off floor"),
            defaultDurationSeconds = 35,
            defaultReps = 12
        ),

        // --- 4. LEGS ---
        Exercise(
            id = "bodyweight_squats",
            nameBn = "বডিওয়েট স্কোয়াট",
            nameEn = "Bodyweight Squats",
            category = ExerciseCategory.LEGS,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "কোয়াড্রিসেপস ও নিতম্ব (Glutes)",
            targetMusclesEn = "Quadriceps & Gluteus Maximus",
            secondaryMusclesBn = "হ্যামস্ট্রিং ও বাছুরের পেশি",
            secondaryMusclesEn = "Hamstrings & Calves",
            instructionsBn = listOf(
                "পা দুটি কাঁধ বরাবর চওড়া করে সোজা হয়ে দাঁড়ান।",
                "চেয়ারে বসার ভঙ্গিতে কোমর পেছনে দিয়ে হাঁটু ভাঁজ করুন।",
                "উরু মেঝের সমান্তরালে এলে গোড়ালিতে ভর দিয়ে উঠে দাঁড়ান।"
            ),
            instructionsEn = listOf(
                "Stand with feet shoulder-width apart, toes turned slightly out.",
                "Hinge at hips and sit back as if into a chair until thighs are parallel.",
                "Drive through your heels to stand fully upright."
            ),
            formTipsBn = listOf("বুক খোলা ও সোজা রাখুন", "হাঁটু যাতে পায়ের আঙুল ছাড়িয়ে খুব বেশি এগিয়ে না যায়"),
            formTipsEn = listOf("Keep chest elevated, weight balanced on midfoot/heel"),
            commonMistakesBn = listOf("হাঁটু ভেতরের দিকে ভেঙে পড়া", "গোড়ালি মেঝে থেকে তোলা"),
            commonMistakesEn = listOf("Knees caving inward (valgus collapse)", "Lifting heels"),
            defaultDurationSeconds = 40,
            defaultReps = 15
        ),
        Exercise(
            id = "forward_lunges",
            nameBn = "ফরওয়ার্ড লাঞ্জেস",
            nameEn = "Forward Lunges",
            category = ExerciseCategory.LEGS,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "উরু ও নিতম্বের শক্তি",
            targetMusclesEn = "Quadriceps, Glutes & Hamstrings",
            secondaryMusclesBn = "কোর ও ভারসাম্য",
            secondaryMusclesEn = "Core & Stabilizers",
            instructionsBn = listOf(
                "এক পা এক বড় কদম সামনে এগিয়ে দিন।",
                "উভয় হাঁটু ৯০ ডিগ্রি কোণে নামিয়ে আনুন।",
                "সামনের পায়ে চাপ দিয়ে শুরুর অবস্থানে ফিরে এসে পা বদল করুন।"
            ),
            instructionsEn = listOf(
                "Take a deliberate step forward and lower hips until both knees form 90 degrees.",
                "Push back through the front heel and switch legs smoothly."
            ),
            formTipsBn = listOf("সামনের হাঁটু গোড়ালির ঠিক উপরে সোজা রাখুন"),
            formTipsEn = listOf("Ensure front knee tracks directly over front ankle"),
            commonMistakesBn = listOf("পেছনের হাঁটু মেঝেতে জোরে আছড়ে ফেলা"),
            commonMistakesEn = listOf("Banging trailing knee against hard floor"),
            defaultDurationSeconds = 40,
            defaultReps = 16
        ),
        Exercise(
            id = "wall_sit",
            nameBn = "ওয়াল সিট আইসোমেট্রিক",
            nameEn = "Wall Sit Isometric Hold",
            category = ExerciseCategory.LEGS,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "কোয়াড্রিসেপসের সহনশীলতা",
            targetMusclesEn = "Quadriceps Endurance",
            secondaryMusclesBn = "গ্লুটস ও কাফ",
            secondaryMusclesEn = "Glutes & Calves",
            instructionsBn = listOf(
                "দেয়ালে পিঠ ঠেকিয়ে উরু মেঝের সমান্তরাল করে বসুন।",
                "হাত বুকের ওপর রেখে নির্দিষ্ট সময় স্থির থাকুন।"
            ),
            instructionsEn = listOf(
                "Lean back against a flat wall and slide down until thighs are parallel to ground.",
                "Hold position statically with 90-degree bend at knees."
            ),
            formTipsBn = listOf("উরু ঠিক ৯০ ডিগ্রিতে রাখার চেষ্টা করুন"),
            formTipsEn = listOf("Keep thighs parallel and knees aligned over ankles"),
            commonMistakesBn = listOf("হাতে ভর দিয়ে উরুর ওপর বিশ্রাম নেওয়া"),
            commonMistakesEn = listOf("Resting hands heavily on thighs"),
            defaultDurationSeconds = 40,
            defaultReps = 1
        ),
        Exercise(
            id = "glute_bridge",
            nameBn = "গ্লুট ব্রিজ",
            nameEn = "Glute Bridge",
            category = ExerciseCategory.LEGS,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "নিতম্ব (Glutes) ও হ্যামস্ট্রিং",
            targetMusclesEn = "Gluteus Maximus & Hamstrings",
            secondaryMusclesBn = "লোয়ার ব্যাক ও কোর",
            secondaryMusclesEn = "Lower Back & Core",
            instructionsBn = listOf(
                "পিঠের ওপর শুয়ে হাঁটু ভাঁজ করে পা মাটিতে রাখুন।",
                "নিতম্বে চাপ দিয়ে কোমর উপরে তুলুন যাতে হাঁটু থেকে কাঁধ সোজা রেখা তৈরি করে।"
            ),
            instructionsEn = listOf(
                "Lie face up with knees bent and feet flat on the floor.",
                "Drive through heels and squeeze glutes to elevate hips into a straight bridge."
            ),
            formTipsBn = listOf("উপরে উঠে ১ সেকেন্ড শক্ত করে চেপে রাখুন"),
            formTipsEn = listOf("Pause for a full second at the peak contraction"),
            commonMistakesBn = listOf("পিঠ অতিরিক্ত ধনুকের মতো বাঁকানো"),
            commonMistakesEn = listOf("Hyperextending the lower back"),
            defaultDurationSeconds = 35,
            defaultReps = 15
        ),
        Exercise(
            id = "standing_calf_raises",
            nameBn = "স্ট্যান্ডিং কাফ রেইজেস",
            nameEn = "Standing Calf Raises",
            category = ExerciseCategory.LEGS,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "বাছুরের পেশি (Calves)",
            targetMusclesEn = "Gastrocnemius & Soleus",
            secondaryMusclesBn = "পায়ের গোড়ালি ও ব্যালান্স",
            secondaryMusclesEn = "Ankle Stabilizers",
            instructionsBn = listOf(
                "সোজা হয়ে দাঁড়িয়ে পায়ের আঙুলের ডগায় ভর দিয়ে শরীর যতটা সম্ভব উঁচুতে তুলুন।",
                "বাছুরের পেশিতে চাপ অনুভব করে ধীরে ধীরে নামান।"
            ),
            instructionsEn = listOf(
                "Stand tall and push onto the balls of your feet as high as possible.",
                "Squeeze calf muscles at top, then lower heels down with control."
            ),
            formTipsBn = listOf("ভারসাম্যের জন্য দেয়ালে হালকা হাত রাখতে পারেন"),
            formTipsEn = listOf("Lightly touch a wall for balance if needed"),
            commonMistakesBn = listOf("দ্রুত লাফালাফি করা"),
            commonMistakesEn = listOf("Bouncing rapidly without contraction"),
            defaultDurationSeconds = 30,
            defaultReps = 20
        ),

        // --- 5. BACK ---
        Exercise(
            id = "superman_hold",
            nameBn = "সুপারম্যান হোল্ড",
            nameEn = "Superman Hold",
            category = ExerciseCategory.BACK,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "লোয়ার ব্যাক ও স্পাইনাল পেশি",
            targetMusclesEn = "Erector Spinae",
            secondaryMusclesBn = "গ্লুটস ও কাঁধের পেছনের অংশ",
            secondaryMusclesEn = "Glutes & Posterior Deltoids",
            instructionsBn = listOf(
                "মেঝেতে উপুড় হয়ে শুয়ে দুই হাত সামনে প্রসারিত করুন।",
                "একসাথে হাত ও পা মেঝে থেকে কয়েক ইঞ্চি উপরে তুলে ২ সেকেন্ড ধরে রাখুন।"
            ),
            instructionsEn = listOf(
                "Lie face down on the floor with arms extended overhead.",
                "Simultaneously lift arms, chest and feet off floor and hold."
            ),
            formTipsBn = listOf("ঘাড় স্বাভাবিক ও মেঝের দিকে মুখ করে রাখুন"),
            formTipsEn = listOf("Keep neck neutral, looking slightly forward/down"),
            commonMistakesBn = listOf("ঘাড় পেছনের দিকে বেশি বাঁকিয়ে ফেলা"),
            commonMistakesEn = listOf("Craning neck backward"),
            defaultDurationSeconds = 35,
            defaultReps = 10
        ),
        Exercise(
            id = "towel_lat_pulldown",
            nameBn = "তোয়ালে ল্যাট পুল-ডাউন (আইসোমেট্রিক)",
            nameEn = "Isometric Towel Lat Pulldown",
            category = ExerciseCategory.BACK,
            difficulty = "beginner",
            equipmentRequired = "towel",
            targetMusclesBn = "পিঠের চওড়া পেশি (Latissimus Dorsi)",
            targetMusclesEn = "Latissimus Dorsi",
            secondaryMusclesBn = "পিঠের মাঝের অংশ ও ট্রাইসেপস",
            secondaryMusclesEn = "Rhomboids & Rear Delts",
            instructionsBn = listOf(
                "একটি তোয়ালের দুই প্রান্ত শক্ত করে ধরে মাথার উপরে সোজা করুন।",
                "তোয়ালেটি দুই দিকে ছিঁড়ে ফেলার মতো টান দিয়ে রেখে বুকের কাছে নামিয়ে আনুন।"
            ),
            instructionsEn = listOf(
                "Hold a towel taut overhead with hands wider than shoulders.",
                "Pull outward actively as if trying to rip towel apart while pulling down to upper chest."
            ),
            formTipsBn = listOf("পিঠের ডানা (Lats) সংকুচিত করুন"),
            formTipsEn = listOf("Engage your shoulder blades down and back"),
            commonMistakesBn = listOf("তোয়ালের টান ঢিলে করে ফেলা"),
            commonMistakesEn = listOf("Losing outward tension on the towel"),
            defaultDurationSeconds = 35,
            defaultReps = 12
        ),
        Exercise(
            id = "reverse_snow_angels",
            nameBn = "রিভার্স স্নো এঞ্জেলস",
            nameEn = "Prone Reverse Snow Angels",
            category = ExerciseCategory.BACK,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "পিঠের উপরের অংশ ও পশ্চাত্ কাঁধ",
            targetMusclesEn = "Upper Back, Rhomboids & Rear Delts",
            secondaryMusclesBn = "রোটেটর কাফ",
            secondaryMusclesEn = "Rotator Cuff & Lower Back",
            instructionsBn = listOf(
                "উপুড় হয়ে শুয়ে হাত মেঝে থেকে হালকা উঁচুতে রেখে গোল করে কোমরের দিকে আনুন।",
                "পিঠের মাংসপেশি সক্রিয় রেখে ধীরে ধীরে মাথার ওপরে ফিরিয়ে নিন।"
            ),
            instructionsEn = listOf(
                "Lie prone, hover arms slightly off floor, and sweep them in a wide arc from overhead to hips."
            ),
            formTipsBn = listOf("হাত যাতে মেঝে স্পর্শ না করে"),
            formTipsEn = listOf("Keep hands hovering continuously off the floor"),
            commonMistakesBn = listOf("দ্রুত হাত ঝাপটানো"),
            commonMistakesEn = listOf("Rushing through the motion"),
            defaultDurationSeconds = 35,
            defaultReps = 12
        ),

        // --- 6. FULL BODY & CARDIO ---
        Exercise(
            id = "jumping_jacks",
            nameBn = "জাম্পিং জ্যাকস",
            nameEn = "Jumping Jacks",
            category = ExerciseCategory.FULL_BODY,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "সম্পূর্ণ শরীর ও হার্টরেট বুস্ট",
            targetMusclesEn = "Full Body Cardiovascular",
            secondaryMusclesBn = "কাফ, কাঁধ ও কোর",
            secondaryMusclesEn = "Calves, Deltoids & Core",
            instructionsBn = listOf(
                "পা জোড়া করে দাঁড়িয়ে হাত পাশে রাখুন।",
                "লাফ দিয়ে পা চওড়া করুন এবং একসাথে হাত মাথার ওপরে তালি দেওয়ার মতো তুলুন।",
                "আবার লাফ দিয়ে শুরুর অবস্থানে ফিরে আসুন।"
            ),
            instructionsEn = listOf(
                "Start with feet together and arms at sides.",
                "Jump feet out while sweeping arms overhead, then return smoothly."
            ),
            formTipsBn = listOf("পায়ের পাতায় আলতোভাবে ল্যান্ড করুন"),
            formTipsEn = listOf("Land softly on balls of feet to protect joints"),
            commonMistakesBn = listOf("গোড়ালিতে সজোরে আছাড় দেওয়া"),
            commonMistakesEn = listOf("Heavy thudding heel landings"),
            defaultDurationSeconds = 40,
            defaultReps = 30
        ),
        Exercise(
            id = "burpees",
            nameBn = "ক্লাসিক বারপিস",
            nameEn = "Full Body Burpees",
            category = ExerciseCategory.FULL_BODY,
            difficulty = "advanced",
            equipmentRequired = "none",
            targetMusclesBn = "ফুল বডি পাওয়ার ও মেটাবলিজম",
            targetMusclesEn = "Total Body Power & Anaerobic Capacity",
            secondaryMusclesBn = "বুক, পা ও কোর",
            secondaryMusclesEn = "Chest, Legs & Core",
            instructionsBn = listOf(
                "স্কোয়াট করে মেঝেতে হাত রাখুন এবং পা পেছনে ছুড়ে পুশ-আপ পজিশনে যান।",
                "একটি পুশ-আপ সম্পন্ন করে পা ফিরিয়ে আনুন এবং উপরে সজোরে লাফ দিন।"
            ),
            instructionsEn = listOf(
                "Drop into a squat, kick feet back to plank, perform a push-up, jump feet in and explode upward."
            ),
            formTipsBn = listOf("নিজের ছন্দ বজায় রাখুন, অতিরিক্ত তাড়াহুড়ো করবেন না"),
            formTipsEn = listOf("Pace yourself with steady breath control"),
            commonMistakesBn = listOf("প্ল্যাঙ্কে কোমর নামিয়ে ফেলা"),
            commonMistakesEn = listOf("Sagging hips during the plank transition"),
            defaultDurationSeconds = 30,
            defaultReps = 8
        ),
        Exercise(
            id = "high_knees",
            nameBn = "হাই নীজ",
            nameEn = "High Knees",
            category = ExerciseCategory.FULL_BODY,
            difficulty = "intermediate",
            equipmentRequired = "none",
            targetMusclesBn = "কার্ডিও ও লোয়ার বডি",
            targetMusclesEn = "Cardiovascular & Hip Flexors",
            secondaryMusclesBn = "কাফ ও কোর",
            secondaryMusclesEn = "Calves & Lower Abs",
            instructionsBn = listOf(
                "এক জায়গায় দাঁড়িয়ে দ্রুত দৌড়ানোর মতো করে হাঁটু কোমর পর্যন্ত উঁচুতে তুলুন।"
            ),
            instructionsEn = listOf(
                "Run in place, explosively lifting knees to waist height with energetic arm drives."
            ),
            formTipsBn = listOf("শরীরের ভারসাম্য সোজা রাখুন"),
            formTipsEn = listOf("Stay tall with active arm swing"),
            commonMistakesBn = listOf("পেছনে অতিরিক্ত ঝুঁকে পড়া"),
            commonMistakesEn = listOf("Leaning too far backward"),
            defaultDurationSeconds = 30,
            defaultReps = 30
        ),

        // --- 7. WARM-UP & STRETCHING ---
        Exercise(
            id = "arm_circles",
            nameBn = "আর্ম সার্কেলস",
            nameEn = "Arm Circles Warm-Up",
            category = ExerciseCategory.WARMUP_COOLDOWN,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "কাঁধ ও রোটেটর কাফ মোবিলিটি",
            targetMusclesEn = "Shoulders & Rotator Cuff",
            secondaryMusclesBn = "বুকের পেশি",
            secondaryMusclesEn = "Upper Trapezius",
            instructionsBn = listOf(
                "হাত দুই পাশে সোজা করে ছড়িয়ে ধীরে ধীরে বৃত্তাকারে ঘোরান।"
            ),
            instructionsEn = listOf(
                "Extend arms to sides and rotate in smooth controlled circular arcs."
            ),
            formTipsBn = listOf("প্রথমে ছোট বৃত্ত, পরে বড় বৃত্ত করুন"),
            formTipsEn = listOf("Gradually expand the circle radius"),
            commonMistakesBn = listOf("খুব দ্রুত হাত ঝাঁকানো"),
            commonMistakesEn = listOf("Jerking shoulder joints"),
            defaultDurationSeconds = 30,
            defaultReps = 20
        ),
        Exercise(
            id = "cobra_stretch",
            nameBn = "কোবরা স্ট্রেচ",
            nameEn = "Cobra Pose Stretch",
            category = ExerciseCategory.WARMUP_COOLDOWN,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "পেটের প্রসারণ ও মেরুদণ্ড রিল্যাক্স",
            targetMusclesEn = "Abdominal & Spine Decompression",
            secondaryMusclesBn = "বুক ও ঘাড়",
            secondaryMusclesEn = "Chest & Neck",
            instructionsBn = listOf(
                "উপুড় হয়ে শুয়ে হাতের তালুতে ভর দিয়ে বুক ধীরে ধীরে উপরে তুলুন।",
                "গভীর শ্বাস নিন এবং পেটের প্রসারণ অনুভব করুন।"
            ),
            instructionsEn = listOf(
                "Lie prone, press hands into mat to gently arch chest up toward ceiling with slow deep breathing."
            ),
            formTipsBn = listOf("কাঁধ কানের থেকে দূরে নামিয়ে রাখুন"),
            formTipsEn = listOf("Keep shoulders down and relaxed away from ears"),
            commonMistakesBn = listOf("কোমরে তীব্র চাপ দেওয়া"),
            commonMistakesEn = listOf("Jamming the lower back"),
            defaultDurationSeconds = 30,
            defaultReps = 1
        ),
        Exercise(
            id = "childs_pose",
            nameBn = "চাইল্ডস পোজ রিকভারি",
            nameEn = "Child's Pose Rest",
            category = ExerciseCategory.WARMUP_COOLDOWN,
            difficulty = "beginner",
            equipmentRequired = "none",
            targetMusclesBn = "পিঠ, কোমর ও মানসিক প্রশান্তি",
            targetMusclesEn = "Lats, Lower Back & Hip Relaxer",
            secondaryMusclesBn = "কাঁধ ও হাঁটু",
            secondaryMusclesEn = "Shoulders & Ankles",
            instructionsBn = listOf(
                "হাঁটু গেড়ে বসে নিতম্ব গোড়ালির ওপর রাখুন।",
                "হাত সামনে প্রসারিত করে মাথা মেঝেতে ঠেকান এবং আরামদায়কভাবে শ্বাস নিন।"
            ),
            instructionsEn = listOf(
                "Kneel and sit back onto heels. Fold torso forward with arms outstretched on the mat."
            ),
            formTipsBn = listOf("প্রতিটি নিঃশ্বাসে শরীরকে আরও রিল্যাক্স হতে দিন"),
            formTipsEn = listOf("Sink deeper into your hips with each exhale"),
            commonMistakesBn = listOf("হাঁটুতে অতিরিক্ত চাপ দেওয়া"),
            commonMistakesEn = listOf("Holding breath"),
            defaultDurationSeconds = 35,
            defaultReps = 1
        )
    )

    // Ready-Made Plans
    val readyPlans: List<WorkoutPlan> = listOf(
        WorkoutPlan(
            id = "plan_beg_7",
            titleBn = "৭ দিনের বিগিনার কিকস্টার্ট",
            titleEn = "7-Day Beginner Kickstart",
            descriptionBn = "নতুনদের জন্য শরীরচর্চার একটি সহজ ও চমৎকার সূচনা রুটিন।",
            descriptionEn = "An accessible zero-equipment foundation routine for beginners.",
            level = "beginner",
            durationDays = 7,
            durationMinutesPerDay = 12,
            exercises = allExercises.filter { it.difficulty == "beginner" && it.category != ExerciseCategory.WARMUP_COOLDOWN }.take(6)
        ),
        WorkoutPlan(
            id = "plan_beg_14",
            titleBn = "১৪ দিনের ফিটনেস ফাউন্ডেশন",
            titleEn = "14-Day Fitness Foundation",
            descriptionBn = "স্ট্যামিনা ও শরীরের নমনীয়তা বৃদ্ধির একটি পূর্ণাঙ্গ দুই সপ্তাহের প্ল্যান।",
            descriptionEn = "Develop real baseline strength and stamina across 2 progressive weeks.",
            level = "beginner",
            durationDays = 14,
            durationMinutesPerDay = 15,
            exercises = allExercises.filter { it.difficulty == "beginner" }.take(7)
        ),
        WorkoutPlan(
            id = "plan_beg_30",
            titleBn = "৩০ দিনের শরীর রূপান্তর",
            titleEn = "30-Day Body Transformation",
            descriptionBn = "পুরো এক মাসে স্থায়ী মেদ ঝরিয়ে সুঠাম শরীর গড়ে তোলার সুষম প্ল্যান।",
            descriptionEn = "A structured 30-day progressive bodyweight regimen.",
            level = "beginner",
            durationDays = 30,
            durationMinutesPerDay = 18,
            exercises = allExercises.take(8)
        ),
        WorkoutPlan(
            id = "plan_int_7",
            titleBn = "৭ দিনের টোন ও ফ্যাট বার্ন",
            titleEn = "7-Day Tone & Fat Burn",
            descriptionBn = "মাঝারি মাত্রার উচ্চ কার্যকর ফ্যাট বার্নিং সেশন।",
            descriptionEn = "Accelerated fat loss and muscle toning for active individuals.",
            level = "intermediate",
            durationDays = 7,
            durationMinutesPerDay = 16,
            exercises = allExercises.filter { it.category == ExerciseCategory.FULL_BODY || it.category == ExerciseCategory.ABS_CORE }.take(6)
        ),
        WorkoutPlan(
            id = "plan_int_14",
            titleBn = "১৪ দিনের কোর ও স্ট্রেংথ",
            titleEn = "14-Day Core & Strength",
            descriptionBn = "পেটের অ্যাবস ও পেশির শক্তি বাড়াতে তীব্রতর রুটিন।",
            descriptionEn = "Intense core development and upper-lower strength progression.",
            level = "intermediate",
            durationDays = 14,
            durationMinutesPerDay = 20,
            exercises = allExercises.filter { it.difficulty == "intermediate" }.take(7)
        ),
        WorkoutPlan(
            id = "plan_int_30",
            titleBn = "৩০ দিনের ইন্টারমিডিয়েট পাওয়ার",
            titleEn = "30-Day Intermediate Power",
            descriptionBn = "এক মাসের সার্বিক শক্তি ও শারীরিক কর্মদক্ষতা বৃদ্ধির পরিকল্পনা।",
            descriptionEn = "A monthly plan elevating overall functional power and endurance.",
            level = "intermediate",
            durationDays = 30,
            durationMinutesPerDay = 22,
            exercises = allExercises.take(9)
        ),
        WorkoutPlan(
            id = "plan_adv_7",
            titleBn = "৭ দিনের হাই-ইনটেনসিটি বুস্টার",
            titleEn = "7-Day High Intensity Beast",
            descriptionBn = "অ্যাডভান্সড লেভেলের জন্য দ্রুত ক্যালরি বার্ন ও পেশি গঠন।",
            descriptionEn = "High intensity explosive circuit for seasoned fitness enthusiasts.",
            level = "advanced",
            durationDays = 7,
            durationMinutesPerDay = 22,
            exercises = allExercises.filter { it.difficulty == "advanced" || it.difficulty == "intermediate" }.take(7)
        ),
        WorkoutPlan(
            id = "plan_adv_14",
            titleBn = "১৪ দিনের অ্যাথলেটিক কন্ডিশনিং",
            titleEn = "14-Day Athlete Conditioning",
            descriptionBn = "পেশাদার ক্রীড়াবিদদের মতো স্ট্যামিনা ও রিফ্লেক্স তৈরির সেশন।",
            descriptionEn = "Advanced power endurance conditioning across two challenging weeks.",
            level = "advanced",
            durationDays = 14,
            durationMinutesPerDay = 25,
            exercises = allExercises.take(8)
        ),
        WorkoutPlan(
            id = "plan_adv_30",
            titleBn = "৩০ দিনের স্পার্টান ওয়ারিয়র",
            titleEn = "30-Day Spartan Warrior",
            descriptionBn = "চরম শারীরিক সক্ষমতা অর্জনের এক মাসের মাস্টার রুটিন।",
            descriptionEn = "The ultimate monthly bodyweight strength and conditioning challenge.",
            level = "advanced",
            durationDays = 30,
            durationMinutesPerDay = 28,
            exercises = allExercises.take(10)
        )
    )

    // Quick Workouts (5, 10, 15 Minutes)
    val quickWorkouts: List<WorkoutPlan> = listOf(
        WorkoutPlan(
            id = "quick_5",
            titleBn = "৫-মিনিট কুইক এনার্জাইজার",
            titleEn = "5-Min Quick Energizer",
            descriptionBn = "ব্যস্ত সময়ে দ্রুত রক্ত সঞ্চালন ও মেটাবলিজম চাঙ্গা করার সেশন।",
            descriptionEn = "A rapid 5-minute metabolic wake-up call for busy days.",
            level = "beginner",
            durationDays = 1,
            durationMinutesPerDay = 5,
            exercises = listOf(
                allExercises.first { it.id == "jumping_jacks" },
                allExercises.first { it.id == "bodyweight_squats" },
                allExercises.first { it.id == "plank_hold" }
            )
        ),
        WorkoutPlan(
            id = "quick_10",
            titleBn = "১০-মিনিট কোর শ্রেডার",
            titleEn = "10-Min Core Shredder",
            descriptionBn = "অল্প সময়ে পেটের মেদ ঝরিয়ে শক্তিশালী কোর গড়ে তোলার ওয়ার্কআউট।",
            descriptionEn = "Time-efficient abdominal conditioning to tighten the core.",
            level = "intermediate",
            durationDays = 1,
            durationMinutesPerDay = 10,
            exercises = listOf(
                allExercises.first { it.id == "classic_crunches" },
                allExercises.first { it.id == "bicycle_crunches" },
                allExercises.first { it.id == "mountain_climbers" },
                allExercises.first { it.id == "plank_hold" }
            )
        ),
        WorkoutPlan(
            id = "quick_15",
            titleBn = "১৫-মিনিট ফুলবডি সোয়েট",
            titleEn = "15-Min Full Body Sweat",
            descriptionBn = "মাঝারি সময়ে সর্বোচ্চ ক্যালরি পোড়ানো ও পেশি সক্রিয় করার পূর্ণাঙ্গ সেশন।",
            descriptionEn = "Complete full-body workout maximizing calorie burn in 15 minutes.",
            level = "intermediate",
            durationDays = 1,
            durationMinutesPerDay = 15,
            exercises = listOf(
                allExercises.first { it.id == "jumping_jacks" },
                allExercises.first { it.id == "push_up" },
                allExercises.first { it.id == "bodyweight_squats" },
                allExercises.first { it.id == "chair_dips" },
                allExercises.first { it.id == "mountain_climbers" }
            )
        )
    )

    // Household Equipment Workouts
    val equipmentWorkouts: List<WorkoutPlan> = listOf(
        WorkoutPlan(
            id = "equip_chair",
            titleBn = "চেয়ার ফিটনেস রুটিন",
            titleEn = "Household Chair Routine",
            descriptionBn = "ঘরের সাধারণ একটি শক্ত চেয়ার ব্যবহার করে বুক, হাত ও পায়ের ব্যায়াম।",
            descriptionEn = "Upper and lower body training using a sturdy household chair.",
            level = "beginner",
            durationDays = 1,
            durationMinutesPerDay = 14,
            equipment = "chair",
            exercises = allExercises.filter { it.equipmentRequired == "chair" }
        ),
        WorkoutPlan(
            id = "equip_towel",
            titleBn = "তোয়ালে আইসোমেট্রিক রুটিন",
            titleEn = "Towel Isometric Routine",
            descriptionBn = "একটি বাথরুমের তোয়ালে দিয়ে ব্যাক ও বাইসেপের অবিশ্বাস্য টান ও শক্তি।",
            descriptionEn = "Powerful back and bicep contractions using towel tension.",
            level = "beginner",
            durationDays = 1,
            durationMinutesPerDay = 12,
            equipment = "towel",
            exercises = allExercises.filter { it.equipmentRequired == "towel" }
        )
    )
}
```

---

## FILE: `app/src/main/java/com/example/data/seed/FoodDatabaseData.kt`

```kotlin
package com.example.data.seed

enum class FoodCategory(val titleBn: String, val titleEn: String) {
    ALL("সকল খাবার", "All Foods"),
    PROTEIN("উচ্চ প্রোটিন", "High Protein"),
    CARBS("শর্করা ও শক্তি", "Carbs & Energy"),
    HEALTHY_FATS("উপকারী ফ্যাট", "Healthy Fats"),
    FRUITS_SNACKS("ফলমূল ও স্ন্যাকস", "Fruits & Snacks")
}

data class DesiFoodItem(
    val id: String,
    val nameBn: String,
    val nameEn: String,
    val portionBn: String,
    val portionEn: String,
    val calories: Int,
    val proteinGrams: Float,
    val carbsGrams: Float,
    val fatGrams: Float,
    val category: FoodCategory,
    val benefitsBn: String,
    val benefitsEn: String,
    val isBudgetFriendly: Boolean = true
)

object FoodDatabaseData {
    val allFoods: List<DesiFoodItem> = listOf(
        DesiFoodItem(
            id = "boiled_egg",
            nameBn = "সিদ্ধ ডিম (Boiled Egg)",
            nameEn = "Boiled Egg",
            portionBn = "১টি মাঝারি ডিম (৫০ গ্রাম)",
            portionEn = "1 medium egg (50g)",
            calories = 78,
            proteinGrams = 6.3f,
            carbsGrams = 0.6f,
            fatGrams = 5.3f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "সর্বোত্তম অ্যামিনো অ্যাসিড সমৃদ্ধ প্রোটিন। সহজে হজম হয় এবং দামেও সাশ্রয়ী।",
            benefitsEn = "Complete amino acid profile. Highly bioavailable and very budget friendly."
        ),
        DesiFoodItem(
            id = "lentils_dal",
            nameBn = "ঘন মসুর ডাল (Lentils / Dal)",
            nameEn = "Lentils / Dal",
            portionBn = "১ বাটি রান্না করা (১৫০ গ্রাম)",
            portionEn = "1 bowl cooked (150g)",
            calories = 165,
            proteinGrams = 12.0f,
            carbsGrams = 28.0f,
            fatGrams = 1.2f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "উচ্চ ফাইবার ও উদ্ভিজ্জ প্রোটিন। হৃদযন্ত্র সুস্থ রাখে ও কোলেস্টেরল কমায়।",
            benefitsEn = "High in dietary fiber and plant protein. Supports heart health."
        ),
        DesiFoodItem(
            id = "chicken_breast",
            nameBn = "মুরগির বুকের মাংস (Chicken Breast)",
            nameEn = "Chicken Breast",
            portionBn = "১০০ গ্রাম রান্না করা",
            portionEn = "100g cooked",
            calories = 165,
            proteinGrams = 31.0f,
            carbsGrams = 0.0f,
            fatGrams = 3.6f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "লিন প্রোটিন—অতিরিক্ত চর্বি ছাড়া পেশি গঠনে সবচেয়ে কার্যকরী খাদ্য।",
            benefitsEn = "Lean protein champion for muscle growth without excess fat."
        ),
        DesiFoodItem(
            id = "fish_rui",
            nameBn = "রুই মাছ (Rui Fish)",
            nameEn = "Rui Fish",
            portionBn = "১ টুকরো (৮০ গ্রাম)",
            portionEn = "1 piece (80g)",
            calories = 110,
            proteinGrams = 16.5f,
            carbsGrams = 0.0f,
            fatGrams = 4.5f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "ওমেগা-৩ ফ্যাটি অ্যাসিড ও প্রোটিন যা মস্তিষ্কের কার্যক্ষমতা ও জয়েন্ট ভালো রাখে।",
            benefitsEn = "Rich in Omega-3 fatty acids and high quality protein."
        ),
        DesiFoodItem(
            id = "chickpeas_chola",
            nameBn = "সিদ্ধ ছোলা বুট (Boiled Chickpeas)",
            nameEn = "Boiled Chickpeas (Chola)",
            portionBn = "১ কাপ (১০০ গ্রাম)",
            portionEn = "1 cup (100g)",
            calories = 164,
            proteinGrams = 8.9f,
            carbsGrams = 27.4f,
            fatGrams = 2.6f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "দীর্ঘক্ষণ পেটে থাকে, শক্তি জোগায় এবং চমৎকার দেশীয় প্রোটিন উৎস।",
            benefitsEn = "Sustained energy and low glycemic index snack."
        ),
        DesiFoodItem(
            id = "soya_chunks",
            nameBn = "সয়াবিন চাংক (Soya Chunks)",
            nameEn = "Soya Chunks",
            portionBn = "৫০ গ্রাম কাঁচা",
            portionEn = "50g dry",
            calories = 172,
            proteinGrams = 26.0f,
            carbsGrams = 16.5f,
            fatGrams = 0.5f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "সবার জন্য সবচেয়ে সস্তা ও সর্বোচ্চ প্রোটিন সমৃদ্ধ খাবার (৫২% প্রোটিন)।",
            benefitsEn = "The most affordable ultra-high protein source (over 50% protein)."
        ),
        DesiFoodItem(
            id = "curd_doi",
            nameBn = "টক দই (Sour Curd / Doi)",
            nameEn = "Sour Curd (Tok Doi)",
            portionBn = "১ বাটি (১০০ গ্রাম)",
            portionEn = "1 bowl (100g)",
            calories = 60,
            proteinGrams = 3.5f,
            carbsGrams = 4.7f,
            fatGrams = 3.3f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "প্রোবায়োটিক সমৃদ্ধ যা অন্ত্রের স্বাস্থ্য ও হজম প্রক্রিয়া দ্রুত ও সুস্থ রাখে।",
            benefitsEn = "Natural probiotic supporting gut health and digestion."
        ),
        DesiFoodItem(
            id = "brown_atta_roti",
            nameBn = "লাল আটার রুটি (Whole Wheat Roti)",
            nameEn = "Whole Wheat Roti",
            portionBn = "১টি মাঝারি রুটি (৪০ গ্রাম)",
            portionEn = "1 medium roti (40g)",
            calories = 104,
            proteinGrams = 3.1f,
            carbsGrams = 22.0f,
            fatGrams = 0.5f,
            category = FoodCategory.CARBS,
            benefitsBn = "কমপ্লেক্স কার্বোহাইড্রেট ও ফাইবার যা ইনসুলিন স্পাইক ছাড়াই দীর্ঘস্থায়ী শক্তি দেয়।",
            benefitsEn = "Complex carbohydrate providing steady, sustained energy."
        ),
        DesiFoodItem(
            id = "cooked_rice",
            nameBn = "সাধারণ ভাত (Cooked White/Red Rice)",
            nameEn = "Cooked Rice",
            portionBn = "১ মাঝারি প্লেট (১৫০ গ্রাম)",
            portionEn = "1 medium plate (150g)",
            calories = 195,
            proteinGrams = 4.1f,
            carbsGrams = 42.0f,
            fatGrams = 0.4f,
            category = FoodCategory.CARBS,
            benefitsBn = "ওয়ার্কআউটের পর মাংসপেশির গ্লাইকোজেন দ্রুত রিকভার করতে সাহায্য করে।",
            benefitsEn = "Quickly replenishes muscle glycogen post workout."
        ),
        DesiFoodItem(
            id = "peanuts_badam",
            nameBn = "ভাজা চিনাবাদাম (Roasted Peanuts)",
            nameEn = "Roasted Peanuts",
            portionBn = "১ মুঠো (৩০ গ্রাম)",
            portionEn = "1 handful (30g)",
            calories = 170,
            proteinGrams = 7.7f,
            carbsGrams = 4.8f,
            fatGrams = 14.8f,
            category = FoodCategory.HEALTHY_FATS,
            benefitsBn = "হার্টের জন্য উপকারী মনোস্যাচুরেটেড ফ্যাট এবং সাশ্রয়ী প্রোটিনের ভাণ্ডার।",
            benefitsEn = "Heart-healthy monounsaturated fats and affordable protein."
        ),
        DesiFoodItem(
            id = "banana_kola",
            nameBn = "বাংলা কলা (Banana)",
            nameEn = "Banana",
            portionBn = "১টি মাঝারি কলা (১০০ গ্রাম)",
            portionEn = "1 medium banana (100g)",
            calories = 89,
            proteinGrams = 1.1f,
            carbsGrams = 23.0f,
            fatGrams = 0.3f,
            category = FoodCategory.FRUITS_SNACKS,
            benefitsBn = "পটাসিয়াম ও দ্রুত শোষণযোগ্য ফ্রুক্টোজ—ওয়ার্কআউটের আগে তাৎক্ষণিক শক্তি দেয়।",
            benefitsEn = "Potassium powerhouse providing fast pre-workout fuel."
        ),
        DesiFoodItem(
            id = "chhatu_drink",
            nameBn = "ছোলা ছাতুর শরবত (Chhatu Drink)",
            nameEn = "Roasted Gram Flour (Chhatu)",
            portionBn = "২ টেবিল চামচ (৪০ গ্রাম)",
            portionEn = "2 tbsp (40g)",
            calories = 160,
            proteinGrams = 9.0f,
            carbsGrams = 25.0f,
            fatGrams = 2.0f,
            category = FoodCategory.PROTEIN,
            benefitsBn = "দেশি প্রাকৃতিক প্রোটিন শেক—গরমের দিনে শরীর ঠাণ্ডা রাখে ও পেট ভরা রাখে।",
            benefitsEn = "Traditional natural protein shake that cools the body."
        )
    )
}
```

---

## FILE: `app/src/main/java/com/example/domain/calculations/HealthCalculations.kt`

```kotlin
package com.example.domain.calculations

import com.example.core.i18n.Language
import com.example.core.i18n.TranslationManager
import java.util.Locale
import kotlin.math.roundToInt

data class HydrationBreakdown(
    val totalMl: Int,
    val totalLiters: Float,
    val targetGlasses250Ml: Int,
    val baseWeightMl: Int,
    val workoutSweatAllowanceMl: Int,
    val ageMetabolicFactorMlPerKg: Float,
    val formulaSummaryBn: String,
    val formulaSummaryEn: String
)

data class MetabolicBreakdown(
    val bmrCalories: Int,
    val tdeeCalories: Int,
    val targetDailyIntakeCalories: Int,
    val targetWorkoutBurnCalories: Int,
    val proteinGrams: Int,
    val carbsGrams: Int,
    val fatsGrams: Int,
    val recommendedStepsGoal: Int
)

object HealthCalculations {

    /**
     * Calculates Body Mass Index (BMI).
     * BMI = weight (kg) / (height (m))^2
     */
    fun calculateBMI(weightKg: Float, heightCm: Float): Float {
        if (heightCm <= 0f || weightKg <= 0f) return 0f
        val heightM = heightCm / 100f
        val bmi = weightKg / (heightM * heightM)
        return String.format(Locale.US, "%.1f", bmi).toFloatOrNull() ?: bmi
    }

    /**
     * Returns human-readable category for BMI in selected language.
     */
    fun getBMICategory(bmi: Float, lang: Language): String {
        val strings = TranslationManager.get(lang)
        return when {
            bmi <= 0f -> "-"
            bmi < 18.5f -> strings.bmiUnderweight
            bmi in 18.5f..24.9f -> strings.bmiNormal
            bmi in 25.0f..29.9f -> strings.bmiOverweight
            else -> strings.bmiObese
        }
    }

    /**
     * Scientifically calculates daily hydration requirements in milliliters, liters, and 250ml glasses.
     * Accounts for:
     * 1. Body weight (supports 25 kg children/youth up to 150+ kg strength athletes)
     * 2. Age-dependent cellular water turnover (40 ml/kg youth, 35 ml/kg young adult, 33 ml/kg adult, 30 ml/kg senior)
     * 3. Training frequency & goal thermoregulatory sweat loss (+150 ml to +750 ml)
     * 4. Biological metabolic thermoregulation factor
     */
    fun calculateScientificHydration(
        weightKg: Float,
        age: Int = 24,
        gender: String = "male",
        goal: String = "fitness",
        workoutDaysPerWeek: Int = 4
    ): HydrationBreakdown {
        val safeWeight = weightKg.coerceIn(20f, 180f)
        val safeAge = age.coerceIn(8, 95)
        val safeDays = workoutDaysPerWeek.coerceIn(1, 7)

        val ageFactorMlPerKg = when {
            safeAge < 18 -> 40f     // Youth/adolescent higher metabolic water turnover per kg
            safeAge <= 30 -> 35f    // Peak adult baseline
            safeAge <= 54 -> 33f    // Mature adult baseline
            else -> 30f             // Senior baseline
        }

        val baseWeightMl = (safeWeight * ageFactorMlPerKg).roundToInt()

        // Sweat & metabolic water demand from weekly training frequency and goal intensity
        val goalSweatBonus = when (goal) {
            "muscle_building" -> 220 // Creatine/glycogen intracellular hydration + hypertrophy sweat
            "weight_loss" -> 180     // Lipolysis & elevated cardio thermogenesis
            else -> 100
        }
        // Scale sweat allowance proportionally if user is very lightweight (< 45 kg)
        val weightScale = (safeWeight / 65f).coerceIn(0.45f, 1.35f)
        val rawSweatMl = ((safeDays * 65) + goalSweatBonus) * weightScale
        val workoutSweatAllowanceMl = ((rawSweatMl / 25f).roundToInt() * 25).coerceAtLeast(100)

        val genderThermoregulationMl = when (gender.lowercase(Locale.ROOT)) {
            "male" -> (120f * weightScale).roundToInt()
            "female" -> 0
            else -> (60f * weightScale).roundToInt()
        }

        val rawTotalMl = (baseWeightMl + workoutSweatAllowanceMl + genderThermoregulationMl).coerceIn(950, 5500)
        // Round to clean 50 ml increment
        val totalMl = ((rawTotalMl + 25) / 50) * 50
        val totalLiters = String.format(Locale.US, "%.2f", totalMl / 1000f).toFloatOrNull() ?: (totalMl / 1000f)
        val targetGlasses250Ml = ((totalMl + 124) / 250).coerceIn(4, 22)

        val formulaSummaryBn = String.format(
            Locale.US,
            "ওজন %.0f কেজি (বেস %d ml) + ট্রেনিং ঘাম (%d ml) = %d ml (%.2f লিটার • %d গ্লাস)",
            safeWeight,
            baseWeightMl,
            workoutSweatAllowanceMl + genderThermoregulationMl,
            totalMl,
            totalLiters,
            targetGlasses250Ml
        )
        val formulaSummaryEn = String.format(
            Locale.US,
            "Weight %.0f kg (Base %d ml) + Sweat Loss (%d ml) = %d ml (%.2f L • %d glasses)",
            safeWeight,
            baseWeightMl,
            workoutSweatAllowanceMl + genderThermoregulationMl,
            totalMl,
            totalLiters,
            targetGlasses250Ml
        )

        return HydrationBreakdown(
            totalMl = totalMl,
            totalLiters = totalLiters,
            targetGlasses250Ml = targetGlasses250Ml,
            baseWeightMl = baseWeightMl,
            workoutSweatAllowanceMl = workoutSweatAllowanceMl + genderThermoregulationMl,
            ageMetabolicFactorMlPerKg = ageFactorMlPerKg,
            formulaSummaryBn = formulaSummaryBn,
            formulaSummaryEn = formulaSummaryEn
        )
    }

    /**
     * Full clinical metabolic breakdown using Mifflin-St Jeor BMR, TDEE, and Evidence-Based Macro Splits.
     */
    fun calculateMetabolicBreakdown(
        weightKg: Float,
        heightCm: Float,
        age: Int,
        gender: String,
        goal: String,
        workoutDaysPerWeek: Int
    ): MetabolicBreakdown {
        val safeWeight = weightKg.coerceIn(20f, 180f)
        val safeHeight = heightCm.coerceIn(100f, 230f)
        val safeAge = age.coerceIn(8, 95)

        val baseBmr = (10f * safeWeight) + (6.25f * safeHeight) - (5f * safeAge)
        val bmr = when (gender.lowercase(Locale.ROOT)) {
            "female" -> (baseBmr - 161f).roundToInt()
            else -> (baseBmr + 5f).roundToInt()
        }.coerceIn(850, 3500)

        val activityMultiplier = when {
            workoutDaysPerWeek <= 1 -> 1.2f
            workoutDaysPerWeek in 2..3 -> 1.375f
            workoutDaysPerWeek in 4..5 -> 1.55f
            else -> 1.725f
        }

        val tdee = (bmr * activityMultiplier).roundToInt()

        // Scale calorie delta appropriately for body mass so lightweight youth aren't over-cut
        val massDeltaScale = (safeWeight / 68f).coerceIn(0.55f, 1.3f)
        val targetIntake = when (goal) {
            "weight_loss" -> (tdee - (380f * massDeltaScale).roundToInt()).coerceAtLeast((bmr * 0.92f).roundToInt())
            "muscle_building" -> tdee + (320f * massDeltaScale).roundToInt()
            else -> tdee
        }.coerceIn(1100, 4800)

        // Daily active workout burn target scaled to weight, goal, and training frequency
        val rawBurnTarget = when (goal) {
            "weight_loss" -> safeWeight * 5.8f
            "muscle_building" -> safeWeight * 4.6f
            else -> safeWeight * 4.8f
        } * (0.85f + (workoutDaysPerWeek.coerceIn(1, 7) * 0.04f))
        val targetWorkoutBurn = (((rawBurnTarget / 10f).roundToInt()) * 10).coerceIn(150, 850)

        // Evidence-based Protein (g/kg):
        // Muscle building: 1.8g/kg, Fat loss (lean mass preservation): 1.65g/kg, General athletic: 1.4g/kg
        val proteinPerKg = when (goal) {
            "muscle_building" -> 1.85f
            "weight_loss" -> 1.65f
            else -> 1.40f
        }
        val proteinGrams = (safeWeight * proteinPerKg).roundToInt().coerceIn(35, 260)
        val proteinCalories = proteinGrams * 4

        val fatCalories = (targetIntake * 0.26f).roundToInt()
        val fatsGrams = (fatCalories / 9).coerceIn(30, 140)

        val remainingCarbCalories = (targetIntake - proteinCalories - (fatsGrams * 9)).coerceAtLeast(400)
        val carbsGrams = (remainingCarbCalories / 4).coerceIn(80, 550)

        val recommendedStepsGoal = when (goal) {
            "weight_loss" -> 8500
            "muscle_building" -> 6500
            else -> 7500
        }

        return MetabolicBreakdown(
            bmrCalories = bmr,
            tdeeCalories = tdee,
            targetDailyIntakeCalories = targetIntake,
            targetWorkoutBurnCalories = targetWorkoutBurn,
            proteinGrams = proteinGrams,
            carbsGrams = carbsGrams,
            fatsGrams = fatsGrams,
            recommendedStepsGoal = recommendedStepsGoal
        )
    }

    /**
     * Estimates daily calorie requirement using Mifflin-St Jeor equation.
     */
    fun calculateEstimatedDailyCalories(
        weightKg: Float,
        heightCm: Float,
        age: Int,
        gender: String,
        goal: String,
        workoutDaysPerWeek: Int
    ): Int {
        return calculateMetabolicBreakdown(
            weightKg = weightKg,
            heightCm = heightCm,
            age = age,
            gender = gender,
            goal = goal,
            workoutDaysPerWeek = workoutDaysPerWeek
        ).targetDailyIntakeCalories
    }
}
```

---

## FILE: `app/src/main/java/com/example/domain/coach/SmartCoachEngine.kt`

```kotlin
package com.example.domain.coach

import com.example.core.i18n.Language
import java.util.concurrent.TimeUnit

enum class CoachTipType {
    RECOVERY,
    ENCOURAGEMENT,
    WEIGHT_REMINDER,
    HYDRATION,
    PROGRESSION
}

data class CoachTip(
    val id: String,
    val type: CoachTipType,
    val titleBn: String,
    val titleEn: String,
    val messageBn: String,
    val messageEn: String,
    val actionTextBn: String?,
    val actionTextEn: String?,
    val priority: Int
)

object SmartCoachEngine {

    fun evaluateTips(
        streakDays: Int,
        lastWorkoutDaysAgo: Int,
        daysSinceLastWeightLog: Int,
        todayWaterGlasses: Int,
        totalCompletedWorkouts: Int
    ): CoachTip {
        // Priority 1: Recovery if streak >= 3
        if (streakDays >= 3) {
            return CoachTip(
                id = "tip_recovery",
                type = CoachTipType.RECOVERY,
                titleBn = "স্মার্ট রিকভারি পরামর্শ",
                titleEn = "Smart Recovery Advice",
                messageBn = "টানা ৩ দিন আপনি নিষ্ঠার সাথে ব্যায়াম করেছেন! পেশির বৃদ্ধি ও চোট এড়াতে আজ পর্যাপ্ত বিশ্রাম ও ভালো ঘুমের ওপর নজর দিন।",
                messageEn = "You've worked out for 3 consecutive days! Rest and quality sleep are essential for muscle repair and injury prevention.",
                actionTextBn = "হালকা স্ট্রেচিং করুন",
                actionTextEn = "Light Stretch",
                priority = 1
            )
        }

        // Priority 2: Inactive for 2 or more days
        if (lastWorkoutDaysAgo >= 2) {
            return CoachTip(
                id = "tip_encouragement",
                type = CoachTipType.ENCOURAGEMENT,
                titleBn = "একটু সচেতনতা",
                titleEn = "Gentle Encouragement",
                messageBn = "গত ২ দিন শরীরচর্চা মিস হয়েছে। কোনো চাপ নেই—আজ মাত্র ৫ মিনিটের একটি কুইক ওয়ার্কআউট দিয়ে আবার ছন্দে ফিরুন!",
                messageEn = "You missed workouts for 2 days. No worries—start fresh today with an easy 5-minute quick session!",
                actionTextBn = "৫ মিনিটের ওয়ার্কআউট",
                actionTextEn = "5-Min Workout",
                priority = 2
            )
        }

        // Priority 3: Weight not logged for 7+ days
        if (daysSinceLastWeightLog >= 7) {
            return CoachTip(
                id = "tip_weight",
                type = CoachTipType.WEIGHT_REMINDER,
                titleBn = "ওজন আপডেট রিমাইন্ডার",
                titleEn = "Weight Check-In",
                messageBn = "গত ১ সপ্তাহ ধরে ওজন রেকর্ড করা হয়নি। আপনার অগ্রগতির সঠিক গ্রাফ দেখতে আজকের সকালের ওজন লগ করুন।",
                messageEn = "It's been a week since your last weight entry. Record your weight to keep your progress charts accurate.",
                actionTextBn = "ওজন লগ করুন",
                actionTextEn = "Log Weight",
                priority = 3
            )
        }

        // Priority 4: Low hydration (< 4 glasses)
        if (todayWaterGlasses < 4) {
            return CoachTip(
                id = "tip_water",
                type = CoachTipType.HYDRATION,
                titleBn = "হাইড্রেটেড থাকুন",
                titleEn = "Stay Hydrated",
                messageBn = "ব্যায়ামের কার্যকারিতা ও বিপাক ক্রিয়া সচল রাখতে পর্যাপ্ত পানি অত্যন্ত জরুরি। আজ আরও কয়েক গ্লাস পানি পান করুন।",
                messageEn = "Proper hydration boosts energy and metabolism. Don't forget to drink a couple more glasses of water today.",
                actionTextBn = "+১ গ্লাস পানি",
                actionTextEn = "+1 Glass Water",
                priority = 4
            )
        }

        // Default: Positive Progression
        return CoachTip(
            id = "tip_progression",
            type = CoachTipType.PROGRESSION,
            titleBn = "চমৎকার ধারাবাহিকতা!",
            titleEn = "Great Consistency!",
            messageBn = "আপনি দারুণ নিয়ম মেনে এগিয়ে যাচ্ছেন। আজকের জন্য প্রস্তুতকৃত ব্যায়ামটি সম্পন্ন করে ফিটনেসকে পরবর্তী ধাপে নিয়ে যান।",
            messageEn = "You are on track. Complete today's recommended workout and take your fitness to the next level!",
            actionTextBn = null,
            actionTextEn = null,
            priority = 5
        )
    }
}
```

---

## FILE: `app/src/main/java/com/example/domain/model/ActiveWorkoutSession.kt`

```kotlin
package com.example.domain.model

enum class WorkoutPhase {
    PREPARE,
    EXERCISE,
    REST,
    COMPLETED
}

data class ActiveWorkoutSession(
    val plan: WorkoutPlan,
    val currentExerciseIndex: Int = 0,
    val phase: WorkoutPhase = WorkoutPhase.PREPARE,
    val remainingSeconds: Int = 3,
    val totalSecondsInPhase: Int = 3,
    val isPaused: Boolean = false,
    val isMuted: Boolean = false,
    val totalElapsedSeconds: Int = 0,
    val totalCaloriesBurned: Int = 0,
    val completedExercisesCount: Int = 0
) {
    val currentExercise: Exercise
        get() = plan.exercises.getOrElse(currentExerciseIndex) { plan.exercises.first() }

    val nextExercise: Exercise?
        get() = plan.exercises.getOrNull(currentExerciseIndex + 1)

    val progressFraction: Float
        get() = if (totalSecondsInPhase > 0) {
            (totalSecondsInPhase - remainingSeconds).toFloat() / totalSecondsInPhase.toFloat()
        } else 0f
}
```

---

## FILE: `app/src/main/java/com/example/domain/model/ExerciseModels.kt`

```kotlin
package com.example.domain.model

enum class ExerciseCategory(val code: String, val nameBn: String, val nameEn: String) {
    ALL("all", "সব", "All"),
    CHEST("chest", "বুক (Chest)", "Chest"),
    ARMS("arms", "হাত (Arms)", "Arms"),
    ABS_CORE("abs_core", "অ্যাবস ও কোর", "Abs & Core"),
    LEGS("legs", "পা (Legs)", "Legs"),
    BACK("back", "পিঠ (Back)", "Back"),
    FULL_BODY("full_body", "ফুল বডি", "Full Body"),
    WARMUP_COOLDOWN("warmup", "ওয়ার্ম-আপ ও স্ট্রেচ", "Warm-up & Stretch")
}

data class Exercise(
    val id: String,
    val nameBn: String,
    val nameEn: String,
    val category: ExerciseCategory,
    val difficulty: String, // "beginner", "intermediate", "advanced"
    val equipmentRequired: String, // "none", "chair", "water_bottle", "towel", "bucket"
    val targetMusclesBn: String,
    val targetMusclesEn: String,
    val secondaryMusclesBn: String,
    val secondaryMusclesEn: String,
    val instructionsBn: List<String>,
    val instructionsEn: List<String>,
    val formTipsBn: List<String>,
    val formTipsEn: List<String>,
    val commonMistakesBn: List<String>,
    val commonMistakesEn: List<String>,
    val defaultDurationSeconds: Int = 30,
    val defaultReps: Int = 12,
    val isTimeBased: Boolean = true,
    val defaultRestSeconds: Int = 15,
    val safetyNoticeBn: String? = null,
    val safetyNoticeEn: String? = null
)

data class WorkoutPlan(
    val id: String,
    val titleBn: String,
    val titleEn: String,
    val descriptionBn: String,
    val descriptionEn: String,
    val level: String, // "beginner", "intermediate", "advanced"
    val durationDays: Int, // 7, 14, 30 or 1 for quick session
    val durationMinutesPerDay: Int,
    val exercises: List<Exercise>,
    val equipment: String = "none",
    val isCustom: Boolean = false
)
```

---

## FILE: `app/src/main/java/com/example/domain/model/UserProfile.kt`

```kotlin
package com.example.domain.model

data class UserProfile(
    val id: Int = 1,
    val name: String = "",
    val age: Int = 25,
    val heightCm: Float = 170f,
    val weightKg: Float = 68f,
    val gender: String = "male",
    val goal: String = "fitness",
    val fitnessLevel: String = "beginner",
    val workoutDaysPerWeek: Int = 4,
    val equipment: String = "none",
    val preferredLanguage: String = "bn",
    val isDarkMode: Boolean = true,
    val isOnboardingCompleted: Boolean = false
)
```

---

## FILE: `app/src/main/java/com/example/domain/recommendation/SmartPlanGenerator.kt`

```kotlin
package com.example.domain.recommendation

import com.example.data.seed.ExerciseLibraryData
import com.example.domain.model.Exercise
import com.example.domain.model.ExerciseCategory
import com.example.domain.model.WorkoutPlan

object SmartPlanGenerator {

    fun generatePlan(
        goal: String,
        fitnessLevel: String,
        availableMinutes: Int,
        equipment: String
    ): WorkoutPlan {
        val all = ExerciseLibraryData.allExercises

        // Filter exercises compatible with user's available equipment
        val filteredByEquipment = all.filter { ex ->
            when (equipment) {
                "none" -> ex.equipmentRequired == "none"
                "basic" -> ex.equipmentRequired == "none" || ex.equipmentRequired == "chair" || ex.equipmentRequired == "towel" || ex.equipmentRequired == "water_bottle"
                else -> true
            }
        }

        // Determine target count based on available minutes
        val exerciseCount = when {
            availableMinutes <= 10 -> 4
            availableMinutes <= 15 -> 6
            availableMinutes <= 20 -> 8
            else -> 10
        }

        val selectedExercises = mutableListOf<Exercise>()

        // Always add a warm-up if >= 15 mins
        if (availableMinutes >= 15) {
            all.find { it.id == "arm_circles" }?.let { selectedExercises.add(it) }
        }

        // Add targeted exercises based on goal
        when (goal) {
            "weight_loss" -> {
                // Focus: Full body cardio + core
                val cardio = filteredByEquipment.filter { it.category == ExerciseCategory.FULL_BODY }
                val core = filteredByEquipment.filter { it.category == ExerciseCategory.ABS_CORE }
                val legs = filteredByEquipment.filter { it.category == ExerciseCategory.LEGS }
                selectedExercises.addAll((cardio + core + legs).shuffled().take(exerciseCount - selectedExercises.size))
            }
            "muscle_building" -> {
                // Focus: Chest, arms, legs strength
                val chest = filteredByEquipment.filter { it.category == ExerciseCategory.CHEST }
                val arms = filteredByEquipment.filter { it.category == ExerciseCategory.ARMS }
                val legs = filteredByEquipment.filter { it.category == ExerciseCategory.LEGS }
                val back = filteredByEquipment.filter { it.category == ExerciseCategory.BACK }
                selectedExercises.addAll((chest + arms + legs + back).shuffled().take(exerciseCount - selectedExercises.size))
            }
            else -> {
                // General Fitness: balanced one from each category
                val balanced = listOfNotNull(
                    filteredByEquipment.find { it.category == ExerciseCategory.CHEST },
                    filteredByEquipment.find { it.category == ExerciseCategory.LEGS },
                    filteredByEquipment.find { it.category == ExerciseCategory.ABS_CORE },
                    filteredByEquipment.find { it.category == ExerciseCategory.ARMS },
                    filteredByEquipment.find { it.category == ExerciseCategory.FULL_BODY }
                )
                selectedExercises.addAll(balanced.take(exerciseCount - selectedExercises.size))
            }
        }

        // Ensure minimum exercises
        if (selectedExercises.size < 4) {
            selectedExercises.addAll(filteredByEquipment.take(4 - selectedExercises.size))
        }

        // Add cool-down stretch if time permits
        if (availableMinutes >= 15) {
            all.find { it.id == "childs_pose" }?.let { selectedExercises.add(it) }
        }

        val titleBn = when (goal) {
            "weight_loss" -> "স্মার্ট ফ্যাট বার্ন কাস্টম প্ল্যান"
            "muscle_building" -> "স্মার্ট মাসল বিল্ড কাস্টম প্ল্যান"
            else -> "স্মার্ট ডেইলি ফিটনেস প্ল্যান"
        }
        val titleEn = when (goal) {
            "weight_loss" -> "Smart Fat Burn Custom Plan"
            "muscle_building" -> "Smart Muscle Build Custom Plan"
            else -> "Smart Daily Fitness Plan"
        }

        return WorkoutPlan(
            id = "generated_smart_plan_${System.currentTimeMillis()}",
            titleBn = "$titleBn ($availableMinutes মিনিট)",
            titleEn = "$titleEn ($availableMinutes min)",
            descriptionBn = "আপনার লক্ষ্য, ফিটনেস স্তর এবং ঘরের সরঞ্জাম অনুযায়ী স্বয়ংক্রিয়ভাবে তৈরি রুটিন।",
            descriptionEn = "Algorithmically tailored routine according to your goal, level and home gear.",
            level = fitnessLevel,
            durationDays = 1,
            durationMinutesPerDay = availableMinutes,
            exercises = selectedExercises.distinctBy { it.id },
            equipment = equipment,
            isCustom = true
        )
    }
}
```

---

## FILE: `app/src/main/java/com/example/domain/recommendation/WorkoutRecommendationEngine.kt`

```kotlin
package com.example.domain.recommendation

import com.example.core.i18n.Language
import com.example.domain.model.UserProfile
import java.util.Calendar

data class RecommendedWorkout(
    val id: String,
    val titleBn: String,
    val titleEn: String,
    val category: String, // "full_body", "chest_arms", "legs", "abs_core", "stretching"
    val durationMinutes: Int,
    val estimatedCalories: Int,
    val targetMusclesBn: String,
    val targetMusclesEn: String,
    val rationaleBn: String,
    val rationaleEn: String,
    val exerciseCount: Int,
    val intensity: String // "Low", "Moderate", "High"
)

object WorkoutRecommendationEngine {

    fun getTodayRecommendation(
        userProfile: UserProfile?,
        lastTrainedCategory: String? = null,
        daysStreak: Int = 0,
        currentHour: Int = Calendar.getInstance().get(Calendar.HOUR_OF_DAY)
    ): RecommendedWorkout {
        val isMorning = currentHour in 5..11
        val isNight = currentHour >= 21 || currentHour < 5
        val goal = userProfile?.goal ?: "fitness"
        val level = userProfile?.fitnessLevel ?: "beginner"
        val hasEquipment = userProfile?.equipment != "none"

        // Rule 1: Rest day recommendation if streak >= 4 days of heavy workouts
        if (daysStreak >= 4 && lastTrainedCategory != "stretching") {
            return RecommendedWorkout(
                id = "rec_recovery",
                titleBn = "রিকভারি ও ফ্লেক্সিবিলিটি স্ট্রেচিং",
                titleEn = "Recovery & Mobility Stretch",
                category = "stretching",
                durationMinutes = 12,
                estimatedCalories = 65,
                targetMusclesBn = "সম্পূর্ণ শরীর ও জয়েন্ট",
                targetMusclesEn = "Full Body & Joints",
                rationaleBn = "আপনি টানা ৪ দিন কঠোর শরীরচর্চা করেছেন। পেশির দ্রুত রিকভারির জন্য আজ হালকা স্ট্রেচিং সুপারিশ করা হলো।",
                rationaleEn = "You trained hard for 4 consecutive days. Light stretching is recommended for optimal muscle recovery.",
                exerciseCount = 6,
                intensity = "Low"
            )
        }

        // Rule 2: Muscle group alternation (Avoid same muscle group as yesterday)
        if (lastTrainedCategory != null) {
            when (lastTrainedCategory) {
                "legs" -> {
                    return RecommendedWorkout(
                        id = "rec_upper_body",
                        titleBn = "আপার বডি ও আর্মস বুস্টার",
                        titleEn = "Upper Body & Arms Sculpt",
                        category = "chest_arms",
                        durationMinutes = if (level == "advanced") 22 else 15,
                        estimatedCalories = if (level == "advanced") 180 else 130,
                        targetMusclesBn = "বুক, ট্রাইসেপস ও কাঁধ",
                        targetMusclesEn = "Chest, Triceps & Shoulders",
                        rationaleBn = "গতকাল পায়ের ব্যায়াম করার পর আজ শরীরের উপরের অংশের জন্য আপার বডি ওয়ার্কআউট সবচেয়ে কার্যকর।",
                        rationaleEn = "Since you trained legs recently, focusing on upper body ensures balanced training and muscle rest.",
                        exerciseCount = if (level == "advanced") 8 else 6,
                        intensity = "Moderate"
                    )
                }
                "chest_arms" -> {
                    return RecommendedWorkout(
                        id = "rec_legs_core",
                        titleBn = "লোয়ার বডি ও কোর পাওয়ার",
                        titleEn = "Lower Body & Core Power",
                        category = "legs",
                        durationMinutes = if (level == "advanced") 20 else 14,
                        estimatedCalories = if (level == "advanced") 190 else 135,
                        targetMusclesBn = "কোয়াডস, হ্যামস্ট্রিং ও অ্যাবস",
                        targetMusclesEn = "Quads, Hamstrings & Abs",
                        rationaleBn = "আপার বডিকে বিশ্রাম দিয়ে আজ পায়ের মাংসপেশি ও কোরের শক্তি বৃদ্ধি করতে এই রুটিন প্রস্তুত করা হয়েছে।",
                        rationaleEn = "Resting your upper body today while targeting lower body maximizes fat burn and core stability.",
                        exerciseCount = if (level == "advanced") 8 else 6,
                        intensity = "High"
                    )
                }
            }
        }

        // Rule 3: Night workout preference -> Mobility & Core calming session
        if (isNight) {
            return RecommendedWorkout(
                id = "rec_night_core",
                titleBn = "নাইট রিল্যাক্স কোর ও স্ট্রেচ",
                titleEn = "Night Relax Core & Stretch",
                category = "abs_core",
                durationMinutes = 10,
                estimatedCalories = 75,
                targetMusclesBn = "অ্যাবস ও লোয়ার ব্যাক",
                targetMusclesEn = "Abs & Lower Back",
                rationaleBn = "দেরী রাতে ভারী কার্ডিও ঘুমের ব্যাঘাত ঘটাতে পারে, তাই শান্ত কোর ও স্ট্রেচিং সেশন নির্বাচন করা হয়েছে।",
                rationaleEn = "Late night workouts favor calming core & mobility rather than high cardio to support quality sleep.",
                exerciseCount = 5,
                intensity = "Low"
            )
        }

        // Default based on Goal & Time of Day
        return when (goal) {
            "weight_loss" -> {
                RecommendedWorkout(
                    id = "rec_fat_burn",
                    titleBn = if (isMorning) "মর্নিং ফ্যাট বার্নার কার্ডিও" else "হিট (HIIT) ফ্যাট বার্ন",
                    titleEn = if (isMorning) "Morning Fat Burn Cardio" else "HIIT Fat Burner",
                    category = "full_body",
                    durationMinutes = 15,
                    estimatedCalories = 160,
                    targetMusclesBn = "সম্পূর্ণ শরীর",
                    targetMusclesEn = "Full Body",
                    rationaleBn = "আপনার লক্ষ্য দ্রুত মেদ কমানো। এই ফুল-বডি কার্ডিও মেটাবলিজম বাড়িয়ে সর্বোচ্চ ক্যালরি পোড়ায়।",
                    rationaleEn = "Tailored for your weight-loss goal. High-energy bodyweight movements maximize calorie burn.",
                    exerciseCount = 7,
                    intensity = "High"
                )
            }
            "muscle_building" -> {
                RecommendedWorkout(
                    id = "rec_muscle_strength",
                    titleBn = "বডিওয়েট স্ট্রেংথ ও পাওয়ার",
                    titleEn = "Bodyweight Strength & Power",
                    category = "chest_arms",
                    durationMinutes = 18,
                    estimatedCalories = 150,
                    targetMusclesBn = "বুক, কোর ও কাঁধ",
                    targetMusclesEn = "Chest, Core & Shoulders",
                    rationaleBn = "পেশি গঠনের লক্ষ্যে প্রগ্রেসিভ বডিওয়েট এক্সারসাইজ নির্বাচন করা হয়েছে।",
                    rationaleEn = "Progressive push and core movements formulated specifically to trigger muscle hypertrophy.",
                    exerciseCount = 7,
                    intensity = "Moderate"
                )
            }
            else -> {
                RecommendedWorkout(
                    id = "rec_daily_fit",
                    titleBn = "দৈনিক ফুল-বডি ফিটনেস",
                    titleEn = "Daily Full-Body Conditioning",
                    category = "full_body",
                    durationMinutes = 12,
                    estimatedCalories = 120,
                    targetMusclesBn = "সম্পূর্ণ শরীর",
                    targetMusclesEn = "Full Body",
                    rationaleBn = "সারাদিনের কর্মচাঞ্চল্য ও রক্ত সঞ্চালন বাড়াতে একটি সুষম ও দ্রুতগতির ফিটনেস রুটিন।",
                    rationaleEn = "A balanced full-body conditioning session designed to boost energy and cardiovascular health.",
                    exerciseCount = 6,
                    intensity = "Moderate"
                )
            }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/domain/service/StorageService.kt`

```kotlin
package com.example.domain.service

import com.example.data.local.entity.ChallengeProgressEntity
import com.example.data.local.entity.CustomWorkoutEntity
import com.example.data.local.entity.NutritionLogEntity
import com.example.data.local.entity.SavedMusicTrackEntity
import com.example.data.local.entity.WaterLogEntity
import com.example.data.local.entity.WeightLogEntity
import com.example.data.local.entity.WorkoutLogEntity
import com.example.domain.model.UserProfile
import kotlinx.coroutines.flow.Flow

interface StorageService {
    fun getUserProfileFlow(): Flow<UserProfile?>
    suspend fun getUserProfile(): UserProfile?
    suspend fun saveUserProfile(profile: UserProfile)
    suspend fun updateLanguage(langCode: String)
    suspend fun updateTheme(isDarkMode: Boolean)
    suspend fun markOnboardingComplete()

    // Water tracking
    fun getTodayWaterGlassesFlow(dateIso: String): Flow<Int>
    fun getAllWaterLogsFlow(): Flow<List<WaterLogEntity>>
    suspend fun addWaterGlass(dateIso: String): Int
    suspend fun removeWaterGlass(dateIso: String): Int

    // Weight tracking
    fun getLatestWeightFlow(): Flow<Float?>
    fun getAllWeightLogsFlow(): Flow<List<WeightLogEntity>>
    suspend fun logWeight(weightKg: Float)

    // Workouts & Stats
    fun getTodayCaloriesBurnedFlow(): Flow<Int>
    fun getAllWorkoutLogsFlow(): Flow<List<WorkoutLogEntity>>
    suspend fun saveWorkoutLog(title: String, durationSeconds: Int, caloriesBurned: Int, exercisesCompleted: Int): Long
    suspend fun getWorkoutStreak(): Int
    suspend fun getTotalCompletedWorkouts(): Int

    // Favorites & Custom Workouts
    fun getFavoriteExerciseIdsFlow(): Flow<List<String>>
    suspend fun toggleFavoriteExercise(exerciseId: String): Boolean
    fun getCustomWorkoutsFlow(): Flow<List<CustomWorkoutEntity>>
    suspend fun saveCustomWorkout(title: String, exerciseIds: List<String>, durationSec: Int, restSec: Int): Long
    suspend fun deleteCustomWorkout(id: Long)

    // Pro Subscription (Secret Code: IshanX10)
    fun isProSubscribedFlow(): Flow<Boolean> = kotlinx.coroutines.flow.flowOf(false)
    suspend fun setProSubscribed(enabled: Boolean) {}

    // Daily Nutrition Logs
    fun getNutritionLogsForDateFlow(dateIso: String): Flow<List<NutritionLogEntity>>
    suspend fun logNutritionItem(
        dateIso: String,
        foodNameBn: String,
        foodNameEn: String,
        calories: Int,
        proteinGrams: Float,
        carbsGrams: Float = 0f,
        fatGrams: Float = 0f
    ): Long
    suspend fun deleteNutritionLog(id: Long)

    // Saved Music Tracks
    fun getSavedMusicTracksFlow(): Flow<List<SavedMusicTrackEntity>>
    suspend fun saveMusicTrack(uriString: String, title: String): Long
    suspend fun deleteMusicTrack(id: Long)

    // 30-Day Challenge Progress
    fun getAllChallengeProgressFlow(): Flow<List<ChallengeProgressEntity>>
    suspend fun toggleChallengeDay(challengeId: String, dayNumber: Int)

    // Local JSON Backup & Restore
    suspend fun exportBackupJson(): String
    suspend fun importBackupJson(json: String): Boolean

    suspend fun deleteAllData(): Boolean
}
```

---

## FILE: `app/src/main/java/com/example/ui/HomeFitViewModel.kt`

```kotlin
package com.example.ui

import androidx.lifecycle.ViewModel
import androidx.lifecycle.viewModelScope
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.core.i18n.TranslationManager
import com.example.domain.calculations.HealthCalculations
import com.example.domain.coach.CoachTip
import com.example.domain.coach.SmartCoachEngine
import com.example.domain.model.UserProfile
import com.example.domain.recommendation.RecommendedWorkout
import com.example.domain.recommendation.WorkoutRecommendationEngine
import com.example.domain.service.StorageService
import com.example.ui.components.MainTab
import kotlinx.coroutines.flow.MutableStateFlow
import kotlinx.coroutines.flow.StateFlow
import kotlinx.coroutines.flow.asStateFlow
import kotlinx.coroutines.flow.update
import kotlinx.coroutines.isActive
import kotlinx.coroutines.launch
import java.text.SimpleDateFormat
import java.util.Date
import java.util.Locale

sealed interface AppScreen {
    data object Splash : AppScreen
    data class WelcomeSlides(val slideIndex: Int = 0) : AppScreen
    data object NameInput : AppScreen
    data object ProfileSetup : AppScreen
    data object HealthDisclaimer : AppScreen
    data class MainApp(val currentTab: MainTab = MainTab.HOME) : AppScreen
    data class WorkoutPreview(val plan: com.example.domain.model.WorkoutPlan) : AppScreen
    data object ActivePlayer : AppScreen
    data class WorkoutCompleted(val session: com.example.domain.model.ActiveWorkoutSession) : AppScreen
}

data class HomeFitUiState(
    val currentScreen: AppScreen = AppScreen.Splash,
    val userProfile: UserProfile? = null,
    val selectedLanguage: Language = Language.BENGALI,
    val isDarkMode: Boolean = true,
    val isLoading: Boolean = true,

    // Onboarding Form Inputs
    val nameInput: String = "",
    val nameError: String? = null,
    val ageInput: Int = 24,
    val heightInput: Float = 170f,
    val weightInput: Float = 66f,
    val genderInput: String = "male",
    val goalInput: String = "fitness",
    val levelInput: String = "beginner",
    val daysInput: Int = 4,
    val equipmentInput: String = "none",
    val disclaimerAccepted: Boolean = false,

    // Live Clinical Biometric & Hydration Metrics
    val liveBmi: Float = 22.8f,
    val liveBmiCategory: String = "",
    val liveBmrCalories: Int = 1610,
    val liveTdeeCalories: Int = 2495,
    val liveDailyCalories: Int = 2495,
    val liveProteinGrams: Int = 92,
    val liveCarbsGrams: Int = 310,
    val liveFatsGrams: Int = 68,
    val todayWaterGoalMl: Int = 2700,
    val todayWaterGoalLiters: Float = 2.70f,
    val hydrationFormulaSummaryBn: String = "",
    val hydrationFormulaSummaryEn: String = "",

    // Phase 2 Smart Home States (Zero Fake Data)
    val recommendedWorkout: RecommendedWorkout = WorkoutRecommendationEngine.getTodayRecommendation(null),
    val todayCaloriesBurned: Int = 0,
    val todayCaloriesGoal: Int = 320,
    val todayWaterGlasses: Int = 0,
    val todayWaterGoal: Int = 11,
    val todaySteps: Int = 0,
    val todayStepsGoal: Int = 7500,
    val streakDays: Int = 0,
    val smartCoachTip: CoachTip = SmartCoachEngine.evaluateTips(0, 0, 0, 0, 0),
    val completedWeekDays: List<Int> = emptyList(),
    val isStepDialogOpen: Boolean = false,
    val isWeightDialogOpen: Boolean = false,
    val favoriteExerciseIds: List<String> = emptyList(),
    val customWorkouts: List<com.example.data.local.entity.CustomWorkoutEntity> = emptyList(),
    val weightLogs: List<com.example.data.local.entity.WeightLogEntity> = emptyList(),
    val waterLogs: List<com.example.data.local.entity.WaterLogEntity> = emptyList(),
    val workoutLogs: List<com.example.data.local.entity.WorkoutLogEntity> = emptyList(),
    val todayNutritionLogs: List<com.example.data.local.entity.NutritionLogEntity> = emptyList(),
    val savedMusicTracks: List<com.example.data.local.entity.SavedMusicTrackEntity> = emptyList(),
    val challengeProgressList: List<com.example.data.local.entity.ChallengeProgressEntity> = emptyList(),
    val voiceRepCounterEnabled: Boolean = true,
    val isProSubscribed: Boolean = false,
    val isProDialogOpen: Boolean = false,
    val proCodeError: String? = null,
    val proActivationMessage: String? = null
) {
    val strings: AppStrings
        get() = TranslationManager.get(selectedLanguage)
}

class HomeFitViewModel(
    private val storageService: StorageService,
    private val audioFeedbackManager: com.example.core.audio.AudioFeedbackManager? = null,
    private val workoutMusicManager: com.example.core.audio.WorkoutMusicManager? = null
) : ViewModel() {

    private val _uiState = MutableStateFlow(HomeFitUiState())
    val uiState: StateFlow<HomeFitUiState> = _uiState.asStateFlow()

    private val _activeWorkoutSession = MutableStateFlow<com.example.domain.model.ActiveWorkoutSession?>(null)
    val activeWorkoutSessionFlow: StateFlow<com.example.domain.model.ActiveWorkoutSession?> = _activeWorkoutSession.asStateFlow()

    private val _fallbackMusicState = MutableStateFlow(com.example.core.audio.WorkoutMusicState())
    val musicStateFlow: StateFlow<com.example.core.audio.WorkoutMusicState> =
        workoutMusicManager?.musicState ?: _fallbackMusicState.asStateFlow()

    private val todayIso: String
        get() = SimpleDateFormat("yyyy-MM-dd", Locale.US).format(Date())

    private var timerJob: kotlinx.coroutines.Job? = null

    init {
        audioFeedbackManager?.onDuckingChange = { isDucked ->
            workoutMusicManager?.setDucking(isDucked)
        }
        loadUserProfile()
        observeTodayData()
    }

    private fun loadUserProfile() {
        viewModelScope.launch {
            storageService.getUserProfileFlow().collect { profile ->
                if (profile != null) {
                    val lang = if (profile.preferredLanguage == "en") Language.ENGLISH else Language.BENGALI
                    val bmi = HealthCalculations.calculateBMI(profile.weightKg, profile.heightCm)
                    val bmiCat = HealthCalculations.getBMICategory(bmi, lang)
                    val metabolic = HealthCalculations.calculateMetabolicBreakdown(
                        weightKg = profile.weightKg,
                        heightCm = profile.heightCm,
                        age = profile.age,
                        gender = profile.gender,
                        goal = profile.goal,
                        workoutDaysPerWeek = profile.workoutDaysPerWeek
                    )
                    val hydration = HealthCalculations.calculateScientificHydration(
                        weightKg = profile.weightKg,
                        age = profile.age,
                        gender = profile.gender,
                        goal = profile.goal,
                        workoutDaysPerWeek = profile.workoutDaysPerWeek
                    )

                    val totalWorkouts = storageService.getTotalCompletedWorkouts()
                    val streak = storageService.getWorkoutStreak().coerceAtLeast(if (totalWorkouts > 0) 1 else 0)
                    val recommendation = WorkoutRecommendationEngine.getTodayRecommendation(
                        userProfile = profile,
                        daysStreak = streak.coerceAtLeast(1)
                    )

                    val coachTip = SmartCoachEngine.evaluateTips(
                        streakDays = streak,
                        lastWorkoutDaysAgo = 0,
                        daysSinceLastWeightLog = 0,
                        todayWaterGlasses = _uiState.value.todayWaterGlasses,
                        totalCompletedWorkouts = totalWorkouts
                    )

                    _uiState.update { current ->
                        current.copy(
                            userProfile = profile,
                            selectedLanguage = lang,
                            isDarkMode = profile.isDarkMode,
                            isLoading = false,
                            nameInput = profile.name,
                            ageInput = profile.age,
                            heightInput = profile.heightCm,
                            weightInput = profile.weightKg,
                            genderInput = profile.gender,
                            goalInput = profile.goal,
                            levelInput = profile.fitnessLevel,
                            daysInput = profile.workoutDaysPerWeek,
                            equipmentInput = profile.equipment,
                            liveBmi = bmi,
                            liveBmiCategory = bmiCat,
                            liveBmrCalories = metabolic.bmrCalories,
                            liveTdeeCalories = metabolic.tdeeCalories,
                            liveDailyCalories = metabolic.targetDailyIntakeCalories,
                            liveProteinGrams = metabolic.proteinGrams,
                            liveCarbsGrams = metabolic.carbsGrams,
                            liveFatsGrams = metabolic.fatsGrams,
                            todayCaloriesGoal = metabolic.targetWorkoutBurnCalories,
                            todayWaterGoal = hydration.targetGlasses250Ml,
                            todayWaterGoalMl = hydration.totalMl,
                            todayWaterGoalLiters = hydration.totalLiters,
                            hydrationFormulaSummaryBn = hydration.formulaSummaryBn,
                            hydrationFormulaSummaryEn = hydration.formulaSummaryEn,
                            todayStepsGoal = metabolic.recommendedStepsGoal,
                            streakDays = streak,
                            recommendedWorkout = recommendation,
                            smartCoachTip = coachTip,
                            currentScreen = if (profile.isOnboardingCompleted) {
                                AppScreen.MainApp(MainTab.HOME)
                            } else {
                                AppScreen.WelcomeSlides(0)
                            }
                        )
                    }
                } else {
                    recomputeMetrics()
                    _uiState.update { current ->
                        current.copy(
                            isLoading = false,
                            currentScreen = AppScreen.Splash
                        )
                    }
                }
            }
        }
    }

    private fun observeTodayData() {
        // Observe water logs for today
        viewModelScope.launch {
            storageService.getTodayWaterGlassesFlow(todayIso).collect { count ->
                _uiState.update { current ->
                    val updated = current.copy(todayWaterGlasses = count)
                    val tip = SmartCoachEngine.evaluateTips(
                        streakDays = current.streakDays,
                        lastWorkoutDaysAgo = 0,
                        daysSinceLastWeightLog = 0,
                        todayWaterGlasses = count,
                        totalCompletedWorkouts = 1
                    )
                    updated.copy(smartCoachTip = tip)
                }
            }
        }

        // Observe calories burned today
        viewModelScope.launch {
            storageService.getTodayCaloriesBurnedFlow().collect { calories ->
                _uiState.update { it.copy(todayCaloriesBurned = calories) }
            }
        }

        // Observe favorites
        viewModelScope.launch {
            storageService.getFavoriteExerciseIdsFlow().collect { favs ->
                _uiState.update { it.copy(favoriteExerciseIds = favs) }
            }
        }

        // Observe custom workouts
        viewModelScope.launch {
            storageService.getCustomWorkoutsFlow().collect { list ->
                _uiState.update { it.copy(customWorkouts = list) }
            }
        }

        // Observe all weight logs
        viewModelScope.launch {
            storageService.getAllWeightLogsFlow().collect { logs ->
                _uiState.update { it.copy(weightLogs = logs) }
            }
        }

        // Observe all water logs
        viewModelScope.launch {
            storageService.getAllWaterLogsFlow().collect { logs ->
                _uiState.update { it.copy(waterLogs = logs) }
            }
        }

        // Observe all workout logs and compute real completed weekdays for the current week
        viewModelScope.launch {
            storageService.getAllWorkoutLogsFlow().collect { logs ->
                val weekCompletedIndices = computeCompletedWeekDaysFromLogs(logs)
                _uiState.update {
                    it.copy(
                        workoutLogs = logs,
                        completedWeekDays = weekCompletedIndices
                    )
                }
            }
        }

        // Observe today's nutrition logs
        viewModelScope.launch {
            storageService.getNutritionLogsForDateFlow(todayIso).collect { logs ->
                _uiState.update { it.copy(todayNutritionLogs = logs) }
            }
        }

        // Observe saved music tracks
        viewModelScope.launch {
            storageService.getSavedMusicTracksFlow().collect { tracks ->
                workoutMusicManager?.updatePlaylist(tracks)
                _uiState.update { it.copy(savedMusicTracks = tracks) }
            }
        }

        // Observe 30-day challenge progress
        viewModelScope.launch {
            storageService.getAllChallengeProgressFlow().collect { progress ->
                _uiState.update { it.copy(challengeProgressList = progress) }
            }
        }

        // Observe Pro Subscription status (Secret Code: IshanX10)
        viewModelScope.launch {
            storageService.isProSubscribedFlow().collect { isPro ->
                _uiState.update { it.copy(isProSubscribed = isPro) }
            }
        }
    }

    suspend fun exportBackupJson(): String {
        return storageService.exportBackupJson()
    }

    suspend fun importBackupJson(json: String): Boolean {
        val success = storageService.importBackupJson(json)
        if (success) {
            loadUserProfile()
        }
        return success
    }

    fun toggleFavorite(exerciseId: String) {
        viewModelScope.launch {
            storageService.toggleFavoriteExercise(exerciseId)
        }
    }

    fun saveCustomWorkout(title: String, exerciseIds: List<String>, durationSec: Int, restSec: Int) {
        viewModelScope.launch {
            storageService.saveCustomWorkout(title, exerciseIds, durationSec, restSec)
        }
    }

    fun deleteCustomWorkout(id: Long) {
        viewModelScope.launch {
            storageService.deleteCustomWorkout(id)
        }
    }

    // Daily Nutrition Logging Actions
    fun logNutritionItem(
        foodNameBn: String,
        foodNameEn: String,
        calories: Int,
        proteinGrams: Float,
        carbsGrams: Float = 0f,
        fatGrams: Float = 0f
    ) {
        viewModelScope.launch {
            storageService.logNutritionItem(
                dateIso = todayIso,
                foodNameBn = foodNameBn,
                foodNameEn = foodNameEn,
                calories = calories,
                proteinGrams = proteinGrams,
                carbsGrams = carbsGrams,
                fatGrams = fatGrams
            )
            audioFeedbackManager?.vibrateShort()
        }
    }

    fun deleteNutritionLog(id: Long) {
        viewModelScope.launch {
            storageService.deleteNutritionLog(id)
        }
    }

    // Music & Offline Gym Beats Actions
    fun addMusicTrack(uriString: String, title: String) {
        viewModelScope.launch {
            val id = storageService.saveMusicTrack(uriString, title)
            val newTrack = com.example.data.local.entity.SavedMusicTrackEntity(
                id = id,
                uriString = uriString,
                title = title
            )
            workoutMusicManager?.playLocalTrack(newTrack)
        }
    }

    fun deleteMusicTrack(id: Long) {
        viewModelScope.launch {
            storageService.deleteMusicTrack(id)
        }
    }

    fun playMusicTrack(track: com.example.data.local.entity.SavedMusicTrackEntity) {
        workoutMusicManager?.playLocalTrack(track)
    }

    fun selectBeatPreset(preset: com.example.core.audio.OfflineBeatPreset) {
        workoutMusicManager?.playBeatPreset(preset)
    }

    fun toggleMusicPlayPause() {
        workoutMusicManager?.togglePlayPause()
    }

    fun nextMusicTrack() {
        workoutMusicManager?.playNextLocalTrack()
    }

    fun setMusicVolume(volume: Float) {
        workoutMusicManager?.setVolume(volume)
    }

    fun toggleVoiceRepCounter() {
        _uiState.update { it.copy(voiceRepCounterEnabled = !it.voiceRepCounterEnabled) }
    }

    // 30-Day Challenge Actions
    fun toggleChallengeDay(challengeId: String, dayNumber: Int) {
        viewModelScope.launch {
            storageService.toggleChallengeDay(challengeId, dayNumber)
            audioFeedbackManager?.vibrateShort()
        }
    }

    // Custom HIIT / Tabata Interval Session
    fun startTabataSession(
        titleBn: String,
        titleEn: String,
        workSeconds: Int,
        restSeconds: Int,
        rounds: Int,
        exercisesPool: List<com.example.domain.model.Exercise>
    ) {
        val pool = exercisesPool.ifEmpty { com.example.data.seed.ExerciseLibraryData.allExercises.take(4) }
        val configuredExercises = (0 until rounds).map { index ->
            val baseEx = pool[index % pool.size]
            baseEx.copy(
                id = "${baseEx.id}_round_${index + 1}",
                nameBn = "${baseEx.nameBn} (রাউন্ড ${index + 1}/$rounds)",
                nameEn = "${baseEx.nameEn} (Round ${index + 1}/$rounds)",
                defaultDurationSeconds = workSeconds,
                defaultRestSeconds = restSeconds
            )
        }
        val totalMinutes = ((workSeconds + restSeconds) * rounds / 60).coerceAtLeast(1)
        val tabataPlan = com.example.domain.model.WorkoutPlan(
            id = "tabata_${System.currentTimeMillis()}",
            titleBn = titleBn,
            titleEn = titleEn,
            descriptionBn = "কাস্টম HIIT/টাবাটা সেশন • কাজ ${workSeconds}s / বিশ্রাম ${restSeconds}s",
            descriptionEn = "Custom HIIT/Tabata • Work ${workSeconds}s / Rest ${restSeconds}s",
            level = _uiState.value.levelInput,
            durationDays = 1,
            durationMinutesPerDay = totalMinutes,
            exercises = configuredExercises,
            isCustom = true
        )
        startWorkoutPlan(tabataPlan)
    }

    fun addWaterGlass() {
        viewModelScope.launch {
            storageService.addWaterGlass(todayIso)
        }
    }

    fun removeWaterGlass() {
        viewModelScope.launch {
            storageService.removeWaterGlass(todayIso)
        }
    }

    fun openWeightDialog() {
        _uiState.update { it.copy(isWeightDialogOpen = true) }
    }

    fun closeWeightDialog() {
        _uiState.update { it.copy(isWeightDialogOpen = false) }
    }

    fun saveWeightLog(weightKg: Float) {
        viewModelScope.launch {
            storageService.logWeight(weightKg)
            _uiState.update {
                it.copy(
                    isWeightDialogOpen = false,
                    weightInput = weightKg
                )
            }
            recomputeMetrics()
        }
    }

    fun openStepDialog() {
        _uiState.update { it.copy(isStepDialogOpen = true) }
    }

    fun closeStepDialog() {
        _uiState.update { it.copy(isStepDialogOpen = false) }
    }

    fun saveSteps(steps: Int) {
        _uiState.update {
            it.copy(
                todaySteps = steps,
                isStepDialogOpen = false
            )
        }
    }

    fun onSplashFinished() {
        val profile = _uiState.value.userProfile
        if (profile != null && profile.isOnboardingCompleted) {
            _uiState.update { it.copy(currentScreen = AppScreen.MainApp(MainTab.HOME)) }
        } else {
            _uiState.update { it.copy(currentScreen = AppScreen.WelcomeSlides(0)) }
        }
    }

    fun setWelcomeSlide(index: Int) {
        _uiState.update { it.copy(currentScreen = AppScreen.WelcomeSlides(index)) }
    }

    fun skipToNameInput() {
        _uiState.update { it.copy(currentScreen = AppScreen.NameInput) }
    }

    fun onNameChange(newName: String) {
        _uiState.update {
            it.copy(
                nameInput = newName,
                nameError = if (newName.trim().length >= 2) null else it.nameError
            )
        }
    }

    fun submitName(): Boolean {
        val trimmed = _uiState.value.nameInput.trim()
        val strings = _uiState.value.strings
        return if (trimmed.isEmpty()) {
            _uiState.update { it.copy(nameError = strings.nameErrorEmpty) }
            false
        } else if (trimmed.length < 2) {
            _uiState.update { it.copy(nameError = strings.nameErrorTooShort) }
            false
        } else {
            _uiState.update { it.copy(nameError = null, currentScreen = AppScreen.ProfileSetup) }
            true
        }
    }

    fun updateAge(age: Int) {
        _uiState.update { it.copy(ageInput = age.coerceIn(10, 100)) }
        recomputeMetrics()
    }

    fun updateHeight(heightCm: Float) {
        _uiState.update { it.copy(heightInput = heightCm.coerceIn(100f, 250f)) }
        recomputeMetrics()
    }

    fun updateWeight(weightKg: Float) {
        _uiState.update { it.copy(weightInput = weightKg.coerceIn(25f, 180f)) }
        recomputeMetrics()
    }

    fun updateGender(gender: String) {
        _uiState.update { it.copy(genderInput = gender) }
        recomputeMetrics()
    }

    fun updateGoal(goal: String) {
        _uiState.update { it.copy(goalInput = goal) }
        recomputeMetrics()
    }

    fun updateFitnessLevel(level: String) {
        _uiState.update { it.copy(levelInput = level) }
    }

    fun updateWorkoutDays(days: Int) {
        _uiState.update { it.copy(daysInput = days.coerceIn(1, 7)) }
        recomputeMetrics()
    }

    fun updateEquipment(equipment: String) {
        _uiState.update { it.copy(equipmentInput = equipment) }
    }

    fun proceedToDisclaimer() {
        _uiState.update { it.copy(currentScreen = AppScreen.HealthDisclaimer) }
    }

    fun updateUserProfile(name: String, age: Int, heightCm: Float, weightKg: Float, goal: String, fitnessLevel: String) {
        viewModelScope.launch {
            val current = _uiState.value.userProfile ?: return@launch
            val updated = current.copy(
                name = name,
                age = age,
                heightCm = heightCm,
                weightKg = weightKg,
                goal = goal,
                fitnessLevel = fitnessLevel
            )
            storageService.saveUserProfile(updated)
            storageService.logWeight(weightKg)
            loadUserProfile()
        }
    }

    fun setDisclaimerAccepted(accepted: Boolean) {
        _uiState.update { it.copy(disclaimerAccepted = accepted) }
    }

    fun completeOnboardingAndSave() {
        viewModelScope.launch {
            val state = _uiState.value
            val profile = UserProfile(
                id = 1,
                name = state.nameInput.trim(),
                age = state.ageInput,
                heightCm = state.heightInput,
                weightKg = state.weightInput,
                gender = state.genderInput,
                goal = state.goalInput,
                fitnessLevel = state.levelInput,
                workoutDaysPerWeek = state.daysInput,
                equipment = state.equipmentInput,
                preferredLanguage = state.selectedLanguage.code,
                isDarkMode = state.isDarkMode,
                isOnboardingCompleted = true
            )
            storageService.saveUserProfile(profile)

            val streak = 1
            val recommendation = WorkoutRecommendationEngine.getTodayRecommendation(
                userProfile = profile,
                daysStreak = streak
            )

            _uiState.update {
                it.copy(
                    userProfile = profile,
                    streakDays = streak,
                    recommendedWorkout = recommendation,
                    currentScreen = AppScreen.MainApp(MainTab.HOME)
                )
            }
        }
    }

    fun selectTab(tab: MainTab) {
        _uiState.update { it.copy(currentScreen = AppScreen.MainApp(tab)) }
    }

    fun toggleLanguage() {
        viewModelScope.launch {
            val newLang = if (_uiState.value.selectedLanguage == Language.BENGALI) Language.ENGLISH else Language.BENGALI
            _uiState.update { it.copy(selectedLanguage = newLang) }
            storageService.updateLanguage(newLang.code)
            recomputeMetrics()
        }
    }

    fun toggleTheme() {
        viewModelScope.launch {
            val newTheme = !_uiState.value.isDarkMode
            _uiState.update { it.copy(isDarkMode = newTheme) }
            storageService.updateTheme(newTheme)
        }
    }

    fun resetAllData() {
        viewModelScope.launch {
            storageService.deleteAllData()
            _uiState.update {
                HomeFitUiState(
                    currentScreen = AppScreen.WelcomeSlides(0),
                    selectedLanguage = it.selectedLanguage,
                    isDarkMode = it.isDarkMode,
                    isLoading = false
                )
            }
        }
    }

    fun navigateBack() {
        val current = _uiState.value.currentScreen
        when (current) {
            is AppScreen.WelcomeSlides -> {
                if (current.slideIndex > 0) {
                    setWelcomeSlide(current.slideIndex - 1)
                }
            }
            is AppScreen.NameInput -> {
                setWelcomeSlide(2)
            }
            is AppScreen.ProfileSetup -> {
                _uiState.update { it.copy(currentScreen = AppScreen.NameInput) }
            }
            is AppScreen.HealthDisclaimer -> {
                _uiState.update { it.copy(currentScreen = AppScreen.ProfileSetup) }
            }
            is AppScreen.MainApp -> {
                if (current.currentTab != MainTab.HOME) {
                    selectTab(MainTab.HOME)
                }
            }
            is AppScreen.WorkoutPreview -> {
                _uiState.update { it.copy(currentScreen = AppScreen.MainApp(MainTab.HOME)) }
            }
            else -> {}
        }
    }

    private fun computeCompletedWeekDaysFromLogs(
        logs: List<com.example.data.local.entity.WorkoutLogEntity>
    ): List<Int> {
        if (logs.isEmpty()) return emptyList()
        val nowCal = java.util.Calendar.getInstance()
        val currentWeek = nowCal.get(java.util.Calendar.WEEK_OF_YEAR)
        val currentYear = nowCal.get(java.util.Calendar.YEAR)

        return logs.mapNotNull { log ->
            val cal = java.util.Calendar.getInstance().apply { timeInMillis = log.completedAtMillis }
            if (cal.get(java.util.Calendar.YEAR) == currentYear &&
                cal.get(java.util.Calendar.WEEK_OF_YEAR) == currentWeek
            ) {
                when (cal.get(java.util.Calendar.DAY_OF_WEEK)) {
                    java.util.Calendar.MONDAY -> 0
                    java.util.Calendar.TUESDAY -> 1
                    java.util.Calendar.WEDNESDAY -> 2
                    java.util.Calendar.THURSDAY -> 3
                    java.util.Calendar.FRIDAY -> 4
                    java.util.Calendar.SATURDAY -> 5
                    java.util.Calendar.SUNDAY -> 6
                    else -> null
                }
            } else {
                null
            }
        }.distinct().sorted()
    }

    private fun recomputeMetrics() {
        val state = _uiState.value
        val bmi = HealthCalculations.calculateBMI(state.weightInput, state.heightInput)
        val bmiCat = HealthCalculations.getBMICategory(bmi, state.selectedLanguage)
        val metabolic = HealthCalculations.calculateMetabolicBreakdown(
            weightKg = state.weightInput,
            heightCm = state.heightInput,
            age = state.ageInput,
            gender = state.genderInput,
            goal = state.goalInput,
            workoutDaysPerWeek = state.daysInput
        )
        val hydration = HealthCalculations.calculateScientificHydration(
            weightKg = state.weightInput,
            age = state.ageInput,
            gender = state.genderInput,
            goal = state.goalInput,
            workoutDaysPerWeek = state.daysInput
        )
        _uiState.update {
            it.copy(
                liveBmi = bmi,
                liveBmiCategory = bmiCat,
                liveBmrCalories = metabolic.bmrCalories,
                liveTdeeCalories = metabolic.tdeeCalories,
                liveDailyCalories = metabolic.targetDailyIntakeCalories,
                liveProteinGrams = metabolic.proteinGrams,
                liveCarbsGrams = metabolic.carbsGrams,
                liveFatsGrams = metabolic.fatsGrams,
                todayCaloriesGoal = metabolic.targetWorkoutBurnCalories,
                todayWaterGoal = hydration.targetGlasses250Ml,
                todayWaterGoalMl = hydration.totalMl,
                todayWaterGoalLiters = hydration.totalLiters,
                hydrationFormulaSummaryBn = hydration.formulaSummaryBn,
                hydrationFormulaSummaryEn = hydration.formulaSummaryEn,
                todayStepsGoal = metabolic.recommendedStepsGoal
            )
        }
    }

    // Active Workout Engine
    fun startWorkoutPlan(plan: com.example.domain.model.WorkoutPlan) {
        val exercises = if (plan.exercises.isEmpty()) com.example.data.seed.ExerciseLibraryData.allExercises.take(4) else plan.exercises
        val initialSession = com.example.domain.model.ActiveWorkoutSession(
            plan = plan.copy(exercises = exercises),
            currentExerciseIndex = 0,
            phase = com.example.domain.model.WorkoutPhase.PREPARE,
            remainingSeconds = 3,
            totalSecondsInPhase = 3
        )
        _activeWorkoutSession.value = initialSession
        _uiState.update {
            it.copy(currentScreen = AppScreen.ActivePlayer)
        }
        audioFeedbackManager?.playToneBeep()
        audioFeedbackManager?.vibrateShort()
        startTimerLoop()
    }

    fun previewRecommendedWorkout() {
        val rec = _uiState.value.recommendedWorkout
        val matchingExercises = com.example.data.seed.ExerciseLibraryData.allExercises.filter {
            when (rec.category) {
                "chest_arms" -> it.category == com.example.domain.model.ExerciseCategory.CHEST || it.category == com.example.domain.model.ExerciseCategory.ARMS
                "legs" -> it.category == com.example.domain.model.ExerciseCategory.LEGS
                "abs_core" -> it.category == com.example.domain.model.ExerciseCategory.ABS_CORE
                "stretching" -> it.category == com.example.domain.model.ExerciseCategory.WARMUP_COOLDOWN
                else -> it.category == com.example.domain.model.ExerciseCategory.FULL_BODY || it.category == com.example.domain.model.ExerciseCategory.CHEST
            }
        }.take(rec.exerciseCount.coerceAtLeast(4))

        val plan = com.example.domain.model.WorkoutPlan(
            id = rec.id,
            titleBn = rec.titleBn,
            titleEn = rec.titleEn,
            descriptionBn = rec.rationaleBn,
            descriptionEn = rec.rationaleEn,
            level = _uiState.value.levelInput,
            durationDays = 1,
            durationMinutesPerDay = rec.durationMinutes,
            exercises = if (matchingExercises.isNotEmpty()) matchingExercises else com.example.data.seed.ExerciseLibraryData.allExercises.take(5)
        )
        previewWorkoutPlan(plan)
    }

    fun previewWorkoutPlan(plan: com.example.domain.model.WorkoutPlan) {
        _uiState.update { it.copy(currentScreen = AppScreen.WorkoutPreview(plan)) }
    }

    fun startRecommendedWorkout() {
        val rec = _uiState.value.recommendedWorkout
        val matchingExercises = com.example.data.seed.ExerciseLibraryData.allExercises.filter {
            when (rec.category) {
                "chest_arms" -> it.category == com.example.domain.model.ExerciseCategory.CHEST || it.category == com.example.domain.model.ExerciseCategory.ARMS
                "legs" -> it.category == com.example.domain.model.ExerciseCategory.LEGS
                "abs_core" -> it.category == com.example.domain.model.ExerciseCategory.ABS_CORE
                "stretching" -> it.category == com.example.domain.model.ExerciseCategory.WARMUP_COOLDOWN
                else -> it.category == com.example.domain.model.ExerciseCategory.FULL_BODY || it.category == com.example.domain.model.ExerciseCategory.CHEST
            }
        }.take(rec.exerciseCount.coerceAtLeast(4))

        val plan = com.example.domain.model.WorkoutPlan(
            id = rec.id,
            titleBn = rec.titleBn,
            titleEn = rec.titleEn,
            descriptionBn = rec.rationaleBn,
            descriptionEn = rec.rationaleEn,
            level = _uiState.value.levelInput,
            durationDays = 1,
            durationMinutesPerDay = rec.durationMinutes,
            exercises = if (matchingExercises.isNotEmpty()) matchingExercises else com.example.data.seed.ExerciseLibraryData.allExercises.take(5)
        )
        startWorkoutPlan(plan)
    }

    private fun startTimerLoop() {
        timerJob?.cancel()
        timerJob = viewModelScope.launch {
            while (isActive) {
                kotlinx.coroutines.delay(1000L)
                if (_uiState.value.currentScreen !is AppScreen.ActivePlayer) break
                val session = _activeWorkoutSession.value ?: break
                if (session.isPaused) continue

                val lang = _uiState.value.selectedLanguage
                val newElapsed = session.totalElapsedSeconds + 1
                val newRemaining = session.remainingSeconds - 1

                when (session.phase) {
                    com.example.domain.model.WorkoutPhase.PREPARE -> {
                        if (newRemaining in 1..3) {
                            audioFeedbackManager?.playToneBeep()
                            audioFeedbackManager?.vibrateShort()
                        }
                        if (newRemaining <= 0) {
                            val activeSec = session.currentExercise.defaultDurationSeconds
                            val activeSession = session.copy(
                                phase = com.example.domain.model.WorkoutPhase.EXERCISE,
                                remainingSeconds = activeSec,
                                totalSecondsInPhase = activeSec,
                                totalElapsedSeconds = newElapsed
                            )
                            _activeWorkoutSession.value = activeSession
                            audioFeedbackManager?.playToneStart()
                            audioFeedbackManager?.speak("শুরু করুন! ${session.currentExercise.nameBn}", "Start! ${session.currentExercise.nameEn}", lang)
                            audioFeedbackManager?.vibrateMedium()
                        } else {
                            val updated = session.copy(remainingSeconds = newRemaining, totalElapsedSeconds = newElapsed)
                            _activeWorkoutSession.value = updated
                        }
                    }

                    com.example.domain.model.WorkoutPhase.EXERCISE -> {
                        val elapsedInEx = session.totalSecondsInPhase - newRemaining
                        if (newRemaining == session.totalSecondsInPhase / 2 && session.totalSecondsInPhase > 10) {
                            audioFeedbackManager?.speak("অর্ধেক সময় পার হয়েছে", "Halfway there", lang)
                        } else if (newRemaining == 5) {
                            audioFeedbackManager?.speak("শেষ ৫ সেকেন্ড", "Last 5 seconds", lang)
                        } else if (newRemaining in 1..3) {
                            audioFeedbackManager?.playToneBeep()
                            audioFeedbackManager?.vibrateShort()
                        } else if (_uiState.value.voiceRepCounterEnabled && newRemaining > 5 && elapsedInEx >= 3 && elapsedInEx % 3 == 0) {
                            val repCount = elapsedInEx / 3
                            audioFeedbackManager?.speakRepCount(repCount, lang)
                        }

                        if (newRemaining <= 0) {
                            val burned = session.totalCaloriesBurned + (session.currentExercise.defaultDurationSeconds * 0.18f).toInt().coerceAtLeast(8)
                            val completedCount = session.completedExercisesCount + 1

                            if (session.currentExerciseIndex < session.plan.exercises.size - 1) {
                                // Transition to Rest
                                val restSec = session.currentExercise.defaultRestSeconds.coerceAtLeast(15)
                                val nextName = session.plan.exercises[session.currentExerciseIndex + 1].nameBn
                                val nextNameEn = session.plan.exercises[session.currentExerciseIndex + 1].nameEn

                                val restingSession = session.copy(
                                    phase = com.example.domain.model.WorkoutPhase.REST,
                                    remainingSeconds = restSec,
                                    totalSecondsInPhase = restSec,
                                    totalElapsedSeconds = newElapsed,
                                    totalCaloriesBurned = burned,
                                    completedExercisesCount = completedCount
                                )
                                _activeWorkoutSession.value = restingSession
                                audioFeedbackManager?.speak("বিশ্রাম। পরবর্তী ব্যায়াম: $nextName", "Rest. Next up: $nextNameEn", lang)
                                audioFeedbackManager?.vibrateShort()
                            } else {
                                // Workout Completed!
                                val finalSession = session.copy(
                                    phase = com.example.domain.model.WorkoutPhase.COMPLETED,
                                    totalElapsedSeconds = newElapsed,
                                    totalCaloriesBurned = burned,
                                    completedExercisesCount = completedCount
                                )
                                storageService.saveWorkoutLog(
                                    title = session.plan.titleBn,
                                    durationSeconds = newElapsed,
                                    caloriesBurned = burned,
                                    exercisesCompleted = completedCount
                                )
                                _activeWorkoutSession.value = null
                                _uiState.update { it.copy(currentScreen = AppScreen.WorkoutCompleted(finalSession)) }
                                audioFeedbackManager?.playToneFinish()
                                audioFeedbackManager?.speak("চমৎকার! সম্পূর্ণ ওয়ার্কআউট সম্পন্ন হয়েছে!", "Awesome! Workout Completed!", lang)
                                audioFeedbackManager?.vibrateMedium()
                                break
                            }
                        } else {
                            val updated = session.copy(remainingSeconds = newRemaining, totalElapsedSeconds = newElapsed)
                            _activeWorkoutSession.value = updated
                        }
                    }

                    com.example.domain.model.WorkoutPhase.REST -> {
                        if (newRemaining in 1..3) {
                            audioFeedbackManager?.playToneBeep()
                            audioFeedbackManager?.vibrateShort()
                        }
                        if (newRemaining <= 0) {
                            // Move to next exercise
                            val nextIndex = session.currentExerciseIndex + 1
                            val nextEx = session.plan.exercises[nextIndex]
                            val activeSec = nextEx.defaultDurationSeconds
                            val activeSession = session.copy(
                                currentExerciseIndex = nextIndex,
                                phase = com.example.domain.model.WorkoutPhase.EXERCISE,
                                remainingSeconds = activeSec,
                                totalSecondsInPhase = activeSec,
                                totalElapsedSeconds = newElapsed
                            )
                            _activeWorkoutSession.value = activeSession
                            audioFeedbackManager?.playToneStart()
                            audioFeedbackManager?.speak("শুরু করুন! ${nextEx.nameBn}", "Start! ${nextEx.nameEn}", lang)
                            audioFeedbackManager?.vibrateMedium()
                        } else {
                            val updated = session.copy(remainingSeconds = newRemaining, totalElapsedSeconds = newElapsed)
                            _activeWorkoutSession.value = updated
                        }
                    }

                    com.example.domain.model.WorkoutPhase.COMPLETED -> break
                }
            }
        }
    }

    fun togglePlayPause() {
        val session = _activeWorkoutSession.value ?: return
        val updated = session.copy(isPaused = !session.isPaused)
        _activeWorkoutSession.value = updated
        audioFeedbackManager?.playToneBeep()
    }

    fun skipNextExercise() {
        val session = _activeWorkoutSession.value ?: return
        if (session.currentExerciseIndex < session.plan.exercises.size - 1) {
            val nextIndex = session.currentExerciseIndex + 1
            val nextEx = session.plan.exercises[nextIndex]
            val updated = session.copy(
                currentExerciseIndex = nextIndex,
                phase = com.example.domain.model.WorkoutPhase.EXERCISE,
                remainingSeconds = nextEx.defaultDurationSeconds,
                totalSecondsInPhase = nextEx.defaultDurationSeconds,
                completedExercisesCount = session.completedExercisesCount + 1
            )
            _activeWorkoutSession.value = updated
            audioFeedbackManager?.playToneStart()
        }
    }

    fun previousExercise() {
        val session = _activeWorkoutSession.value ?: return
        if (session.currentExerciseIndex > 0) {
            val prevIndex = session.currentExerciseIndex - 1
            val prevEx = session.plan.exercises[prevIndex]
            val updated = session.copy(
                currentExerciseIndex = prevIndex,
                phase = com.example.domain.model.WorkoutPhase.EXERCISE,
                remainingSeconds = prevEx.defaultDurationSeconds,
                totalSecondsInPhase = prevEx.defaultDurationSeconds
            )
            _activeWorkoutSession.value = updated
            audioFeedbackManager?.playToneStart()
        }
    }

    fun restartCurrentExercise() {
        val session = _activeWorkoutSession.value ?: return
        val dur = session.currentExercise.defaultDurationSeconds
        val updated = session.copy(
            phase = com.example.domain.model.WorkoutPhase.EXERCISE,
            remainingSeconds = dur,
            totalSecondsInPhase = dur
        )
        _activeWorkoutSession.value = updated
        audioFeedbackManager?.playToneStart()
    }

    fun skipRest() {
        val session = _activeWorkoutSession.value ?: return
        if (session.phase == com.example.domain.model.WorkoutPhase.REST) {
            val nextIndex = session.currentExerciseIndex + 1
            if (nextIndex < session.plan.exercises.size) {
                val nextEx = session.plan.exercises[nextIndex]
                val updated = session.copy(
                    currentExerciseIndex = nextIndex,
                    phase = com.example.domain.model.WorkoutPhase.EXERCISE,
                    remainingSeconds = nextEx.defaultDurationSeconds,
                    totalSecondsInPhase = nextEx.defaultDurationSeconds
                )
                _activeWorkoutSession.value = updated
                audioFeedbackManager?.playToneStart()
            }
        }
    }

    fun toggleMute() {
        val session = _activeWorkoutSession.value ?: return
        val isMuted = !session.isMuted
        audioFeedbackManager?.isSoundEnabled = !isMuted
        val updated = session.copy(isMuted = isMuted)
        _activeWorkoutSession.value = updated
    }

    fun exitWorkout() {
        timerJob?.cancel()
        workoutMusicManager?.setDucking(false)
        _activeWorkoutSession.value = null
        _uiState.update { it.copy(currentScreen = AppScreen.MainApp(MainTab.HOME)) }
    }

    fun finishCompletedWorkout() {
        workoutMusicManager?.setDucking(false)
        _uiState.update { it.copy(currentScreen = AppScreen.MainApp(MainTab.HOME)) }
    }

    // --- Pro Subscription Secret Code (IshanX10) Management ---
    fun openProDialog() {
        _uiState.update {
            it.copy(
                isProDialogOpen = true,
                proCodeError = null,
                proActivationMessage = null
            )
        }
    }

    fun closeProDialog() {
        _uiState.update {
            it.copy(
                isProDialogOpen = false,
                proCodeError = null,
                proActivationMessage = null
            )
        }
    }

    fun redeemSecretProCode(inputCode: String): Boolean {
        val trimmed = inputCode.trim()
        val isBn = _uiState.value.selectedLanguage == Language.BENGALI
        if (trimmed.equals("IshanX10", ignoreCase = true)) {
            viewModelScope.launch {
                storageService.setProSubscribed(true)
            }
            audioFeedbackManager?.playToneStart()
            _uiState.update {
                it.copy(
                    isProSubscribed = true,
                    proCodeError = null,
                    proActivationMessage = if (isBn) {
                        "অভিনন্দন! গোপন কোড (IshanX10) দিয়ে আপনার আজীবন PRO ELITE মেম্বারশিপ সক্রিয় হয়েছে!"
                    } else {
                        "Congratulations! Lifetime PRO ELITE Membership activated via secret code (IshanX10)!"
                    }
                )
            }
            return true
        } else {
            _uiState.update {
                it.copy(
                    proCodeError = if (isBn) {
                        "গোপন কোডটি সঠিক নয়! প্রো সাবস্ক্রিপশন চালু করতে সঠিক কোড লিখুন।"
                    } else {
                        "Invalid secret code! Please enter the valid Pro activation code."
                    },
                    proActivationMessage = null
                )
            }
            return false
        }
    }

    fun deactivateProSubscription() {
        viewModelScope.launch {
            storageService.setProSubscribed(false)
        }
        _uiState.update {
            it.copy(
                isProSubscribed = false,
                proCodeError = null,
                proActivationMessage = null
            )
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/components/HomeFitComponents.kt`

```kotlin
package com.example.ui.components

import androidx.compose.animation.animateColorAsState
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.PaddingValues
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.heightIn
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.CheckCircle
import androidx.compose.material.icons.filled.DarkMode
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.Home
import androidx.compose.material.icons.filled.Language
import androidx.compose.material.icons.filled.LightMode
import androidx.compose.material.icons.filled.Person
import androidx.compose.material.icons.filled.Restaurant
import androidx.compose.material.icons.filled.ShowChart
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.ExperimentalMaterial3Api
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.NavigationBar
import androidx.compose.material3.NavigationBarItem
import androidx.compose.material3.NavigationBarItemDefaults
import androidx.compose.material3.OutlinedButton
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.material3.TopAppBar
import androidx.compose.material3.TopAppBarDefaults
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Brush
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.vector.ImageVector
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.text.style.TextOverflow
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language

/**
 * Primary Luxury Studio Button with minimum 58.dp height, emerald glow, and single-line discipline.
 */
@Composable
fun HomeFitButton(
    text: String,
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    enabled: Boolean = true,
    leadingIcon: ImageVector? = null,
    testTag: String = "homefit_primary_button"
) {
    Button(
        onClick = onClick,
        enabled = enabled,
        shape = RoundedCornerShape(16.dp),
        colors = ButtonDefaults.buttonColors(
            containerColor = MaterialTheme.colorScheme.primary,
            contentColor = MaterialTheme.colorScheme.onPrimary,
            disabledContainerColor = MaterialTheme.colorScheme.surfaceVariant,
            disabledContentColor = MaterialTheme.colorScheme.onSurfaceVariant.copy(alpha = 0.5f)
        ),
        contentPadding = PaddingValues(horizontal = 20.dp, vertical = 14.dp),
        modifier = modifier
            .fillMaxWidth()
            .heightIn(min = 58.dp)
            .border(
                width = 1.dp,
                color = if (enabled) Color.White.copy(alpha = 0.22f) else Color.Transparent,
                shape = RoundedCornerShape(16.dp)
            )
            .testTag(testTag)
    ) {
        Row(
            verticalAlignment = Alignment.CenterVertically,
            horizontalArrangement = Arrangement.Center
        ) {
            if (leadingIcon != null) {
                Icon(
                    imageVector = leadingIcon,
                    contentDescription = null,
                    modifier = Modifier.size(20.dp)
                )
                Spacer(modifier = Modifier.width(10.dp))
            }
            Text(
                text = text,
                style = MaterialTheme.typography.titleMedium.copy(
                    fontWeight = FontWeight.ExtraBold,
                    letterSpacing = 0.2.sp
                ),
                maxLines = 1,
                overflow = TextOverflow.Ellipsis
            )
        }
    }
}

/**
 * Secondary Outlined Glassmorphic Button with clean single-line layout.
 */
@Composable
fun HomeFitOutlinedButton(
    text: String,
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    leadingIcon: ImageVector? = null,
    testTag: String = "homefit_outlined_button"
) {
    OutlinedButton(
        onClick = onClick,
        shape = RoundedCornerShape(16.dp),
        border = BorderStroke(1.2.dp, MaterialTheme.colorScheme.outline),
        colors = ButtonDefaults.outlinedButtonColors(
            containerColor = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.35f),
            contentColor = MaterialTheme.colorScheme.onSurface
        ),
        contentPadding = PaddingValues(horizontal = 16.dp, vertical = 12.dp),
        modifier = modifier
            .fillMaxWidth()
            .heightIn(min = 52.dp)
            .testTag(testTag)
    ) {
        Row(
            verticalAlignment = Alignment.CenterVertically,
            horizontalArrangement = Arrangement.Center
        ) {
            if (leadingIcon != null) {
                Icon(
                    imageVector = leadingIcon,
                    contentDescription = null,
                    modifier = Modifier.size(18.dp),
                    tint = MaterialTheme.colorScheme.primary
                )
                Spacer(modifier = Modifier.width(8.dp))
            }
            Text(
                text = text,
                style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Bold),
                maxLines = 1,
                overflow = TextOverflow.Ellipsis
            )
        }
    }
}

/**
 * Glassmorphic Dark Luxury Card container with subtle specular border highlight.
 */
@Composable
fun HomeFitCard(
    modifier: Modifier = Modifier,
    borderColor: Color = MaterialTheme.colorScheme.outline.copy(alpha = 0.65f),
    content: @Composable () -> Unit
) {
    Card(
        shape = RoundedCornerShape(22.dp),
        colors = CardDefaults.cardColors(
            containerColor = MaterialTheme.colorScheme.surface
        ),
        border = BorderStroke(1.dp, borderColor),
        elevation = CardDefaults.cardElevation(defaultElevation = 4.dp),
        modifier = modifier.fillMaxWidth()
    ) {
        Box(
            modifier = Modifier
                .fillMaxWidth()
                .background(
                    Brush.verticalGradient(
                        colors = listOf(
                            MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.32f),
                            MaterialTheme.colorScheme.surface
                        )
                    )
                )
                .padding(18.dp)
        ) {
            content()
        }
    }
}

/**
 * Top Bar with Dark Luxury Studio badge, Language Switcher (BN / EN), and Theme Toggle.
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun HomeFitTopBar(
    title: String,
    currentLanguage: Language,
    isDarkMode: Boolean,
    onToggleLanguage: () -> Unit,
    onToggleTheme: () -> Unit,
    modifier: Modifier = Modifier
) {
    TopAppBar(
        title = {
            Row(verticalAlignment = Alignment.CenterVertically) {
                Box(
                    modifier = Modifier
                        .size(34.dp)
                        .clip(RoundedCornerShape(10.dp))
                        .background(
                            Brush.linearGradient(
                                colors = listOf(
                                    MaterialTheme.colorScheme.primary,
                                    MaterialTheme.colorScheme.secondary
                                )
                            )
                        ),
                    contentAlignment = Alignment.Center
                ) {
                    Icon(
                        imageVector = Icons.Default.FitnessCenter,
                        contentDescription = null,
                        tint = Color(0xFF051811),
                        modifier = Modifier.size(19.dp)
                    )
                }
                Spacer(modifier = Modifier.width(10.dp))
                Column {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        Text(
                            text = title,
                            style = MaterialTheme.typography.titleLarge.copy(
                                fontWeight = FontWeight.ExtraBold,
                                letterSpacing = 0.4.sp
                            ),
                            color = MaterialTheme.colorScheme.onBackground
                        )
                        Spacer(modifier = Modifier.width(6.dp))
                        Surface(
                            shape = RoundedCornerShape(6.dp),
                            color = MaterialTheme.colorScheme.secondary.copy(alpha = 0.18f),
                            border = BorderStroke(0.8.dp, MaterialTheme.colorScheme.secondary.copy(alpha = 0.5f))
                        ) {
                            Text(
                                text = "PRO",
                                style = MaterialTheme.typography.labelSmall.copy(
                                    fontSize = 9.sp,
                                    fontWeight = FontWeight.Black,
                                    letterSpacing = 0.8.sp
                                ),
                                color = MaterialTheme.colorScheme.secondary,
                                modifier = Modifier.padding(horizontal = 5.dp, vertical = 1.dp)
                            )
                        }
                    }
                }
            }
        },
        actions = {
            // Language Pill Button
            Surface(
                shape = RoundedCornerShape(50),
                color = MaterialTheme.colorScheme.surfaceVariant,
                border = BorderStroke(1.dp, MaterialTheme.colorScheme.outline),
                modifier = Modifier
                    .height(38.dp)
                    .clip(RoundedCornerShape(50))
                    .clickable { onToggleLanguage() }
                    .testTag("language_toggle_button")
            ) {
                Row(
                    verticalAlignment = Alignment.CenterVertically,
                    modifier = Modifier.padding(horizontal = 12.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.Language,
                        contentDescription = "Switch Language",
                        tint = MaterialTheme.colorScheme.primary,
                        modifier = Modifier.size(16.dp)
                    )
                    Spacer(modifier = Modifier.width(5.dp))
                    Text(
                        text = if (currentLanguage == Language.BENGALI) "বাংলা" else "EN",
                        style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface,
                        maxLines = 1
                    )
                }
            }

            Spacer(modifier = Modifier.width(6.dp))

            // Theme Toggle IconButton (48dp touch target)
            IconButton(
                onClick = onToggleTheme,
                modifier = Modifier
                    .size(48.dp)
                    .testTag("theme_toggle_button")
            ) {
                Icon(
                    imageVector = if (isDarkMode) Icons.Default.LightMode else Icons.Default.DarkMode,
                    contentDescription = if (isDarkMode) "Switch to Light Mode" else "Switch to Dark Mode",
                    tint = MaterialTheme.colorScheme.secondary
                )
            }
        },
        colors = TopAppBarDefaults.topAppBarColors(
            containerColor = MaterialTheme.colorScheme.background,
            titleContentColor = MaterialTheme.colorScheme.onBackground
        ),
        modifier = modifier
    )
}

/**
 * Selectable Pill / Choice Chip with anti-wrap protection so text never fractures mid-word.
 */
@Composable
fun AthleticChoiceChip(
    text: String = "",
    selected: Boolean,
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    label: String = "",
    testTag: String = "choice_chip"
) {
    val displayText = text.ifEmpty { label }
    val bgColor by animateColorAsState(
        targetValue = if (selected) {
            MaterialTheme.colorScheme.primary.copy(alpha = 0.20f)
        } else {
            MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.65f)
        },
        label = "chipBg"
    )
    val borderColor by animateColorAsState(
        targetValue = if (selected) {
            MaterialTheme.colorScheme.primary
        } else {
            MaterialTheme.colorScheme.outline.copy(alpha = 0.7f)
        },
        label = "chipBorder"
    )
    val textColor by animateColorAsState(
        targetValue = if (selected) {
            MaterialTheme.colorScheme.primary
        } else {
            MaterialTheme.colorScheme.onSurface
        },
        label = "chipText"
    )

    Box(
        modifier = modifier
            .heightIn(min = 48.dp)
            .clip(RoundedCornerShape(14.dp))
            .background(bgColor)
            .border(width = if (selected) 1.6.dp else 1.dp, color = borderColor, shape = RoundedCornerShape(14.dp))
            .clickable { onClick() }
            .padding(horizontal = 10.dp, vertical = 10.dp)
            .testTag(testTag),
        contentAlignment = Alignment.Center
    ) {
        Text(
            text = displayText,
            style = MaterialTheme.typography.labelLarge.copy(
                fontWeight = if (selected) FontWeight.ExtraBold else FontWeight.SemiBold,
                fontSize = 13.sp
            ),
            color = textColor,
            textAlign = TextAlign.Center,
            maxLines = 1,
            softWrap = false,
            overflow = TextOverflow.Ellipsis
        )
    }
}

/**
 * Full-width Luxury Selection Option Card for longer bilingual choices (Goal, Level, Equipment)
 * so Bengali/English labels never crowd or clip inside narrow 3-column chips.
 */
@Composable
fun LuxurySelectionOptionCard(
    title: String,
    subtitle: String? = null,
    badgeText: String? = null,
    selected: Boolean,
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    testTag: String = "luxury_option_card"
) {
    val borderColor by animateColorAsState(
        targetValue = if (selected) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.outline.copy(alpha = 0.6f),
        label = "optBorder"
    )
    val bgColor by animateColorAsState(
        targetValue = if (selected) MaterialTheme.colorScheme.primary.copy(alpha = 0.14f) else MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.45f),
        label = "optBg"
    )

    Row(
        modifier = modifier
            .fillMaxWidth()
            .heightIn(min = 56.dp)
            .clip(RoundedCornerShape(16.dp))
            .background(bgColor)
            .border(width = if (selected) 1.6.dp else 1.dp, color = borderColor, shape = RoundedCornerShape(16.dp))
            .clickable { onClick() }
            .padding(horizontal = 16.dp, vertical = 12.dp)
            .testTag(testTag),
        verticalAlignment = Alignment.CenterVertically,
        horizontalArrangement = Arrangement.SpaceBetween
    ) {
        Column(modifier = Modifier.weight(1f)) {
            Text(
                text = title,
                style = MaterialTheme.typography.titleMedium.copy(
                    fontWeight = if (selected) FontWeight.ExtraBold else FontWeight.SemiBold,
                    fontSize = 15.sp
                ),
                color = if (selected) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.onSurface
            )
            if (!subtitle.isNullOrBlank()) {
                Spacer(modifier = Modifier.height(2.dp))
                Text(
                    text = subtitle,
                    style = MaterialTheme.typography.bodyMedium.copy(fontSize = 12.sp),
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        }

        Spacer(modifier = Modifier.width(12.dp))

        if (!badgeText.isNullOrBlank()) {
            Surface(
                shape = RoundedCornerShape(8.dp),
                color = if (selected) MaterialTheme.colorScheme.primary.copy(alpha = 0.22f) else MaterialTheme.colorScheme.surface,
                border = BorderStroke(1.dp, if (selected) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.outline)
            ) {
                Text(
                    text = badgeText,
                    style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                    color = if (selected) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.onSurfaceVariant,
                    modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp)
                )
            }
            Spacer(modifier = Modifier.width(8.dp))
        }

        if (selected) {
            Icon(
                imageVector = Icons.Default.CheckCircle,
                contentDescription = null,
                tint = MaterialTheme.colorScheme.primary,
                modifier = Modifier.size(22.dp)
            )
        } else {
            Box(
                modifier = Modifier
                    .size(20.dp)
                    .clip(CircleShape)
                    .border(1.5.dp, MaterialTheme.colorScheme.outline, CircleShape)
            )
        }
    }
}

enum class MainTab(val icon: ImageVector, val testTag: String) {
    HOME(Icons.Default.Home, "nav_tab_home"),
    WORKOUTS(Icons.Default.FitnessCenter, "nav_tab_workouts"),
    PROGRESS(Icons.Default.ShowChart, "nav_tab_progress"),
    DIET(Icons.Default.Restaurant, "nav_tab_diet"),
    PROFILE(Icons.Default.Person, "nav_tab_profile")
}

@Composable
fun HomeFitBottomNav(
    selectedTab: MainTab,
    onTabSelected: (MainTab) -> Unit,
    strings: AppStrings,
    modifier: Modifier = Modifier
) {
    NavigationBar(
        containerColor = MaterialTheme.colorScheme.surface,
        tonalElevation = 10.dp,
        modifier = modifier
            .border(
                width = 0.8.dp,
                color = MaterialTheme.colorScheme.outline.copy(alpha = 0.45f)
            )
            .testTag("bottom_navigation_bar")
    ) {
        MainTab.entries.forEach { tab ->
            val label = when (tab) {
                MainTab.HOME -> strings.navHome
                MainTab.WORKOUTS -> strings.navWorkouts
                MainTab.PROGRESS -> strings.navProgress
                MainTab.DIET -> strings.navDiet
                MainTab.PROFILE -> strings.navProfile
            }
            NavigationBarItem(
                selected = selectedTab == tab,
                onClick = { onTabSelected(tab) },
                icon = {
                    Icon(
                        imageVector = tab.icon,
                        contentDescription = label
                    )
                },
                label = {
                    Text(
                        text = label,
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontWeight = if (selectedTab == tab) FontWeight.ExtraBold else FontWeight.Medium,
                            fontSize = 11.sp
                        ),
                        maxLines = 1,
                        softWrap = false,
                        overflow = TextOverflow.Ellipsis
                    )
                },
                colors = NavigationBarItemDefaults.colors(
                    selectedIconColor = MaterialTheme.colorScheme.primary,
                    selectedTextColor = MaterialTheme.colorScheme.primary,
                    indicatorColor = MaterialTheme.colorScheme.primaryContainer,
                    unselectedIconColor = MaterialTheme.colorScheme.onSurfaceVariant,
                    unselectedTextColor = MaterialTheme.colorScheme.onSurfaceVariant
                ),
                modifier = Modifier.testTag(tab.testTag)
            )
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/components/ProSubscriptionComponents.kt`

```kotlin
package com.example.ui.components

import androidx.compose.animation.AnimatedVisibility
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.AutoAwesome
import androidx.compose.material.icons.filled.CheckCircle
import androidx.compose.material.icons.filled.Key
import androidx.compose.material.icons.filled.LockOpen
import androidx.compose.material.icons.filled.Star
import androidx.compose.material.icons.filled.Verified
import androidx.compose.material.icons.filled.WorkspacePremium
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.OutlinedTextFieldDefaults
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Brush
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.text.style.TextOverflow
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.compose.ui.window.Dialog
import com.example.core.i18n.Language

@Composable
fun ProStatusBadgePill(
    isProSubscribed: Boolean,
    selectedLanguage: Language,
    onClick: () -> Unit,
    modifier: Modifier = Modifier
) {
    val isBn = selectedLanguage == Language.BENGALI
    Surface(
        shape = RoundedCornerShape(50),
        color = if (isProSubscribed) Color(0xFF28200B) else Color(0xFF141E30),
        border = BorderStroke(
            width = 1.2.dp,
            brush = Brush.horizontalGradient(
                colors = if (isProSubscribed) {
                    listOf(Color(0xFFFBBF24), Color(0xFF10B981))
                } else {
                    listOf(Color(0xFFF59E0B).copy(alpha = 0.7f), Color(0xFF38BDF8).copy(alpha = 0.7f))
                }
            )
        ),
        modifier = modifier
            .clip(RoundedCornerShape(50))
            .clickable { onClick() }
            .testTag("pro_status_badge_pill")
    ) {
        Row(
            verticalAlignment = Alignment.CenterVertically,
            modifier = Modifier.padding(horizontal = 12.dp, vertical = 6.dp)
        ) {
            Icon(
                imageVector = if (isProSubscribed) Icons.Default.WorkspacePremium else Icons.Default.Key,
                contentDescription = null,
                tint = Color(0xFFFBBF24),
                modifier = Modifier.size(15.dp)
            )
            Spacer(modifier = Modifier.width(6.dp))
            Text(
                text = if (isProSubscribed) {
                    if (isBn) "VIP PRO সক্রিয়" else "VIP PRO ACTIVE"
                } else {
                    if (isBn) "প্রো কোড দিন" else "UNLOCK PRO"
                },
                style = MaterialTheme.typography.labelSmall.copy(
                    fontSize = 11.sp,
                    fontWeight = FontWeight.ExtraBold,
                    letterSpacing = 0.5.sp
                ),
                color = if (isProSubscribed) Color(0xFFFDE68A) else Color(0xFFF8FAFC),
                maxLines = 1
            )
        }
    }
}

@Composable
fun ProMembershipBannerCard(
    isProSubscribed: Boolean,
    selectedLanguage: Language,
    onOpenProDialog: () -> Unit,
    modifier: Modifier = Modifier
) {
    val isBn = selectedLanguage == Language.BENGALI

    Surface(
        shape = RoundedCornerShape(22.dp),
        color = Color.Transparent,
        border = BorderStroke(
            width = 1.4.dp,
            brush = Brush.linearGradient(
                colors = if (isProSubscribed) {
                    listOf(Color(0xFFFBBF24), Color(0xFF10B981), Color(0xFFF59E0B))
                } else {
                    listOf(Color(0xFFF59E0B).copy(alpha = 0.65f), Color(0xFF283753), Color(0xFF10B981).copy(alpha = 0.55f))
                }
            )
        ),
        modifier = modifier
            .fillMaxWidth()
            .clip(RoundedCornerShape(22.dp))
            .clickable { onOpenProDialog() }
            .testTag("pro_membership_banner_card")
    ) {
        Box(
            modifier = Modifier
                .background(
                    Brush.horizontalGradient(
                        colors = if (isProSubscribed) {
                            listOf(Color(0xFF1C1608), Color(0xFF0E221D), Color(0xFF111A2E))
                        } else {
                            listOf(Color(0xFF11192B), Color(0xFF1A162B), Color(0xFF0E1726))
                        }
                    )
                )
                .padding(16.dp)
        ) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Row(
                    verticalAlignment = Alignment.CenterVertically,
                    modifier = Modifier.weight(1f)
                ) {
                    Box(
                        modifier = Modifier
                            .size(46.dp)
                            .clip(CircleShape)
                            .background(
                                Brush.linearGradient(
                                    colors = if (isProSubscribed) {
                                        listOf(Color(0xFFFBBF24), Color(0xFFD97706))
                                    } else {
                                        listOf(Color(0xFF26354D), Color(0xFF1E293B))
                                    }
                                )
                            )
                            .border(1.dp, Color(0xFFFBBF24).copy(alpha = 0.7f), CircleShape),
                        contentAlignment = Alignment.Center
                    ) {
                        Icon(
                            imageVector = if (isProSubscribed) Icons.Default.WorkspacePremium else Icons.Default.Key,
                            contentDescription = null,
                            tint = if (isProSubscribed) Color(0xFF090D16) else Color(0xFFFBBF24),
                            modifier = Modifier.size(24.dp)
                        )
                    }

                    Spacer(modifier = Modifier.width(12.dp))

                    Column(modifier = Modifier.weight(1f)) {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Text(
                                text = if (isProSubscribed) {
                                    if (isBn) "VIP PRO ELITE মেম্বারশিপ সক্রিয়" else "VIP PRO ELITE ACTIVE"
                                } else {
                                    if (isBn) "প্রো সাবস্ক্রিপশন আনলক করুন" else "Unlock Pro Subscription"
                                },
                                style = MaterialTheme.typography.titleMedium.copy(
                                    fontWeight = FontWeight.ExtraBold,
                                    fontSize = 15.sp
                                ),
                                color = if (isProSubscribed) Color(0xFFFDE68A) else Color(0xFFF8FAFC),
                                maxLines = 1,
                                overflow = TextOverflow.Ellipsis
                            )
                            if (isProSubscribed) {
                                Spacer(modifier = Modifier.width(6.dp))
                                Icon(
                                    imageVector = Icons.Default.Verified,
                                    contentDescription = null,
                                    tint = Color(0xFF34D399),
                                    modifier = Modifier.size(16.dp)
                                )
                            }
                        }

                        Spacer(modifier = Modifier.height(3.dp))

                        Text(
                            text = if (isProSubscribed) {
                                if (isBn) "সব অ্যাডভান্সড ওয়ার্কআউট, প্রো ডায়েট চার্ট ও ৩ডি অ্যানালিটিক্স আনলকড"
                                else "All Advanced Plans, Pro Diet Charts & 3D Macro Analytics Unlocked"
                            } else {
                                if (isBn) "গোপন কোড ব্যবহার করে মুহূর্তেই সব প্রিমিয়াম ফিচার চালু করুন"
                                else "Redeem your secret code to unlock all VIP Pro plans & analytics"
                            },
                            style = MaterialTheme.typography.bodySmall.copy(
                                fontSize = 12.sp,
                                lineHeight = 16.sp
                            ),
                            color = Color(0xFFCBD5E1),
                            maxLines = 2,
                            overflow = TextOverflow.Ellipsis
                        )
                    }
                }

                Spacer(modifier = Modifier.width(10.dp))

                Surface(
                    shape = RoundedCornerShape(12.dp),
                    color = if (isProSubscribed) Color(0xFF10B981).copy(alpha = 0.2f) else Color(0xFFF59E0B),
                    border = if (isProSubscribed) BorderStroke(1.dp, Color(0xFF10B981)) else null
                ) {
                    Text(
                        text = if (isProSubscribed) {
                            if (isBn) "VIP সক্রিয়" else "ACTIVE"
                        } else {
                            if (isBn) "কোড দিন" else "REDEEM"
                        },
                        style = MaterialTheme.typography.labelMedium.copy(
                            fontWeight = FontWeight.Black,
                            fontSize = 11.5.sp
                        ),
                        color = if (isProSubscribed) Color(0xFF34D399) else Color(0xFF090D16),
                        maxLines = 1,
                        modifier = Modifier.padding(horizontal = 12.dp, vertical = 8.dp)
                    )
                }
            }
        }
    }
}

@Composable
fun ProSubscriptionDialog(
    isProSubscribed: Boolean,
    selectedLanguage: Language,
    errorMessage: String?,
    successMessage: String?,
    onRedeemCode: (String) -> Boolean,
    onDeactivatePro: () -> Unit,
    onDismiss: () -> Unit
) {
    val isBn = selectedLanguage == Language.BENGALI
    var secretCodeInput by remember { mutableStateOf("") }

    Dialog(onDismissRequest = onDismiss) {
        Surface(
            shape = RoundedCornerShape(26.dp),
            color = Color(0xFF0B1220),
            border = BorderStroke(
                width = 1.5.dp,
                brush = Brush.linearGradient(
                    colors = listOf(Color(0xFFFBBF24), Color(0xFF10B981), Color(0xFF38BDF8))
                )
            ),
            modifier = Modifier
                .fillMaxWidth()
                .testTag("pro_subscription_dialog")
        ) {
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(22.dp),
                horizontalAlignment = Alignment.CenterHorizontally
            ) {
                // Top Crown Icon
                Box(
                    modifier = Modifier
                        .size(62.dp)
                        .clip(CircleShape)
                        .background(
                            Brush.linearGradient(
                                colors = listOf(Color(0xFFFBBF24), Color(0xFFD97706))
                            )
                        ),
                    contentAlignment = Alignment.Center
                ) {
                    Icon(
                        imageVector = Icons.Default.WorkspacePremium,
                        contentDescription = null,
                        tint = Color(0xFF090D16),
                        modifier = Modifier.size(34.dp)
                    )
                }

                Spacer(modifier = Modifier.height(14.dp))

                Text(
                    text = if (isProSubscribed) {
                        if (isBn) "HOMEFIT VIP PRO সক্রিয়" else "HOMEFIT VIP PRO ACTIVE"
                    } else {
                        if (isBn) "প্রো সাবস্ক্রিপশন অ্যাক্টিভেশন" else "PRO SUBSCRIPTION ACTIVATION"
                    },
                    style = MaterialTheme.typography.titleLarge.copy(
                        fontWeight = FontWeight.Black,
                        fontSize = 20.sp
                    ),
                    color = Color(0xFFFDE68A),
                    textAlign = TextAlign.Center
                )

                Spacer(modifier = Modifier.height(6.dp))

                Text(
                    text = if (isProSubscribed) {
                        if (isBn) "আপনার অ্যাপে সব প্রিমিয়াম ওয়ার্কআউট, অ্যাডভান্সড ব্যায়াম এবং প্রো ডায়েট অ্যানালিটিক্স সম্পূর্ণ আনলক করা আছে।"
                        else "All premium workout plans, advanced exercises, and Pro diet macro analytics are unlocked."
                    } else {
                        if (isBn) "কোনো পেমেন্ট ঝামেলা ছাড়াই আপনার গোপন অ্যাক্টিভেশন কোডটি নিচে লিখে প্রো ভার্সন চালু করুন।"
                        else "Enter your secret activation code below to unlock lifetime VIP Pro features instantly."
                    },
                    style = MaterialTheme.typography.bodyMedium.copy(
                        fontSize = 13.sp,
                        lineHeight = 19.sp
                    ),
                    color = Color(0xFFCBD5E1),
                    textAlign = TextAlign.Center
                )

                Spacer(modifier = Modifier.height(16.dp))

                // Pro Benefits Checklist
                Column(
                    modifier = Modifier
                        .fillMaxWidth()
                        .clip(RoundedCornerShape(16.dp))
                        .background(Color(0xFF121C2E))
                        .border(1.dp, Color(0xFF24344E), RoundedCornerShape(16.dp))
                        .padding(14.dp),
                    verticalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    val benefits = if (isBn) {
                        listOf(
                            "সব ইন্টারমিডিয়েট ও অ্যাডভান্সড ওয়ার্কআউট প্ল্যান আনলক",
                            "২৭টি ব্যায়ামের ৩ডি হিউম্যানিস্টিক মাসল হিটম্যাপ ও প্রো কন্ট্রোল",
                            "কাস্টম প্রো ডায়েট চার্ট ও প্রোটিন-ক্যালোরি ডিপ ম্যাক্রো অ্যানালিটিক্স",
                            "ভিআইপি গোল্ড ব্যাজ ও প্রো মেম্বারশিপ ড্যাশবোর্ড থিম"
                        )
                    } else {
                        listOf(
                            "Unlock all Intermediate & Advanced 14/30-Day Workout Plans",
                            "All 27 Humanistic 3D Exercise Animations & Pro Controls",
                            "Custom Pro Diet Chart & Deep Protein-Calorie Macro Analytics",
                            "VIP Gold Badge & Pro Studio Dashboard Theme"
                        )
                    }

                    benefits.forEach { item ->
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Icon(
                                imageVector = Icons.Default.CheckCircle,
                                contentDescription = null,
                                tint = Color(0xFF34D399),
                                modifier = Modifier.size(16.dp)
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Text(
                                text = item,
                                style = MaterialTheme.typography.bodySmall.copy(
                                    fontSize = 12.sp,
                                    fontWeight = FontWeight.SemiBold
                                ),
                                color = Color(0xFFF8FAFC)
                            )
                        }
                    }
                }

                Spacer(modifier = Modifier.height(16.dp))

                if (!isProSubscribed) {
                    OutlinedTextField(
                        value = secretCodeInput,
                        onValueChange = { secretCodeInput = it },
                        label = {
                            Text(if (isBn) "গোপন প্রো কোড লিখুন" else "Enter Secret Pro Code")
                        },
                        placeholder = {
                            Text(if (isBn) "গোপন কোড দিন..." else "Enter secret code...")
                        },
                        leadingIcon = {
                            Icon(
                                imageVector = Icons.Default.Key,
                                contentDescription = null,
                                tint = Color(0xFFFBBF24)
                            )
                        },
                        singleLine = true,
                        shape = RoundedCornerShape(14.dp),
                        colors = OutlinedTextFieldDefaults.colors(
                            focusedContainerColor = Color(0xFF141E30),
                            unfocusedContainerColor = Color(0xFF141E30),
                            focusedBorderColor = Color(0xFFFBBF24),
                            unfocusedBorderColor = Color(0xFF334766),
                            focusedTextColor = Color.White,
                            unfocusedTextColor = Color.White
                        ),
                        modifier = Modifier
                            .fillMaxWidth()
                            .testTag("secret_pro_code_input")
                    )

                    AnimatedVisibility(visible = !errorMessage.isNullOrBlank()) {
                        Text(
                            text = errorMessage.orEmpty(),
                            style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.Bold),
                            color = Color(0xFFFB7185),
                            textAlign = TextAlign.Center,
                            modifier = Modifier.padding(top = 8.dp)
                        )
                    }

                    Spacer(modifier = Modifier.height(16.dp))

                    Button(
                        onClick = { onRedeemCode(secretCodeInput) },
                        shape = RoundedCornerShape(14.dp),
                        colors = ButtonDefaults.buttonColors(
                            containerColor = Color(0xFFFBBF24),
                            contentColor = Color(0xFF090D16)
                        ),
                        modifier = Modifier
                            .fillMaxWidth()
                            .height(50.dp)
                            .testTag("activate_pro_code_btn")
                    ) {
                        Icon(
                            imageVector = Icons.Default.LockOpen,
                            contentDescription = null,
                            modifier = Modifier.size(18.dp)
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text(
                            text = if (isBn) "প্রো সাবস্ক্রিপশন চালু করুন" else "Activate Pro Subscription",
                            style = MaterialTheme.typography.titleMedium.copy(
                                fontWeight = FontWeight.Black,
                                fontSize = 15.sp
                            )
                        )
                    }
                } else {
                    AnimatedVisibility(visible = !successMessage.isNullOrBlank()) {
                        Surface(
                            shape = RoundedCornerShape(12.dp),
                            color = Color(0xFF064E3B),
                            border = BorderStroke(1.dp, Color(0xFF34D399)),
                            modifier = Modifier
                                .fillMaxWidth()
                                .padding(bottom = 12.dp)
                        ) {
                            Text(
                                text = successMessage.orEmpty(),
                                style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.Bold),
                                color = Color(0xFFA7F3D0),
                                textAlign = TextAlign.Center,
                                modifier = Modifier.padding(12.dp)
                            )
                        }
                    }

                    Button(
                        onClick = onDismiss,
                        shape = RoundedCornerShape(14.dp),
                        colors = ButtonDefaults.buttonColors(
                            containerColor = Color(0xFF10B981),
                            contentColor = Color(0xFF05130E)
                        ),
                        modifier = Modifier
                            .fillMaxWidth()
                            .height(48.dp)
                    ) {
                        Icon(imageVector = Icons.Default.Verified, contentDescription = null, modifier = Modifier.size(18.dp))
                        Spacer(modifier = Modifier.width(8.dp))
                        Text(
                            text = if (isBn) "প্রো ড্যাশবোর্ডে ফিরে যান" else "Continue with VIP Pro",
                            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Black)
                        )
                    }

                    Spacer(modifier = Modifier.height(8.dp))

                    TextButton(
                        onClick = {
                            onDeactivatePro()
                            onDismiss()
                        }
                    ) {
                        Text(
                            text = if (isBn) "নরমাল ভার্সনে স্যুইচ করুন" else "Switch back to Normal Version",
                            style = MaterialTheme.typography.labelMedium,
                            color = Color(0xFF94A3B8)
                        )
                    }
                }

                if (!isProSubscribed) {
                    Spacer(modifier = Modifier.height(6.dp))
                    TextButton(onClick = onDismiss) {
                        Text(
                            text = if (isBn) "নরমাল ভার্সনে চালিয়ে যান" else "Continue with Normal Version",
                            style = MaterialTheme.typography.labelLarge,
                            color = Color(0xFF94A3B8)
                        )
                    }
                }
            }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/components/animation/ExerciseAnimationVisualizer.kt`

```kotlin
package com.example.ui.components.animation

import androidx.compose.animation.core.FastOutSlowInEasing
import androidx.compose.animation.core.LinearEasing
import androidx.compose.animation.core.RepeatMode
import androidx.compose.animation.core.animateFloat
import androidx.compose.animation.core.infiniteRepeatable
import androidx.compose.animation.core.rememberInfiniteTransition
import androidx.compose.animation.core.tween
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.Canvas
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.clickable
import androidx.compose.foundation.gestures.detectTransformGestures
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableFloatStateOf
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.geometry.CornerRadius
import androidx.compose.ui.geometry.Offset
import androidx.compose.ui.geometry.Size
import androidx.compose.ui.graphics.Brush
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.Path
import androidx.compose.ui.graphics.StrokeCap
import androidx.compose.ui.graphics.StrokeJoin
import androidx.compose.ui.graphics.drawscope.DrawScope
import androidx.compose.ui.graphics.drawscope.Stroke
import androidx.compose.ui.graphics.graphicsLayer
import androidx.compose.ui.input.pointer.pointerInput
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextOverflow
import androidx.compose.ui.unit.Dp
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import java.util.Locale
import kotlin.math.PI
import kotlin.math.abs
import kotlin.math.cos
import kotlin.math.hypot
import kotlin.math.sin

/**
 * 27 Dedicated Biomechanical & Humanistic 3D Exercise Animation Types
 * — 1-to-1 mapped to every single exercise in ExerciseLibraryData.
 */
enum class ExerciseAnimType {
    // 1. CHEST (4)
    PUSH_UP,
    CHAIR_INCLINE_PUSHUP,
    WIDE_PUSHUP,
    WATER_BOTTLE_FLOOR_PRESS,

    // 2. ARMS (4)
    CHAIR_DIPS,
    TOWEL_BICEP_CURL,
    DIAMOND_PUSHUP,
    PLANK_SHOULDER_TAPS,

    // 3. ABS & CORE (5)
    CLASSIC_CRUNCHES,
    BICYCLE_CRUNCHES,
    PLANK_HOLD,
    MOUNTAIN_CLIMBERS,
    LEG_RAISES,

    // 4. LEGS (5)
    BODYWEIGHT_SQUATS,
    FORWARD_LUNGES,
    WALL_SIT,
    GLUTE_BRIDGE,
    STANDING_CALF_RAISES,

    // 5. BACK (3)
    SUPERMAN_HOLD,
    TOWEL_LAT_PULLDOWN,
    REVERSE_SNOW_ANGELS,

    // 6. CARDIO & STRETCH (6)
    JUMPING_JACKS,
    BURPEES,
    HIGH_KNEES,
    ARM_CIRCLES,
    COBRA_STRETCH,
    CHILDS_POSE
}

fun resolveAnimType(key: String): ExerciseAnimType {
    val normalized = key.trim().lowercase(Locale.US)
    return when {
        normalized.contains("chair_incline") || normalized.contains("incline_push") -> ExerciseAnimType.CHAIR_INCLINE_PUSHUP
        normalized.contains("wide_push") -> ExerciseAnimType.WIDE_PUSHUP
        normalized.contains("diamond_push") -> ExerciseAnimType.DIAMOND_PUSHUP
        normalized.contains("floor_press") || normalized.contains("water_bottle") || normalized.contains("dumbbell") -> ExerciseAnimType.WATER_BOTTLE_FLOOR_PRESS
        normalized.contains("shoulder_tap") -> ExerciseAnimType.PLANK_SHOULDER_TAPS
        normalized.contains("push_up") || normalized.contains("pushup") -> ExerciseAnimType.PUSH_UP

        normalized.contains("chair_dip") || normalized.contains("tricep_dip") || normalized.contains("dips") -> ExerciseAnimType.CHAIR_DIPS
        normalized.contains("bicep_curl") || normalized.contains("towel_bicep") -> ExerciseAnimType.TOWEL_BICEP_CURL

        normalized.contains("bicycle") -> ExerciseAnimType.BICYCLE_CRUNCHES
        normalized.contains("crunch") -> ExerciseAnimType.CLASSIC_CRUNCHES
        normalized.contains("mountain_climber") || normalized.contains("climber") -> ExerciseAnimType.MOUNTAIN_CLIMBERS
        normalized.contains("leg_raise") -> ExerciseAnimType.LEG_RAISES
        normalized.contains("plank") -> ExerciseAnimType.PLANK_HOLD

        normalized.contains("lunge") -> ExerciseAnimType.FORWARD_LUNGES
        normalized.contains("wall_sit") -> ExerciseAnimType.WALL_SIT
        normalized.contains("glute_bridge") || normalized.contains("bridge") -> ExerciseAnimType.GLUTE_BRIDGE
        normalized.contains("calf_raise") || normalized.contains("calf") -> ExerciseAnimType.STANDING_CALF_RAISES
        normalized.contains("squat") -> ExerciseAnimType.BODYWEIGHT_SQUATS

        normalized.contains("superman") -> ExerciseAnimType.SUPERMAN_HOLD
        normalized.contains("lat_pulldown") || normalized.contains("pulldown") -> ExerciseAnimType.TOWEL_LAT_PULLDOWN
        normalized.contains("snow_angel") || normalized.contains("reverse_snow") -> ExerciseAnimType.REVERSE_SNOW_ANGELS

        normalized.contains("burpee") -> ExerciseAnimType.BURPEES
        normalized.contains("high_knee") -> ExerciseAnimType.HIGH_KNEES
        normalized.contains("arm_circle") -> ExerciseAnimType.ARM_CIRCLES
        normalized.contains("cobra") -> ExerciseAnimType.COBRA_STRETCH
        normalized.contains("childs_pose") || normalized.contains("child_pose") -> ExerciseAnimType.CHILDS_POSE
        else -> ExerciseAnimType.JUMPING_JACKS
    }
}

private fun getCycleDurationMs(type: ExerciseAnimType): Int {
    return when (type) {
        ExerciseAnimType.HIGH_KNEES, ExerciseAnimType.MOUNTAIN_CLIMBERS -> 820
        ExerciseAnimType.JUMPING_JACKS, ExerciseAnimType.ARM_CIRCLES -> 1050
        ExerciseAnimType.BICYCLE_CRUNCHES, ExerciseAnimType.STANDING_CALF_RAISES -> 1200
        ExerciseAnimType.PLANK_SHOULDER_TAPS -> 1350
        ExerciseAnimType.BURPEES -> 1900
        ExerciseAnimType.PLANK_HOLD, ExerciseAnimType.WALL_SIT,
        ExerciseAnimType.COBRA_STRETCH, ExerciseAnimType.CHILDS_POSE -> 2200
        else -> 1500
    }
}

private fun getMuscleTargetLabel(type: ExerciseAnimType, isBengali: Boolean): String {
    return when (type) {
        ExerciseAnimType.PUSH_UP ->
            if (isBengali) "টার্গেট পেশি: মধ্য বুক (Pectoralis Major) ও ট্রাইসেপস" else "Target: Mid Pectorals, Triceps & Core"
        ExerciseAnimType.CHAIR_INCLINE_PUSHUP ->
            if (isBengali) "টার্গেট পেশি: লোয়ার চেস্ট ও সামনের কাঁধ (Incline)" else "Target: Lower Chest & Anterior Deltoids"
        ExerciseAnimType.WIDE_PUSHUP ->
            if (isBengali) "টার্গেট পেশি: আউটার চেস্ট (Outer Pectorals)" else "Target: Outer Pectorals & Chest Width"
        ExerciseAnimType.WATER_BOTTLE_FLOOR_PRESS ->
            if (isBengali) "টার্গেট পেশি: আপার ও মিড চেস্ট (Floor Press)" else "Target: Mid Chest & Triceps Lockout"
        ExerciseAnimType.CHAIR_DIPS ->
            if (isBengali) "টার্গেট পেশি: ট্রাইসেপস ব্রাকি ও কাঁধ (Chair Dips)" else "Target: Triceps Brachii & Anterior Delts"
        ExerciseAnimType.TOWEL_BICEP_CURL ->
            if (isBengali) "টার্গেট পেশি: বাইসেপস পিক ও ফোরআর্মস (Towel Curl)" else "Target: Biceps Brachii & Forearm Flexors"
        ExerciseAnimType.DIAMOND_PUSHUP ->
            if (isBengali) "টার্গেট পেশি: ইনার চেস্ট ও ট্রাইসেপস হর্সশু" else "Target: Inner Chest & Triceps Lateral Head"
        ExerciseAnimType.PLANK_SHOULDER_TAPS ->
            if (isBengali) "টার্গেট পেশি: ডেল্টয়েড কাঁধ ও অ্যান্টি-রোটেশন কোর" else "Target: Deltoids & Core Anti-Rotation"
        ExerciseAnimType.CLASSIC_CRUNCHES ->
            if (isBengali) "টার্গেট পেশি: আপার সিক্স-প্যাক অ্যাবস (Rectus Abdominis)" else "Target: Upper Rectus Abdominis"
        ExerciseAnimType.BICYCLE_CRUNCHES ->
            if (isBengali) "টার্গেট পেশি: অবলিকস (পাশের পেট) ও সম্পূর্ণ কোর" else "Target: Internal/External Obliques & Abs"
        ExerciseAnimType.PLANK_HOLD ->
            if (isBengali) "টার্গেট পেশি: ডিপ ট্রান্সভার্স কোর ও গ্লুটস" else "Target: Transverse Abdominis & Spine Stabilizers"
        ExerciseAnimType.MOUNTAIN_CLIMBERS ->
            if (isBengali) "টার্গেট পেশি: লোয়ার অ্যাবস, হিপ ফ্লেক্সর ও কার্ডিও" else "Target: Lower Abs, Hip Flexors & VO2 Max"
        ExerciseAnimType.LEG_RAISES ->
            if (isBengali) "টার্গেট পেশি: লোয়ার অ্যাবস (Lower Abdominals)" else "Target: Lower Abdominals & Hip Flexors"
        ExerciseAnimType.BODYWEIGHT_SQUATS ->
            if (isBengali) "টার্গেট পেশি: কোয়াড্রিসেপস (উরু), গ্লুটস ও হ্যামস্ট্রিং" else "Target: Quadriceps, Gluteus Maximus & Core"
        ExerciseAnimType.FORWARD_LUNGES ->
            if (isBengali) "টার্গেট পেশি: একক পায়ের কোয়াডস, গ্লুটস ও ব্যালেন্স" else "Target: Unilateral Quads, Glutes & Hamstrings"
        ExerciseAnimType.WALL_SIT ->
            if (isBengali) "টার্গেট পেশি: আইসোমেট্রিক কোয়াড্রিসেপস ও হাঁটুর শক্তি" else "Target: Isometric Quadriceps Endurance"
        ExerciseAnimType.GLUTE_BRIDGE ->
            if (isBengali) "টার্গেট পেশি: গ্লুটস, হ্যামস্ট্রিং ও লোয়ার ব্যাক" else "Target: Gluteus Maximus & Posterior Chain"
        ExerciseAnimType.STANDING_CALF_RAISES ->
            if (isBengali) "টার্গেট পেশি: কাফ মাসল (Gastrocnemius & Soleus)" else "Target: Gastrocnemius & Soleus Calves"
        ExerciseAnimType.SUPERMAN_HOLD ->
            if (isBengali) "টার্গেট পেশি: ইরেক্টর স্পাইনি (লোয়ার ব্যাক) ও গ্লুটস" else "Target: Erector Spinae & Posterior Delts"
        ExerciseAnimType.TOWEL_LAT_PULLDOWN ->
            if (isBengali) "টার্গেট পেশি: ল্যাটিসিমাস ডরসি (V-Taper Back)" else "Target: Latissimus Dorsi & Rhomboids"
        ExerciseAnimType.REVERSE_SNOW_ANGELS ->
            if (isBengali) "টার্গেট পেশি: আপার ব্যাক, ট্র্যাপস ও রিয়ার ডেল্টস" else "Target: Traps, Rhomboids & Rear Deltoids"
        ExerciseAnimType.JUMPING_JACKS ->
            if (isBengali) "টার্গেট পেশি: ফুল-বডি কার্ডিও, কাফ ও কাঁধ" else "Target: Full-Body Cardio & Calves"
        ExerciseAnimType.BURPEES ->
            if (isBengali) "টার্গেট পেশি: ফুল-বডি মেটাবলিক কন্ডিশনিং ও ফ্যাট বার্ন" else "Target: Full-Body Explosive Conditioning"
        ExerciseAnimType.HIGH_KNEES ->
            if (isBengali) "টার্গেট পেশি: কার্ডিও গতি, কোর ও হিপ ফ্লেক্সর" else "Target: Sprint Cardio, Core & Hip Flexors"
        ExerciseAnimType.ARM_CIRCLES ->
            if (isBengali) "টার্গেট পেশি: শোল্ডার জয়েন্ট মোবিলিটি ও ডেল্টয়েডস" else "Target: Rotator Cuff & Deltoid Mobility"
        ExerciseAnimType.COBRA_STRETCH ->
            if (isBengali) "টার্গেট পেশি: মেরুদণ্ডের নমনীয়তা ও অ্যাবস স্ট্রেচ" else "Target: Thoracic Extension & Core Stretch"
        ExerciseAnimType.CHILDS_POSE ->
            if (isBengali) "টার্গেট পেশি: ল্যাটস, লোয়ার ব্যাক ও শ্বাস-প্রশ্বাস রিল্যাক্স" else "Target: Lumbar Decompression & Lat Stretch"
    }
}

@Composable
fun ExerciseAnimationVisualizer(
    exerciseId: String,
    modifier: Modifier = Modifier,
    size: Dp = 200.dp,
    isPaused: Boolean = false,
    tintColor: Color = Color(0xFF10B981),
    showInteractiveControls: Boolean = false,
    isBengali: Boolean = true
) {
    ExerciseAnimationVisualizer(
        animKey = exerciseId,
        modifier = modifier.size(size),
        isPlaying = !isPaused,
        tintColor = tintColor,
        showInteractiveControls = showInteractiveControls,
        isBengali = isBengali
    )
}

/**
 * Humanistic 3D Anatomical Exercise Visualizer with warm human skin tones, sculpted athletic
 * muscle bellies, realistic hair/head/neck/sneakers, 3D gym props (Chair, Towel, Water Bottles,
 * Wall, Mat), and live muscle contraction heatmaps for all 27 exercises.
 */
@Composable
fun ExerciseAnimationVisualizer(
    animKey: String,
    modifier: Modifier = Modifier,
    isPlaying: Boolean = true,
    tintColor: Color = Color(0xFF10B981),
    showInteractiveControls: Boolean = false,
    isBengali: Boolean = true
) {
    val animType = remember(animKey) { resolveAnimType(animKey) }
    val durationMs = remember(animType) { getCycleDurationMs(animType) }

    val infiniteTransition = rememberInfiniteTransition(label = "human3DExerciseAnim")

    // Smooth sinusoidal-like往復 progress (0f -> 1f -> 0f)
    val rawProgress by infiniteTransition.animateFloat(
        initialValue = 0f,
        targetValue = 1f,
        animationSpec = infiniteRepeatable(
            animation = tween(durationMillis = durationMs, easing = FastOutSlowInEasing),
            repeatMode = RepeatMode.Reverse
        ),
        label = "repProgress"
    )

    // Continuous 0..1 phase for cyclic movements (Bicycle Crunches, Arm Circles, Burpees, Mountain Climbers, High Knees)
    val continuousCycle by infiniteTransition.animateFloat(
        initialValue = 0f,
        targetValue = 1f,
        animationSpec = infiniteRepeatable(
            animation = tween(durationMillis = durationMs * 2, easing = LinearEasing),
            repeatMode = RepeatMode.Restart
        ),
        label = "continuousCycle"
    )

    val progress = if (isPlaying) rawProgress else 0.45f
    val cycle = if (isPlaying) continuousCycle else 0.25f

    var showMuscleGlow by remember { mutableStateOf(true) }
    var zoomScale by remember { mutableFloatStateOf(1f) }
    var panOffset by remember { mutableStateOf(Offset.Zero) }

    Box(
        modifier = modifier
            .clip(RoundedCornerShape(22.dp))
            .background(
                Brush.verticalGradient(
                    colors = listOf(
                        Color(0xFF070C17),
                        Color(0xFF10192B),
                        Color(0xFF080D18)
                    )
                )
            )
            .border(
                width = 1.2.dp,
                brush = Brush.linearGradient(
                    colors = listOf(
                        tintColor.copy(alpha = 0.45f),
                        Color(0xFF283753).copy(alpha = 0.65f),
                        Color(0xFFF59E0B).copy(alpha = 0.30f)
                    )
                ),
                shape = RoundedCornerShape(22.dp)
            )
            .then(
                if (showInteractiveControls) {
                    Modifier.pointerInput(Unit) {
                        detectTransformGestures { _, pan, zoom, _ ->
                            val newScale = (zoomScale * zoom).coerceIn(1f, 2.5f)
                            zoomScale = newScale
                            panOffset = if (newScale > 1.02f) {
                                val maxPan = 140f * (newScale - 1f)
                                Offset(
                                    x = (panOffset.x + pan.x).coerceIn(-maxPan, maxPan),
                                    y = (panOffset.y + pan.y).coerceIn(-maxPan, maxPan)
                                )
                            } else {
                                Offset.Zero
                            }
                        }
                    }
                } else {
                    Modifier
                }
            ),
        contentAlignment = Alignment.Center
    ) {
        Canvas(
            modifier = Modifier
                .fillMaxSize()
                .padding(10.dp)
                .graphicsLayer(
                    scaleX = zoomScale,
                    scaleY = zoomScale,
                    translationX = panOffset.x,
                    translationY = panOffset.y
                )
        ) {
            val w = size.width
            val h = size.height
            val u = minOf(w, h)
            val floorY = h * 0.82f

            // 1. Render 3D Dark Luxury Gym Studio Stage & Mat
            draw3DStudioStage(w, h, floorY, tintColor, progress)

            // 2. Render Exercise-Specific Humanistic 3D Athlete & Props
            when (animType) {
                // =========================================================================
                // 1. CHEST EXERCISES (4 DISTINCT ANIMATIONS)
                // =========================================================================
                ExerciseAnimType.PUSH_UP -> {
                    val bodyDrop = progress * (h * 0.16f)
                    val ankle = Offset(w * 0.17f, floorY - u * 0.03f)
                    val knee = Offset(w * 0.34f, floorY - (h * 0.16f) + bodyDrop * 0.45f)
                    val hip = Offset(w * 0.50f, floorY - (h * 0.27f) + bodyDrop * 0.82f)
                    val shoulder = Offset(w * 0.72f, floorY - (h * 0.37f) + bodyDrop)
                    val head = Offset(w * 0.82f, shoulder.y - u * 0.02f)
                    val hand = Offset(w * 0.73f, floorY - u * 0.01f)
                    val elbow = Offset(
                        w * 0.65f - (progress * w * 0.05f),
                        (shoulder.y + hand.y) * 0.52f
                    )

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.62f, progress)
                    // Back arm & leg
                    drawHumanLimb(shoulder, elbow, u * 0.044f, u * 0.033f, isBackLayer = true)
                    drawHumanLimb(elbow, hand, u * 0.032f, u * 0.023f, isBackLayer = true)
                    drawHumanLimb(hip, knee, u * 0.060f, u * 0.042f, isBackLayer = true)
                    drawHumanLimb(knee, ankle, u * 0.040f, u * 0.028f, isBackLayer = true)

                    // Sculpted Torso + Head
                    drawHumanSideTorso(shoulder, hip, u * 0.105f, u * 0.082f, showMuscleGlow, chestGlow = progress, coreGlow = 0.6f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    // Front Leg + Shoe
                    drawHumanLimb(hip, knee, u * 0.062f, u * 0.043f, isClothed = true, isActiveMuscle = false, contraction = progress)
                    drawHumanLimb(knee, ankle, u * 0.042f, u * 0.028f, isActiveMuscle = false, contraction = progress)
                    drawAthleticShoe(ankle, u * 0.062f, facingRight = false, plantarFlex = 0.6f)

                    // Front Arm (Biceps/Triceps + Forearm + Palm on Floor)
                    drawHumanLimb(shoulder, elbow, u * 0.046f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(elbow, hand, u * 0.034f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = progress * 0.7f)
                    drawHumanHandOnFloor(hand, u * 0.032f, facingRight = true)
                }

                ExerciseAnimType.CHAIR_INCLINE_PUSHUP -> {
                    // 3D Studio Chair on Right Side
                    val chairLeft = w * 0.68f
                    val chairSeatY = floorY - (h * 0.25f)
                    draw3DStudioChair(chairLeft, chairSeatY, w * 0.20f, floorY, facingLeft = true)

                    val bodyDrop = progress * (h * 0.14f)
                    val ankle = Offset(w * 0.15f, floorY - u * 0.03f)
                    val knee = Offset(w * 0.31f, floorY - (h * 0.21f) + bodyDrop * 0.4f)
                    val hip = Offset(w * 0.46f, floorY - (h * 0.36f) + bodyDrop * 0.75f)
                    val shoulder = Offset(w * 0.65f, chairSeatY - (h * 0.22f) + bodyDrop)
                    val head = Offset(w * 0.73f, shoulder.y - u * 0.04f)
                    val hand = Offset(chairLeft + u * 0.03f, chairSeatY)
                    val elbow = Offset(
                        w * 0.60f - (progress * w * 0.04f),
                        (shoulder.y + hand.y) * 0.54f
                    )

                    drawFloorContactShadow(w * 0.44f, floorY, w * 0.55f, progress)
                    drawHumanLimb(shoulder, elbow, u * 0.042f, u * 0.032f, isBackLayer = true)
                    drawHumanLimb(elbow, hand, u * 0.030f, u * 0.022f, isBackLayer = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.104f, u * 0.080f, showMuscleGlow, chestGlow = progress, coreGlow = 0.65f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.055f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = false, contraction = progress)
                    drawHumanLimb(knee, ankle, u * 0.041f, u * 0.027f, isActiveMuscle = false, contraction = progress)
                    drawAthleticShoe(ankle, u * 0.060f, facingRight = false, plantarFlex = 0.5f)

                    drawHumanLimb(shoulder, elbow, u * 0.045f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(elbow, hand, u * 0.033f, u * 0.023f, isActiveMuscle = showMuscleGlow, contraction = progress * 0.7f)
                    drawHumanHandOnFloor(hand, u * 0.030f, facingRight = true)
                }

                ExerciseAnimType.WIDE_PUSHUP -> {
                    // Front-Angled 3/4 View to Showcase Wide Hand Stance & Outer Pectorals
                    val drop = progress * (h * 0.15f)
                    val hipCenter = Offset(w * 0.50f, floorY - (h * 0.34f) + drop * 0.6f)
                    val shoulderCenter = Offset(w * 0.50f, floorY - (h * 0.24f) + drop)
                    val headCenter = Offset(w * 0.50f, shoulderCenter.y - u * 0.07f)

                    val leftFoot = Offset(w * 0.43f, floorY - (h * 0.38f))
                    val rightFoot = Offset(w * 0.57f, floorY - (h * 0.38f))
                    val leftShoulder = Offset(w * 0.35f, shoulderCenter.y)
                    val rightShoulder = Offset(w * 0.65f, shoulderCenter.y)

                    // Extra wide hands on floor
                    val leftHand = Offset(w * 0.16f, floorY - u * 0.03f)
                    val rightHand = Offset(w * 0.84f, floorY - u * 0.03f)
                    val leftElbow = Offset(w * 0.22f - progress * u * 0.03f, (leftShoulder.y + leftHand.y) * 0.50f)
                    val rightElbow = Offset(w * 0.78f + progress * u * 0.03f, (rightShoulder.y + rightHand.y) * 0.50f)

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.72f, progress)

                    // Legs in perspective behind torso
                    drawHumanLimb(Offset(hipCenter.x - u * 0.06f, hipCenter.y), leftFoot, u * 0.048f, u * 0.028f, isClothed = true)
                    drawHumanLimb(Offset(hipCenter.x + u * 0.06f, hipCenter.y), rightFoot, u * 0.048f, u * 0.028f, isClothed = true)

                    // Wide Pectoral Torso
                    drawHumanFrontTorso(
                        shoulderCenter = shoulderCenter,
                        hipCenter = Offsets.lerp(hipCenter, Offset(w * 0.50f, floorY - u * 0.08f), 0.45f),
                        shoulderHalfW = u * 0.16f,
                        waistHalfW = u * 0.10f,
                        showMuscleGlow = showMuscleGlow,
                        coreActivation = 0.5f,
                        chestActivation = 0.35f + progress * 0.65f
                    )

                    // Wide Left & Right Arms
                    drawHumanLimb(leftShoulder, leftElbow, u * 0.046f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(leftElbow, leftHand, u * 0.034f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(rightShoulder, rightElbow, u * 0.046f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(rightElbow, rightHand, u * 0.034f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanHandOnFloor(leftHand, u * 0.032f, facingRight = false)
                    drawHumanHandOnFloor(rightHand, u * 0.032f, facingRight = true)

                    drawHumanHeadAndNeck(shoulderCenter, headCenter, u * 0.058f, facingRight = null)
                }

                ExerciseAnimType.WATER_BOTTLE_FLOOR_PRESS -> {
                    // Supine on Floor Mat Pressing 3D Aqua Water Bottles Vertically
                    val shoulder = Offset(w * 0.30f, floorY - u * 0.055f)
                    val head = Offset(w * 0.18f, floorY - u * 0.06f)
                    val hip = Offset(w * 0.54f, floorY - u * 0.05f)
                    val knee = Offset(w * 0.70f, floorY - (h * 0.22f))
                    val ankle = Offset(w * 0.80f, floorY - u * 0.01f)

                    // Press from elbow on floor (progress=0) to vertical lockout (progress=1)
                    val elbow = Offset(
                        shoulder.x + u * 0.03f * (1f - progress),
                        floorY - u * 0.03f - (progress * h * 0.14f)
                    )
                    val hand = Offset(
                        shoulder.x + u * 0.01f,
                        elbow.y - (h * 0.15f) - (progress * h * 0.06f)
                    )

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.68f, progress)

                    // Back arm & bottle
                    drawHumanLimb(shoulder, Offset(elbow.x - u * 0.03f, elbow.y - u * 0.02f), u * 0.042f, u * 0.032f, isBackLayer = true)
                    drawHumanLimb(Offset(elbow.x - u * 0.03f, elbow.y - u * 0.02f), Offset(hand.x - u * 0.03f, hand.y - u * 0.02f), u * 0.030f, u * 0.022f, isBackLayer = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.082f, showMuscleGlow, chestGlow = progress, coreGlow = 0.45f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.054f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = false, contraction = 0.3f)
                    drawHumanLimb(knee, ankle, u * 0.041f, u * 0.027f, isActiveMuscle = false, contraction = 0.3f)
                    drawAthleticShoe(ankle, u * 0.060f, facingRight = true)

                    // Front Pressing Arm + 3D Aqua Water Bottle Prop
                    drawHumanLimb(shoulder, elbow, u * 0.046f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(elbow, hand, u * 0.034f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    draw3DWaterBottleProp(hand, u * 0.095f)
                }

                // =========================================================================
                // 2. ARMS EXERCISES (4 DISTINCT ANIMATIONS)
                // =========================================================================
                ExerciseAnimType.CHAIR_DIPS -> {
                    // 3D Studio Chair on Left
                    val chairRight = w * 0.34f
                    val chairSeatY = floorY - (h * 0.27f)
                    draw3DStudioChair(w * 0.14f, chairSeatY, w * 0.20f, floorY, facingLeft = false)

                    val dipDrop = progress * (h * 0.14f)
                    val hip = Offset(chairRight + u * 0.11f, chairSeatY - u * 0.02f + dipDrop)
                    val shoulder = Offset(hip.x - u * 0.02f, hip.y - (h * 0.23f))
                    val head = Offset(shoulder.x + u * 0.01f, shoulder.y - u * 0.09f)
                    val knee = Offset(hip.x + u * 0.18f, hip.y + u * 0.02f)
                    val ankle = Offset(knee.x + u * 0.06f, floorY - u * 0.01f)

                    val hand = Offset(chairRight - u * 0.01f, chairSeatY)
                    val elbow = Offset(chairRight - u * 0.07f - progress * u * 0.03f, (shoulder.y + hand.y) * 0.50f)

                    drawFloorContactShadow(w * 0.52f, floorY, w * 0.50f, progress)
                    drawHumanLimb(shoulder, elbow, u * 0.042f, u * 0.032f, isBackLayer = true)
                    drawHumanLimb(elbow, hand, u * 0.030f, u * 0.022f, isBackLayer = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.100f, u * 0.080f, showMuscleGlow, chestGlow = progress * 0.5f, coreGlow = 0.5f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.055f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.064f, u * 0.044f, isClothed = true, isActiveMuscle = false, contraction = progress)
                    drawHumanLimb(knee, ankle, u * 0.042f, u * 0.028f, isActiveMuscle = false, contraction = progress)
                    drawAthleticShoe(ankle, u * 0.062f, facingRight = true)

                    // Active Triceps Arm
                    drawHumanLimb(shoulder, elbow, u * 0.046f, u * 0.035f, isActiveMuscle = showMuscleGlow, contraction = 0.35f + progress * 0.65f)
                    drawHumanLimb(elbow, hand, u * 0.034f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = progress)
                }

                ExerciseAnimType.TOWEL_BICEP_CURL -> {
                    // Standing Athlete Anchoring a 3D Towel Under Front Foot & Curling With Bulging Biceps
                    val backAnkle = Offset(w * 0.42f, floorY - u * 0.01f)
                    val backKnee = Offset(w * 0.44f, floorY - (h * 0.22f))
                    val hip = Offset(w * 0.46f, floorY - (h * 0.42f))
                    val shoulder = Offset(w * 0.47f, floorY - (h * 0.66f))
                    val head = Offset(w * 0.48f, shoulder.y - u * 0.095f)

                    // Front foot raised slightly stepping onto towel loop
                    val frontKnee = Offset(w * 0.56f, floorY - (h * 0.25f) - progress * u * 0.02f)
                    val frontAnkle = Offset(w * 0.58f, floorY - u * 0.06f)

                    val elbow = Offset(shoulder.x + u * 0.03f, shoulder.y + (h * 0.14f))
                    // Forearm curls from 35 deg up to 125 deg
                    val curlAngle = (0.35f - progress * 1.45f)
                    val forearmLen = h * 0.14f
                    val hand = Offset(
                        elbow.x + cos(curlAngle) * forearmLen,
                        elbow.y + sin(curlAngle) * forearmLen
                    )

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.36f, progress)

                    // Back Leg
                    drawHumanLimb(hip, backKnee, u * 0.062f, u * 0.042f, isBackLayer = true)
                    drawHumanLimb(backKnee, backAnkle, u * 0.042f, u * 0.028f, isBackLayer = true)
                    drawAthleticShoe(backAnkle, u * 0.060f, facingRight = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.104f, u * 0.082f, showMuscleGlow, chestGlow = 0.3f, coreGlow = 0.55f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    // Front Leg stepping in towel
                    drawHumanLimb(hip, frontKnee, u * 0.064f, u * 0.044f, isClothed = true, isActiveMuscle = false, contraction = 0.5f)
                    drawHumanLimb(frontKnee, frontAnkle, u * 0.042f, u * 0.028f, isActiveMuscle = false, contraction = 0.5f)
                    drawAthleticShoe(frontAnkle, u * 0.062f, facingRight = true)

                    // 3D Woven Fitness Towel Loop from Foot to Hands
                    draw3DTowelStrap(frontAnkle, hand, progress)

                    // Upper Arm with Pronounced Biceps Peak + Forearm
                    drawHumanLimb(shoulder, elbow, u * 0.048f, u * 0.038f, isActiveMuscle = showMuscleGlow, contraction = 0.3f + progress * 0.7f)
                    drawHumanLimb(elbow, hand, u * 0.036f, u * 0.026f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawCircle(color = Color(0xFFD99B78), radius = u * 0.024f, center = hand)
                }

                ExerciseAnimType.DIAMOND_PUSHUP -> {
                    // Close-Grip Diamond Push-Up with Glowing Cyan Diamond Hand-Formation HUD on Mat
                    val bodyDrop = progress * (h * 0.16f)
                    val ankle = Offset(w * 0.17f, floorY - u * 0.03f)
                    val knee = Offset(w * 0.34f, floorY - (h * 0.16f) + bodyDrop * 0.45f)
                    val hip = Offset(w * 0.50f, floorY - (h * 0.27f) + bodyDrop * 0.82f)
                    val shoulder = Offset(w * 0.71f, floorY - (h * 0.37f) + bodyDrop)
                    val head = Offset(w * 0.81f, shoulder.y - u * 0.02f)
                    // Hands directly under sternum (closer than standard pushup)
                    val hand = Offset(w * 0.67f, floorY - u * 0.01f)
                    val elbow = Offset(
                        w * 0.58f - (progress * w * 0.04f),
                        (shoulder.y + hand.y) * 0.55f
                    )

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.62f, progress)

                    // Glowing Diamond Grip Emblem on Mat under Hands
                    val diamondPath = Path().apply {
                        moveTo(hand.x, hand.y - u * 0.045f)
                        lineTo(hand.x + u * 0.055f, hand.y)
                        lineTo(hand.x, hand.y + u * 0.045f)
                        lineTo(hand.x - u * 0.055f, hand.y)
                        close()
                    }
                    drawPath(diamondPath, color = Color(0xFF38BDF8).copy(alpha = 0.28f + progress * 0.35f))
                    drawPath(diamondPath, color = Color(0xFF38BDF8), style = Stroke(width = 2.dp.toPx()))

                    drawHumanSideTorso(shoulder, hip, u * 0.105f, u * 0.082f, showMuscleGlow, chestGlow = progress, coreGlow = 0.7f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.062f, u * 0.043f, isClothed = true)
                    drawHumanLimb(knee, ankle, u * 0.042f, u * 0.028f)
                    drawAthleticShoe(ankle, u * 0.062f, facingRight = false, plantarFlex = 0.6f)

                    // Intense Triceps Horseshoe Arm
                    drawHumanLimb(shoulder, elbow, u * 0.048f, u * 0.036f, isActiveMuscle = showMuscleGlow, contraction = 0.4f + progress * 0.6f)
                    drawHumanLimb(elbow, hand, u * 0.035f, u * 0.025f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanHandOnFloor(hand, u * 0.032f, facingRight = true)
                }

                ExerciseAnimType.PLANK_SHOULDER_TAPS -> {
                    // Front-3/4 Plank Where Left & Right Hands Alternately Tap Opposite Shoulder
                    val leftTap = ((sin(cycle * 2f * PI).toFloat()).coerceAtLeast(0f))
                    val rightTap = ((sin((cycle + 0.5f) * 2f * PI).toFloat()).coerceAtLeast(0f))

                    val hipCenter = Offset(w * 0.50f, floorY - (h * 0.36f))
                    val shoulderCenter = Offset(w * 0.50f, floorY - (h * 0.28f))
                    val headCenter = Offset(w * 0.50f, shoulderCenter.y - u * 0.075f)

                    val leftShoulder = Offset(w * 0.37f, shoulderCenter.y)
                    val rightShoulder = Offset(w * 0.63f, shoulderCenter.y)

                    val leftHandFloor = Offset(w * 0.35f, floorY - u * 0.02f)
                    val rightHandFloor = Offset(w * 0.65f, floorY - u * 0.02f)

                    val leftHand = Offsets.lerp(leftHandFloor, rightShoulder, leftTap)
                    val rightHand = Offsets.lerp(rightHandFloor, leftShoulder, rightTap)

                    val leftElbow = Offset(
                        w * 0.32f - leftTap * u * 0.04f,
                        (leftShoulder.y + leftHand.y) * 0.52f
                    )
                    val rightElbow = Offset(
                        w * 0.68f + rightTap * u * 0.04f,
                        (rightShoulder.y + rightHand.y) * 0.52f
                    )

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.56f, progress)

                    // Plank Legs behind torso
                    drawHumanLimb(Offset(hipCenter.x - u * 0.06f, hipCenter.y), Offset(w * 0.42f, floorY - (h * 0.38f)), u * 0.048f, u * 0.028f, isClothed = true)
                    drawHumanLimb(Offset(hipCenter.x + u * 0.06f, hipCenter.y), Offset(w * 0.58f, floorY - (h * 0.38f)), u * 0.048f, u * 0.028f, isClothed = true)

                    drawHumanFrontTorso(
                        shoulderCenter = shoulderCenter,
                        hipCenter = Offset(w * 0.50f, shoulderCenter.y + h * 0.16f),
                        shoulderHalfW = u * 0.145f,
                        waistHalfW = u * 0.095f,
                        showMuscleGlow = showMuscleGlow,
                        coreActivation = 0.85f,
                        chestActivation = 0.6f
                    )

                    drawHumanLimb(leftShoulder, leftElbow, u * 0.044f, u * 0.032f, isActiveMuscle = showMuscleGlow, contraction = maxOf(leftTap, 0.5f))
                    drawHumanLimb(leftElbow, leftHand, u * 0.033f, u * 0.023f, isActiveMuscle = showMuscleGlow, contraction = leftTap)
                    drawHumanLimb(rightShoulder, rightElbow, u * 0.044f, u * 0.032f, isActiveMuscle = showMuscleGlow, contraction = maxOf(rightTap, 0.5f))
                    drawHumanLimb(rightElbow, rightHand, u * 0.033f, u * 0.023f, isActiveMuscle = showMuscleGlow, contraction = rightTap)

                    // Tap Impact Ripple on Shoulder
                    if (leftTap > 0.75f) {
                        drawCircle(color = Color(0xFF34D399).copy(alpha = 0.55f), radius = u * 0.055f, center = rightShoulder)
                    }
                    if (rightTap > 0.75f) {
                        drawCircle(color = Color(0xFF34D399).copy(alpha = 0.55f), radius = u * 0.055f, center = leftShoulder)
                    }

                    drawHumanHeadAndNeck(shoulderCenter, headCenter, u * 0.056f, facingRight = null)
                }

                // =========================================================================
                // 3. ABS & CORE EXERCISES (5 DISTINCT ANIMATIONS)
                // =========================================================================
                ExerciseAnimType.CLASSIC_CRUNCHES -> {
                    val curlUp = progress * (h * 0.18f)
                    val hip = Offset(w * 0.48f, floorY - u * 0.04f)
                    val knee = Offset(w * 0.68f, floorY - (h * 0.25f))
                    val ankle = Offset(w * 0.81f, floorY - u * 0.01f)
                    val shoulder = Offset(
                        w * 0.25f + (progress * w * 0.11f),
                        floorY - u * 0.06f - curlUp
                    )
                    val head = Offset(
                        shoulder.x - u * 0.04f + (progress * u * 0.05f),
                        shoulder.y - u * 0.07f
                    )
                    val elbow = Offset(shoulder.x + u * 0.07f, shoulder.y - u * 0.04f)

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.62f, progress)
                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.084f, showMuscleGlow, chestGlow = 0.3f, coreGlow = 0.35f + progress * 0.65f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.054f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.064f, u * 0.042f, isClothed = true)
                    drawHumanLimb(knee, ankle, u * 0.041f, u * 0.027f)
                    drawAthleticShoe(ankle, u * 0.060f, facingRight = true)

                    // Hands behind temples
                    drawHumanLimb(shoulder, elbow, u * 0.038f, u * 0.028f)
                    drawHumanLimb(elbow, head, u * 0.026f, u * 0.020f)
                }

                ExerciseAnimType.BICYCLE_CRUNCHES -> {
                    // Alternating Pedal Motion in Mid-Air + Torso Twist
                    val phaseAngle = (cycle * 2f * PI).toFloat()
                    val rightExtend = (sin(phaseAngle) + 1f) * 0.5f
                    val leftExtend = 1f - rightExtend

                    val hip = Offset(w * 0.46f, floorY - u * 0.045f)
                    val shoulder = Offset(
                        w * 0.25f + abs(sin(phaseAngle)) * w * 0.07f,
                        floorY - (h * 0.14f) - abs(sin(phaseAngle)) * h * 0.05f
                    )
                    val head = Offset(shoulder.x - u * 0.04f, shoulder.y - u * 0.07f)

                    // Back leg (left) cycling
                    val leftKnee = Offset(
                        hip.x + u * 0.06f + leftExtend * (w * 0.18f),
                        floorY - (h * 0.26f) + leftExtend * (h * 0.08f)
                    )
                    val leftAnkle = Offset(
                        leftKnee.x + u * 0.12f + leftExtend * (w * 0.12f),
                        leftKnee.y + (1f - leftExtend) * u * 0.05f
                    )

                    // Front leg (right) cycling in opposition
                    val rightKnee = Offset(
                        hip.x + u * 0.06f + rightExtend * (w * 0.18f),
                        floorY - (h * 0.26f) + rightExtend * (h * 0.08f)
                    )
                    val rightAnkle = Offset(
                        rightKnee.x + u * 0.12f + rightExtend * (w * 0.12f),
                        rightKnee.y + (1f - rightExtend) * u * 0.05f
                    )

                    val activeElbow = Offsets.lerp(
                        Offset(shoulder.x + u * 0.06f, shoulder.y - u * 0.04f),
                        if (rightExtend < 0.5f) rightKnee else leftKnee,
                        0.55f
                    )

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.64f, progress)

                    // Back Cycling Leg
                    drawHumanLimb(hip, leftKnee, u * 0.058f, u * 0.040f, isBackLayer = true)
                    drawHumanLimb(leftKnee, leftAnkle, u * 0.038f, u * 0.026f, isBackLayer = true)
                    drawAthleticShoe(leftAnkle, u * 0.055f, facingRight = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.084f, showMuscleGlow, chestGlow = 0.4f, coreGlow = 0.90f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.054f, facingRight = true)

                    // Front Cycling Leg
                    drawHumanLimb(hip, rightKnee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = 1f - rightExtend)
                    drawHumanLimb(rightKnee, rightAnkle, u * 0.040f, u * 0.027f)
                    drawAthleticShoe(rightAnkle, u * 0.058f, facingRight = true)

                    // Twisting Elbow to Knee
                    drawHumanLimb(shoulder, activeElbow, u * 0.040f, u * 0.030f, isActiveMuscle = showMuscleGlow, contraction = 0.8f)
                    drawHumanLimb(activeElbow, head, u * 0.028f, u * 0.022f)
                }

                ExerciseAnimType.PLANK_HOLD -> {
                    val breathe = progress * (h * 0.022f)
                    val ankle = Offset(w * 0.16f, floorY - u * 0.02f)
                    val knee = Offset(w * 0.34f, floorY - (h * 0.13f) + breathe)
                    val hip = Offset(w * 0.50f, floorY - (h * 0.22f) + breathe)
                    val shoulder = Offset(w * 0.72f, floorY - (h * 0.26f) + breathe)
                    val head = Offset(w * 0.82f, shoulder.y - u * 0.01f)
                    val elbow = Offset(w * 0.71f, floorY - u * 0.01f)
                    val hand = Offset(w * 0.81f, floorY - u * 0.01f)

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.65f, progress)

                    // Core Tension Energy Waves under Abdomen
                    if (showMuscleGlow) {
                        for (ring in 1..2) {
                            val rY = hip.y + u * (0.06f * ring) + progress * u * 0.03f
                            drawLine(
                                color = Color(0xFFF59E0B).copy(alpha = 0.45f / ring),
                                start = Offset(w * 0.42f, rY),
                                end = Offset(w * 0.65f, rY),
                                strokeWidth = 2.dp.toPx(),
                                cap = StrokeCap.Round
                            )
                        }
                    }

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.080f, showMuscleGlow, chestGlow = 0.5f, coreGlow = 0.75f + progress * 0.25f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.055f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = 0.7f)
                    drawHumanLimb(knee, ankle, u * 0.041f, u * 0.027f)
                    drawAthleticShoe(ankle, u * 0.060f, facingRight = false, plantarFlex = 0.65f)

                    drawHumanLimb(shoulder, elbow, u * 0.044f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = 0.8f)
                    drawHumanLimb(elbow, hand, u * 0.032f, u * 0.024f)
                }

                ExerciseAnimType.MOUNTAIN_CLIMBERS -> {
                    val phaseAngle = (cycle * 2f * PI).toFloat()
                    val leftDrive = (sin(phaseAngle) + 1f) * 0.5f
                    val rightDrive = 1f - leftDrive

                    val hip = Offset(w * 0.44f, floorY - (h * 0.28f))
                    val shoulder = Offset(w * 0.70f, floorY - (h * 0.34f))
                    val head = Offset(w * 0.80f, shoulder.y - u * 0.02f)
                    val hand = Offset(w * 0.72f, floorY - u * 0.01f)

                    val leftKnee = Offsets.lerp(Offset(w * 0.29f, floorY - h * 0.14f), Offset(w * 0.62f, floorY - h * 0.22f), leftDrive)
                    val leftFoot = Offsets.lerp(Offset(w * 0.15f, floorY - u * 0.02f), Offset(w * 0.48f, floorY - u * 0.08f), leftDrive)

                    val rightKnee = Offsets.lerp(Offset(w * 0.29f, floorY - h * 0.14f), Offset(w * 0.62f, floorY - h * 0.22f), rightDrive)
                    val rightFoot = Offsets.lerp(Offset(w * 0.15f, floorY - u * 0.02f), Offset(w * 0.48f, floorY - u * 0.08f), rightDrive)

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.62f, progress)

                    // Back Leg
                    drawHumanLimb(hip, leftKnee, u * 0.058f, u * 0.040f, isBackLayer = true)
                    drawHumanLimb(leftKnee, leftFoot, u * 0.038f, u * 0.026f, isBackLayer = true)
                    drawAthleticShoe(leftFoot, u * 0.056f, facingRight = false)

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.080f, showMuscleGlow, chestGlow = 0.6f, coreGlow = 0.90f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.055f, facingRight = true)

                    // Front Driving Leg
                    drawHumanLimb(hip, rightKnee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = rightDrive)
                    drawHumanLimb(rightKnee, rightFoot, u * 0.040f, u * 0.027f)
                    drawAthleticShoe(rightFoot, u * 0.058f, facingRight = false)

                    drawHumanLimb(shoulder, hand, u * 0.042f, u * 0.028f, isActiveMuscle = showMuscleGlow, contraction = 0.75f)
                    drawHumanHandOnFloor(hand, u * 0.032f, facingRight = true)
                }

                ExerciseAnimType.LEG_RAISES -> {
                    // Supine Flat on Mat, Lifting Both Straight Sculpted Legs Together up to 90 Degrees
                    val shoulder = Offset(w * 0.22f, floorY - u * 0.045f)
                    val head = Offset(w * 0.12f, floorY - u * 0.05f)
                    val hip = Offset(w * 0.47f, floorY - u * 0.045f)

                    // Leg angle sweeps from 12 deg (just above floor) to 86 deg (vertical)
                    val legAngleRad = (0.20f + progress * 1.28f)
                    val thighLen = u * 0.21f
                    val shinLen = u * 0.19f
                    val knee = Offset(
                        hip.x + cos(legAngleRad) * thighLen,
                        hip.y - sin(legAngleRad) * thighLen
                    )
                    val ankle = Offset(
                        knee.x + cos(legAngleRad) * shinLen,
                        knee.y - sin(legAngleRad) * shinLen
                    )

                    drawFloorContactShadow(w * 0.45f, floorY, w * 0.65f, progress)

                    // Arc trajectory indicator for legs
                    drawArc(
                        color = tintColor.copy(alpha = 0.28f),
                        startAngle = -86f,
                        sweepAngle = 74f,
                        useCenter = false,
                        topLeft = Offset(hip.x - (thighLen + shinLen), hip.y - (thighLen + shinLen)),
                        size = Size((thighLen + shinLen) * 2f, (thighLen + shinLen) * 2f),
                        style = Stroke(width = 1.5.dp.toPx(), cap = StrokeCap.Round)
                    )

                    drawHumanSideTorso(shoulder, hip, u * 0.100f, u * 0.082f, showMuscleGlow, chestGlow = 0.2f, coreGlow = 0.4f + progress * 0.6f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.054f, facingRight = true)

                    // Hands anchored under lower back/hips
                    drawHumanLimb(shoulder, Offset(hip.x - u * 0.02f, floorY - u * 0.02f), u * 0.038f, u * 0.026f)

                    // Elevated Straight Legs
                    drawHumanLimb(hip, knee, u * 0.064f, u * 0.044f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(knee, ankle, u * 0.042f, u * 0.028f, isActiveMuscle = showMuscleGlow, contraction = progress * 0.6f)
                    drawAthleticShoe(ankle, u * 0.060f, facingRight = true, plantarFlex = 0.3f)
                }

                // =========================================================================
                // 4. LEGS EXERCISES (5 DISTINCT ANIMATIONS)
                // =========================================================================
                ExerciseAnimType.BODYWEIGHT_SQUATS -> {
                    val squatDrop = progress * (h * 0.20f)
                    val ankle = Offset(w * 0.48f, floorY - u * 0.01f)
                    val knee = Offset(
                        w * 0.50f + (progress * w * 0.11f),
                        floorY - (h * 0.24f) + (squatDrop * 0.28f)
                    )
                    val hip = Offset(
                        w * 0.45f - (progress * w * 0.12f),
                        floorY - (h * 0.45f) + squatDrop
                    )
                    val shoulder = Offset(
                        w * 0.48f - (progress * w * 0.03f),
                        hip.y - (h * 0.23f) + (progress * h * 0.03f)
                    )
                    val head = Offset(shoulder.x + u * 0.02f, shoulder.y - u * 0.095f)
                    val elbow = Offset(
                        shoulder.x + (progress * w * 0.12f),
                        shoulder.y + (h * 0.10f) - (progress * h * 0.06f)
                    )
                    val hand = Offset(
                        elbow.x + u * 0.05f + (progress * w * 0.12f),
                        elbow.y + (h * 0.06f) - (progress * h * 0.09f)
                    )

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.42f, progress)

                    // Back Leg & Back Arm
                    drawHumanLimb(hip, Offset(knee.x - u * 0.04f, knee.y - u * 0.01f), u * 0.062f, u * 0.042f, isBackLayer = true)
                    drawHumanLimb(Offset(knee.x - u * 0.04f, knee.y - u * 0.01f), Offset(ankle.x - u * 0.04f, ankle.y), u * 0.042f, u * 0.028f, isBackLayer = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.106f, u * 0.086f, showMuscleGlow, chestGlow = 0.25f, coreGlow = 0.6f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.058f, facingRight = true)

                    // Front Sculpted Quad/Glute & Calf
                    drawHumanLimb(hip, knee, u * 0.070f, u * 0.046f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = 0.3f + progress * 0.7f)
                    drawHumanLimb(knee, ankle, u * 0.046f, u * 0.030f, isActiveMuscle = showMuscleGlow, contraction = progress * 0.6f)
                    drawAthleticShoe(ankle, u * 0.066f, facingRight = true)

                    // Counterbalance Arm
                    drawHumanLimb(shoulder, elbow, u * 0.042f, u * 0.032f)
                    drawHumanLimb(elbow, hand, u * 0.032f, u * 0.022f)
                }

                ExerciseAnimType.FORWARD_LUNGES -> {
                    val lungeDrop = progress * (h * 0.16f)
                    val stride = progress * (w * 0.15f)
                    val hip = Offset(w * 0.47f + stride * 0.35f, floorY - (h * 0.43f) + lungeDrop)
                    val shoulder = Offset(hip.x, hip.y - (h * 0.23f))
                    val head = Offset(shoulder.x + u * 0.01f, shoulder.y - u * 0.095f)

                    val frontKnee = Offset(w * 0.56f + stride, floorY - (h * 0.22f) + lungeDrop * 0.35f)
                    val frontAnkle = Offset(w * 0.56f + stride, floorY - u * 0.01f)

                    val backKnee = Offset(w * 0.38f - stride * 0.4f, floorY - (h * 0.20f) + lungeDrop * 0.85f)
                    val backAnkle = Offset(w * 0.24f - stride * 0.5f, floorY - u * 0.02f)

                    // Hands on hips / athletic runner balance
                    val elbow = Offset(shoulder.x - u * 0.05f, shoulder.y + h * 0.11f)
                    val hand = Offset(hip.x + u * 0.02f, hip.y - u * 0.02f)

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.58f, progress)

                    // Rear Split Leg
                    drawHumanLimb(hip, backKnee, u * 0.062f, u * 0.042f, isBackLayer = true)
                    drawHumanLimb(backKnee, backAnkle, u * 0.040f, u * 0.028f, isBackLayer = true)
                    drawAthleticShoe(backAnkle, u * 0.058f, facingRight = true, plantarFlex = 0.5f)

                    drawHumanSideTorso(shoulder, hip, u * 0.104f, u * 0.084f, showMuscleGlow, chestGlow = 0.2f, coreGlow = 0.65f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    // Front Lead Lunge Leg
                    drawHumanLimb(hip, frontKnee, u * 0.068f, u * 0.046f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = 0.3f + progress * 0.7f)
                    drawHumanLimb(frontKnee, frontAnkle, u * 0.044f, u * 0.030f, isActiveMuscle = showMuscleGlow, contraction = progress * 0.6f)
                    drawAthleticShoe(frontAnkle, u * 0.064f, facingRight = true)

                    drawHumanLimb(shoulder, elbow, u * 0.040f, u * 0.030f)
                    drawHumanLimb(elbow, hand, u * 0.030f, u * 0.022f)
                }

                ExerciseAnimType.WALL_SIT -> {
                    // 3D Vertical Architectural Studio Wall on Left + 90-Degree Isometric Sit
                    val wallRight = w * 0.28f
                    drawRoundRect(
                        brush = Brush.horizontalGradient(
                            colors = listOf(Color(0xFF0F172A), Color(0xFF334155)),
                            startX = w * 0.14f,
                            endX = wallRight
                        ),
                        topLeft = Offset(w * 0.14f, h * 0.16f),
                        size = Size(w * 0.14f, floorY - h * 0.14f),
                        cornerRadius = CornerRadius(8.dp.toPx())
                    )
                    drawLine(
                        color = tintColor.copy(alpha = 0.7f),
                        start = Offset(wallRight, h * 0.16f),
                        end = Offset(wallRight, floorY),
                        strokeWidth = 2.5.dp.toPx()
                    )

                    val microTremor = progress * (h * 0.015f)
                    val hip = Offset(wallRight + u * 0.065f, floorY - (h * 0.25f) + microTremor)
                    val shoulder = Offset(wallRight + u * 0.065f, hip.y - (h * 0.24f))
                    val head = Offset(shoulder.x + u * 0.01f, shoulder.y - u * 0.095f)
                    val knee = Offset(hip.x + u * 0.21f, hip.y)
                    val ankle = Offset(knee.x, floorY - u * 0.01f)

                    val elbow = Offset(shoulder.x + u * 0.08f, shoulder.y + h * 0.12f)
                    val hand = Offset(knee.x - u * 0.02f, knee.y - u * 0.05f)

                    drawFloorContactShadow(w * 0.45f, floorY, w * 0.42f, progress)

                    // 90-Degree Right-Angle HUD Guide at Knee
                    drawLine(color = Color(0xFFFBBF24).copy(alpha = 0.6f), start = Offset(knee.x - u * 0.06f, knee.y), end = Offset(knee.x, knee.y), strokeWidth = 1.5.dp.toPx())
                    drawLine(color = Color(0xFFFBBF24).copy(alpha = 0.6f), start = Offset(knee.x, knee.y), end = Offset(knee.x, knee.y + u * 0.06f), strokeWidth = 1.5.dp.toPx())

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.084f, showMuscleGlow, chestGlow = 0.2f, coreGlow = 0.75f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    // Glowing Isometric Quads
                    drawHumanLimb(hip, knee, u * 0.070f, u * 0.046f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = 0.75f + progress * 0.25f)
                    drawHumanLimb(knee, ankle, u * 0.044f, u * 0.030f, isActiveMuscle = showMuscleGlow, contraction = 0.6f)
                    drawAthleticShoe(ankle, u * 0.064f, facingRight = true)

                    drawHumanLimb(shoulder, elbow, u * 0.040f, u * 0.030f)
                    drawHumanLimb(elbow, hand, u * 0.030f, u * 0.022f)
                }

                ExerciseAnimType.GLUTE_BRIDGE -> {
                    val shoulder = Offset(w * 0.24f, floorY - u * 0.045f)
                    val head = Offset(w * 0.14f, floorY - u * 0.05f)
                    val knee = Offset(w * 0.67f, floorY - (h * 0.24f))
                    val ankle = Offset(w * 0.74f, floorY - u * 0.01f)
                    val hipLift = progress * (h * 0.18f)
                    val hip = Offset(w * 0.47f, floorY - u * 0.05f - hipLift)

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.62f, progress)

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.086f, showMuscleGlow, chestGlow = 0.2f, coreGlow = 0.5f + progress * 0.5f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.054f, facingRight = true)

                    // Arms resting flat on mat
                    drawHumanLimb(shoulder, Offset(w * 0.46f, floorY - u * 0.02f), u * 0.038f, u * 0.026f)

                    // Glutes & Hamstrings Driving Upward
                    drawHumanLimb(hip, knee, u * 0.068f, u * 0.045f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = 0.35f + progress * 0.65f)
                    drawHumanLimb(knee, ankle, u * 0.042f, u * 0.028f)
                    drawAthleticShoe(ankle, u * 0.060f, facingRight = true)
                }

                ExerciseAnimType.STANDING_CALF_RAISES -> {
                    // Standing Tall & Rising Smoothly Onto Balls of Feet With Pronounced Calf Muscle Bulge
                    val heelLift = progress * (h * 0.095f)
                    val toe = Offset(w * 0.54f, floorY - u * 0.01f)
                    val ankle = Offset(w * 0.47f, floorY - u * 0.02f - heelLift)
                    val knee = Offset(w * 0.48f, ankle.y - (h * 0.21f))
                    val hip = Offset(w * 0.46f, knee.y - (h * 0.21f))
                    val shoulder = Offset(w * 0.47f, hip.y - (h * 0.23f))
                    val head = Offset(w * 0.48f, shoulder.y - u * 0.095f)

                    val elbow = Offset(shoulder.x - u * 0.05f, shoulder.y + h * 0.11f)
                    val hand = Offset(hip.x + u * 0.01f, hip.y - u * 0.01f)

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.36f, progress)

                    // Back Leg
                    drawHumanLimb(hip, Offset(knee.x - u * 0.03f, knee.y), u * 0.062f, u * 0.042f, isBackLayer = true)
                    drawHumanLimb(Offset(knee.x - u * 0.03f, knee.y), Offset(ankle.x - u * 0.03f, ankle.y), u * 0.046f, u * 0.028f, isBackLayer = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.104f, u * 0.084f, showMuscleGlow, chestGlow = 0.2f, coreGlow = 0.45f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.066f, u * 0.044f, isClothed = true, isActiveMuscle = false, contraction = progress)
                    // Gastrocnemius & Soleus Calf with Extra Contraction Swell
                    drawHumanLimb(knee, ankle, u * 0.050f, u * 0.028f, isActiveMuscle = showMuscleGlow, contraction = 0.35f + progress * 0.65f)

                    // Articulated Tiptoe Shoe
                    drawLine(
                        color = Color(0xFFF8FAFC),
                        start = ankle,
                        end = toe,
                        strokeWidth = 6.dp.toPx(),
                        cap = StrokeCap.Round
                    )
                    drawCircle(color = tintColor, radius = u * 0.022f, center = toe)

                    drawHumanLimb(shoulder, elbow, u * 0.040f, u * 0.030f)
                    drawHumanLimb(elbow, hand, u * 0.030f, u * 0.022f)
                }

                // =========================================================================
                // 5. BACK EXERCISES (3 DISTINCT ANIMATIONS)
                // =========================================================================
                ExerciseAnimType.SUPERMAN_HOLD -> {
                    // Prone on Stomach, Simultaneously Lifting Arms & Legs into a Graceful Spinal Arch
                    val lift = progress * (h * 0.15f)
                    val hip = Offset(w * 0.48f, floorY - u * 0.045f)
                    val shoulder = Offset(w * 0.67f, floorY - u * 0.07f - lift * 0.85f)
                    val head = Offset(w * 0.75f, shoulder.y - u * 0.04f - lift * 0.2f)
                    val hand = Offset(w * 0.88f, shoulder.y - u * 0.06f - lift * 0.45f)

                    val knee = Offset(w * 0.31f, floorY - u * 0.05f - lift * 0.65f)
                    val ankle = Offset(w * 0.14f, floorY - u * 0.07f - lift * 1.05f)

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.60f, progress)

                    // Rear Leg & Rear Arm
                    drawHumanLimb(hip, Offset(knee.x, knee.y - u * 0.02f), u * 0.058f, u * 0.040f, isBackLayer = true)
                    drawHumanLimb(Offset(knee.x, knee.y - u * 0.02f), Offset(ankle.x, ankle.y - u * 0.02f), u * 0.038f, u * 0.026f, isBackLayer = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.082f, showMuscleGlow, chestGlow = 0.3f, coreGlow = 0.45f + progress * 0.55f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.054f, facingRight = true)

                    // Hyperextended Legs (Glutes + Hamstrings)
                    drawHumanLimb(hip, knee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(knee, ankle, u * 0.040f, u * 0.026f, isActiveMuscle = showMuscleGlow, contraction = progress * 0.7f)
                    drawAthleticShoe(ankle, u * 0.056f, facingRight = false, plantarFlex = 0.5f)

                    // Extended Superman Arms Forward
                    drawHumanLimb(shoulder, hand, u * 0.040f, u * 0.026f, isActiveMuscle = showMuscleGlow, contraction = progress)
                }

                ExerciseAnimType.TOWEL_LAT_PULLDOWN -> {
                    // Front-Facing Athlete Holding Taut 3D Towel Wide Overhead & Pulling Down to Upper Chest
                    val hipCenter = Offset(w * 0.50f, floorY - (h * 0.36f))
                    val shoulderCenter = Offset(w * 0.50f, floorY - (h * 0.62f))
                    val headCenter = Offset(w * 0.50f, shoulderCenter.y - u * 0.095f)

                    val leftShoulder = Offset(w * 0.37f, shoulderCenter.y)
                    val rightShoulder = Offset(w * 0.63f, shoulderCenter.y)

                    // Towel bar drops from overhead (progress=0) to collarbone level (progress=1)
                    val towelY = (shoulderCenter.y - h * 0.20f) + progress * (h * 0.22f)
                    val leftHand = Offset(w * 0.24f, towelY)
                    val rightHand = Offset(w * 0.76f, towelY)

                    // Elbows drive down and inward toward ribs during pulldown
                    val leftElbow = Offset(
                        w * 0.26f + progress * (w * 0.06f),
                        shoulderCenter.y - h * 0.06f + progress * (h * 0.16f)
                    )
                    val rightElbow = Offset(
                        w * 0.74f - progress * (w * 0.06f),
                        shoulderCenter.y - h * 0.06f + progress * (h * 0.16f)
                    )

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.44f, progress)

                    // Athletic Stance Legs
                    drawHumanLimb(Offset(hipCenter.x - u * 0.06f, hipCenter.y), Offset(w * 0.41f, floorY - u * 0.01f), u * 0.062f, u * 0.032f, isClothed = true)
                    drawHumanLimb(Offset(hipCenter.x + u * 0.06f, hipCenter.y), Offset(w * 0.59f, floorY - u * 0.01f), u * 0.062f, u * 0.032f, isClothed = true)
                    drawAthleticShoe(Offset(w * 0.41f, floorY - u * 0.01f), u * 0.055f, facingRight = false)
                    drawAthleticShoe(Offset(w * 0.59f, floorY - u * 0.01f), u * 0.055f, facingRight = true)

                    // V-Taper Torso with Glowing Lats Wing Expansion
                    drawHumanFrontTorso(
                        shoulderCenter = shoulderCenter,
                        hipCenter = hipCenter,
                        shoulderHalfW = u * 0.145f + progress * u * 0.02f,
                        waistHalfW = u * 0.095f,
                        showMuscleGlow = showMuscleGlow,
                        coreActivation = 0.5f,
                        chestActivation = 0.4f + progress * 0.6f
                    )
                    drawHumanHeadAndNeck(shoulderCenter, headCenter, u * 0.056f, facingRight = null)

                    // Arms Pulling Down
                    drawHumanLimb(leftShoulder, leftElbow, u * 0.045f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(leftElbow, leftHand, u * 0.034f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(rightShoulder, rightElbow, u * 0.045f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(rightElbow, rightHand, u * 0.034f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = progress)

                    // Taut 3D Horizontal Towel Across Hands
                    draw3DTowelStrap(leftHand, rightHand, progress)
                }

                ExerciseAnimType.REVERSE_SNOW_ANGELS -> {
                    // Angled Top-Back View of Athlete Lying Prone Sweeping Arms in 180-Degree Arcs
                    val hipCenter = Offset(w * 0.50f, floorY - (h * 0.25f))
                    val shoulderCenter = Offset(w * 0.50f, floorY - (h * 0.52f))
                    val headCenter = Offset(w * 0.50f, shoulderCenter.y - u * 0.085f)

                    val leftShoulder = Offset(w * 0.37f, shoulderCenter.y)
                    val rightShoulder = Offset(w * 0.63f, shoulderCenter.y)

                    // Sweep angle from down by hips (progress=0) to overhead Y-shape (progress=1)
                    val sweepRad = (0.35f + progress * 2.25f)
                    val armLen = u * 0.24f
                    val leftHand = Offset(
                        leftShoulder.x - sin(sweepRad) * armLen,
                        leftShoulder.y + cos(sweepRad) * armLen
                    )
                    val rightHand = Offset(
                        rightShoulder.x + sin(sweepRad) * armLen,
                        rightShoulder.y + cos(sweepRad) * armLen
                    )

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.58f, progress)

                    // Snow Angel Wing Arc Trails
                    drawArc(
                        color = tintColor.copy(alpha = 0.32f),
                        startAngle = 100f,
                        sweepAngle = 150f,
                        useCenter = false,
                        topLeft = Offset(leftShoulder.x - armLen, leftShoulder.y - armLen),
                        size = Size(armLen * 2f, armLen * 2f),
                        style = Stroke(width = 2.dp.toPx(), cap = StrokeCap.Round)
                    )
                    drawArc(
                        color = tintColor.copy(alpha = 0.32f),
                        startAngle = -70f,
                        sweepAngle = 150f,
                        useCenter = false,
                        topLeft = Offset(rightShoulder.x - armLen, rightShoulder.y - armLen),
                        size = Size(armLen * 2f, armLen * 2f),
                        style = Stroke(width = 2.dp.toPx(), cap = StrokeCap.Round)
                    )

                    // Prone Legs
                    drawHumanLimb(Offset(hipCenter.x - u * 0.05f, hipCenter.y), Offset(w * 0.43f, floorY - u * 0.02f), u * 0.056f, u * 0.032f, isClothed = true)
                    drawHumanLimb(Offset(hipCenter.x + u * 0.05f, hipCenter.y), Offset(w * 0.57f, floorY - u * 0.02f), u * 0.056f, u * 0.032f, isClothed = true)

                    drawHumanFrontTorso(
                        shoulderCenter = shoulderCenter,
                        hipCenter = hipCenter,
                        shoulderHalfW = u * 0.145f,
                        waistHalfW = u * 0.095f,
                        showMuscleGlow = showMuscleGlow,
                        coreActivation = 0.6f,
                        chestActivation = 0.4f + progress * 0.6f
                    )
                    drawHumanHeadAndNeck(shoulderCenter, headCenter, u * 0.055f, facingRight = null)

                    // Sweeping Arms
                    drawHumanLimb(leftShoulder, leftHand, u * 0.042f, u * 0.026f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(rightShoulder, rightHand, u * 0.042f, u * 0.026f, isActiveMuscle = showMuscleGlow, contraction = progress)
                }

                // =========================================================================
                // 6. CARDIO & STRETCH EXERCISES (6 DISTINCT ANIMATIONS)
                // =========================================================================
                ExerciseAnimType.JUMPING_JACKS -> {
                    val jumpLift = progress * (h * 0.07f)
                    val hipCenter = Offset(w * 0.50f, floorY - (h * 0.39f) - jumpLift)
                    val shoulderCenter = Offset(w * 0.50f, hipCenter.y - (h * 0.23f))
                    val headCenter = Offset(w * 0.50f, shoulderCenter.y - u * 0.095f)

                    val legSpread = u * 0.05f + (progress * w * 0.16f)
                    val leftKnee = Offset(w * 0.50f - legSpread * 0.65f, floorY - (h * 0.20f) - jumpLift * 0.5f)
                    val rightKnee = Offset(w * 0.50f + legSpread * 0.65f, floorY - (h * 0.20f) - jumpLift * 0.5f)
                    val leftFoot = Offset(w * 0.50f - legSpread, floorY - u * 0.01f - jumpLift * 0.4f)
                    val rightFoot = Offset(w * 0.50f + legSpread, floorY - u * 0.01f - jumpLift * 0.4f)

                    val armAngle = (0.25f + progress * 2.35f)
                    val upperArmLen = u * 0.13f
                    val forearmLen = u * 0.12f
                    val leftShoulder = Offset(shoulderCenter.x - u * 0.12f, shoulderCenter.y)
                    val rightShoulder = Offset(shoulderCenter.x + u * 0.12f, shoulderCenter.y)

                    val leftElbow = Offset(leftShoulder.x - sin(armAngle) * upperArmLen, leftShoulder.y - cos(armAngle) * upperArmLen)
                    val rightElbow = Offset(rightShoulder.x + sin(armAngle) * upperArmLen, rightShoulder.y - cos(armAngle) * upperArmLen)
                    val leftHand = Offset(leftElbow.x - sin(armAngle + 0.2f) * forearmLen, leftElbow.y - cos(armAngle + 0.2f) * forearmLen)
                    val rightHand = Offset(rightElbow.x + sin(armAngle + 0.2f) * forearmLen, rightElbow.y - cos(armAngle + 0.2f) * forearmLen)

                    drawFloorContactShadow(w * 0.50f, floorY, w * (0.48f - progress * 0.12f), progress)

                    drawHumanFrontTorso(
                        shoulderCenter = shoulderCenter,
                        hipCenter = hipCenter,
                        shoulderHalfW = u * 0.135f,
                        waistHalfW = u * 0.095f,
                        showMuscleGlow = showMuscleGlow,
                        coreActivation = progress,
                        chestActivation = progress * 0.8f
                    )
                    drawHumanHeadAndNeck(shoulderCenter, headCenter, u * 0.056f, facingRight = null)

                    drawHumanLimb(Offset(hipCenter.x - u * 0.06f, hipCenter.y), leftKnee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(leftKnee, leftFoot, u * 0.042f, u * 0.028f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(Offset(hipCenter.x + u * 0.06f, hipCenter.y), rightKnee, u * 0.062f, u * 0.042f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(rightKnee, rightFoot, u * 0.042f, u * 0.028f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawAthleticShoe(leftFoot, u * 0.056f, facingRight = false)
                    drawAthleticShoe(rightFoot, u * 0.056f, facingRight = true)

                    drawHumanLimb(leftShoulder, leftElbow, u * 0.042f, u * 0.032f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(leftElbow, leftHand, u * 0.032f, u * 0.022f)
                    drawHumanLimb(rightShoulder, rightElbow, u * 0.042f, u * 0.032f, isActiveMuscle = showMuscleGlow, contraction = progress)
                    drawHumanLimb(rightElbow, rightHand, u * 0.032f, u * 0.022f)
                }

                ExerciseAnimType.BURPEES -> {
                    // 4-Phase Full-Body Sequence Driven by progress:
                    // progress 0.0 -> Explosive Jump Overhead
                    // progress 0.5 -> Squat Thrust
                    // progress 1.0 -> Full Plank Push-Up on Floor
                    val jumpFactor = (1f - progress * 2f).coerceIn(0f, 1f)
                    val plankFactor = ((progress - 0.35f) / 0.65f).coerceIn(0f, 1f)

                    val ankle = Offsets.lerp(
                        Offset(w * 0.48f, floorY - u * 0.01f - jumpFactor * h * 0.09f),
                        Offset(w * 0.16f, floorY - u * 0.02f),
                        plankFactor
                    )
                    val knee = Offsets.lerp(
                        Offset(w * 0.52f, floorY - h * 0.24f - jumpFactor * h * 0.08f),
                        Offset(w * 0.33f, floorY - h * 0.14f),
                        plankFactor
                    )
                    val hip = Offsets.lerp(
                        Offset(w * 0.46f, floorY - h * 0.44f - jumpFactor * h * 0.08f),
                        Offset(w * 0.49f, floorY - h * 0.24f),
                        plankFactor
                    )
                    val shoulder = Offsets.lerp(
                        Offset(w * 0.48f, hip.y - h * 0.22f),
                        Offset(w * 0.72f, floorY - h * 0.30f),
                        plankFactor
                    )
                    val head = Offset(
                        shoulder.x + u * 0.02f + plankFactor * u * 0.07f,
                        shoulder.y - u * 0.085f + plankFactor * u * 0.06f
                    )
                    val hand = Offsets.lerp(
                        Offset(shoulder.x + u * 0.04f, shoulder.y - h * 0.18f * jumpFactor + (1f - jumpFactor) * h * 0.15f),
                        Offset(w * 0.73f, floorY - u * 0.01f),
                        plankFactor
                    )
                    val elbow = Offsets.lerp(shoulder, hand, 0.52f)

                    drawFloorContactShadow(w * 0.50f, floorY, w * (0.42f + plankFactor * 0.22f), progress)

                    drawHumanSideTorso(shoulder, hip, u * 0.104f, u * 0.084f, showMuscleGlow, chestGlow = 0.85f, coreGlow = 0.90f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    drawHumanLimb(hip, knee, u * 0.066f, u * 0.044f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = 0.85f)
                    drawHumanLimb(knee, ankle, u * 0.042f, u * 0.028f, isActiveMuscle = showMuscleGlow, contraction = 0.75f)
                    drawAthleticShoe(ankle, u * 0.060f, facingRight = plankFactor < 0.5f)

                    drawHumanLimb(shoulder, elbow, u * 0.044f, u * 0.032f, isActiveMuscle = showMuscleGlow, contraction = 0.85f)
                    drawHumanLimb(elbow, hand, u * 0.033f, u * 0.024f, isActiveMuscle = showMuscleGlow, contraction = 0.85f)
                }

                ExerciseAnimType.HIGH_KNEES -> {
                    val phaseAngle = (cycle * 2f * PI).toFloat()
                    val rightLift = (sin(phaseAngle) + 1f) * 0.5f
                    val leftLift = 1f - rightLift

                    val hip = Offset(w * 0.47f, floorY - (h * 0.43f))
                    val shoulder = Offset(w * 0.48f, hip.y - (h * 0.23f))
                    val head = Offset(w * 0.49f, shoulder.y - u * 0.095f)

                    val leftKnee = Offsets.lerp(
                        Offset(w * 0.46f, floorY - h * 0.22f),
                        Offset(w * 0.65f, hip.y - u * 0.04f),
                        leftLift
                    )
                    val leftAnkle = Offsets.lerp(
                        Offset(w * 0.44f, floorY - u * 0.01f),
                        Offset(w * 0.58f, hip.y + h * 0.17f),
                        leftLift
                    )

                    val rightKnee = Offsets.lerp(
                        Offset(w * 0.46f, floorY - h * 0.22f),
                        Offset(w * 0.65f, hip.y - u * 0.04f),
                        rightLift
                    )
                    val rightAnkle = Offsets.lerp(
                        Offset(w * 0.44f, floorY - u * 0.01f),
                        Offset(w * 0.58f, hip.y + h * 0.17f),
                        rightLift
                    )

                    val armSwing = (rightLift - 0.5f) * (w * 0.18f)
                    val elbow = Offset(shoulder.x - armSwing * 0.6f, shoulder.y + h * 0.11f)
                    val hand = Offset(elbow.x + u * 0.09f + armSwing * 0.5f, elbow.y - h * 0.05f)

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.38f, progress)

                    // Back Leg
                    drawHumanLimb(hip, leftKnee, u * 0.060f, u * 0.040f, isBackLayer = true)
                    drawHumanLimb(leftKnee, leftAnkle, u * 0.040f, u * 0.026f, isBackLayer = true)
                    drawAthleticShoe(leftAnkle, u * 0.058f, facingRight = true)

                    drawHumanSideTorso(shoulder, hip, u * 0.104f, u * 0.084f, showMuscleGlow, chestGlow = 0.4f, coreGlow = 0.85f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.056f, facingRight = true)

                    // Front High-Driving Knee
                    drawHumanLimb(hip, rightKnee, u * 0.066f, u * 0.044f, isClothed = true, isActiveMuscle = showMuscleGlow, contraction = rightLift)
                    drawHumanLimb(rightKnee, rightAnkle, u * 0.042f, u * 0.028f)
                    drawAthleticShoe(rightAnkle, u * 0.060f, facingRight = true)

                    drawHumanLimb(shoulder, elbow, u * 0.042f, u * 0.032f, isActiveMuscle = showMuscleGlow, contraction = 0.7f)
                    drawHumanLimb(elbow, hand, u * 0.032f, u * 0.022f)
                }

                ExerciseAnimType.ARM_CIRCLES -> {
                    // Front-Facing Athlete Tracing 360-Degree 3D Orbital Arm Circles
                    val orbitAngle = (cycle * 2f * PI).toFloat()
                    val hipCenter = Offset(w * 0.50f, floorY - (h * 0.39f))
                    val shoulderCenter = Offset(w * 0.50f, hipCenter.y - (h * 0.23f))
                    val headCenter = Offset(w * 0.50f, shoulderCenter.y - u * 0.095f)

                    val leftShoulder = Offset(w * 0.37f, shoulderCenter.y)
                    val rightShoulder = Offset(w * 0.63f, shoulderCenter.y)

                    val orbitR = u * 0.085f
                    val leftCircleCenter = Offset(w * 0.16f, shoulderCenter.y)
                    val rightCircleCenter = Offset(w * 0.84f, shoulderCenter.y)

                    val leftHand = Offset(
                        leftCircleCenter.x + cos(orbitAngle) * orbitR * 0.65f,
                        leftCircleCenter.y + sin(orbitAngle) * orbitR
                    )
                    val rightHand = Offset(
                        rightCircleCenter.x - cos(orbitAngle) * orbitR * 0.65f,
                        rightCircleCenter.y + sin(orbitAngle) * orbitR
                    )
                    val leftElbow = Offsets.lerp(leftShoulder, leftHand, 0.52f)
                    val rightElbow = Offsets.lerp(rightShoulder, rightHand, 0.52f)

                    drawFloorContactShadow(w * 0.50f, floorY, w * 0.42f, progress)

                    // 3D Orbital Ring Guides at Each Hand
                    drawCircle(
                        color = tintColor.copy(alpha = 0.35f),
                        radius = orbitR,
                        center = leftCircleCenter,
                        style = Stroke(width = 1.8.dp.toPx())
                    )
                    drawCircle(
                        color = tintColor.copy(alpha = 0.35f),
                        radius = orbitR,
                        center = rightCircleCenter,
                        style = Stroke(width = 1.8.dp.toPx())
                    )

                    // Legs
                    drawHumanLimb(Offset(hipCenter.x - u * 0.06f, hipCenter.y), Offset(w * 0.42f, floorY - u * 0.01f), u * 0.062f, u * 0.032f, isClothed = true)
                    drawHumanLimb(Offset(hipCenter.x + u * 0.06f, hipCenter.y), Offset(w * 0.58f, floorY - u * 0.01f), u * 0.062f, u * 0.032f, isClothed = true)
                    drawAthleticShoe(Offset(w * 0.42f, floorY - u * 0.01f), u * 0.055f, facingRight = false)
                    drawAthleticShoe(Offset(w * 0.58f, floorY - u * 0.01f), u * 0.055f, facingRight = true)

                    drawHumanFrontTorso(
                        shoulderCenter = shoulderCenter,
                        hipCenter = hipCenter,
                        shoulderHalfW = u * 0.140f,
                        waistHalfW = u * 0.095f,
                        showMuscleGlow = showMuscleGlow,
                        coreActivation = 0.45f,
                        chestActivation = 0.6f
                    )
                    drawHumanHeadAndNeck(shoulderCenter, headCenter, u * 0.056f, facingRight = null)

                    // Extended Rotating Deltoid Arms
                    drawHumanLimb(leftShoulder, leftElbow, u * 0.044f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = 0.85f)
                    drawHumanLimb(leftElbow, leftHand, u * 0.032f, u * 0.022f, isActiveMuscle = showMuscleGlow, contraction = 0.6f)
                    drawHumanLimb(rightShoulder, rightElbow, u * 0.044f, u * 0.034f, isActiveMuscle = showMuscleGlow, contraction = 0.85f)
                    drawHumanLimb(rightElbow, rightHand, u * 0.032f, u * 0.022f, isActiveMuscle = showMuscleGlow, contraction = 0.6f)
                }

                ExerciseAnimType.COBRA_STRETCH -> {
                    // Yoga Bhujangasana: Pelvis & Legs Grounded on Mat, Chest & Head Arching Gracefully Upward
                    val arch = progress * (h * 0.18f)
                    val ankle = Offset(w * 0.16f, floorY - u * 0.02f)
                    val knee = Offset(w * 0.32f, floorY - u * 0.025f)
                    val hip = Offset(w * 0.49f, floorY - u * 0.035f)
                    val shoulder = Offset(w * 0.69f, floorY - (h * 0.14f) - arch)
                    val head = Offset(w * 0.74f, shoulder.y - u * 0.085f - progress * u * 0.02f)
                    val hand = Offset(w * 0.70f, floorY - u * 0.01f)
                    val elbow = Offset(w * 0.66f, (shoulder.y + hand.y) * 0.54f)

                    drawFloorContactShadow(w * 0.48f, floorY, w * 0.64f, progress)

                    drawHumanLimb(hip, knee, u * 0.060f, u * 0.042f, isClothed = true)
                    drawHumanLimb(knee, ankle, u * 0.040f, u * 0.026f)
                    drawAthleticShoe(ankle, u * 0.056f, facingRight = false, plantarFlex = 0.7f)

                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.080f, showMuscleGlow, chestGlow = progress, coreGlow = 0.4f + progress * 0.6f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.055f, facingRight = true)

                    drawHumanLimb(shoulder, elbow, u * 0.042f, u * 0.032f, isActiveMuscle = showMuscleGlow, contraction = progress * 0.7f)
                    drawHumanLimb(elbow, hand, u * 0.032f, u * 0.024f)
                    drawHumanHandOnFloor(hand, u * 0.032f, facingRight = true)
                }

                ExerciseAnimType.CHILDS_POSE -> {
                    // Yoga Balasana: Kneeling Shins on Mat, Hips Folded Onto Heels, Torso Bowed Forward & Arms Extended Long
                    val breathe = progress * (h * 0.035f)
                    val ankle = Offset(w * 0.22f, floorY - u * 0.02f)
                    val knee = Offset(w * 0.42f, floorY - u * 0.025f)
                    val hip = Offset(w * 0.27f, floorY - (h * 0.12f) - breathe * 0.4f)
                    val shoulder = Offset(w * 0.56f, floorY - (h * 0.15f) - breathe)
                    val head = Offset(w * 0.64f, floorY - u * 0.065f - breathe * 0.5f)
                    val elbow = Offset(w * 0.71f, floorY - u * 0.025f)
                    val hand = Offset(w * 0.85f, floorY - u * 0.015f)

                    drawFloorContactShadow(w * 0.52f, floorY, w * 0.68f, progress)

                    // Folded Shin & Thigh
                    drawHumanLimb(knee, ankle, u * 0.042f, u * 0.028f)
                    drawHumanLimb(hip, knee, u * 0.064f, u * 0.044f, isClothed = true)

                    // Bowed Torso with Lumbar/Lat Stretch Glow
                    drawHumanSideTorso(shoulder, hip, u * 0.102f, u * 0.084f, showMuscleGlow, chestGlow = 0.4f, coreGlow = 0.5f + progress * 0.4f)
                    drawHumanHeadAndNeck(shoulder, head, u * 0.052f, facingRight = true)

                    // Outstretched Arms on Mat
                    drawHumanLimb(shoulder, elbow, u * 0.040f, u * 0.030f, isActiveMuscle = showMuscleGlow, contraction = 0.6f)
                    drawHumanLimb(elbow, hand, u * 0.030f, u * 0.022f)
                    drawHumanHandOnFloor(hand, u * 0.032f, facingRight = true)
                }
            }

            // 3. Biomechanical Phase Tension Progress Bar along bottom of stage
            val barW = w * 0.44f
            val barX = (w - barW) * 0.5f
            val barY = floorY + (h - floorY) * 0.48f
            drawRoundRect(
                color = Color(0xFF1E293B),
                topLeft = Offset(barX, barY),
                size = Size(barW, 5.dp.toPx()),
                cornerRadius = CornerRadius(4.dp.toPx())
            )
            drawRoundRect(
                brush = Brush.horizontalGradient(
                    colors = listOf(tintColor, Color(0xFFF59E0B), Color(0xFFF43F5E))
                ),
                topLeft = Offset(barX, barY),
                size = Size(barW * progress.coerceIn(0.08f, 1f), 5.dp.toPx()),
                cornerRadius = CornerRadius(4.dp.toPx())
            )
        }

        // Interactive Overlay Controls for 3D Muscle Heat-Map & Pinch Zoom
        if (showInteractiveControls) {
            Row(
                modifier = Modifier
                    .fillMaxWidth()
                    .align(Alignment.TopCenter)
                    .padding(horizontal = 10.dp, vertical = 8.dp),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Surface(
                    shape = RoundedCornerShape(50),
                    color = if (showMuscleGlow) Color(0xFFF43F5E).copy(alpha = 0.22f) else Color(0xFF131D31).copy(alpha = 0.90f),
                    border = BorderStroke(1.dp, if (showMuscleGlow) Color(0xFFF43F5E) else Color(0xFF26354D)),
                    modifier = Modifier.clickable { showMuscleGlow = !showMuscleGlow }
                ) {
                    Text(
                        text = if (isBengali) {
                            if (showMuscleGlow) "3D মাসল হিটম্যাপ: চালু" else "3D মাসল দেখুন"
                        } else {
                            if (showMuscleGlow) "3D Muscle Heatmap: ON" else "3D Muscle View"
                        },
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontSize = 10.sp,
                            fontWeight = FontWeight.ExtraBold
                        ),
                        color = if (showMuscleGlow) Color(0xFFFF8A80) else Color.White,
                        maxLines = 1,
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                    )
                }

                Spacer(modifier = Modifier.width(6.dp))

                Surface(
                    shape = RoundedCornerShape(50),
                    color = if (zoomScale > 1.05f) tintColor.copy(alpha = 0.24f) else Color(0xFF131D31).copy(alpha = 0.90f),
                    border = BorderStroke(1.dp, if (zoomScale > 1.05f) tintColor else Color(0xFF26354D)),
                    modifier = Modifier.clickable {
                        zoomScale = when {
                            zoomScale < 1.3f -> 1.65f
                            zoomScale < 2.0f -> 2.25f
                            else -> 1f
                        }
                        if (zoomScale == 1f) panOffset = Offset.Zero
                    }
                ) {
                    Text(
                        text = String.format(Locale.US, "3D ZOOM %.1fx", zoomScale),
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontSize = 10.sp,
                            fontWeight = FontWeight.ExtraBold
                        ),
                        color = if (zoomScale > 1.05f) tintColor else Color.White,
                        maxLines = 1,
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                    )
                }
            }

            if (showMuscleGlow) {
                Surface(
                    shape = RoundedCornerShape(10.dp),
                    color = Color(0xFF0A101D).copy(alpha = 0.92f),
                    border = BorderStroke(1.dp, Color(0xFFF59E0B).copy(alpha = 0.45f)),
                    modifier = Modifier
                        .align(Alignment.BottomCenter)
                        .padding(horizontal = 10.dp, vertical = 6.dp)
                ) {
                    Text(
                        text = getMuscleTargetLabel(animType, isBengali),
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontSize = 10.5.sp,
                            fontWeight = FontWeight.Bold
                        ),
                        color = Color(0xFFFBBF24),
                        maxLines = 1,
                        overflow = TextOverflow.Ellipsis,
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 4.dp)
                    )
                }
            }
        }
    }
}

private object Offsets {
    fun lerp(a: Offset, b: Offset, t: Float): Offset {
        val f = t.coerceIn(0f, 1f)
        return Offset(a.x + (b.x - a.x) * f, a.y + (b.y - a.y) * f)
    }
}

/**
 * Renders the 3D Dark Luxury Gym perspective floor mat, grid lines, and overhead volumetric spotlight.
 */
private fun DrawScope.draw3DStudioStage(
    w: Float,
    h: Float,
    floorY: Float,
    primaryAccent: Color,
    progress: Float
) {
    drawCircle(
        brush = Brush.radialGradient(
            colors = listOf(
                primaryAccent.copy(alpha = 0.16f + progress * 0.06f),
                Color(0xFFF59E0B).copy(alpha = 0.05f * progress),
                Color.Transparent
            ),
            center = Offset(w * 0.50f, h * 0.44f),
            radius = w * 0.54f
        ),
        radius = w * 0.54f,
        center = Offset(w * 0.50f, h * 0.44f)
    )

    for (i in 1..3) {
        val gy = h * (0.20f * i)
        drawLine(
            color = Color(0xFF1E293B).copy(alpha = 0.45f),
            start = Offset(w * 0.08f, gy),
            end = Offset(w * 0.92f, gy),
            strokeWidth = 1.dp.toPx()
        )
    }

    val matPath = Path().apply {
        moveTo(w * 0.12f, floorY - 6.dp.toPx())
        lineTo(w * 0.88f, floorY - 6.dp.toPx())
        lineTo(w * 0.95f, floorY + 12.dp.toPx())
        lineTo(w * 0.05f, floorY + 12.dp.toPx())
        close()
    }
    drawPath(
        path = matPath,
        brush = Brush.verticalGradient(
            colors = listOf(Color(0xFF1E293B), Color(0xFF0F172A))
        )
    )
    drawPath(
        path = matPath,
        color = primaryAccent.copy(alpha = 0.45f),
        style = Stroke(width = 1.5.dp.toPx())
    )
}

private fun DrawScope.drawFloorContactShadow(
    centerX: Float,
    floorY: Float,
    shadowWidth: Float,
    progress: Float
) {
    drawOval(
        brush = Brush.radialGradient(
            colors = listOf(
                Color.Black.copy(alpha = 0.55f + progress * 0.15f),
                Color.Transparent
            ),
            center = Offset(centerX, floorY + 2.dp.toPx()),
            radius = shadowWidth * 0.5f
        ),
        topLeft = Offset(centerX - shadowWidth * 0.5f, floorY - 4.dp.toPx()),
        size = Size(shadowWidth, 10.dp.toPx())
    )
}

/**
 * Renders an organic, humanistic 3D limb with warm human skin tones (or sculpted athletic shorts/leggings),
 * asymmetric anatomical muscle belly curves, and active muscle contraction heat-glow.
 */
private fun DrawScope.drawHumanLimb(
    start: Offset,
    end: Offset,
    startRadius: Float,
    endRadius: Float,
    isClothed: Boolean = false,
    isActiveMuscle: Boolean = false,
    contraction: Float = 0.5f,
    isBackLayer: Boolean = false
) {
    val dx = end.x - start.x
    val dy = end.y - start.y
    val len = hypot(dx, dy).coerceAtLeast(1f)
    val nx = -dy / len
    val ny = dx / len

    // Asymmetric human muscle belly (anterior peak is fuller than posterior)
    val anteriorPeakFactor = if (isActiveMuscle) (1.34f + 0.25f * contraction) else 1.22f
    val posteriorFactor = if (isActiveMuscle) (1.16f + 0.12f * contraction) else 1.08f
    val anteriorRadius = ((startRadius + endRadius) * 0.5f) * anteriorPeakFactor
    val posteriorRadius = ((startRadius + endRadius) * 0.5f) * posteriorFactor
    val peakX = start.x + dx * 0.44f
    val peakY = start.y + dy * 0.44f

    val limbPath = Path().apply {
        moveTo(start.x + nx * startRadius, start.y + ny * startRadius)
        quadraticTo(
            peakX + nx * anteriorRadius,
            peakY + ny * anteriorRadius,
            end.x + nx * endRadius,
            end.y + ny * endRadius
        )
        lineTo(end.x - nx * endRadius, end.y - ny * endRadius)
        quadraticTo(
            peakX - nx * posteriorRadius,
            peakY - ny * posteriorRadius,
            start.x - nx * startRadius,
            start.y - ny * startRadius
        )
        close()
    }

    if (isBackLayer) {
        val backColor = if (isClothed) Color(0xFF172033) else Color(0xFF7C4D34)
        drawPath(path = limbPath, color = backColor)
        drawCircle(color = backColor, radius = startRadius * 0.92f, center = start)
        drawCircle(color = backColor, radius = endRadius * 0.90f, center = end)
        return
    }

    val lightStart = Offset(peakX + nx * anteriorRadius, peakY + ny * anteriorRadius)
    val lightEnd = Offset(peakX - nx * posteriorRadius, peakY - ny * posteriorRadius)

    val surfaceColors = when {
        isActiveMuscle && contraction > 0.15f -> listOf(
            Color(0xFFFF9E80), // Warm highlighted skin + muscle heat
            Color(0xFFF43F5E), // Contracting crimson muscle fiber core
            Color(0xFF881337)  // Sculpted 3D shadow
        )
        isClothed -> listOf(
            Color(0xFF334155), // Athletic compression gear highlight
            Color(0xFF1E293B), // Compression midtone
            Color(0xFF0F172A)  // Deep contour shadow
        )
        else -> listOf(
            Color(0xFFE8B08D), // Warm human skin highlight
            Color(0xFFC88763), // Natural athletic skin midtone
            Color(0xFF8E5537)  // Anatomical skin shadow
        )
    }

    drawPath(
        path = limbPath,
        brush = Brush.linearGradient(
            colors = surfaceColors,
            start = lightStart,
            end = lightEnd
        )
    )

    // Smooth human joint connection (no robotic bolt circles!)
    val jointColor = when {
        isActiveMuscle && contraction > 0.15f -> Color(0xFFFB7185)
        isClothed -> Color(0xFF1E293B)
        else -> Color(0xFFC88763)
    }
    drawCircle(color = jointColor, radius = startRadius * 0.92f, center = start)
    drawCircle(
        color = if (isClothed) Color(0xFF1E293B) else Color(0xFFB97A57),
        radius = endRadius * 0.88f,
        center = end
    )

    // Subtle specular skin/muscle rim highlight
    drawPath(
        path = limbPath,
        color = if (isActiveMuscle) Color(0xFFFDA4AF).copy(alpha = 0.7f) else Color(0xFFFDE68A).copy(alpha = 0.22f),
        style = Stroke(width = 1.dp.toPx(), join = StrokeJoin.Round)
    )

    // Volumetric Muscle Contraction Glow
    if (isActiveMuscle && contraction > 0.12f) {
        drawCircle(
            brush = Brush.radialGradient(
                colors = listOf(
                    Color(0xFFFBBF24).copy(alpha = 0.42f * contraction),
                    Color(0xFFF43F5E).copy(alpha = 0.24f * contraction),
                    Color.Transparent
                ),
                center = Offset(peakX, peakY),
                radius = anteriorRadius * 1.85f
            ),
            radius = anteriorRadius * 1.85f,
            center = Offset(peakX, peakY)
        )
    }
}

/**
 * Renders a humanistic side/3-4 profile torso clad in luxury gym compression wear with sculpted
 * chest pectorals, abdominal wall, and pelvis/shorts, plus dynamic muscle heat illumination.
 */
private fun DrawScope.drawHumanSideTorso(
    shoulder: Offset,
    hip: Offset,
    chestRadius: Float,
    waistRadius: Float,
    showMuscleGlow: Boolean,
    chestGlow: Float,
    coreGlow: Float
) {
    val dx = hip.x - shoulder.x
    val dy = hip.y - shoulder.y
    val len = hypot(dx, dy).coerceAtLeast(1f)
    val nx = -dy / len
    val ny = dx / len

    val chestPeakX = shoulder.x + dx * 0.30f
    val chestPeakY = shoulder.y + dy * 0.30f
    val waistX = shoulder.x + dx * 0.68f
    val waistY = shoulder.y + dy * 0.68f

    val torsoPath = Path().apply {
        moveTo(shoulder.x + nx * chestRadius, shoulder.y + ny * chestRadius)
        // Sculpted Pectoral Curve
        quadraticTo(
            chestPeakX + nx * (chestRadius * (1.18f + chestGlow * 0.12f)),
            chestPeakY + ny * (chestRadius * (1.18f + chestGlow * 0.12f)),
            waistX + nx * (waistRadius * 0.92f),
            waistY + ny * (waistRadius * 0.92f)
        )
        lineTo(hip.x + nx * waistRadius, hip.y + ny * waistRadius)
        lineTo(hip.x - nx * waistRadius, hip.y - ny * waistRadius)
        // Sculpted Latissimus & Lumbar Curve
        quadraticTo(
            chestPeakX - nx * (chestRadius * 0.98f),
            chestPeakY - ny * (chestRadius * 0.98f),
            shoulder.x - nx * (chestRadius * 0.88f),
            shoulder.y - ny * (chestRadius * 0.88f)
        )
        close()
    }

    drawPath(
        path = torsoPath,
        brush = Brush.linearGradient(
            colors = listOf(
                Color(0xFF334155),
                Color(0xFF1E293B),
                Color(0xFF0F172A)
            ),
            start = Offset(chestPeakX + nx * chestRadius, chestPeakY + ny * chestRadius),
            end = Offset(chestPeakX - nx * chestRadius, chestPeakY - ny * chestRadius)
        )
    )

    // Athletic Pelvis / Shorts Hip Cap
    drawCircle(
        color = Color(0xFF1E293B),
        radius = waistRadius * 1.04f,
        center = hip
    )
    // Exposed Deltoid Shoulder Cap in Human Skin Tone
    drawCircle(
        brush = Brush.radialGradient(
            colors = listOf(Color(0xFFE8B08D), Color(0xFFB97A57)),
            center = shoulder,
            radius = chestRadius * 0.85f
        ),
        radius = chestRadius * 0.72f,
        center = shoulder
    )

    drawPath(
        path = torsoPath,
        color = Color(0xFF94A3B8).copy(alpha = 0.45f),
        style = Stroke(width = 1.2.dp.toPx(), join = StrokeJoin.Round)
    )

    // Pectoral Heatmap Glow
    if (showMuscleGlow && chestGlow > 0.15f) {
        val pecCenter = Offset(chestPeakX + nx * (chestRadius * 0.5f), chestPeakY + ny * (chestRadius * 0.5f))
        drawCircle(
            brush = Brush.radialGradient(
                colors = listOf(
                    Color(0xFFF43F5E).copy(alpha = 0.65f * chestGlow),
                    Color(0xFFF59E0B).copy(alpha = 0.30f * chestGlow),
                    Color.Transparent
                ),
                center = pecCenter,
                radius = chestRadius * 1.4f
            ),
            radius = chestRadius * 1.4f,
            center = pecCenter
        )
    }

    // Abdominal Core Heatmap Glow
    if (showMuscleGlow && coreGlow > 0.15f) {
        val absCenter = Offset(waistX + nx * (waistRadius * 0.45f), waistY + ny * (waistRadius * 0.45f))
        drawCircle(
            brush = Brush.radialGradient(
                colors = listOf(
                    Color(0xFFF59E0B).copy(alpha = 0.62f * coreGlow),
                    Color(0xFF10B981).copy(alpha = 0.25f * coreGlow),
                    Color.Transparent
                ),
                center = absCenter,
                radius = waistRadius * 1.45f
            ),
            radius = waistRadius * 1.45f,
            center = absCenter
        )
    }
}

/**
 * Renders a humanistic front-facing V-taper torso with warm skin neck/shoulders, pectoral plates,
 * and 6-pack abdominal musculature.
 */
private fun DrawScope.drawHumanFrontTorso(
    shoulderCenter: Offset,
    hipCenter: Offset,
    shoulderHalfW: Float,
    waistHalfW: Float,
    showMuscleGlow: Boolean,
    coreActivation: Float,
    chestActivation: Float
) {
    val torsoPath = Path().apply {
        moveTo(shoulderCenter.x - shoulderHalfW, shoulderCenter.y)
        lineTo(shoulderCenter.x + shoulderHalfW, shoulderCenter.y)
        lineTo(hipCenter.x + waistHalfW, hipCenter.y)
        lineTo(hipCenter.x - waistHalfW, hipCenter.y)
        close()
    }
    drawPath(
        path = torsoPath,
        brush = Brush.horizontalGradient(
            colors = listOf(
                Color(0xFF0F172A),
                Color(0xFF334155),
                Color(0xFF0F172A)
            ),
            startX = shoulderCenter.x - shoulderHalfW,
            endX = shoulderCenter.x + shoulderHalfW
        )
    )
    drawPath(
        path = torsoPath,
        color = Color(0xFF94A3B8).copy(alpha = 0.45f),
        style = Stroke(width = 1.2.dp.toPx())
    )

    val torsoH = (hipCenter.y - shoulderCenter.y).coerceAtLeast(10f)
    val pecColor = if (showMuscleGlow) Color(0xFFF43F5E).copy(alpha = 0.42f + chestActivation * 0.40f) else Color(0xFF334155)
    drawRoundRect(
        color = pecColor,
        topLeft = Offset(shoulderCenter.x - shoulderHalfW * 0.80f, shoulderCenter.y + torsoH * 0.08f),
        size = Size(shoulderHalfW * 0.72f, torsoH * 0.28f),
        cornerRadius = CornerRadius(6.dp.toPx())
    )
    drawRoundRect(
        color = pecColor,
        topLeft = Offset(shoulderCenter.x + shoulderHalfW * 0.08f, shoulderCenter.y + torsoH * 0.08f),
        size = Size(shoulderHalfW * 0.72f, torsoH * 0.28f),
        cornerRadius = CornerRadius(6.dp.toPx())
    )

    val absColor = if (showMuscleGlow) Color(0xFFF59E0B).copy(alpha = 0.40f + coreActivation * 0.42f) else Color(0xFF334155)
    for (row in 0..2) {
        val segY = shoulderCenter.y + torsoH * (0.42f + row * 0.16f)
        val segW = waistHalfW * 0.54f
        val segH = torsoH * 0.12f
        drawRoundRect(
            color = absColor,
            topLeft = Offset(shoulderCenter.x - segW - 2.dp.toPx(), segY),
            size = Size(segW, segH),
            cornerRadius = CornerRadius(3.dp.toPx())
        )
        drawRoundRect(
            color = absColor,
            topLeft = Offset(shoulderCenter.x + 2.dp.toPx(), segY),
            size = Size(segW, segH),
            cornerRadius = CornerRadius(3.dp.toPx())
        )
    }
}

/**
 * Renders a realistic human head, jawline, muscular neck bridge, and sculpted dark athletic hair
 * (completely eliminating any robotic circle/visor look).
 */
private fun DrawScope.drawHumanHeadAndNeck(
    shoulder: Offset,
    headCenter: Offset,
    headRadius: Float,
    facingRight: Boolean?
) {
    // 1. Muscular Human Neck connecting shoulder to head base
    drawLine(
        color = Color(0xFFC07F5B),
        start = shoulder,
        end = headCenter,
        strokeWidth = headRadius * 0.92f,
        cap = StrokeCap.Round
    )

    // 2. Sculpted Human Cranium & Jawline in 3D Warm Skin Tone
    drawOval(
        brush = Brush.radialGradient(
            colors = listOf(
                Color(0xFFEBC9B2),
                Color(0xFFD2936F),
                Color(0xFF9A5F3F)
            ),
            center = Offset(headCenter.x - headRadius * 0.2f, headCenter.y - headRadius * 0.2f),
            radius = headRadius * 1.4f
        ),
        topLeft = Offset(headCenter.x - headRadius * 0.92f, headCenter.y - headRadius * 1.05f),
        size = Size(headRadius * 1.84f, headRadius * 2.10f)
    )

    // 3. Sculpted Dark Espresso Athletic Haircut Cap (No robot visor!)
    val hairPath = Path().apply {
        when (facingRight) {
            true -> {
                moveTo(headCenter.x - headRadius * 0.95f, headCenter.y + headRadius * 0.15f)
                quadraticTo(
                    headCenter.x - headRadius * 1.05f,
                    headCenter.y - headRadius * 1.15f,
                    headCenter.x + headRadius * 0.15f,
                    headCenter.y - headRadius * 1.12f
                )
                quadraticTo(
                    headCenter.x + headRadius * 0.95f,
                    headCenter.y - headRadius * 1.05f,
                    headCenter.x + headRadius * 0.78f,
                    headCenter.y - headRadius * 0.38f
                )
                quadraticTo(
                    headCenter.x - headRadius * 0.10f,
                    headCenter.y - headRadius * 0.55f,
                    headCenter.x - headRadius * 0.95f,
                    headCenter.y + headRadius * 0.15f
                )
            }
            false -> {
                moveTo(headCenter.x + headRadius * 0.95f, headCenter.y + headRadius * 0.15f)
                quadraticTo(
                    headCenter.x + headRadius * 1.05f,
                    headCenter.y - headRadius * 1.15f,
                    headCenter.x - headRadius * 0.15f,
                    headCenter.y - headRadius * 1.12f
                )
                quadraticTo(
                    headCenter.x - headRadius * 0.95f,
                    headCenter.y - headRadius * 1.05f,
                    headCenter.x - headRadius * 0.78f,
                    headCenter.y - headRadius * 0.38f
                )
                close()
            }
            null -> {
                moveTo(headCenter.x - headRadius * 0.92f, headCenter.y - headRadius * 0.25f)
                quadraticTo(
                    headCenter.x,
                    headCenter.y - headRadius * 1.30f,
                    headCenter.x + headRadius * 0.92f,
                    headCenter.y - headRadius * 0.25f
                )
                quadraticTo(
                    headCenter.x,
                    headCenter.y - headRadius * 0.65f,
                    headCenter.x - headRadius * 0.92f,
                    headCenter.y - headRadius * 0.25f
                )
            }
        }
        close()
    }
    drawPath(
        path = hairPath,
        brush = Brush.verticalGradient(
            colors = listOf(Color(0xFF27272A), Color(0xFF09090B))
        )
    )
}

/**
 * Renders a sculpted 3D athletic sneaker with white/emerald cushioned sole and dark upper mesh.
 */
private fun DrawScope.drawAthleticShoe(
    ankle: Offset,
    length: Float,
    facingRight: Boolean,
    plantarFlex: Float = 0f
) {
    val dir = if (facingRight) 1f else -1f
    val toeX = ankle.x + dir * length
    val toeY = ankle.y + plantarFlex * (length * 0.35f)

    // Upper Shoe Body
    val shoePath = Path().apply {
        moveTo(ankle.x - dir * (length * 0.22f), ankle.y - length * 0.18f)
        lineTo(ankle.x + dir * (length * 0.25f), ankle.y - length * 0.18f)
        lineTo(toeX, toeY)
        lineTo(ankle.x - dir * (length * 0.25f), toeY)
        close()
    }
    drawPath(shoePath, color = Color(0xFF1E293B))

    // Cushioned White/Emerald Athletic Sole
    drawLine(
        color = Color(0xFFF8FAFC),
        start = Offset(ankle.x - dir * (length * 0.24f), toeY),
        end = Offset(toeX, toeY),
        strokeWidth = 3.5.dp.toPx(),
        cap = StrokeCap.Round
    )
}

private fun DrawScope.drawHumanHandOnFloor(
    hand: Offset,
    length: Float,
    facingRight: Boolean
) {
    val dir = if (facingRight) 1f else -1f
    drawLine(
        color = Color(0xFFD99B78),
        start = Offset(hand.x - dir * length * 0.3f, hand.y),
        end = Offset(hand.x + dir * length, hand.y),
        strokeWidth = 4.5.dp.toPx(),
        cap = StrokeCap.Round
    )
}

/**
 * Renders a realistic 3D Studio Chair Prop with seat cushion, backrest, and legs.
 */
private fun DrawScope.draw3DStudioChair(
    leftX: Float,
    seatY: Float,
    width: Float,
    floorY: Float,
    facingLeft: Boolean
) {
    val rightX = leftX + width
    val backrestX = if (facingLeft) rightX - width * 0.18f else leftX
    val backrestTop = seatY - (floorY - seatY) * 0.85f

    // Backrest
    drawRoundRect(
        brush = Brush.verticalGradient(listOf(Color(0xFF475569), Color(0xFF1E293B))),
        topLeft = Offset(backrestX, backrestTop),
        size = Size(width * 0.18f, seatY - backrestTop),
        cornerRadius = CornerRadius(6.dp.toPx())
    )
    // Seat Cushion
    drawRoundRect(
        brush = Brush.horizontalGradient(listOf(Color(0xFF334155), Color(0xFF475569))),
        topLeft = Offset(leftX, seatY - 6.dp.toPx()),
        size = Size(width, 12.dp.toPx()),
        cornerRadius = CornerRadius(6.dp.toPx())
    )
    drawRoundRect(
        color = Color(0xFF38BDF8).copy(alpha = 0.6f),
        topLeft = Offset(leftX, seatY - 6.dp.toPx()),
        size = Size(width, 12.dp.toPx()),
        cornerRadius = CornerRadius(6.dp.toPx()),
        style = Stroke(width = 1.2.dp.toPx())
    )
    // Chair Legs
    drawLine(
        color = Color(0xFF64748B),
        start = Offset(leftX + width * 0.12f, seatY + 4.dp.toPx()),
        end = Offset(leftX + width * 0.08f, floorY),
        strokeWidth = 4.dp.toPx(),
        cap = StrokeCap.Round
    )
    drawLine(
        color = Color(0xFF64748B),
        start = Offset(rightX - width * 0.12f, seatY + 4.dp.toPx()),
        end = Offset(rightX - width * 0.08f, floorY),
        strokeWidth = 4.dp.toPx(),
        cap = StrokeCap.Round
    )
}

/**
 * Renders a taut 3D woven fitness towel strap between two anchor points (e.g., foot to hands or hand to hand).
 */
private fun DrawScope.draw3DTowelStrap(
    anchorA: Offset,
    anchorB: Offset,
    tension: Float
) {
    drawLine(
        color = Color(0xFF38BDF8).copy(alpha = 0.35f + tension * 0.35f),
        start = anchorA,
        end = anchorB,
        strokeWidth = 8.dp.toPx(),
        cap = StrokeCap.Round
    )
    drawLine(
        color = Color(0xFFE0F2FE),
        start = anchorA,
        end = anchorB,
        strokeWidth = 4.dp.toPx(),
        cap = StrokeCap.Round
    )
}

/**
 * Renders a 3D Aqua Water Bottle / Dumbbell Prop in the athlete's hand for Floor Chest Press.
 */
private fun DrawScope.draw3DWaterBottleProp(
    handCenter: Offset,
    length: Float
) {
    val halfL = length * 0.5f
    val bottleH = length * 0.38f
    drawRoundRect(
        brush = Brush.verticalGradient(
            colors = listOf(Color(0xFF7DD3FC), Color(0xFF0284C7), Color(0xFF0369A1))
        ),
        topLeft = Offset(handCenter.x - halfL, handCenter.y - bottleH * 0.5f),
        size = Size(length, bottleH),
        cornerRadius = CornerRadius(6.dp.toPx())
    )
    drawRoundRect(
        color = Color(0xFFE0F2FE),
        topLeft = Offset(handCenter.x - halfL, handCenter.y - bottleH * 0.5f),
        size = Size(length, bottleH),
        cornerRadius = CornerRadius(6.dp.toPx()),
        style = Stroke(width = 1.2.dp.toPx())
    )
    // Bottle cap highlight
    drawCircle(
        color = Color(0xFF34D399),
        radius = bottleH * 0.32f,
        center = Offset(handCenter.x + halfL + 2.dp.toPx(), handCenter.y)
    )
}
```

---

## FILE: `app/src/main/java/com/example/ui/components/charts/AnalyticsCharts.kt`

```kotlin
package com.example.ui.components.charts

import androidx.compose.foundation.Canvas
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.geometry.Offset
import androidx.compose.ui.graphics.Brush
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.Path
import androidx.compose.ui.graphics.StrokeCap
import androidx.compose.ui.graphics.drawscope.Stroke
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.Language
import com.example.data.local.entity.WaterLogEntity
import com.example.data.local.entity.WeightLogEntity
import java.text.SimpleDateFormat
import java.util.Calendar
import java.util.Date
import java.util.Locale

@Composable
fun WeightTrendChart(
    weightLogs: List<WeightLogEntity>,
    selectedLanguage: Language,
    modifier: Modifier = Modifier
) {
    if (weightLogs.isEmpty()) {
        Surface(
            shape = RoundedCornerShape(16.dp),
            color = MaterialTheme.colorScheme.surface,
            modifier = modifier.fillMaxWidth()
        ) {
            Box(modifier = Modifier.padding(24.dp), contentAlignment = Alignment.Center) {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "এখনো কোনো ওজন লগ করা হয়নি। নিচে আপনার ওজন যোগ করুন।"
                    else "No weight logged yet. Log your weight below to view trend.",
                    style = MaterialTheme.typography.bodyMedium,
                    color = MaterialTheme.colorScheme.onSurfaceVariant,
                    textAlign = TextAlign.Center
                )
            }
        }
        return
    }

    // Sort chronologically ascending
    val sorted = weightLogs.sortedBy { it.loggedAtMillis }
    val weights = sorted.map { it.weightKg }
    val minWeight = weights.minOrNull() ?: 60f
    val maxWeight = weights.maxOrNull() ?: 70f
    val range = (maxWeight - minWeight).coerceAtLeast(2f)

    Surface(
        shape = RoundedCornerShape(16.dp),
        color = MaterialTheme.colorScheme.surface,
        modifier = modifier.fillMaxWidth()
    ) {
        Column(modifier = Modifier.padding(16.dp)) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "ওজন ট্রেন্ড চার্ট" else "Weight Trend Graph",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                    Text(
                        text = "${weights.first()} kg ➔ ${weights.last()} kg",
                        style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.SemiBold),
                        color = MaterialTheme.colorScheme.primary
                    )
                }

                val diff = weights.last() - weights.first()
                val diffColor = if (diff <= 0) MaterialTheme.colorScheme.tertiary else MaterialTheme.colorScheme.error
                Surface(
                    shape = RoundedCornerShape(8.dp),
                    color = diffColor.copy(alpha = 0.15f)
                ) {
                    Text(
                        text = (if (diff > 0) "+${String.format(Locale.US, "%.1f", diff)}" else String.format(Locale.US, "%.1f", diff)) + " kg",
                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                        color = diffColor,
                        modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp)
                    )
                }
            }

            Spacer(modifier = Modifier.height(14.dp))

            // Canvas Chart
            Box(
                modifier = Modifier
                    .fillMaxWidth()
                    .height(140.dp)
            ) {
                Canvas(modifier = Modifier.fillMaxSize()) {
                    val w = size.width
                    val h = size.height
                    val padding = 16.dp.toPx()

                    val chartWidth = w - (padding * 2)
                    val chartHeight = h - (padding * 2)

                    // Grid guide lines
                    drawLine(Color(0xFF263345), Offset(padding, padding), Offset(w - padding, padding), strokeWidth = 1.dp.toPx())
                    drawLine(Color(0xFF263345), Offset(padding, h - padding), Offset(w - padding, h - padding), strokeWidth = 1.dp.toPx())

                    val stepX = if (weights.size > 1) chartWidth / (weights.size - 1) else chartWidth

                    val points = weights.mapIndexed { idx, wt ->
                        val x = padding + (idx * stepX)
                        val normalized = (wt - minWeight) / range
                        val y = (h - padding) - (normalized * chartHeight)
                        Offset(x, y)
                    }

                    // Draw line
                    val path = Path().apply {
                        moveTo(points.first().x, points.first().y)
                        for (i in 1 until points.size) {
                            lineTo(points[i].x, points[i].y)
                        }
                    }

                    // Fill under line
                    val fillPath = Path().apply {
                        addPath(path)
                        lineTo(points.last().x, h - padding)
                        lineTo(points.first().x, h - padding)
                        close()
                    }

                    drawPath(
                        fillPath,
                        brush = Brush.verticalGradient(
                            colors = listOf(Color(0xFFFF9800).copy(alpha = 0.35f), Color(0xFFFF9800).copy(alpha = 0.0f)),
                            startY = padding,
                            endY = h - padding
                        )
                    )

                    drawPath(
                        path,
                        color = Color(0xFFFF9800),
                        style = Stroke(width = 3.dp.toPx(), cap = StrokeCap.Round)
                    )

                    // Draw point dots
                    for (p in points) {
                        drawCircle(Color.White, radius = 4.5.dp.toPx(), center = p)
                        drawCircle(Color(0xFFFF9800), radius = 3.dp.toPx(), center = p)
                    }
                }
            }

            Spacer(modifier = Modifier.height(6.dp))

            // X-axis label dates
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                val startIso = SimpleDateFormat("dd MMM", Locale.getDefault()).format(Date(sorted.first().loggedAtMillis))
                val endIso = SimpleDateFormat("dd MMM", Locale.getDefault()).format(Date(sorted.last().loggedAtMillis))
                Text(startIso, style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
                Text(endIso, style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
            }
        }
    }
}

@Composable
fun WaterIntakeBarChart(
    waterLogs: List<WaterLogEntity>,
    todayGlasses: Int,
    selectedLanguage: Language,
    modifier: Modifier = Modifier
) {
    // Collect last 7 days
    val daysData = (6 downTo 0).map { daysAgo ->
        val cal = Calendar.getInstance().apply { add(Calendar.DAY_OF_YEAR, -daysAgo) }
        val dateIso = SimpleDateFormat("yyyy-MM-dd", Locale.US).format(cal.time)
        val dayLabel = SimpleDateFormat("EEE", Locale.getDefault()).format(cal.time)
        val count = if (daysAgo == 0) todayGlasses else (waterLogs.find { it.dateIso == dateIso }?.glassesCount ?: 0)
        dayLabel to count
    }

    val totalGlasses = daysData.sumOf { it.second }
    val avgGlasses = if (daysData.isNotEmpty()) totalGlasses.toFloat() / daysData.size.toFloat() else 0f
    val goal = 8

    Surface(
        shape = RoundedCornerShape(16.dp),
        color = MaterialTheme.colorScheme.surface,
        modifier = modifier.fillMaxWidth()
    ) {
        Column(modifier = Modifier.padding(16.dp)) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "গত ৭ দিনের পানি পানের ইতিহাস" else "7-Day Water Consumption",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                    Text(
                        text = "${if (selectedLanguage == Language.BENGALI) "দৈনিক গড়:" else "Daily Avg:"} ${String.format(Locale.US, "%.1f", avgGlasses)} ${if (selectedLanguage == Language.BENGALI) "গ্লাস" else "glasses"}",
                        style = MaterialTheme.typography.bodySmall,
                        color = Color(0xFF38BDF8)
                    )
                }

                Surface(
                    shape = RoundedCornerShape(8.dp),
                    color = Color(0xFF38BDF8).copy(alpha = 0.15f)
                ) {
                    Text(
                        text = "🎯 $goal ${if (selectedLanguage == Language.BENGALI) "গ্লাস/দিন" else "gl/day"}",
                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold, color = Color(0xFF38BDF8)),
                        modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp)
                    )
                }
            }

            Spacer(modifier = Modifier.height(16.dp))

            // Bars Row
            Row(
                modifier = Modifier
                    .fillMaxWidth()
                    .height(120.dp),
                horizontalArrangement = Arrangement.SpaceEvenly,
                verticalAlignment = Alignment.Bottom
            ) {
                daysData.forEach { (label, count) ->
                    val fraction = (count.toFloat() / 10f).coerceIn(0.08f, 1f)
                    val isGoalMet = count >= goal

                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        modifier = Modifier.weight(1f)
                    ) {
                        Text(
                            text = "$count",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold, fontSize = 10.sp),
                            color = if (isGoalMet) MaterialTheme.colorScheme.tertiary else MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Spacer(modifier = Modifier.height(4.dp))
                        Box(
                            modifier = Modifier
                                .fillMaxWidth(0.55f)
                                .height((fraction * 78).dp)
                                .clip(RoundedCornerShape(topStart = 6.dp, topEnd = 6.dp))
                                .background(
                                    if (isGoalMet) MaterialTheme.colorScheme.tertiary else Color(0xFF38BDF8)
                                )
                        )
                        Spacer(modifier = Modifier.height(6.dp))
                        Text(
                            text = label.take(2),
                            style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            }
        }
    }
}

@Composable
fun StreakCalendarHeatmap(
    streakDays: Int,
    completedWorkoutDatesIso: Set<String>,
    selectedLanguage: Language,
    modifier: Modifier = Modifier
) {
    val cal = Calendar.getInstance()
    val monthName = SimpleDateFormat("MMMM yyyy", Locale.getDefault()).format(cal.time)
    val maxDays = cal.getActualMaximum(Calendar.DAY_OF_MONTH)
    val currentMonthYear = SimpleDateFormat("yyyy-MM", Locale.US).format(cal.time)
    val todayDay = cal.get(Calendar.DAY_OF_MONTH)

    Surface(
        shape = RoundedCornerShape(16.dp),
        color = MaterialTheme.colorScheme.surface,
        modifier = modifier.fillMaxWidth()
    ) {
        Column(modifier = Modifier.padding(16.dp)) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "স্ট্রিক ও ওয়ার্কআউট ক্যালেন্ডার" else "Streak & Workout Calendar",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                    Text(
                        text = monthName,
                        style = MaterialTheme.typography.bodySmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }

                Surface(
                    shape = RoundedCornerShape(10.dp),
                    color = MaterialTheme.colorScheme.primaryContainer
                ) {
                    Row(
                        modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Text("🔥", fontSize = 14.sp)
                        Spacer(modifier = Modifier.size(4.dp))
                        Text(
                            text = "$streakDays ${if (selectedLanguage == Language.BENGALI) "দিন স্ট্রিক" else "days streak"}",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.primary
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(14.dp))

            // 7x5 Days Grid
            val daysInGrid = (1..maxDays).toList()
            val rows = daysInGrid.chunked(7)

            Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                rows.forEach { week ->
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween
                    ) {
                        week.forEach { dayNum ->
                            val dateIso = String.format(Locale.US, "%s-%02d", currentMonthYear, dayNum)
                            val isCompleted = completedWorkoutDatesIso.contains(dateIso)
                            val isToday = dayNum == todayDay

                            Box(
                                modifier = Modifier
                                    .size(36.dp)
                                    .clip(CircleShape)
                                    .background(
                                        when {
                                            isCompleted -> MaterialTheme.colorScheme.primary
                                            isToday -> MaterialTheme.colorScheme.primary.copy(alpha = 0.25f)
                                            else -> MaterialTheme.colorScheme.surfaceVariant
                                        }
                                    ),
                                contentAlignment = Alignment.Center
                            ) {
                                Text(
                                    text = "$dayNum",
                                    style = MaterialTheme.typography.labelSmall.copy(
                                        fontWeight = if (isCompleted || isToday) FontWeight.Bold else FontWeight.Normal,
                                        color = if (isCompleted) Color.White else MaterialTheme.colorScheme.onSurface
                                    )
                                )
                            }
                        }
                    }
                }
            }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/diet/DietScreen.kt`

```kotlin
package com.example.ui.screens.diet

import androidx.compose.foundation.background
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.LazyRow
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Bedtime
import androidx.compose.material.icons.filled.CheckCircle
import androidx.compose.material.icons.filled.Clear
import androidx.compose.material.icons.filled.LocalDining
import androidx.compose.material.icons.filled.LocalFireDepartment
import androidx.compose.material.icons.filled.Restaurant
import androidx.compose.material.icons.filled.Search
import androidx.compose.material.icons.filled.WaterDrop
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.FilterChip
import androidx.compose.material3.FilterChipDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.ScrollableTabRow
import androidx.compose.material3.Surface
import androidx.compose.material3.Tab
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableIntStateOf
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.data.seed.BudgetDietPlans
import com.example.data.seed.DesiFoodItem
import com.example.data.seed.DietPlanModel
import com.example.data.seed.FoodCategory
import com.example.data.seed.FoodDatabaseData
import com.example.ui.components.HomeFitCard
import java.util.Locale

import android.widget.Toast
import androidx.compose.animation.AnimatedVisibility
import androidx.compose.foundation.text.KeyboardOptions
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.Delete
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.LinearProgressIndicator
import androidx.compose.material3.TextButton
import androidx.compose.ui.draw.clip
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.text.input.KeyboardType
import com.example.data.local.entity.NutritionLogEntity

enum class DietSubTab(val titleBn: String, val titleEn: String) {
    BUDGET_PLANS("বাজেট ডায়েট", "Budget Diet"),
    FOOD_DATABASE("খাদ্য ও পুষ্টি", "Food Library"),
    PRE_POST_MEALS("ব্যায়ামের আগে-পরে", "Pre/Post Meals"),
    WATER_AND_SLEEP("পানি ও ঘুম গাইড", "Water & Sleep")
}

@Composable
fun DietScreen(
    userWeightKg: Float,
    selectedLanguage: Language,
    strings: AppStrings,
    todayNutritionLogs: List<NutritionLogEntity> = emptyList(),
    dailyCalorieTarget: Int = 2100,
    onLogNutritionItem: (
        foodNameBn: String,
        foodNameEn: String,
        calories: Int,
        proteinGrams: Float,
        carbsGrams: Float,
        fatGrams: Float
    ) -> Unit = { _, _, _, _, _, _ -> },
    onDeleteNutritionLog: (Long) -> Unit = {},
    modifier: Modifier = Modifier,
    userHeightCm: Float = 170f,
    userAge: Int = 24,
    userGender: String = "male",
    userGoal: String = "fitness",
    userWorkoutDays: Int = 4,
    todayWaterGlasses: Int = 0,
    onAddWaterGlass: () -> Unit = {},
    onRemoveWaterGlass: () -> Unit = {},
    isProSubscribed: Boolean = false,
    onOpenProDialog: () -> Unit = {}
) {
    val context = LocalContext.current
    val isBn = selectedLanguage == Language.BENGALI
    var selectedTab by remember { mutableStateOf(DietSubTab.BUDGET_PLANS) }
    var showCustomFoodDialog by remember { mutableStateOf(false) }

    val metabolic = com.example.domain.calculations.HealthCalculations.calculateMetabolicBreakdown(
        weightKg = userWeightKg,
        heightCm = userHeightCm,
        age = userAge,
        gender = userGender,
        goal = userGoal,
        workoutDaysPerWeek = userWorkoutDays
    )
    val hydration = com.example.domain.calculations.HealthCalculations.calculateScientificHydration(
        weightKg = userWeightKg,
        age = userAge,
        gender = userGender,
        goal = userGoal,
        workoutDaysPerWeek = userWorkoutDays
    )
    val effectiveCalorieTarget = if (dailyCalorieTarget > 900) dailyCalorieTarget else metabolic.targetDailyIntakeCalories
    val proteinTargetGrams = metabolic.proteinGrams

    if (showCustomFoodDialog) {
        AddCustomMealDialog(
            selectedLanguage = selectedLanguage,
            onDismiss = { showCustomFoodDialog = false },
            onSave = { name, cal, prot, carbs, fat ->
                onLogNutritionItem(name, name, cal, prot, carbs, fat)
                showCustomFoodDialog = false
                Toast.makeText(
                    context,
                    if (isBn) "✅ '$name' আজকের খাবারে যোগ হয়েছে!" else "✅ Added '$name' to today's log!",
                    Toast.LENGTH_SHORT
                ).show()
            }
        )
    }

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(MaterialTheme.colorScheme.background)
            .testTag("diet_screen")
    ) {
        // Header + Daily Nutrition & Protein Tracker Card
        Column(modifier = Modifier.padding(horizontal = 16.dp, vertical = 10.dp)) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column(modifier = Modifier.weight(1f)) {
                    Text(
                        text = if (isBn) "পুষ্টি ও প্রোটিন ট্র্যাকার" else "Nutrition & Protein Tracker",
                        style = MaterialTheme.typography.headlineSmall.copy(fontWeight = FontWeight.Black),
                        color = MaterialTheme.colorScheme.onBackground
                    )
                    Text(
                        text = if (isBn) "প্রতিদিনের খাবার, ক্যালরি ও প্রোটিন হিসাব রাখুন"
                        else "Track daily meals, protein & affordable local diets",
                        style = MaterialTheme.typography.bodySmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }

                Button(
                    onClick = { showCustomFoodDialog = true },
                    shape = RoundedCornerShape(12.dp),
                    colors = ButtonDefaults.buttonColors(containerColor = MaterialTheme.colorScheme.primary),
                    modifier = Modifier
                        .height(36.dp)
                        .testTag("open_custom_meal_dialog_btn")
                ) {
                    Icon(Icons.Default.Add, contentDescription = null, modifier = Modifier.size(16.dp))
                    Spacer(modifier = Modifier.width(4.dp))
                    Text(
                        text = if (isBn) "খাবার যোগ" else "Log Meal",
                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold)
                    )
                }
            }

            Spacer(modifier = Modifier.height(10.dp))

            TodayNutritionSummaryCard(
                todayLogs = todayNutritionLogs,
                calorieGoal = effectiveCalorieTarget,
                proteinGoalGrams = proteinTargetGrams,
                selectedLanguage = selectedLanguage,
                onDeleteLog = onDeleteNutritionLog
            )

            Spacer(modifier = Modifier.height(8.dp))

            // VIP Pro Custom Diet & Macro Analytics Strip
            Surface(
                shape = RoundedCornerShape(14.dp),
                color = if (isProSubscribed) Color(0xFF0E231E) else Color(0xFF1A162B),
                border = androidx.compose.foundation.BorderStroke(
                    1.dp,
                    if (isProSubscribed) Color(0xFF10B981).copy(alpha = 0.7f) else Color(0xFFFBBF24).copy(alpha = 0.6f)
                ),
                modifier = Modifier
                    .fillMaxWidth()
                    .clickable { if (!isProSubscribed) onOpenProDialog() }
            ) {
                if (isProSubscribed) {
                    Column(modifier = Modifier.padding(horizontal = 12.dp, vertical = 9.dp)) {
                        Text(
                            text = if (isBn) "VIP PRO ম্যাক্রো ও মেটাবলিক অ্যানালিটিক্স (আনলকড)"
                            else "VIP PRO MACRO & METABOLIC ANALYTICS (UNLOCKED)",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Black, fontSize = 10.5.sp),
                            color = Color(0xFFFDE68A)
                        )
                        Spacer(modifier = Modifier.height(3.dp))
                        Text(
                            text = if (isBn) {
                                "BMR: ${metabolic.bmrCalories} kcal • TDEE: ${metabolic.tdeeCalories} kcal | প্রোটিন: ${metabolic.proteinGrams}g • কার্বস: ${metabolic.carbsGrams}g • ফ্যাট: ${metabolic.fatsGrams}g | পানি: ${hydration.totalMl} ml"
                            } else {
                                "BMR: ${metabolic.bmrCalories} kcal • TDEE: ${metabolic.tdeeCalories} kcal | Protein: ${metabolic.proteinGrams}g • Carbs: ${metabolic.carbsGrams}g • Fat: ${metabolic.fatsGrams}g | Water: ${hydration.totalMl} ml"
                            },
                            style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.SemiBold, fontSize = 11.5.sp),
                            color = Color(0xFFA7F3D0)
                        )
                    }
                } else {
                    Row(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(horizontal = 12.dp, vertical = 9.dp),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Column(modifier = Modifier.weight(1f)) {
                            Text(
                                text = if (isBn) "প্রো ডায়েট চার্ট ও ম্যাক্রো অ্যানালিটিক্স" else "Pro Diet Chart & Macro Analytics",
                                style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.ExtraBold),
                                color = Color(0xFFFDE68A)
                            )
                            Text(
                                text = if (isBn) "গোপন কোড দিয়ে আপনার BMR, TDEE ও সঠিক গ্রাম ম্যাক্রো আনলক করুন"
                                else "Redeem secret Pro code to unlock BMR, TDEE & exact gram macros",
                                style = MaterialTheme.typography.bodySmall.copy(fontSize = 11.sp),
                                color = Color(0xFFCBD5E1)
                            )
                        }
                        Spacer(modifier = Modifier.width(8.dp))
                        Surface(
                            shape = RoundedCornerShape(8.dp),
                            color = Color(0xFFFBBF24)
                        ) {
                            Text(
                                text = if (isBn) "আনলক" else "UNLOCK",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Black, fontSize = 10.5.sp),
                                color = Color(0xFF090D16),
                                modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                            )
                        }
                    }
                }
            }
        }

        // Sub-tabs
        ScrollableTabRow(
            selectedTabIndex = selectedTab.ordinal,
            edgePadding = 16.dp,
            containerColor = MaterialTheme.colorScheme.background,
            contentColor = MaterialTheme.colorScheme.primary
        ) {
            DietSubTab.values().forEach { tab ->
                val title = if (selectedLanguage == Language.BENGALI) tab.titleBn else tab.titleEn
                Tab(
                    selected = selectedTab == tab,
                    onClick = { selectedTab = tab },
                    text = {
                        Text(
                            text = title,
                            fontWeight = if (selectedTab == tab) FontWeight.Bold else FontWeight.Normal
                        )
                    }
                )
            }
        }

        Spacer(modifier = Modifier.height(8.dp))

        when (selectedTab) {
            DietSubTab.BUDGET_PLANS -> BudgetPlansTabContent(
                selectedLanguage = selectedLanguage,
                onQuickLogMeal = { titleBn, titleEn, cal, prot ->
                    onLogNutritionItem(titleBn, titleEn, cal, prot, 28f, 8f)
                    Toast.makeText(
                        context,
                        if (isBn) "✅ '${titleBn}' আজকের খাবারে যোগ হয়েছে!" else "✅ Logged '${titleEn}'!",
                        Toast.LENGTH_SHORT
                    ).show()
                }
            )
            DietSubTab.FOOD_DATABASE -> FoodDatabaseTabContent(
                selectedLanguage = selectedLanguage,
                onLogFood = { food ->
                    onLogNutritionItem(
                        food.nameBn,
                        food.nameEn,
                        food.calories,
                        food.proteinGrams,
                        food.carbsGrams,
                        food.fatGrams
                    )
                    Toast.makeText(
                        context,
                        if (isBn) "✅ '${food.nameBn}' (+${food.proteinGrams}g প্রোটিন) যোগ হয়েছে!"
                        else "✅ Added '${food.nameEn}' (+${food.proteinGrams}g protein)!",
                        Toast.LENGTH_SHORT
                    ).show()
                }
            )
            DietSubTab.PRE_POST_MEALS -> PrePostMealsTabContent(selectedLanguage)
            DietSubTab.WATER_AND_SLEEP -> WaterAndSleepTabContent(
                userWeightKg = userWeightKg,
                selectedLanguage = selectedLanguage,
                userAge = userAge,
                hydration = hydration,
                todayWaterGlasses = todayWaterGlasses,
                onAddWaterGlass = onAddWaterGlass,
                onRemoveWaterGlass = onRemoveWaterGlass
            )
        }
    }
}

@Composable
fun TodayNutritionSummaryCard(
    todayLogs: List<NutritionLogEntity>,
    calorieGoal: Int,
    proteinGoalGrams: Int,
    selectedLanguage: Language,
    onDeleteLog: (Long) -> Unit
) {
    val isBn = selectedLanguage == Language.BENGALI
    var showLoggedList by remember { mutableStateOf(false) }

    val totalCalories = todayLogs.sumOf { it.calories }
    val totalProtein = todayLogs.sumOf { it.proteinGrams.toDouble() }.toFloat()
    val totalCarbs = todayLogs.sumOf { it.carbsGrams.toDouble() }.toFloat()
    val totalFat = todayLogs.sumOf { it.fatGrams.toDouble() }.toFloat()

    val calProgress = (totalCalories.toFloat() / calorieGoal.coerceAtLeast(1000)).coerceIn(0f, 1f)
    val protProgress = (totalProtein / proteinGoalGrams.coerceAtLeast(40)).coerceIn(0f, 1f)

    HomeFitCard(borderColor = MaterialTheme.colorScheme.primary) {
        Column {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column(modifier = Modifier.weight(1f)) {
                    Text(
                        text = if (isBn) "🔥 আজকের পুষ্টি মিটার (${todayLogs.size}টি খাবার)"
                        else "🔥 Today's Nutrition (${todayLogs.size} items)",
                        style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                }

                if (todayLogs.isNotEmpty()) {
                    Surface(
                        shape = RoundedCornerShape(8.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant,
                        modifier = Modifier.clickable { showLoggedList = !showLoggedList }
                    ) {
                        Text(
                            text = if (isBn) {
                                if (showLoggedList) "তালিকা লুকান ▲" else "তালিকা দেখুন ▼"
                            } else {
                                if (showLoggedList) "Hide List ▲" else "View Logs ▼"
                            },
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp)
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(8.dp))

            // Calorie & Protein Dual Progress Bars
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(12.dp)
            ) {
                Column(modifier = Modifier.weight(1f)) {
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween
                    ) {
                        Text(
                            text = if (isBn) "ক্যালরি" else "Calories",
                            style = MaterialTheme.typography.labelSmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Text(
                            text = "$totalCalories / $calorieGoal kcal",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.primary
                        )
                    }
                    Spacer(modifier = Modifier.height(4.dp))
                    LinearProgressIndicator(
                        progress = { calProgress },
                        color = MaterialTheme.colorScheme.primary,
                        trackColor = MaterialTheme.colorScheme.surfaceVariant,
                        modifier = Modifier
                            .fillMaxWidth()
                            .height(7.dp)
                            .clip(RoundedCornerShape(50))
                    )
                }

                Column(modifier = Modifier.weight(1f)) {
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween
                    ) {
                        Text(
                            text = if (isBn) "প্রোটিন" else "Protein",
                            style = MaterialTheme.typography.labelSmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Text(
                            text = "${String.format(Locale.US, "%.1f", totalProtein)} / ${proteinGoalGrams}g",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.secondary
                        )
                    }
                    Spacer(modifier = Modifier.height(4.dp))
                    LinearProgressIndicator(
                        progress = { protProgress },
                        color = MaterialTheme.colorScheme.secondary,
                        trackColor = MaterialTheme.colorScheme.surfaceVariant,
                        modifier = Modifier
                            .fillMaxWidth()
                            .height(7.dp)
                            .clip(RoundedCornerShape(50))
                    )
                }
            }

            Spacer(modifier = Modifier.height(6.dp))

            // Secondary Macros Row
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Text(
                    text = if (isBn) "কার্বস: ${totalCarbs.toInt()}g • ফ্যাট: ${totalFat.toInt()}g"
                    else "Carbs: ${totalCarbs.toInt()}g • Fat: ${totalFat.toInt()}g",
                    style = MaterialTheme.typography.labelSmall.copy(fontSize = 11.sp),
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
                Text(
                    text = if (isBn) "নিচের যেকোনো খাবারে '+ যোগ' ট্যাপ করুন"
                    else "Tap '+ Log' on any meal below",
                    style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
                    color = MaterialTheme.colorScheme.tertiary
                )
            }

            // Expandable Logged Items Drawer
            AnimatedVisibility(visible = showLoggedList && todayLogs.isNotEmpty()) {
                Column(modifier = Modifier.padding(top = 10.dp)) {
                    todayLogs.forEach { item ->
                        Row(
                            modifier = Modifier
                                .fillMaxWidth()
                                .padding(vertical = 3.dp),
                            verticalAlignment = Alignment.CenterVertically,
                            horizontalArrangement = Arrangement.SpaceBetween
                        ) {
                            Column(modifier = Modifier.weight(1f)) {
                                Text(
                                    text = if (isBn) item.foodNameBn else item.foodNameEn,
                                    style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.Bold),
                                    color = MaterialTheme.colorScheme.onSurface
                                )
                                Text(
                                    text = "${item.calories} kcal • ${item.proteinGrams}g ${if (isBn) "প্রোটিন" else "protein"}",
                                    style = MaterialTheme.typography.labelSmall,
                                    color = MaterialTheme.colorScheme.primary
                                )
                            }
                            IconButton(
                                onClick = { onDeleteLog(item.id) },
                                modifier = Modifier.size(28.dp)
                            ) {
                                Icon(
                                    imageVector = Icons.Default.Delete,
                                    contentDescription = "Delete Food Log",
                                    tint = MaterialTheme.colorScheme.error,
                                    modifier = Modifier.size(16.dp)
                                )
                            }
                        }
                    }
                }
            }
        }
    }
}

@Composable
fun AddCustomMealDialog(
    selectedLanguage: Language,
    onDismiss: () -> Unit,
    onSave: (name: String, calories: Int, protein: Float, carbs: Float, fat: Float) -> Unit
) {
    val isBn = selectedLanguage == Language.BENGALI
    var name by remember { mutableStateOf("") }
    var caloriesStr by remember { mutableStateOf("250") }
    var proteinStr by remember { mutableStateOf("15") }
    var carbsStr by remember { mutableStateOf("25") }
    var fatStr by remember { mutableStateOf("6") }

    AlertDialog(
        onDismissRequest = onDismiss,
        title = {
            Text(
                text = if (isBn) "🍲 আজকের খাবার যোগ করুন" else "🍲 Log Custom Meal",
                style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Bold)
            )
        },
        text = {
            Column(verticalArrangement = Arrangement.spacedBy(10.dp)) {
                OutlinedTextField(
                    value = name,
                    onValueChange = { name = it },
                    label = { Text(if (isBn) "খাবারের নাম (যেমন: ভাত ও মুরগির মাংস)" else "Meal Name (e.g. Rice & Chicken)") },
                    singleLine = true,
                    modifier = Modifier.fillMaxWidth()
                )
                Row(horizontalArrangement = Arrangement.spacedBy(8.dp)) {
                    OutlinedTextField(
                        value = caloriesStr,
                        onValueChange = { caloriesStr = it },
                        label = { Text(if (isBn) "ক্যালরি (kcal)" else "Calories") },
                        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Number),
                        singleLine = true,
                        modifier = Modifier.weight(1f)
                    )
                    OutlinedTextField(
                        value = proteinStr,
                        onValueChange = { proteinStr = it },
                        label = { Text(if (isBn) "প্রোটিন (g)" else "Protein (g)") },
                        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Decimal),
                        singleLine = true,
                        modifier = Modifier.weight(1f)
                    )
                }
                Row(horizontalArrangement = Arrangement.spacedBy(8.dp)) {
                    OutlinedTextField(
                        value = carbsStr,
                        onValueChange = { carbsStr = it },
                        label = { Text(if (isBn) "কার্বস (g)" else "Carbs (g)") },
                        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Decimal),
                        singleLine = true,
                        modifier = Modifier.weight(1f)
                    )
                    OutlinedTextField(
                        value = fatStr,
                        onValueChange = { fatStr = it },
                        label = { Text(if (isBn) "ফ্যাট (g)" else "Fat (g)") },
                        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Decimal),
                        singleLine = true,
                        modifier = Modifier.weight(1f)
                    )
                }
            }
        },
        confirmButton = {
            Button(
                onClick = {
                    val finalName = name.trim().ifEmpty { if (isBn) "ঘরোয়া খাবার" else "Home Meal" }
                    val cal = caloriesStr.toIntOrNull()?.coerceIn(10, 3000) ?: 250
                    val prot = proteinStr.toFloatOrNull()?.coerceIn(0f, 200f) ?: 15f
                    val carbs = carbsStr.toFloatOrNull()?.coerceIn(0f, 300f) ?: 25f
                    val fat = fatStr.toFloatOrNull()?.coerceIn(0f, 150f) ?: 6f
                    onSave(finalName, cal, prot, carbs, fat)
                }
            ) {
                Text(if (isBn) "সংরক্ষণ করুন" else "Save Meal", fontWeight = FontWeight.Bold)
            }
        },
        dismissButton = {
            TextButton(onClick = onDismiss) {
                Text(if (isBn) "বাতিল" else "Cancel")
            }
        }
    )
}

@Composable
fun BudgetPlansTabContent(
    selectedLanguage: Language,
    onQuickLogMeal: (titleBn: String, titleEn: String, calories: Int, protein: Float) -> Unit = { _, _, _, _ -> }
) {
    var selectedPlanId by remember { mutableStateOf("student_budget") }
    val currentPlan = if (selectedPlanId == "student_budget") BudgetDietPlans.studentBudgetPlan else BudgetDietPlans.familyBalancedPlan

    LazyColumn(
        modifier = Modifier
            .fillMaxSize()
            .padding(horizontal = 16.dp),
        verticalArrangement = Arrangement.spacedBy(14.dp)
    ) {
        item {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                FilterChip(
                    selected = selectedPlanId == "student_budget",
                    onClick = { selectedPlanId = "student_budget" },
                    label = { Text(if (selectedLanguage == Language.BENGALI) "ছাত্র / ব্যাচেলর প্ল্যান" else "Student Budget Plan") },
                    colors = FilterChipDefaults.filterChipColors(
                        selectedContainerColor = MaterialTheme.colorScheme.primaryContainer,
                        selectedLabelColor = MaterialTheme.colorScheme.onPrimaryContainer
                    ),
                    modifier = Modifier.weight(1f)
                )

                FilterChip(
                    selected = selectedPlanId == "family_balanced",
                    onClick = { selectedPlanId = "family_balanced" },
                    label = { Text(if (selectedLanguage == Language.BENGALI) "পারিবারিক দেশীয় প্ল্যান" else "Family Balanced Plan") },
                    colors = FilterChipDefaults.filterChipColors(
                        selectedContainerColor = MaterialTheme.colorScheme.primaryContainer,
                        selectedLabelColor = MaterialTheme.colorScheme.onPrimaryContainer
                    ),
                    modifier = Modifier.weight(1f)
                )
            }
        }

        item {
            // Plan Overview Card
            HomeFitCard(borderColor = MaterialTheme.colorScheme.primary) {
                Column {
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Text(
                            text = if (selectedLanguage == Language.BENGALI) currentPlan.titleBn else currentPlan.titleEn,
                            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.onSurface,
                            modifier = Modifier.weight(1f)
                        )
                        Surface(
                            shape = RoundedCornerShape(8.dp),
                            color = MaterialTheme.colorScheme.primary.copy(alpha = 0.15f)
                        ) {
                            Text(
                                text = "🥩 ${currentPlan.totalProteinEstimate}",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.primary,
                                modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp)
                            )
                        }
                    }

                    Spacer(modifier = Modifier.height(6.dp))

                    Text(
                        text = if (selectedLanguage == Language.BENGALI) currentPlan.targetBn else currentPlan.targetEn,
                        style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.SemiBold),
                        color = MaterialTheme.colorScheme.secondary
                    )

                    Spacer(modifier = Modifier.height(4.dp))

                    Text(
                        text = "💰 ${if (selectedLanguage == Language.BENGALI) currentPlan.dailyBudgetEstimateBn else currentPlan.dailyBudgetEstimateEn}",
                        style = MaterialTheme.typography.labelSmall.copy(color = MaterialTheme.colorScheme.tertiary, fontWeight = FontWeight.Bold)
                    )

                    Spacer(modifier = Modifier.height(8.dp))

                    Text(
                        text = if (selectedLanguage == Language.BENGALI) currentPlan.descriptionBn else currentPlan.descriptionEn,
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }
            }
        }

        item {
            Text(
                text = if (selectedLanguage == Language.BENGALI) "দিনের বেলার খাবার তালিকা (Meals Schedule):" else "Daily Meals Breakdown:",
                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                color = MaterialTheme.colorScheme.onBackground
            )
        }

        // Meal Cards
        items(currentPlan.meals) { meal ->
            val time = if (selectedLanguage == Language.BENGALI) meal.timeBn else meal.timeEn
            val title = if (selectedLanguage == Language.BENGALI) meal.titleBn else meal.titleEn
            val items = if (selectedLanguage == Language.BENGALI) meal.itemsBn else meal.itemsEn

            Card(
                shape = RoundedCornerShape(16.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                modifier = Modifier.fillMaxWidth()
            ) {
                Column(modifier = Modifier.padding(14.dp)) {
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Surface(
                            shape = RoundedCornerShape(6.dp),
                            color = MaterialTheme.colorScheme.surfaceVariant
                        ) {
                            Text(
                                text = time,
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.primary,
                                modifier = Modifier.padding(horizontal = 8.dp, vertical = 3.dp)
                            )
                        }

                        Text(
                            text = "প্রোটিন: ~${meal.approxProtein}",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.secondary
                        )
                    }

                    Spacer(modifier = Modifier.height(8.dp))

                    Text(
                        text = title,
                        style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )

                    Spacer(modifier = Modifier.height(6.dp))

                    items.forEach { item ->
                        Text(
                            text = "• $item",
                            style = MaterialTheme.typography.bodyMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant,
                            modifier = Modifier.padding(vertical = 2.dp)
                        )
                    }

                    Spacer(modifier = Modifier.height(8.dp))

                    val parsedProt = meal.approxProtein.filter { it.isDigit() }.toFloatOrNull() ?: 18f
                    val estCal = (parsedProt * 18f).toInt().coerceIn(220, 620)
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.End
                    ) {
                        Surface(
                            shape = RoundedCornerShape(8.dp),
                            color = MaterialTheme.colorScheme.primaryContainer,
                            modifier = Modifier.clickable {
                                onQuickLogMeal(meal.titleBn, meal.titleEn, estCal, parsedProt)
                            }
                        ) {
                            Text(
                                text = if (selectedLanguage == Language.BENGALI) "+ আজকের খাবারে যোগ করুন" else "+ Log This Meal",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.onPrimaryContainer,
                                modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                            )
                        }
                    }
                }
            }
        }

        item { Spacer(modifier = Modifier.height(40.dp)) }
    }
}

@Composable
fun FoodDatabaseTabContent(
    selectedLanguage: Language,
    onLogFood: (DesiFoodItem) -> Unit = {}
) {
    var searchQuery by remember { mutableStateOf("") }
    var selectedCategory by remember { mutableStateOf(FoodCategory.ALL) }

    val filteredFoods = remember(searchQuery, selectedCategory) {
        FoodDatabaseData.allFoods.filter { food ->
            val matchCategory = selectedCategory == FoodCategory.ALL || food.category == selectedCategory
            val matchQuery = searchQuery.isBlank() ||
                    food.nameBn.contains(searchQuery, ignoreCase = true) ||
                    food.nameEn.contains(searchQuery, ignoreCase = true)
            matchCategory && matchQuery
        }
    }

    Column(modifier = Modifier.fillMaxSize().padding(horizontal = 16.dp)) {
        // Search field
        OutlinedTextField(
            value = searchQuery,
            onValueChange = { searchQuery = it },
            placeholder = { Text(if (selectedLanguage == Language.BENGALI) "খাবারের নাম লিখে খুঁজুন (ডিম, ডাল, মাছ...)" else "Search food (egg, dal, fish...)") },
            leadingIcon = { Icon(imageVector = Icons.Default.Search, contentDescription = null) },
            trailingIcon = {
                if (searchQuery.isNotEmpty()) {
                    IconButton(onClick = { searchQuery = "" }) {
                        Icon(imageVector = Icons.Default.Clear, contentDescription = "Clear")
                    }
                }
            },
            shape = RoundedCornerShape(14.dp),
            modifier = Modifier.fillMaxWidth()
        )

        Spacer(modifier = Modifier.height(10.dp))

        // Categories Chips
        LazyRow(horizontalArrangement = Arrangement.spacedBy(8.dp)) {
            items(FoodCategory.values()) { cat ->
                val title = if (selectedLanguage == Language.BENGALI) cat.titleBn else cat.titleEn
                FilterChip(
                    selected = selectedCategory == cat,
                    onClick = { selectedCategory = cat },
                    label = { Text(title) },
                    colors = FilterChipDefaults.filterChipColors(
                        selectedContainerColor = MaterialTheme.colorScheme.primaryContainer,
                        selectedLabelColor = MaterialTheme.colorScheme.onPrimaryContainer
                    )
                )
            }
        }

        Spacer(modifier = Modifier.height(12.dp))

        // Foods List
        LazyColumn(
            modifier = Modifier.fillMaxSize(),
            verticalArrangement = Arrangement.spacedBy(10.dp)
        ) {
            items(filteredFoods, key = { it.id }) { food ->
                val name = if (selectedLanguage == Language.BENGALI) food.nameBn else food.nameEn
                val portion = if (selectedLanguage == Language.BENGALI) food.portionBn else food.portionEn
                val benefits = if (selectedLanguage == Language.BENGALI) food.benefitsBn else food.benefitsEn

                Card(
                    shape = RoundedCornerShape(16.dp),
                    colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                    modifier = Modifier.fillMaxWidth()
                ) {
                    Column(modifier = Modifier.padding(14.dp)) {
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.SpaceBetween,
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Text(
                                text = name,
                                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.onSurface,
                                modifier = Modifier.weight(1f)
                            )
                            Surface(
                                shape = RoundedCornerShape(6.dp),
                                color = MaterialTheme.colorScheme.primary.copy(alpha = 0.15f)
                            ) {
                                Text(
                                    text = "🔥 ${food.calories} kcal",
                                    style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                    color = MaterialTheme.colorScheme.primary,
                                    modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                                )
                            }
                        }

                        Spacer(modifier = Modifier.height(2.dp))

                        Text(
                            text = "পরিমাপ: $portion",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )

                        Spacer(modifier = Modifier.height(8.dp))

                        // Macros Row
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.spacedBy(12.dp)
                        ) {
                            Text(
                                text = "প্রোটিন: ${food.proteinGrams}g",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.primary
                            )
                            Text(
                                text = "কার্বস: ${food.carbsGrams}g",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.secondary
                            )
                            Text(
                                text = "ফ্যাট: ${food.fatGrams}g",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.tertiary
                            )
                        }

                        Spacer(modifier = Modifier.height(6.dp))

                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.SpaceBetween,
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Text(
                                text = benefits,
                                style = MaterialTheme.typography.bodySmall.copy(fontSize = 11.sp),
                                color = MaterialTheme.colorScheme.onSurfaceVariant,
                                modifier = Modifier.weight(1f)
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Surface(
                                shape = RoundedCornerShape(8.dp),
                                color = MaterialTheme.colorScheme.primary,
                                modifier = Modifier
                                    .clickable { onLogFood(food) }
                                    .testTag("log_food_btn_${food.id}")
                            ) {
                                Text(
                                    text = if (selectedLanguage == Language.BENGALI) "+ যোগ করুন" else "+ Log",
                                    style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                    color = Color.White,
                                    modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                                )
                            }
                        }
                    }
                }
            }

            item { Spacer(modifier = Modifier.height(40.dp)) }
        }
    }
}

@Composable
fun PrePostMealsTabContent(selectedLanguage: Language) {
    val tips = if (selectedLanguage == Language.BENGALI) BudgetDietPlans.prePostWorkoutTipsBn else BudgetDietPlans.prePostWorkoutTipsEn

    LazyColumn(
        modifier = Modifier
            .fillMaxSize()
            .padding(horizontal = 16.dp),
        verticalArrangement = Arrangement.spacedBy(14.dp)
    ) {
        item {
            HomeFitCard(borderColor = MaterialTheme.colorScheme.secondary) {
                Column {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        Icon(
                            imageVector = Icons.Default.LocalDining,
                            contentDescription = null,
                            tint = MaterialTheme.colorScheme.secondary,
                            modifier = Modifier.size(24.dp)
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text(
                            text = if (selectedLanguage == Language.BENGALI) "ব্যায়ামের আগে ও পরের খাদ্য নির্দেশিকা" else "Pre & Post Workout Guidance",
                            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                        )
                    }
                    Spacer(modifier = Modifier.height(8.dp))
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "সঠিক সময়ে সঠিক খাবার খাওয়া আপনার স্ট্যামিনা দ্বিগুণ করে এবং ওয়ার্কআউটের ক্লান্তি দ্রুত দূর করে।"
                        else "Timing your meals correctly enhances endurance and accelerates recovery.",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }
            }
        }

        items(tips) { tip ->
            Card(
                shape = RoundedCornerShape(14.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                modifier = Modifier.fillMaxWidth()
            ) {
                Row(modifier = Modifier.padding(14.dp)) {
                    Text("💡", fontSize = 18.sp)
                    Spacer(modifier = Modifier.width(10.dp))
                    Text(
                        text = tip,
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurface
                    )
                }
            }
        }

        item {
            // Foods to Avoid
            HomeFitCard(borderColor = MaterialTheme.colorScheme.error) {
                Column {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "⚠️ ব্যায়ামের আগে যেসব খাবার এড়িয়ে চলবেন:" else "⚠️ Foods to avoid before workouts:",
                        style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold, color = MaterialTheme.colorScheme.error)
                    )
                    Spacer(modifier = Modifier.height(6.dp))
                    Text("• অতিরিক্ত তেলযুক্ত পরোটা বা মোগলাই (পেট ভারী করে ও আলস্য আনে)")
                    Text("• কোল্ড ড্রিংকস বা অতিরিক্ত চিনিযুক্ত প্যাকেট জুস")
                    Text("• ভারী বিরিয়ানি বা খিচুড়ি খাওয়ার সাথে সাথে ব্যায়াম শুরু করা")
                }
            }
        }

        item { Spacer(modifier = Modifier.height(40.dp)) }
    }
}

@Composable
fun WaterAndSleepTabContent(
    userWeightKg: Float,
    selectedLanguage: Language,
    userAge: Int = 24,
    hydration: com.example.domain.calculations.HydrationBreakdown =
        com.example.domain.calculations.HealthCalculations.calculateScientificHydration(userWeightKg, userAge),
    todayWaterGlasses: Int = 0,
    onAddWaterGlass: () -> Unit = {},
    onRemoveWaterGlass: () -> Unit = {}
) {
    val isBn = selectedLanguage == Language.BENGALI
    val currentMl = todayWaterGlasses * 250

    val hydrationTips = if (selectedLanguage == Language.BENGALI) BudgetDietPlans.hydrationTipsBn else BudgetDietPlans.hydrationTipsEn
    val sleepTips = if (selectedLanguage == Language.BENGALI) BudgetDietPlans.sleepRecoveryTipsBn else BudgetDietPlans.sleepRecoveryTipsEn

    LazyColumn(
        modifier = Modifier
            .fillMaxSize()
            .padding(horizontal = 16.dp),
        verticalArrangement = Arrangement.spacedBy(14.dp)
    ) {
        item {
            // Personalized Clinical Water Calculator Card
            HomeFitCard(borderColor = Color(0xFF38BDF8)) {
                Column {
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Row(
                            verticalAlignment = Alignment.CenterVertically,
                            modifier = Modifier.weight(1f)
                        ) {
                            Icon(
                                imageVector = Icons.Default.WaterDrop,
                                contentDescription = null,
                                tint = Color(0xFF38BDF8),
                                modifier = Modifier.size(24.dp)
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Column {
                                Text(
                                    text = if (isBn) "ক্লিনিক্যাল হাইড্রেশন ক্যালকুলেটর (ml/L)" else "Clinical Hydration Calculator (ml/L)",
                                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.ExtraBold)
                                )
                                Text(
                                    text = if (isBn) "ওজন ${userWeightKg.toInt()} কেজি • বয়স $userAge বছর অনুযায়ী"
                                    else "Calibrated for Weight ${userWeightKg.toInt()} kg • Age $userAge yrs",
                                    style = MaterialTheme.typography.bodySmall,
                                    color = MaterialTheme.colorScheme.onSurfaceVariant
                                )
                            }
                        }

                        Surface(
                            shape = RoundedCornerShape(8.dp),
                            color = Color(0xFF38BDF8).copy(alpha = 0.16f)
                        ) {
                            Text(
                                text = String.format(Locale.US, "%.2f L (%d ml)", hydration.totalLiters, hydration.totalMl),
                                style = MaterialTheme.typography.labelMedium.copy(
                                    fontWeight = FontWeight.ExtraBold,
                                    color = Color(0xFF38BDF8)
                                ),
                                modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                            )
                        }
                    }

                    Spacer(modifier = Modifier.height(10.dp))

                    Text(
                        text = if (isBn) hydration.formulaSummaryBn else hydration.formulaSummaryEn,
                        style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.SemiBold),
                        color = MaterialTheme.colorScheme.onSurface
                    )

                    Spacer(modifier = Modifier.height(12.dp))

                    // Interactive Today's Water Intake Row Synced with Home
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Column {
                            Text(
                                text = if (isBn) "আজকের পানকৃত পানি" else "Today's Logged Water",
                                style = MaterialTheme.typography.labelSmall,
                                color = MaterialTheme.colorScheme.onSurfaceVariant
                            )
                            Text(
                                text = "$currentMl / ${hydration.totalMl} ml ($todayWaterGlasses/${hydration.targetGlasses250Ml} ${if (isBn) "গ্লাস" else "glasses"})",
                                style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.ExtraBold),
                                color = Color(0xFF38BDF8)
                            )
                        }
                        Row(horizontalArrangement = Arrangement.spacedBy(8.dp)) {
                            Surface(
                                shape = RoundedCornerShape(10.dp),
                                color = MaterialTheme.colorScheme.surfaceVariant,
                                modifier = Modifier.clickable(enabled = todayWaterGlasses > 0) { onRemoveWaterGlass() }
                            ) {
                                Text(
                                    text = "-250ml",
                                    style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                    color = MaterialTheme.colorScheme.onSurface,
                                    modifier = Modifier.padding(horizontal = 10.dp, vertical = 7.dp)
                                )
                            }
                            Surface(
                                shape = RoundedCornerShape(10.dp),
                                color = Color(0xFF0EA5E9),
                                modifier = Modifier.clickable { onAddWaterGlass() }
                            ) {
                                Text(
                                    text = "+250ml",
                                    style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.ExtraBold),
                                    color = Color.White,
                                    modifier = Modifier.padding(horizontal = 12.dp, vertical = 7.dp)
                                )
                            }
                        }
                    }
                }
            }
        }

        item {
            // Scientific Weight & Age Hydration Reference Guide
            HomeFitCard(borderColor = MaterialTheme.colorScheme.outline) {
                Column {
                    Text(
                        text = if (isBn) "কার জন্য কত লিটার পানি প্রয়োজন? (বৈজ্ঞানিক চার্ট)"
                        else "Clinical Hydration Chart by Weight & Age",
                        style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.ExtraBold),
                        color = MaterialTheme.colorScheme.primary
                    )
                    Spacer(modifier = Modifier.height(6.dp))
                    Text(
                        text = if (isBn) "সবার জন্য ২ লিটার পানি সঠিক নয়। বয়স ও শরীরের ওজনের অনুপাতে (৩০–৪০ ml/kg + ব্যায়ামের ঘাম) প্রকৃত পানির চাহিদা:"
                        else "A flat 2-liter rule is inaccurate. True hydration scales by body weight (30–40 ml/kg) plus sweat loss:",
                        style = MaterialTheme.typography.bodySmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Spacer(modifier = Modifier.height(10.dp))

                    val tiers = if (isBn) {
                        listOf(
                            Triple("শিশু ও কিশোর (২৫–৪০ কেজি)", "১.১০ – ১.৬০ লিটার", "৫–৬ গ্লাস (৪০ ml/kg বেস)"),
                            Triple("হালকা ওজন প্রাপ্তবয়স্ক (৪১–৫৫ কেজি)", "১.৬৫ – ২.১৫ লিটার", "৭–৯ গ্লাস (৩৫ ml/kg + ঘাম)"),
                            Triple("মাঝারি ওজন অ্যাথলেট (৫৬–৭৫ কেজি)", "২.২০ – ২.৯০ লিটার", "৯–১২ গ্লাস (৩৫ ml/kg + ওয়ার্কআউট)"),
                            Triple("হেভিওয়েট ও জিম বিল্ডার (৭৬–১২০+ কেজি)", "৩.০০ – ৪.৪০ লিটার", "১২–১৮ গ্লাস (পেশি ও ক্রিয়েটিন হাইড্রেশন)")
                        )
                    } else {
                        listOf(
                            Triple("Youth / Lightweight (25–40 kg)", "1.10 – 1.60 Liters", "5–6 glasses (40 ml/kg base)"),
                            Triple("Petite Adult (41–55 kg)", "1.65 – 2.15 Liters", "7–9 glasses (35 ml/kg + sweat)"),
                            Triple("Standard Athlete (56–75 kg)", "2.20 – 2.90 Liters", "9–12 glasses (35 ml/kg + workout)"),
                            Triple("Heavy Lifter (76–120+ kg)", "3.00 – 4.40 Liters", "12–18 glasses (hypertrophy turnover)")
                        )
                    }

                    Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                        tiers.forEach { (group, liters, note) ->
                            Surface(
                                shape = RoundedCornerShape(10.dp),
                                color = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.55f),
                                modifier = Modifier.fillMaxWidth()
                            ) {
                                Row(
                                    modifier = Modifier.padding(horizontal = 12.dp, vertical = 8.dp),
                                    horizontalArrangement = Arrangement.SpaceBetween,
                                    verticalAlignment = Alignment.CenterVertically
                                ) {
                                    Column(modifier = Modifier.weight(1f)) {
                                        Text(group, style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.Bold))
                                        Text(note, style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
                                    }
                                    Spacer(modifier = Modifier.width(8.dp))
                                    Text(
                                        text = liters,
                                        style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.ExtraBold),
                                        color = Color(0xFF38BDF8)
                                    )
                                }
                            }
                        }
                    }
                }
            }
        }

        item {
            Text(
                text = if (selectedLanguage == Language.BENGALI) "💧 সুস্থ হাইড্রেশন টিপস:" else "💧 Hydration Guidelines:",
                style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                color = MaterialTheme.colorScheme.onBackground
            )
        }

        items(hydrationTips) { tip ->
            Card(
                shape = RoundedCornerShape(12.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                modifier = Modifier.fillMaxWidth()
            ) {
                Row(modifier = Modifier.padding(12.dp)) {
                    Text("✓", color = Color(0xFF38BDF8), fontWeight = FontWeight.Bold)
                    Spacer(modifier = Modifier.width(8.dp))
                    Text(tip, style = MaterialTheme.typography.bodySmall, color = MaterialTheme.colorScheme.onSurface)
                }
            }
        }

        item {
            // Sleep & Recovery Section
            HomeFitCard(borderColor = MaterialTheme.colorScheme.tertiary) {
                Column {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        Icon(
                            imageVector = Icons.Default.Bedtime,
                            contentDescription = null,
                            tint = MaterialTheme.colorScheme.tertiary,
                            modifier = Modifier.size(24.dp)
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text(
                            text = if (selectedLanguage == Language.BENGALI) "ঘুম ও পেশি পুনর্গঠন (Sleep & Recovery)" else "Sleep & Muscle Recovery",
                            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                        )
                    }
                    Spacer(modifier = Modifier.height(8.dp))
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "ব্যায়ামের ফলে পেশিতে যে ক্ষুদ্র টিয়ার তৈরি হয়, তা মেরামত হয়ে শরীর শক্তিশালী হয় শুধুমাত্র গভীর ঘুমের সময়।"
                        else "Micro-tears in muscle repair and grow only during deep sleep cycles.",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }
            }
        }

        items(sleepTips) { tip ->
            Card(
                shape = RoundedCornerShape(12.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                modifier = Modifier.fillMaxWidth()
            ) {
                Row(modifier = Modifier.padding(12.dp)) {
                    Text("🌙", fontSize = 14.sp)
                    Spacer(modifier = Modifier.width(8.dp))
                    Text(tip, style = MaterialTheme.typography.bodySmall, color = MaterialTheme.colorScheme.onSurface)
                }
            }
        }

        item { Spacer(modifier = Modifier.height(40.dp)) }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/home/HomeWidgets.kt`

```kotlin
package com.example.ui.screens.home

import androidx.compose.animation.animateContentSize
import androidx.compose.animation.core.animateFloatAsState
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.Canvas
import androidx.compose.foundation.background
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.heightIn
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.Check
import androidx.compose.material.icons.filled.DirectionsWalk
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.HelpOutline
import androidx.compose.material.icons.filled.LocalFireDepartment
import androidx.compose.material.icons.filled.LocalMall
import androidx.compose.material.icons.filled.Opacity
import androidx.compose.material.icons.filled.PlayArrow
import androidx.compose.material.icons.filled.Psychology
import androidx.compose.material.icons.filled.Remove
import androidx.compose.material.icons.filled.Scale
import androidx.compose.material.icons.filled.Timer
import androidx.compose.material.icons.filled.Whatshot
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.StrokeCap
import androidx.compose.ui.graphics.drawscope.Stroke
import androidx.compose.ui.graphics.vector.ImageVector
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.domain.coach.CoachTip
import com.example.domain.recommendation.RecommendedWorkout
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitCard
import java.util.Calendar

@Composable
fun TodayWorkoutHeroCard(
    workout: RecommendedWorkout,
    selectedLanguage: Language,
    strings: AppStrings,
    onStartWorkout: () -> Unit,
    modifier: Modifier = Modifier
) {
    var showRationale by remember { mutableStateOf(false) }

    val workoutTitle = if (selectedLanguage == Language.BENGALI) workout.titleBn else workout.titleEn
    val rationaleText = if (selectedLanguage == Language.BENGALI) workout.rationaleBn else workout.rationaleEn
    val targetMuscles = if (selectedLanguage == Language.BENGALI) workout.targetMusclesBn else workout.targetMusclesEn

    Card(
        modifier = modifier
            .fillMaxWidth()
            .testTag("today_workout_hero_card"),
        shape = RoundedCornerShape(22.dp),
        colors = CardDefaults.cardColors(
            containerColor = MaterialTheme.colorScheme.surface
        ),
        border = BorderStroke(1.5.dp, MaterialTheme.colorScheme.primary.copy(alpha = 0.6f)),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Column(modifier = Modifier.padding(18.dp)) {
            // Header Tag & Intensity
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Surface(
                    shape = RoundedCornerShape(10.dp),
                    color = MaterialTheme.colorScheme.primaryContainer
                ) {
                    Row(
                        modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Icon(
                            imageVector = Icons.Default.Whatshot,
                            contentDescription = null,
                            tint = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.size(15.dp)
                        )
                        Spacer(modifier = Modifier.width(4.dp))
                        Text(
                            text = strings.todayWorkoutTitle,
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.onPrimaryContainer
                        )
                    }
                }

                Surface(
                    shape = RoundedCornerShape(8.dp),
                    color = MaterialTheme.colorScheme.surfaceVariant
                ) {
                    Text(
                        text = "${strings.intensityLabel}: ${workout.intensity}",
                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.SemiBold),
                        color = MaterialTheme.colorScheme.onSurfaceVariant,
                        modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                    )
                }
            }

            Spacer(modifier = Modifier.height(14.dp))

            // Workout Title
            Text(
                text = workoutTitle,
                style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Black),
                color = MaterialTheme.colorScheme.onSurface
            )

            Spacer(modifier = Modifier.height(8.dp))

            // Metrics row: Duration, Calories, Exercise Count
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(16.dp),
                verticalAlignment = Alignment.CenterVertically
            ) {
                WorkoutMetricChip(
                    icon = Icons.Default.Timer,
                    label = "${workout.durationMinutes} ${strings.minutesUnit}"
                )
                WorkoutMetricChip(
                    icon = Icons.Default.LocalFireDepartment,
                    label = "${workout.estimatedCalories} ${strings.caloriesUnit}"
                )
                WorkoutMetricChip(
                    icon = Icons.Default.FitnessCenter,
                    label = "${workout.exerciseCount} ${strings.exercisesUnit}"
                )
            }

            Spacer(modifier = Modifier.height(10.dp))

            Text(
                text = "🎯 $targetMuscles",
                style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.Medium),
                color = MaterialTheme.colorScheme.onSurfaceVariant
            )

            Spacer(modifier = Modifier.height(14.dp))

            // Rationale toggle & explanation
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .animateContentSize()
            ) {
                Row(
                    modifier = Modifier
                        .clickable { showRationale = !showRationale }
                        .padding(vertical = 4.dp),
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Icon(
                        imageVector = Icons.Default.HelpOutline,
                        contentDescription = null,
                        tint = MaterialTheme.colorScheme.primary,
                        modifier = Modifier.size(16.dp)
                    )
                    Spacer(modifier = Modifier.width(6.dp))
                    Text(
                        text = strings.whyRecommended,
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontWeight = FontWeight.Bold,
                            color = MaterialTheme.colorScheme.primary
                        )
                    )
                }

                if (showRationale) {
                    Surface(
                        shape = RoundedCornerShape(10.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.6f),
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(top = 6.dp)
                    ) {
                        Text(
                            text = rationaleText,
                            style = MaterialTheme.typography.bodyMedium.copy(fontSize = 13.sp),
                            color = MaterialTheme.colorScheme.onSurfaceVariant,
                            modifier = Modifier.padding(10.dp),
                            lineHeight = 18.sp
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(18.dp))

            // Primary Start CTA
            HomeFitButton(
                text = strings.startWorkoutBtn,
                onClick = onStartWorkout,
                leadingIcon = Icons.Default.PlayArrow,
                testTag = "start_today_workout_btn"
            )
        }
    }
}

@Composable
fun WorkoutMetricChip(icon: ImageVector, label: String) {
    Row(verticalAlignment = Alignment.CenterVertically) {
        Icon(
            imageVector = icon,
            contentDescription = null,
            tint = MaterialTheme.colorScheme.primary,
            modifier = Modifier.size(17.dp)
        )
        Spacer(modifier = Modifier.width(4.dp))
        Text(
            text = label,
            style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.SemiBold),
            color = MaterialTheme.colorScheme.onSurface
        )
    }
}

@Composable
fun DashboardProgressSection(
    caloriesBurned: Int,
    caloriesGoal: Int,
    waterGlasses: Int,
    waterGoal: Int,
    stepsCount: Int,
    stepsGoal: Int,
    streakDays: Int,
    strings: AppStrings,
    onOpenStepDialog: () -> Unit,
    modifier: Modifier = Modifier
) {
    HomeFitCard(modifier = modifier.testTag("dashboard_progress_card")) {
        Column {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Text(
                    text = strings.progressRingTitle,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onSurface
                )

                // Streak Badge
                Surface(
                    shape = RoundedCornerShape(12.dp),
                    color = MaterialTheme.colorScheme.primaryContainer
                ) {
                    Row(
                        modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Icon(
                            imageVector = Icons.Default.Whatshot,
                            contentDescription = null,
                            tint = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.size(16.dp)
                        )
                        Spacer(modifier = Modifier.width(4.dp))
                        Text(
                            text = "$streakDays ${strings.streakDaysUnit} ${strings.streakTitle}",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.onPrimaryContainer
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(18.dp))

            // 3 Progress Rings row
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceAround
            ) {
                CircularStatRing(
                    current = caloriesBurned,
                    max = caloriesGoal,
                    unit = "kcal",
                    label = strings.caloriesBurnedToday,
                    ringColor = MaterialTheme.colorScheme.primary,
                    icon = Icons.Default.LocalFireDepartment
                )

                CircularStatRing(
                    current = waterGlasses,
                    max = waterGoal,
                    unit = strings.waterGlassesUnit,
                    label = strings.waterTrackerTitle,
                    ringColor = MaterialTheme.colorScheme.secondary,
                    icon = Icons.Default.Opacity
                )

                Box(modifier = Modifier.clickable { onOpenStepDialog() }) {
                    CircularStatRing(
                        current = stepsCount,
                        max = stepsGoal,
                        unit = strings.stepGoalUnit,
                        label = strings.stepTrackerTitle,
                        ringColor = MaterialTheme.colorScheme.tertiary,
                        icon = Icons.Default.DirectionsWalk
                    )
                }
            }
        }
    }
}

@Composable
fun CircularStatRing(
    current: Int,
    max: Int,
    unit: String,
    label: String,
    ringColor: Color,
    icon: ImageVector
) {
    val progress = (current.toFloat() / max.coerceAtLeast(1).toFloat()).coerceIn(0f, 1f)
    val animatedProgress by animateFloatAsState(targetValue = progress, label = "ring_progress")

    Column(
        horizontalAlignment = Alignment.CenterHorizontally,
        modifier = Modifier.width(96.dp)
    ) {
        Box(
            modifier = Modifier.size(76.dp),
            contentAlignment = Alignment.Center
        ) {
            Canvas(modifier = Modifier.fillMaxSize()) {
                val strokeWidth = 7.dp.toPx()
                // Track
                drawArc(
                    color = ringColor.copy(alpha = 0.2f),
                    startAngle = -90f,
                    sweepAngle = 360f,
                    useCenter = false,
                    style = Stroke(width = strokeWidth, cap = StrokeCap.Round)
                )
                // Progress
                drawArc(
                    color = ringColor,
                    startAngle = -90f,
                    sweepAngle = 360f * animatedProgress,
                    useCenter = false,
                    style = Stroke(width = strokeWidth, cap = StrokeCap.Round)
                )
            }

            Column(horizontalAlignment = Alignment.CenterHorizontally) {
                Icon(
                    imageVector = icon,
                    contentDescription = null,
                    tint = ringColor,
                    modifier = Modifier.size(16.dp)
                )
                Text(
                    text = "$current",
                    style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onSurface
                )
            }
        }

        Spacer(modifier = Modifier.height(6.dp))

        Text(
            text = label,
            style = MaterialTheme.typography.labelSmall.copy(fontSize = 11.sp),
            color = MaterialTheme.colorScheme.onSurfaceVariant,
            textAlign = TextAlign.Center,
            maxLines = 1
        )
        Text(
            text = "/$max $unit",
            style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
            color = MaterialTheme.colorScheme.onSurfaceVariant.copy(alpha = 0.7f),
            textAlign = TextAlign.Center
        )
    }
}

@Composable
fun WaterTrackerWidget(
    glassesCount: Int,
    goalGlasses: Int,
    strings: AppStrings,
    onAddGlass: () -> Unit,
    onRemoveGlass: () -> Unit,
    modifier: Modifier = Modifier,
    goalMlOverride: Int? = null
) {
    val safeGoalGlasses = goalGlasses.coerceIn(4, 22)
    val currentMl = glassesCount * 250
    val targetMl = goalMlOverride ?: (safeGoalGlasses * 250)
    val targetLiters = targetMl / 1000f
    val currentLiters = currentMl / 1000f

    HomeFitCard(
        borderColor = Color(0xFF38BDF8).copy(alpha = 0.45f),
        modifier = modifier.testTag("water_tracker_widget")
    ) {
        Column {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Row(
                    verticalAlignment = Alignment.CenterVertically,
                    modifier = Modifier.weight(1f)
                ) {
                    Box(
                        modifier = Modifier
                            .size(42.dp)
                            .clip(CircleShape)
                            .background(Color(0xFF38BDF8).copy(alpha = 0.16f)),
                        contentAlignment = Alignment.Center
                    ) {
                        Icon(
                            imageVector = Icons.Default.Opacity,
                            contentDescription = null,
                            tint = Color(0xFF38BDF8),
                            modifier = Modifier.size(22.dp)
                        )
                    }
                    Spacer(modifier = Modifier.width(12.dp))
                    Column {
                        Text(
                            text = strings.waterTrackerTitle,
                            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.ExtraBold),
                            color = MaterialTheme.colorScheme.onSurface
                        )
                        Text(
                            text = String.format(
                                java.util.Locale.US,
                                "%s: %d ml (%.2f L • %d %s)",
                                strings.waterTargetLabel,
                                targetMl,
                                targetLiters,
                                safeGoalGlasses,
                                strings.waterGlassesUnit.substringBefore(" ")
                            ),
                            style = MaterialTheme.typography.bodyMedium.copy(
                                fontSize = 12.sp,
                                fontWeight = FontWeight.SemiBold
                            ),
                            color = Color(0xFF38BDF8)
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(12.dp))

            // Live Hydration Progress Readout + Well-Spaced Vessel Buttons
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column {
                    Text(
                        text = String.format(
                            java.util.Locale.US,
                            "%d / %d ml",
                            currentMl,
                            targetMl
                        ),
                        style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Black),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                    Text(
                        text = String.format(
                            java.util.Locale.US,
                            "%.2f L / %.2f L (%d/%d)",
                            currentLiters,
                            targetLiters,
                            glassesCount,
                            safeGoalGlasses
                        ),
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }

                Row(
                    verticalAlignment = Alignment.CenterVertically,
                    horizontalArrangement = Arrangement.spacedBy(10.dp)
                ) {
                    Surface(
                        onClick = onRemoveGlass,
                        enabled = glassesCount > 0,
                        shape = RoundedCornerShape(12.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant,
                        border = BorderStroke(1.dp, MaterialTheme.colorScheme.outline),
                        modifier = Modifier.height(42.dp)
                    ) {
                        Row(
                            verticalAlignment = Alignment.CenterVertically,
                            modifier = Modifier.padding(horizontal = 12.dp)
                        ) {
                            Icon(
                                imageVector = Icons.Default.Remove,
                                contentDescription = "Remove water",
                                tint = if (glassesCount > 0) MaterialTheme.colorScheme.onSurface else MaterialTheme.colorScheme.outline,
                                modifier = Modifier.size(16.dp)
                            )
                            Spacer(modifier = Modifier.width(4.dp))
                            Text(
                                text = "250ml",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                color = if (glassesCount > 0) MaterialTheme.colorScheme.onSurface else MaterialTheme.colorScheme.outline
                            )
                        }
                    }

                    Surface(
                        onClick = onAddGlass,
                        shape = RoundedCornerShape(12.dp),
                        color = Color(0xFF0EA5E9).copy(alpha = 0.22f),
                        border = BorderStroke(1.2.dp, Color(0xFF38BDF8)),
                        modifier = Modifier
                            .height(42.dp)
                            .testTag("add_water_btn")
                    ) {
                        Row(
                            verticalAlignment = Alignment.CenterVertically,
                            modifier = Modifier.padding(horizontal = 14.dp)
                        ) {
                            Icon(
                                imageVector = Icons.Default.Add,
                                contentDescription = "Add water",
                                tint = Color(0xFF38BDF8),
                                modifier = Modifier.size(17.dp)
                            )
                            Spacer(modifier = Modifier.width(4.dp))
                            Text(
                                text = "250ml",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.ExtraBold),
                                color = Color(0xFF38BDF8)
                            )
                        }
                    }
                }
            }

            Spacer(modifier = Modifier.height(14.dp))

            // Multi-Row Adaptive Glass Grid (Max 7 glasses per row so 10-18 glasses never crowd or overflow)
            val glassIndices = (1..safeGoalGlasses).toList()
            Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                glassIndices.chunked(7).forEach { rowChunk ->
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.spacedBy(6.dp)
                    ) {
                        rowChunk.forEach { i ->
                            val isFilled = i <= glassesCount
                            Surface(
                                shape = RoundedCornerShape(8.dp),
                                color = if (isFilled) Color(0xFF0EA5E9) else MaterialTheme.colorScheme.surfaceVariant,
                                border = BorderStroke(
                                    width = 1.dp,
                                    color = if (isFilled) Color(0xFF38BDF8) else MaterialTheme.colorScheme.outline.copy(alpha = 0.5f)
                                ),
                                modifier = Modifier
                                    .weight(1f)
                                    .height(30.dp)
                            ) {
                                Box(contentAlignment = Alignment.Center) {
                                    if (isFilled) {
                                        Icon(
                                            imageVector = Icons.Default.Check,
                                            contentDescription = null,
                                            tint = Color.White,
                                            modifier = Modifier.size(14.dp)
                                        )
                                    } else {
                                        Text(
                                            text = "$i",
                                            style = MaterialTheme.typography.labelSmall.copy(fontSize = 9.sp),
                                            color = MaterialTheme.colorScheme.onSurfaceVariant
                                        )
                                    }
                                }
                            }
                        }
                        // Fill remaining slots in last row to keep uniform pill width
                        val remainder = 7 - rowChunk.size
                        if (remainder > 0 && safeGoalGlasses > 7) {
                            repeat(remainder) {
                                Spacer(modifier = Modifier.weight(1f))
                            }
                        }
                    }
                }
            }
        }
    }
}

@Composable
fun SmartCoachCard(
    tip: CoachTip,
    selectedLanguage: Language,
    strings: AppStrings,
    onActionClick: () -> Unit,
    modifier: Modifier = Modifier
) {
    val title = if (selectedLanguage == Language.BENGALI) tip.titleBn else tip.titleEn
    val message = if (selectedLanguage == Language.BENGALI) tip.messageBn else tip.messageEn
    val actionText = if (selectedLanguage == Language.BENGALI) tip.actionTextBn else tip.actionTextEn

    Card(
        modifier = modifier
            .fillMaxWidth()
            .testTag("smart_coach_card"),
        shape = RoundedCornerShape(18.dp),
        colors = CardDefaults.cardColors(
            containerColor = MaterialTheme.colorScheme.surface
        ),
        border = BorderStroke(1.dp, MaterialTheme.colorScheme.primary.copy(alpha = 0.35f))
    ) {
        Column(modifier = Modifier.padding(16.dp)) {
            Row(
                verticalAlignment = Alignment.CenterVertically,
                modifier = Modifier.fillMaxWidth()
            ) {
                Box(
                    modifier = Modifier
                        .size(34.dp)
                        .clip(CircleShape)
                        .background(MaterialTheme.colorScheme.primary.copy(alpha = 0.15f)),
                    contentAlignment = Alignment.Center
                ) {
                    Icon(
                        imageVector = Icons.Default.Psychology,
                        contentDescription = null,
                        tint = MaterialTheme.colorScheme.primary,
                        modifier = Modifier.size(20.dp)
                    )
                }
                Spacer(modifier = Modifier.width(10.dp))
                Column {
                    Text(
                        text = strings.smartCoachTitle,
                        style = MaterialTheme.typography.labelSmall.copy(color = MaterialTheme.colorScheme.primary, fontWeight = FontWeight.Bold)
                    )
                    Text(
                        text = title,
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                }
            }

            Spacer(modifier = Modifier.height(10.dp))

            Text(
                text = message,
                style = MaterialTheme.typography.bodyMedium,
                color = MaterialTheme.colorScheme.onSurfaceVariant,
                lineHeight = 20.sp
            )

            if (actionText != null) {
                Spacer(modifier = Modifier.height(12.dp))
                Button(
                    onClick = onActionClick,
                    shape = RoundedCornerShape(16.dp),
                    colors = ButtonDefaults.buttonColors(
                        containerColor = MaterialTheme.colorScheme.surfaceVariant,
                        contentColor = MaterialTheme.colorScheme.primary
                    ),
                    modifier = Modifier.heightIn(min = 36.dp)
                ) {
                    Text(
                        text = "⚡ $actionText",
                        style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.Bold)
                    )
                }
            }
        }
    }
}

@Composable
fun WeeklyMiniCalendar(
    completedDayIndices: List<Int>, // 0..6 (Mon..Sun)
    strings: AppStrings,
    modifier: Modifier = Modifier
) {
    val dayNames = listOf(
        strings.dayMon, strings.dayTue, strings.dayWed,
        strings.dayThu, strings.dayFri, strings.daySat, strings.daySun
    )

    // Current day of week in 0..6 (Mon = 0, Sun = 6)
    val calendar = Calendar.getInstance()
    val todayDow = when (calendar.get(Calendar.DAY_OF_WEEK)) {
        Calendar.MONDAY -> 0
        Calendar.TUESDAY -> 1
        Calendar.WEDNESDAY -> 2
        Calendar.THURSDAY -> 3
        Calendar.FRIDAY -> 4
        Calendar.SATURDAY -> 5
        Calendar.SUNDAY -> 6
        else -> 0
    }

    HomeFitCard(modifier = modifier.testTag("weekly_calendar_card")) {
        Column {
            Text(
                text = strings.weeklyCalendarTitle,
                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                color = MaterialTheme.colorScheme.onSurface
            )

            Spacer(modifier = Modifier.height(14.dp))

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                dayNames.forEachIndexed { index, name ->
                    val isToday = index == todayDow
                    val isCompleted = completedDayIndices.contains(index)

                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        modifier = Modifier.width(42.dp)
                    ) {
                        Text(
                            text = name,
                            style = MaterialTheme.typography.labelSmall.copy(
                                fontWeight = if (isToday) FontWeight.Bold else FontWeight.Normal,
                                color = if (isToday) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.onSurfaceVariant
                            )
                        )

                        Spacer(modifier = Modifier.height(6.dp))

                        Surface(
                            shape = CircleShape,
                            color = when {
                                isCompleted -> MaterialTheme.colorScheme.primary
                                isToday -> MaterialTheme.colorScheme.primary.copy(alpha = 0.2f)
                                else -> MaterialTheme.colorScheme.surfaceVariant
                            },
                            border = if (isToday) BorderStroke(1.5.dp, MaterialTheme.colorScheme.primary) else null,
                            modifier = Modifier.size(34.dp)
                        ) {
                            Box(contentAlignment = Alignment.Center) {
                                if (isCompleted) {
                                    Icon(
                                        imageVector = Icons.Default.Check,
                                        contentDescription = strings.statusCompleted,
                                        tint = Color.White,
                                        modifier = Modifier.size(16.dp)
                                    )
                                } else {
                                    Text(
                                        text = "${index + 1}",
                                        style = MaterialTheme.typography.labelSmall.copy(
                                            color = if (isToday) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.onSurfaceVariant
                                        )
                                    )
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}

@Composable
fun QuickActionsGrid(
    strings: AppStrings,
    on5MinClick: () -> Unit,
    on10MinClick: () -> Unit,
    on15MinClick: () -> Unit,
    onAddWaterClick: () -> Unit,
    onLogWeightClick: () -> Unit,
    onCreateCustomClick: () -> Unit,
    modifier: Modifier = Modifier
) {
    Column(modifier = modifier.fillMaxWidth()) {
        Text(
            text = strings.quickActionsTitle,
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.ExtraBold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(12.dp))

        // Spacious 2-Column x 3-Row Studio Action Grid so bilingual labels never crowd or wrap
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(12.dp)
        ) {
            QuickActionButton(
                label = strings.quick5Min,
                icon = Icons.Default.Timer,
                color = MaterialTheme.colorScheme.primary,
                onClick = on5MinClick,
                modifier = Modifier.weight(1f),
                tag = "quick_5min_btn"
            )
            QuickActionButton(
                label = strings.quick10Min,
                icon = Icons.Default.LocalFireDepartment,
                color = MaterialTheme.colorScheme.primary,
                onClick = on10MinClick,
                modifier = Modifier.weight(1f),
                tag = "quick_10min_btn"
            )
        }

        Spacer(modifier = Modifier.height(12.dp))

        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(12.dp)
        ) {
            QuickActionButton(
                label = strings.quick15Min,
                icon = Icons.Default.FitnessCenter,
                color = MaterialTheme.colorScheme.primary,
                onClick = on15MinClick,
                modifier = Modifier.weight(1f),
                tag = "quick_15min_btn"
            )
            QuickActionButton(
                label = strings.waterAddBtn,
                icon = Icons.Default.Opacity,
                color = Color(0xFF38BDF8),
                onClick = onAddWaterClick,
                modifier = Modifier.weight(1f),
                tag = "quick_water_btn"
            )
        }

        Spacer(modifier = Modifier.height(12.dp))

        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(12.dp)
        ) {
            QuickActionButton(
                label = strings.logWeightTitle,
                icon = Icons.Default.Scale,
                color = MaterialTheme.colorScheme.secondary,
                onClick = onLogWeightClick,
                modifier = Modifier.weight(1f),
                tag = "quick_weight_btn"
            )
            QuickActionButton(
                label = strings.customWorkoutTitle,
                icon = Icons.Default.LocalMall,
                color = MaterialTheme.colorScheme.tertiary,
                onClick = onCreateCustomClick,
                modifier = Modifier.weight(1f),
                tag = "quick_custom_btn"
            )
        }
    }
}

@Composable
fun QuickActionButton(
    label: String,
    icon: ImageVector,
    color: Color,
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    tag: String = "quick_action"
) {
    Surface(
        onClick = onClick,
        shape = RoundedCornerShape(16.dp),
        color = MaterialTheme.colorScheme.surface,
        border = BorderStroke(1.dp, MaterialTheme.colorScheme.outline.copy(alpha = 0.65f)),
        modifier = modifier
            .height(58.dp)
            .testTag(tag)
    ) {
        Row(
            modifier = Modifier.padding(horizontal = 12.dp, vertical = 8.dp),
            verticalAlignment = Alignment.CenterVertically,
            horizontalArrangement = Arrangement.Start
        ) {
            Box(
                modifier = Modifier
                    .size(34.dp)
                    .clip(RoundedCornerShape(10.dp))
                    .background(color.copy(alpha = 0.16f)),
                contentAlignment = Alignment.Center
            ) {
                Icon(
                    imageVector = icon,
                    contentDescription = null,
                    tint = color,
                    modifier = Modifier.size(18.dp)
                )
            }
            Spacer(modifier = Modifier.width(10.dp))
            Text(
                text = label,
                style = MaterialTheme.typography.labelLarge.copy(
                    fontWeight = FontWeight.Bold,
                    fontSize = 13.sp
                ),
                color = MaterialTheme.colorScheme.onSurface,
                maxLines = 1
            )
        }
    }
}

@Composable
fun LogWeightDialog(
    initialWeight: Float,
    strings: AppStrings,
    onDismiss: () -> Unit,
    onConfirm: (Float) -> Unit
) {
    var weightText by remember { mutableStateOf("$initialWeight") }
    var errorText by remember { mutableStateOf<String?>(null) }

    AlertDialog(
        onDismissRequest = onDismiss,
        title = {
            Text(
                text = strings.logWeightTitle,
                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
            )
        },
        text = {
            Column {
                OutlinedTextField(
                    value = weightText,
                    onValueChange = {
                        weightText = it
                        errorText = null
                    },
                    label = { Text(strings.logWeightHint) },
                    singleLine = true,
                    isError = errorText != null,
                    supportingText = {
                        if (errorText != null) {
                            Text(text = errorText!!, color = MaterialTheme.colorScheme.error)
                        }
                    },
                    modifier = Modifier
                        .fillMaxWidth()
                        .testTag("weight_dialog_input")
                )
            }
        },
        confirmButton = {
            TextButton(
                onClick = {
                    val parsed = weightText.toFloatOrNull()
                    if (parsed == null || parsed < 20f || parsed > 250f) {
                        errorText = "দয়া করে ২০ থেকে ২৫০ কেজির মধ্যে সঠিক ওজন লিখুন।"
                    } else {
                        onConfirm(parsed)
                    }
                }
            ) {
                Text(text = strings.saveBtn, fontWeight = FontWeight.Bold)
            }
        },
        dismissButton = {
            TextButton(onClick = onDismiss) {
                Text(text = strings.cancelBtn)
            }
        }
    )
}

@Composable
fun LogStepsDialog(
    currentSteps: Int,
    strings: AppStrings,
    onDismiss: () -> Unit,
    onConfirm: (Int) -> Unit
) {
    var stepsText by remember { mutableStateOf("$currentSteps") }
    var errorText by remember { mutableStateOf<String?>(null) }

    AlertDialog(
        onDismissRequest = onDismiss,
        title = {
            Text(
                text = strings.stepInputDialogTitle,
                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
            )
        },
        text = {
            Column {
                Text(
                    text = strings.stepManualActive,
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
                Spacer(modifier = Modifier.height(10.dp))
                OutlinedTextField(
                    value = stepsText,
                    onValueChange = {
                        stepsText = it
                        errorText = null
                    },
                    label = { Text(strings.stepInputHint) },
                    singleLine = true,
                    isError = errorText != null,
                    supportingText = {
                        if (errorText != null) {
                            Text(text = errorText!!, color = MaterialTheme.colorScheme.error)
                        }
                    },
                    modifier = Modifier
                        .fillMaxWidth()
                        .testTag("steps_dialog_input")
                )
            }
        },
        confirmButton = {
            TextButton(
                onClick = {
                    val parsed = stepsText.toIntOrNull()
                    if (parsed == null || parsed < 0 || parsed > 100000) {
                        errorText = "দয়া করে সঠিক পদক্ষেপ সংখ্যা লিখুন।"
                    } else {
                        onConfirm(parsed)
                    }
                }
            ) {
                Text(text = strings.saveBtn, fontWeight = FontWeight.Bold)
            }
        },
        dismissButton = {
            TextButton(onClick = onDismiss) {
                Text(text = strings.cancelBtn)
            }
        }
    )
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/main/MainAppScreen.kt`

```kotlin
package com.example.ui.screens.main

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.DeleteForever
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.Restaurant
import androidx.compose.material.icons.filled.ShowChart
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.domain.coach.CoachTip
import com.example.domain.coach.CoachTipType
import com.example.domain.model.UserProfile
import com.example.domain.recommendation.RecommendedWorkout
import com.example.ui.components.HomeFitBottomNav
import com.example.ui.components.HomeFitCard
import com.example.ui.components.HomeFitOutlinedButton
import com.example.ui.components.HomeFitTopBar
import com.example.ui.components.MainTab
import com.example.ui.screens.home.DashboardProgressSection
import com.example.ui.screens.home.LogStepsDialog
import com.example.ui.screens.home.LogWeightDialog
import com.example.ui.screens.home.QuickActionsGrid
import com.example.ui.screens.home.SmartCoachCard
import com.example.ui.screens.home.TodayWorkoutHeroCard
import com.example.ui.screens.home.WaterTrackerWidget
import com.example.ui.screens.home.WeeklyMiniCalendar
import java.util.Calendar

@Composable
fun MainAppScreen(
    currentTab: MainTab,
    userProfile: UserProfile?,
    recommendedWorkout: RecommendedWorkout,
    todayCaloriesBurned: Int,
    todayCaloriesGoal: Int,
    todayWaterGlasses: Int,
    todayWaterGoal: Int,
    todaySteps: Int,
    todayStepsGoal: Int,
    streakDays: Int,
    dailyIntakeCaloriesGoal: Int = 2200,
    todayWaterGoalMl: Int = todayWaterGoal * 250,
    smartCoachTip: CoachTip,
    completedWeekDays: List<Int>,
    isStepDialogOpen: Boolean,
    isWeightDialogOpen: Boolean,
    favoriteExerciseIds: List<String>,
    customWorkouts: List<com.example.data.local.entity.CustomWorkoutEntity>,
    weightLogs: List<com.example.data.local.entity.WeightLogEntity>,
    waterLogs: List<com.example.data.local.entity.WaterLogEntity>,
    workoutLogs: List<com.example.data.local.entity.WorkoutLogEntity>,
    todayNutritionLogs: List<com.example.data.local.entity.NutritionLogEntity>,
    savedMusicTracks: List<com.example.data.local.entity.SavedMusicTrackEntity>,
    challengeProgressList: List<com.example.data.local.entity.ChallengeProgressEntity>,
    voiceRepCounterEnabled: Boolean,
    musicState: com.example.core.audio.WorkoutMusicState,
    selectedLanguage: Language,
    isDarkMode: Boolean,
    strings: AppStrings,
    onTabSelected: (MainTab) -> Unit,
    onToggleLanguage: () -> Unit,
    onToggleTheme: () -> Unit,
    onAddWaterGlass: () -> Unit,
    onRemoveWaterGlass: () -> Unit,
    onOpenStepDialog: () -> Unit,
    onCloseStepDialog: () -> Unit,
    onSaveSteps: (Int) -> Unit,
    onOpenWeightDialog: () -> Unit,
    onCloseWeightDialog: () -> Unit,
    onSaveWeight: (Float) -> Unit,
    onToggleFavorite: (String) -> Unit,
    onSaveCustomWorkout: (String, List<String>, Int, Int) -> Unit,
    onDeleteCustomWorkout: (Long) -> Unit,
    onStartWorkout: () -> Unit,
    onStartWorkoutPlan: (com.example.domain.model.WorkoutPlan) -> Unit,
    onToggleChallengeDay: (String, Int) -> Unit,
    onToggleVoiceRepCounter: () -> Unit,
    onStartTabataSession: (String, String, Int, Int, Int, List<com.example.domain.model.Exercise>) -> Unit,
    onLogNutritionItem: (String, String, Int, Float, Float, Float) -> Unit,
    onDeleteNutritionLog: (Long) -> Unit,
    onSelectBeatPreset: (com.example.core.audio.OfflineBeatPreset) -> Unit,
    onPlayMusicTrack: (com.example.data.local.entity.SavedMusicTrackEntity) -> Unit,
    onToggleMusicPlayPause: () -> Unit,
    onNextMusicTrack: () -> Unit,
    onMusicVolumeChange: (Float) -> Unit,
    onAddMusicTrack: (String, String) -> Unit,
    onDeleteMusicTrack: (Long) -> Unit,
    onExportBackup: suspend () -> String,
    onImportBackup: suspend (String) -> Boolean,
    onSaveProfile: (name: String, age: Int, heightCm: Float, weightKg: Float, goal: String, fitnessLevel: String) -> Unit,
    onResetAllData: () -> Unit,
    isProSubscribed: Boolean = false,
    onOpenProDialog: () -> Unit = {},
    modifier: Modifier = Modifier
) {
    if (isWeightDialogOpen) {
        LogWeightDialog(
            initialWeight = userProfile?.weightKg ?: 65f,
            strings = strings,
            onDismiss = onCloseWeightDialog,
            onConfirm = onSaveWeight
        )
    }

    if (isStepDialogOpen) {
        LogStepsDialog(
            currentSteps = todaySteps,
            strings = strings,
            onDismiss = onCloseStepDialog,
            onConfirm = onSaveSteps
        )
    }

    Scaffold(
        modifier = modifier.fillMaxSize(),
        topBar = {
            HomeFitTopBar(
                title = strings.appName,
                currentLanguage = selectedLanguage,
                isDarkMode = isDarkMode,
                onToggleLanguage = onToggleLanguage,
                onToggleTheme = onToggleTheme
            )
        },
        bottomBar = {
            HomeFitBottomNav(
                selectedTab = currentTab,
                onTabSelected = onTabSelected,
                strings = strings
            )
        },
        containerColor = MaterialTheme.colorScheme.background
    ) { innerPadding ->
        Box(
            modifier = Modifier
                .fillMaxSize()
                .padding(innerPadding)
        ) {
            when (currentTab) {
                MainTab.HOME -> SmartHomeTabContent(
                    userProfile = userProfile,
                    recommendedWorkout = recommendedWorkout,
                    todayCaloriesBurned = todayCaloriesBurned,
                    todayCaloriesGoal = todayCaloriesGoal,
                    todayWaterGlasses = todayWaterGlasses,
                    todayWaterGoal = todayWaterGoal,
                    todayWaterGoalMl = todayWaterGoalMl,
                    todaySteps = todaySteps,
                    todayStepsGoal = todayStepsGoal,
                    streakDays = streakDays,
                    smartCoachTip = smartCoachTip,
                    completedWeekDays = completedWeekDays,
                    selectedLanguage = selectedLanguage,
                    strings = strings,
                    isProSubscribed = isProSubscribed,
                    onOpenProDialog = onOpenProDialog,
                    onStartWorkout = onStartWorkout,
                    onAddWaterGlass = onAddWaterGlass,
                    onRemoveWaterGlass = onRemoveWaterGlass,
                    onOpenStepDialog = onOpenStepDialog,
                    onOpenWeightDialog = onOpenWeightDialog,
                    onNavigateToWorkouts = { onTabSelected(MainTab.WORKOUTS) }
                )
                MainTab.WORKOUTS -> com.example.ui.screens.workouts.WorkoutsScreen(
                    favoriteExerciseIds = favoriteExerciseIds,
                    customWorkouts = customWorkouts,
                    challengeProgressList = challengeProgressList,
                    voiceRepCounterEnabled = voiceRepCounterEnabled,
                    savedMusicTracks = savedMusicTracks,
                    musicState = musicState,
                    selectedLanguage = selectedLanguage,
                    strings = strings,
                    isProSubscribed = isProSubscribed,
                    onOpenProDialog = onOpenProDialog,
                    onToggleFavorite = onToggleFavorite,
                    onSaveCustomWorkout = onSaveCustomWorkout,
                    onDeleteCustomWorkout = onDeleteCustomWorkout,
                    onStartWorkoutPlan = onStartWorkoutPlan,
                    onToggleChallengeDay = onToggleChallengeDay,
                    onToggleVoiceRepCounter = onToggleVoiceRepCounter,
                    onStartTabataSession = onStartTabataSession,
                    onSelectBeatPreset = onSelectBeatPreset,
                    onPlayMusicTrack = onPlayMusicTrack,
                    onToggleMusicPlayPause = onToggleMusicPlayPause,
                    onNextMusicTrack = onNextMusicTrack,
                    onMusicVolumeChange = onMusicVolumeChange,
                    onAddMusicTrack = onAddMusicTrack,
                    onDeleteMusicTrack = onDeleteMusicTrack
                )
                MainTab.PROGRESS -> com.example.ui.screens.progress.ProgressScreen(
                    userProfile = userProfile,
                    weightLogs = weightLogs,
                    waterLogs = waterLogs,
                    workoutLogs = workoutLogs,
                    challengeProgressList = challengeProgressList,
                    todayWaterGlasses = todayWaterGlasses,
                    streakDays = streakDays,
                    selectedLanguage = selectedLanguage,
                    strings = strings,
                    onOpenWeightDialog = onOpenWeightDialog,
                    onAddWaterGlass = onAddWaterGlass,
                    onExportBackup = onExportBackup,
                    onImportBackup = onImportBackup
                )
                MainTab.DIET -> com.example.ui.screens.diet.DietScreen(
                    userWeightKg = userProfile?.weightKg ?: 65f,
                    userHeightCm = userProfile?.heightCm ?: 170f,
                    userAge = userProfile?.age ?: 24,
                    userGender = userProfile?.gender ?: "male",
                    userGoal = userProfile?.goal ?: "fitness",
                    userWorkoutDays = userProfile?.workoutDaysPerWeek ?: 4,
                    dailyCalorieTarget = dailyIntakeCaloriesGoal,
                    todayWaterGlasses = todayWaterGlasses,
                    onAddWaterGlass = onAddWaterGlass,
                    onRemoveWaterGlass = onRemoveWaterGlass,
                    todayNutritionLogs = todayNutritionLogs,
                    selectedLanguage = selectedLanguage,
                    strings = strings,
                    isProSubscribed = isProSubscribed,
                    onOpenProDialog = onOpenProDialog,
                    onLogNutritionItem = onLogNutritionItem,
                    onDeleteNutritionLog = onDeleteNutritionLog
                )
                MainTab.PROFILE -> com.example.ui.screens.profile.ProfileScreen(
                    userProfile = userProfile,
                    selectedLanguage = selectedLanguage,
                    isDarkMode = isDarkMode,
                    strings = strings,
                    isProSubscribed = isProSubscribed,
                    onOpenProDialog = onOpenProDialog,
                    onToggleLanguage = onToggleLanguage,
                    onToggleTheme = onToggleTheme,
                    onSaveProfile = onSaveProfile,
                    onResetAllData = onResetAllData
                )
            }
        }
    }
}

@Composable
fun SmartHomeTabContent(
    userProfile: UserProfile?,
    recommendedWorkout: RecommendedWorkout,
    todayCaloriesBurned: Int,
    todayCaloriesGoal: Int,
    todayWaterGlasses: Int,
    todayWaterGoal: Int,
    todaySteps: Int,
    todayStepsGoal: Int,
    streakDays: Int,
    todayWaterGoalMl: Int = todayWaterGoal * 250,
    smartCoachTip: CoachTip,
    completedWeekDays: List<Int>,
    selectedLanguage: Language,
    strings: AppStrings,
    onStartWorkout: () -> Unit,
    onAddWaterGlass: () -> Unit,
    onRemoveWaterGlass: () -> Unit,
    onOpenStepDialog: () -> Unit,
    onOpenWeightDialog: () -> Unit,
    onNavigateToWorkouts: () -> Unit,
    isProSubscribed: Boolean = false,
    onOpenProDialog: () -> Unit = {}
) {
    val scrollState = rememberScrollState()

    // Time-based greeting calculation
    val hour = Calendar.getInstance().get(Calendar.HOUR_OF_DAY)
    val greetingPhrase = when {
        hour in 5..11 -> strings.greetingMorning
        hour in 12..15 -> strings.greetingAfternoon
        hour in 16..18 -> strings.greetingLateAfternoon
        hour in 19..22 -> strings.greetingEvening
        else -> strings.greetingNight
    }

    val userName = userProfile?.name.orEmpty().ifEmpty { "Athlete" }

    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(16.dp)
            .verticalScroll(scrollState)
            .testTag("smart_home_tab_content")
    ) {
        // Personalized Executive Greeting Header + VIP Pro Status Pill
        Row(
            modifier = Modifier.fillMaxWidth(),
            verticalAlignment = Alignment.CenterVertically,
            horizontalArrangement = Arrangement.SpaceBetween
        ) {
            Row(
                verticalAlignment = Alignment.CenterVertically,
                modifier = Modifier.weight(1f)
            ) {
                Box(
                    modifier = Modifier
                        .size(52.dp)
                        .clip(CircleShape)
                        .background(MaterialTheme.colorScheme.primaryContainer),
                    contentAlignment = Alignment.Center
                ) {
                    Text(
                        text = userName.take(1).uppercase(),
                        style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Black),
                        color = MaterialTheme.colorScheme.primary
                    )
                }
                Spacer(modifier = Modifier.width(12.dp))
                Column(modifier = Modifier.weight(1f)) {
                    Text(
                        text = "$greetingPhrase,",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Text(
                        text = userName,
                        style = MaterialTheme.typography.headlineSmall.copy(fontWeight = FontWeight.ExtraBold),
                        color = MaterialTheme.colorScheme.onBackground,
                        maxLines = 1
                    )
                }
            }

            Spacer(modifier = Modifier.width(8.dp))

            com.example.ui.components.ProStatusBadgePill(
                isProSubscribed = isProSubscribed,
                selectedLanguage = selectedLanguage,
                onClick = onOpenProDialog
            )
        }

        Spacer(modifier = Modifier.height(16.dp))

        // Today's Recommended Workout Hero Card
        TodayWorkoutHeroCard(
            workout = recommendedWorkout,
            selectedLanguage = selectedLanguage,
            strings = strings,
            onStartWorkout = onStartWorkout
        )

        Spacer(modifier = Modifier.height(14.dp))

        // VIP Pro Membership Activation / Status Banner Card
        com.example.ui.components.ProMembershipBannerCard(
            isProSubscribed = isProSubscribed,
            selectedLanguage = selectedLanguage,
            onOpenProDialog = onOpenProDialog
        )

        Spacer(modifier = Modifier.height(16.dp))

        // Progress Rings Section (Calories, Water, Steps)
        DashboardProgressSection(
            caloriesBurned = todayCaloriesBurned,
            caloriesGoal = todayCaloriesGoal,
            waterGlasses = todayWaterGlasses,
            waterGoal = todayWaterGoal,
            stepsCount = todaySteps,
            stepsGoal = todayStepsGoal,
            streakDays = streakDays,
            strings = strings,
            onOpenStepDialog = onOpenStepDialog
        )

        Spacer(modifier = Modifier.height(18.dp))

        // Smart Coach Card
        SmartCoachCard(
            tip = smartCoachTip,
            selectedLanguage = selectedLanguage,
            strings = strings,
            onActionClick = {
                when (smartCoachTip.type) {
                    CoachTipType.HYDRATION -> onAddWaterGlass()
                    CoachTipType.WEIGHT_REMINDER -> onOpenWeightDialog()
                    else -> onStartWorkout()
                }
            }
        )

        Spacer(modifier = Modifier.height(18.dp))

        // Water Tracker Visual Widget
        WaterTrackerWidget(
            glassesCount = todayWaterGlasses,
            goalGlasses = todayWaterGoal,
            strings = strings,
            onAddGlass = onAddWaterGlass,
            onRemoveGlass = onRemoveWaterGlass,
            goalMlOverride = todayWaterGoalMl
        )

        Spacer(modifier = Modifier.height(18.dp))

        // Weekly Calendar
        WeeklyMiniCalendar(
            completedDayIndices = completedWeekDays,
            strings = strings
        )

        Spacer(modifier = Modifier.height(18.dp))

        // Quick Actions Grid
        QuickActionsGrid(
            strings = strings,
            on5MinClick = onStartWorkout,
            on10MinClick = onStartWorkout,
            on15MinClick = onStartWorkout,
            onAddWaterClick = onAddWaterGlass,
            onLogWeightClick = onOpenWeightDialog,
            onCreateCustomClick = onNavigateToWorkouts
        )

        Spacer(modifier = Modifier.height(24.dp))
    }
}

@Composable
fun WorkoutsTabContent(strings: AppStrings) {
    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(20.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {
        Icon(
            imageVector = Icons.Default.FitnessCenter,
            contentDescription = null,
            tint = MaterialTheme.colorScheme.primary,
            modifier = Modifier.size(64.dp)
        )
        Spacer(modifier = Modifier.height(16.dp))
        Text(
            text = strings.navWorkouts,
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )
        Spacer(modifier = Modifier.height(8.dp))
        Text(
            text = "Phase 3-তে ৩০+ অফলাইন ব্যায়াম ও প্ল্যান সক্রিয় হবে।",
            style = MaterialTheme.typography.bodyMedium,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )
    }
}

@Composable
fun ProgressTabContent(strings: AppStrings) {
    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(20.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {
        Icon(
            imageVector = Icons.Default.ShowChart,
            contentDescription = null,
            tint = MaterialTheme.colorScheme.secondary,
            modifier = Modifier.size(64.dp)
        )
        Spacer(modifier = Modifier.height(16.dp))
        Text(
            text = strings.navProgress,
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )
        Spacer(modifier = Modifier.height(8.dp))
        Text(
            text = "Phase 5-তে অফলাইন চার্ট, ওজন ও পানি ট্র্যাকার যুক্ত হবে।",
            style = MaterialTheme.typography.bodyMedium,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )
    }
}

@Composable
fun DietTabContent(strings: AppStrings) {
    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(20.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {
        Icon(
            imageVector = Icons.Default.Restaurant,
            contentDescription = null,
            tint = MaterialTheme.colorScheme.tertiary,
            modifier = Modifier.size(64.dp)
        )
        Spacer(modifier = Modifier.height(16.dp))
        Text(
            text = strings.navDiet,
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )
        Spacer(modifier = Modifier.height(8.dp))
        Text(
            text = "Phase 6-তে বাঙালি পুষ্টিকর খাবার ও ক্যালরি হিসাব আসবে।",
            style = MaterialTheme.typography.bodyMedium,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )
    }
}

@Composable
fun ProfileTabContent(
    userProfile: UserProfile?,
    selectedLanguage: Language,
    isDarkMode: Boolean,
    strings: AppStrings,
    onToggleLanguage: () -> Unit,
    onToggleTheme: () -> Unit,
    onResetAllData: () -> Unit
) {
    var showResetDialog by remember { mutableStateOf(false) }

    if (showResetDialog) {
        AlertDialog(
            onDismissRequest = { showResetDialog = false },
            title = {
                Text(
                    text = strings.resetConfirmTitle,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                )
            },
            text = {
                Text(
                    text = strings.resetConfirmBody,
                    style = MaterialTheme.typography.bodyMedium
                )
            },
            confirmButton = {
                TextButton(
                    onClick = {
                        showResetDialog = false
                        onResetAllData()
                    }
                ) {
                    Text(
                        text = strings.deleteBtn,
                        color = MaterialTheme.colorScheme.error,
                        style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Bold)
                    )
                }
            },
            dismissButton = {
                TextButton(onClick = { showResetDialog = false }) {
                    Text(text = strings.cancelBtn)
                }
            }
        )
    }

    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(20.dp)
            .verticalScroll(rememberScrollState())
            .testTag("profile_tab_content")
    ) {
        Text(
            text = strings.settingsTitle,
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(20.dp))

        // Language Switch Card
        HomeFitCard {
            Row(
                modifier = Modifier.fillMaxWidth(),
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Column {
                    Text(
                        text = strings.languageSetting,
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                    )
                    Text(
                        text = selectedLanguage.displayName,
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.primary
                    )
                }
                HomeFitOutlinedButton(
                    text = if (selectedLanguage == Language.BENGALI) "Switch to EN" else "বাংলা করুন",
                    onClick = onToggleLanguage,
                    modifier = Modifier.width(150.dp)
                )
            }
        }

        Spacer(modifier = Modifier.height(14.dp))

        // Theme Switch Card
        HomeFitCard {
            Row(
                modifier = Modifier.fillMaxWidth(),
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Column {
                    Text(
                        text = strings.themeSetting,
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                    )
                    Text(
                        text = if (isDarkMode) strings.themeDark else strings.themeLight,
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.primary
                    )
                }
                HomeFitOutlinedButton(
                    text = if (isDarkMode) strings.themeLight else strings.themeDark,
                    onClick = onToggleTheme,
                    modifier = Modifier.width(150.dp)
                )
            }
        }

        Spacer(modifier = Modifier.height(24.dp))

        // Delete All Data Button
        HomeFitOutlinedButton(
            text = strings.resetDataBtn,
            onClick = { showResetDialog = true },
            leadingIcon = Icons.Default.DeleteForever,
            testTag = "delete_all_data_btn"
        )
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/onboarding/HealthDisclaimerScreen.kt`

```kotlin
package com.example.ui.screens.onboarding

import androidx.activity.compose.BackHandler
import androidx.compose.foundation.background
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.HealthAndSafety
import androidx.compose.material.icons.filled.WarningAmber
import androidx.compose.material3.Checkbox
import androidx.compose.material3.CheckboxDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitCard

@Composable
fun HealthDisclaimerScreen(
    disclaimerAccepted: Boolean,
    strings: AppStrings,
    onAcceptChanged: (Boolean) -> Unit,
    onConfirm: () -> Unit,
    onBack: () -> Unit,
    modifier: Modifier = Modifier
) {
    BackHandler(onBack = onBack)

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(MaterialTheme.colorScheme.background)
            .padding(24.dp)
            .testTag("health_disclaimer_screen")
    ) {
        Spacer(modifier = Modifier.height(20.dp))

        Box(
            modifier = Modifier
                .align(Alignment.CenterHorizontally)
                .size(90.dp)
                .clip(CircleShape)
                .background(MaterialTheme.colorScheme.error.copy(alpha = 0.12f)),
            contentAlignment = Alignment.Center
        ) {
            Icon(
                imageVector = Icons.Default.HealthAndSafety,
                contentDescription = null,
                tint = MaterialTheme.colorScheme.error,
                modifier = Modifier.size(52.dp)
            )
        }

        Spacer(modifier = Modifier.height(28.dp))

        Text(
            text = strings.disclaimerTitle,
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground,
            textAlign = TextAlign.Center,
            modifier = Modifier.fillMaxWidth()
        )

        Spacer(modifier = Modifier.height(24.dp))

        HomeFitCard(
            borderColor = MaterialTheme.colorScheme.error.copy(alpha = 0.35f),
            modifier = Modifier.testTag("disclaimer_card")
        ) {
            Column {
                Row(
                    verticalAlignment = Alignment.CenterVertically,
                    modifier = Modifier.fillMaxWidth()
                ) {
                    Icon(
                        imageVector = Icons.Default.WarningAmber,
                        contentDescription = null,
                        tint = MaterialTheme.colorScheme.error
                    )
                    Spacer(modifier = Modifier.width(8.dp))
                    Text(
                        text = strings.disclaimerWarning,
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.error
                    )
                }

                Spacer(modifier = Modifier.height(14.dp))

                Text(
                    text = strings.disclaimerBody,
                    style = MaterialTheme.typography.bodyLarge,
                    color = MaterialTheme.colorScheme.onSurface,
                    lineHeight = 24.sp
                )
            }
        }

        Spacer(modifier = Modifier.weight(1f))

        // Checkbox confirmation
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .clickable { onAcceptChanged(!disclaimerAccepted) }
                .padding(vertical = 12.dp)
                .testTag("disclaimer_checkbox_row"),
            verticalAlignment = Alignment.CenterVertically
        ) {
            Checkbox(
                checked = disclaimerAccepted,
                onCheckedChange = onAcceptChanged,
                colors = CheckboxDefaults.colors(
                    checkedColor = MaterialTheme.colorScheme.primary,
                    uncheckedColor = MaterialTheme.colorScheme.outline
                ),
                modifier = Modifier.testTag("disclaimer_checkbox")
            )
            Spacer(modifier = Modifier.width(8.dp))
            Text(
                text = strings.disclaimerCheckbox,
                style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.Medium),
                color = MaterialTheme.colorScheme.onBackground
            )
        }

        Spacer(modifier = Modifier.height(16.dp))

        HomeFitButton(
            text = strings.disclaimerConfirmBtn,
            onClick = onConfirm,
            enabled = disclaimerAccepted,
            testTag = "disclaimer_submit_button"
        )
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/onboarding/NameInputScreen.kt`

```kotlin
package com.example.ui.screens.onboarding

import androidx.activity.compose.BackHandler
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.text.KeyboardActions
import androidx.compose.foundation.text.KeyboardOptions
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Clear
import androidx.compose.material.icons.filled.Person
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.OutlinedTextFieldDefaults
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.input.ImeAction
import androidx.compose.ui.text.input.KeyboardCapitalization
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.ui.components.HomeFitButton

@Composable
fun NameInputScreen(
    name: String,
    errorMessage: String?,
    strings: AppStrings,
    onNameChange: (String) -> Unit,
    onSubmit: () -> Unit,
    onBack: () -> Unit,
    modifier: Modifier = Modifier
) {
    BackHandler(onBack = onBack)

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(MaterialTheme.colorScheme.background)
            .padding(24.dp)
            .testTag("name_input_screen")
    ) {
        Spacer(modifier = Modifier.height(24.dp))

        // Avatar Preview
        Box(
            modifier = Modifier
                .align(Alignment.CenterHorizontally)
                .size(96.dp)
                .clip(CircleShape)
                .background(MaterialTheme.colorScheme.primaryContainer),
            contentAlignment = Alignment.Center
        ) {
            val initial = name.trim().take(1).uppercase()
            if (initial.isNotEmpty()) {
                Text(
                    text = initial,
                    style = MaterialTheme.typography.displayLarge.copy(
                        fontSize = 40.sp,
                        fontWeight = FontWeight.Black
                    ),
                    color = MaterialTheme.colorScheme.primary
                )
            } else {
                Icon(
                    imageVector = Icons.Default.Person,
                    contentDescription = null,
                    tint = MaterialTheme.colorScheme.primary,
                    modifier = Modifier.size(48.dp)
                )
            }
        }

        Spacer(modifier = Modifier.height(28.dp))

        Text(
            text = strings.nameTitle,
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground,
            textAlign = TextAlign.Center,
            modifier = Modifier.fillMaxWidth()
        )

        Spacer(modifier = Modifier.height(10.dp))

        Text(
            text = strings.nameSubtitle,
            style = MaterialTheme.typography.bodyLarge,
            color = MaterialTheme.colorScheme.onSurfaceVariant,
            textAlign = TextAlign.Center,
            modifier = Modifier.fillMaxWidth()
        )

        Spacer(modifier = Modifier.height(36.dp))

        OutlinedTextField(
            value = name,
            onValueChange = onNameChange,
            placeholder = { Text(strings.namePlaceholder) },
            isError = errorMessage != null,
            supportingText = {
                if (errorMessage != null) {
                    Text(
                        text = errorMessage,
                        color = MaterialTheme.colorScheme.error,
                        style = MaterialTheme.typography.bodyMedium
                    )
                }
            },
            trailingIcon = {
                if (name.isNotEmpty()) {
                    IconButton(onClick = { onNameChange("") }) {
                        Icon(
                            imageVector = Icons.Default.Clear,
                            contentDescription = "Clear name",
                            tint = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            },
            singleLine = true,
            keyboardOptions = KeyboardOptions(
                capitalization = KeyboardCapitalization.Words,
                imeAction = ImeAction.Done
            ),
            keyboardActions = KeyboardActions(
                onDone = { onSubmit() }
            ),
            shape = RoundedCornerShape(16.dp),
            colors = OutlinedTextFieldDefaults.colors(
                focusedBorderColor = MaterialTheme.colorScheme.primary,
                unfocusedBorderColor = MaterialTheme.colorScheme.outline,
                focusedContainerColor = MaterialTheme.colorScheme.surface,
                unfocusedContainerColor = MaterialTheme.colorScheme.surface
            ),
            modifier = Modifier
                .fillMaxWidth()
                .testTag("name_text_field")
        )

        Spacer(modifier = Modifier.weight(1f))

        HomeFitButton(
            text = strings.continueBtn,
            onClick = onSubmit,
            testTag = "name_continue_button"
        )
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/onboarding/ProfileSetupScreen.kt`

```kotlin
package com.example.ui.screens.onboarding

import androidx.activity.compose.BackHandler
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.LocalFireDepartment
import androidx.compose.material.icons.filled.MonitorWeight
import androidx.compose.material.icons.filled.Science
import androidx.compose.material.icons.filled.WaterDrop
import androidx.compose.material3.HorizontalDivider
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Slider
import androidx.compose.material3.SliderDefaults
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.domain.calculations.HealthCalculations
import com.example.ui.components.AthleticChoiceChip
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitCard
import com.example.ui.components.LuxurySelectionOptionCard
import java.util.Locale
import kotlin.math.roundToInt

@Composable
fun ProfileSetupScreen(
    age: Int,
    heightCm: Float,
    weightKg: Float,
    gender: String,
    goal: String,
    level: String,
    daysPerWeek: Int,
    equipment: String,
    liveBmi: Float,
    liveBmiCategory: String,
    liveCalories: Int,
    strings: AppStrings,
    onAgeChange: (Int) -> Unit,
    onHeightChange: (Float) -> Unit,
    onWeightChange: (Float) -> Unit,
    onGenderChange: (String) -> Unit,
    onGoalChange: (String) -> Unit,
    onLevelChange: (String) -> Unit,
    onDaysChange: (Int) -> Unit,
    onEquipmentChange: (String) -> Unit,
    onProceed: () -> Unit,
    onBack: () -> Unit,
    modifier: Modifier = Modifier
) {
    BackHandler(onBack = onBack)

    val scrollState = rememberScrollState()
    val isBengali = strings.appTagline.contains("এলিট") || strings.genderMale == "পুরুষ"

    // Live scientific hydration & metabolic breakdown computed directly for the calibration HUD
    val hydration = HealthCalculations.calculateScientificHydration(
        weightKg = weightKg,
        age = age,
        gender = gender,
        goal = goal,
        workoutDaysPerWeek = daysPerWeek
    )
    val metabolic = HealthCalculations.calculateMetabolicBreakdown(
        weightKg = weightKg,
        heightCm = heightCm,
        age = age,
        gender = gender,
        goal = goal,
        workoutDaysPerWeek = daysPerWeek
    )

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(MaterialTheme.colorScheme.background)
            .padding(horizontal = 20.dp, vertical = 16.dp)
            .verticalScroll(scrollState)
            .testTag("profile_setup_screen")
    ) {
        Text(
            text = strings.profileTitle,
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.ExtraBold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(6.dp))

        Text(
            text = strings.profileSubtitle,
            style = MaterialTheme.typography.bodyMedium,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )

        Spacer(modifier = Modifier.height(18.dp))

        // Live Clinical Biometric & Hydration HUD (Top Featured Card so user sees changes immediately)
        HomeFitCard(
            borderColor = MaterialTheme.colorScheme.primary.copy(alpha = 0.65f),
            modifier = Modifier.testTag("live_metrics_card")
        ) {
            Column {
                Row(
                    verticalAlignment = Alignment.CenterVertically,
                    horizontalArrangement = Arrangement.SpaceBetween,
                    modifier = Modifier.fillMaxWidth()
                ) {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        Icon(
                            imageVector = Icons.Default.Science,
                            contentDescription = null,
                            tint = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.size(20.dp)
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text(
                            text = strings.liveMetricsTitle,
                            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.ExtraBold),
                            color = MaterialTheme.colorScheme.primary
                        )
                    }
                    Surface(
                        shape = RoundedCornerShape(50),
                        color = MaterialTheme.colorScheme.primary.copy(alpha = 0.16f)
                    ) {
                        Text(
                            text = "LIVE SYNC",
                            style = MaterialTheme.typography.labelSmall.copy(
                                fontSize = 9.sp,
                                fontWeight = FontWeight.Black
                            ),
                            color = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.padding(horizontal = 8.dp, vertical = 3.dp)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(14.dp))

                // 2x2 Clinical Biometric Telemetry Grid
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(10.dp)
                ) {
                    // 1. BMI Box
                    Surface(
                        shape = RoundedCornerShape(14.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.55f),
                        border = BorderStroke(1.dp, MaterialTheme.colorScheme.outline.copy(alpha = 0.6f)),
                        modifier = Modifier.weight(1f)
                    ) {
                        Column(modifier = Modifier.padding(12.dp)) {
                            Row(verticalAlignment = Alignment.CenterVertically) {
                                Icon(
                                    imageVector = Icons.Default.MonitorWeight,
                                    contentDescription = null,
                                    tint = MaterialTheme.colorScheme.secondary,
                                    modifier = Modifier.size(15.dp)
                                )
                                Spacer(modifier = Modifier.width(5.dp))
                                Text(
                                    text = "BMI INDEX",
                                    style = MaterialTheme.typography.labelSmall,
                                    color = MaterialTheme.colorScheme.onSurfaceVariant
                                )
                            }
                            Spacer(modifier = Modifier.height(4.dp))
                            Text(
                                text = "$liveBmi",
                                style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Black),
                                color = MaterialTheme.colorScheme.onSurface,
                                modifier = Modifier.testTag("live_bmi_value")
                            )
                            Text(
                                text = liveBmiCategory,
                                style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
                                color = MaterialTheme.colorScheme.secondary,
                                maxLines = 1
                            )
                        }
                    }

                    // 2. Scientific Daily Water Box (ml + Liters + Glasses)
                    Surface(
                        shape = RoundedCornerShape(14.dp),
                        color = Color(0xFF0EA5E9).copy(alpha = 0.12f),
                        border = BorderStroke(1.dp, Color(0xFF38BDF8).copy(alpha = 0.45f)),
                        modifier = Modifier.weight(1f)
                    ) {
                        Column(modifier = Modifier.padding(12.dp)) {
                            Row(verticalAlignment = Alignment.CenterVertically) {
                                Icon(
                                    imageVector = Icons.Default.WaterDrop,
                                    contentDescription = null,
                                    tint = Color(0xFF38BDF8),
                                    modifier = Modifier.size(15.dp)
                                )
                                Spacer(modifier = Modifier.width(5.dp))
                                Text(
                                    text = if (isBengali) "পানির লক্ষ্যমাত্রা" else "DAILY WATER",
                                    style = MaterialTheme.typography.labelSmall,
                                    color = Color(0xFF38BDF8)
                                )
                            }
                            Spacer(modifier = Modifier.height(4.dp))
                            Text(
                                text = String.format(Locale.US, "%.2f L (%d ml)", hydration.totalLiters, hydration.totalMl),
                                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Black),
                                color = MaterialTheme.colorScheme.onSurface
                            )
                            Text(
                                text = if (isBengali) {
                                    "${hydration.targetGlasses250Ml} গ্লাস • ${hydration.ageMetabolicFactorMlPerKg.toInt()} ml/kg + ঘাম"
                                } else {
                                    "${hydration.targetGlasses250Ml} glasses • ${hydration.ageMetabolicFactorMlPerKg.toInt()} ml/kg + sweat"
                                },
                                style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
                                color = Color(0xFF38BDF8),
                                maxLines = 1
                            )
                        }
                    }
                }

                Spacer(modifier = Modifier.height(10.dp))

                // Second Row: TDEE Calorie Target & Daily Protein Synthesis
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(10.dp)
                ) {
                    Surface(
                        shape = RoundedCornerShape(14.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.55f),
                        border = BorderStroke(1.dp, MaterialTheme.colorScheme.outline.copy(alpha = 0.6f)),
                        modifier = Modifier.weight(1f)
                    ) {
                        Column(modifier = Modifier.padding(12.dp)) {
                            Row(verticalAlignment = Alignment.CenterVertically) {
                                Icon(
                                    imageVector = Icons.Default.LocalFireDepartment,
                                    contentDescription = null,
                                    tint = MaterialTheme.colorScheme.primary,
                                    modifier = Modifier.size(15.dp)
                                )
                                Spacer(modifier = Modifier.width(5.dp))
                                Text(
                                    text = if (isBengali) "দৈনিক ক্যালরি (TDEE)" else "DAILY TDEE",
                                    style = MaterialTheme.typography.labelSmall,
                                    color = MaterialTheme.colorScheme.onSurfaceVariant
                                )
                            }
                            Spacer(modifier = Modifier.height(4.dp))
                            Text(
                                text = "$liveCalories kcal",
                                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Black),
                                color = MaterialTheme.colorScheme.primary,
                                modifier = Modifier.testTag("live_calories_value")
                            )
                            Text(
                                text = "BMR: ${metabolic.bmrCalories} kcal",
                                style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
                                color = MaterialTheme.colorScheme.onSurfaceVariant
                            )
                        }
                    }

                    Surface(
                        shape = RoundedCornerShape(14.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.55f),
                        border = BorderStroke(1.dp, MaterialTheme.colorScheme.outline.copy(alpha = 0.6f)),
                        modifier = Modifier.weight(1f)
                    ) {
                        Column(modifier = Modifier.padding(12.dp)) {
                            Text(
                                text = if (isBengali) "দৈনিক প্রোটিন ও বার্ন" else "PROTEIN & BURN",
                                style = MaterialTheme.typography.labelSmall,
                                color = MaterialTheme.colorScheme.onSurfaceVariant
                            )
                            Spacer(modifier = Modifier.height(4.dp))
                            Text(
                                text = "${metabolic.proteinGrams}g Protein",
                                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Black),
                                color = MaterialTheme.colorScheme.secondary
                            )
                            Text(
                                text = if (isBengali) "ওয়ার্কআউট বার্ন: ${metabolic.targetWorkoutBurnCalories} kcal" else "Burn Target: ${metabolic.targetWorkoutBurnCalories} kcal",
                                style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
                                color = MaterialTheme.colorScheme.onSurfaceVariant,
                                maxLines = 1
                            )
                        }
                    }
                }

                Spacer(modifier = Modifier.height(10.dp))
                HorizontalDivider(color = MaterialTheme.colorScheme.outline.copy(alpha = 0.4f))
                Spacer(modifier = Modifier.height(8.dp))

                Text(
                    text = if (isBengali) hydration.formulaSummaryBn else hydration.formulaSummaryEn,
                    style = MaterialTheme.typography.bodyMedium.copy(
                        fontSize = 12.sp,
                        fontWeight = FontWeight.SemiBold
                    ),
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        }

        Spacer(modifier = Modifier.height(16.dp))

        // 1. Age, Height, Weight Sliders Card (Supports 25 kg to 160 kg)
        HomeFitCard {
            Column {
                // Age Slider (10 - 80 yrs)
                SliderControlRow(
                    label = strings.ageLabel,
                    valueText = "$age",
                    value = age.toFloat(),
                    valueRange = 10f..80f,
                    onValueChange = { onAgeChange(it.roundToInt()) },
                    testTag = "age_slider"
                )

                Spacer(modifier = Modifier.height(14.dp))

                // Height Slider (120 - 220 cm)
                SliderControlRow(
                    label = strings.heightLabel,
                    valueText = "${heightCm.roundToInt()} cm",
                    value = heightCm,
                    valueRange = 120f..220f,
                    onValueChange = { onHeightChange(it.roundToInt().toFloat()) },
                    testTag = "height_slider"
                )

                Spacer(modifier = Modifier.height(14.dp))

                // Weight Slider (25 - 160 kg — supports lightweight youth & heavy lifters)
                SliderControlRow(
                    label = strings.weightLabel,
                    valueText = "${weightKg.roundToInt()} kg",
                    value = weightKg,
                    valueRange = 25f..160f,
                    onValueChange = { onWeightChange(it.roundToInt().toFloat()) },
                    testTag = "weight_slider"
                )
            }
        }

        Spacer(modifier = Modifier.height(16.dp))

        // 2. Biological Gender Selection
        HomeFitCard {
            Column {
                Text(
                    text = strings.genderLabel,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onSurface
                )
                Spacer(modifier = Modifier.height(12.dp))
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(10.dp)
                ) {
                    val genderOptions = listOf(
                        "male" to strings.genderMale,
                        "female" to strings.genderFemale,
                        "other" to strings.genderOther
                    )
                    genderOptions.forEach { (key, label) ->
                        AthleticChoiceChip(
                            label = label,
                            selected = gender == key,
                            onClick = { onGenderChange(key) },
                            modifier = Modifier.weight(1f),
                            testTag = "gender_chip_$key"
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(16.dp))

        // 3. Primary Goal & Experience Level (Full-Width Luxury Cards — Zero Text Wrapping)
        HomeFitCard {
            Column {
                Text(
                    text = strings.goalLabel,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onSurface
                )
                Spacer(modifier = Modifier.height(12.dp))

                val goalOptions = listOf(
                    Triple(
                        "weight_loss",
                        strings.goalWeightLoss,
                        if (isBengali) "ক্যালরি ডেফিসিট • কার্ডিও ও ফ্যাট বার্ন ফোকাস" else "Calorie deficit • High metabolic fat burn"
                    ),
                    Triple(
                        "muscle_building",
                        strings.goalMuscleBuilding,
                        if (isBengali) "উচ্চ প্রোটিন (১.৮৫ গ্রাম/কেজি) • প্রগ্রেসিভ স্ট্রেংথ" else "High protein (1.85g/kg) • Progressive hypertrophy"
                    ),
                    Triple(
                        "fitness",
                        strings.goalGeneralFitness,
                        if (isBengali) "সুষম মেটাবলিজম • কোর স্ট্যামিনা ও মোবিলিটি" else "Balanced TDEE • Core stamina & athletic mobility"
                    )
                )
                Column(verticalArrangement = Arrangement.spacedBy(10.dp)) {
                    goalOptions.forEach { (key, title, subtitle) ->
                        LuxurySelectionOptionCard(
                            title = title,
                            subtitle = subtitle,
                            selected = goal == key,
                            onClick = { onGoalChange(key) },
                            testTag = "goal_chip_$key"
                        )
                    }
                }

                Spacer(modifier = Modifier.height(20.dp))

                Text(
                    text = strings.levelLabel,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onSurface
                )
                Spacer(modifier = Modifier.height(12.dp))

                val levelOptions = listOf(
                    Triple("beginner", strings.levelBeginner, "30s Work / 20s Rest"),
                    Triple("intermediate", strings.levelIntermediate, "45s Work / 15s Rest"),
                    Triple("advanced", strings.levelAdvanced, "60s Work / 10s Rest")
                )
                Column(verticalArrangement = Arrangement.spacedBy(10.dp)) {
                    levelOptions.forEach { (key, title, badge) ->
                        LuxurySelectionOptionCard(
                            title = title,
                            badgeText = badge,
                            selected = level == key,
                            onClick = { onLevelChange(key) },
                            testTag = "level_chip_$key"
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(16.dp))

        // 4. Days Per Week & Equipment Selection (Full-Width Luxury Cards)
        HomeFitCard {
            Column {
                SliderControlRow(
                    label = strings.daysPerWeekLabel,
                    valueText = "$daysPerWeek ${strings.daysUnit}",
                    value = daysPerWeek.toFloat(),
                    valueRange = 1f..7f,
                    steps = 5,
                    onValueChange = { onDaysChange(it.roundToInt()) },
                    testTag = "days_slider"
                )

                Spacer(modifier = Modifier.height(18.dp))

                Text(
                    text = strings.equipmentLabel,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onSurface
                )
                Spacer(modifier = Modifier.height(12.dp))

                val equipmentOptions = listOf(
                    Triple(
                        "none",
                        strings.equipNone,
                        if (isBengali) "পুশ-আপ, স্কোয়াট, প্ল্যাঙ্ক ও ক্যালিস্থেনিক্স" else "Push-ups, squats, planks & calisthenics"
                    ),
                    Triple(
                        "basic",
                        strings.equipBasic,
                        if (isBengali) "চেয়ার ডিপস, ইনক্লাইন পুশ-আপ ও হোম সাপোর্ট" else "Chair dips, incline push-ups & home props"
                    ),
                    Triple(
                        "full",
                        strings.equipFull,
                        if (isBengali) "ডাম্বেল কার্ল, ওয়েটেড স্কোয়াট ও জিম স্টুডিও" else "Dumbbell curls, weighted squats & gym studio"
                    )
                )
                Column(verticalArrangement = Arrangement.spacedBy(10.dp)) {
                    equipmentOptions.forEach { (key, title, subtitle) ->
                        LuxurySelectionOptionCard(
                            title = title,
                            subtitle = subtitle,
                            selected = equipment == key,
                            onClick = { onEquipmentChange(key) },
                            testTag = "equip_chip_$key"
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(24.dp))

        HomeFitButton(
            text = strings.continueBtn,
            onClick = onProceed,
            testTag = "profile_continue_button"
        )

        Spacer(modifier = Modifier.height(24.dp))
    }
}

@Composable
private fun SliderControlRow(
    label: String,
    valueText: String,
    value: Float,
    valueRange: ClosedFloatingPointRange<Float>,
    steps: Int = 0,
    onValueChange: (Float) -> Unit,
    testTag: String
) {
    Column(modifier = Modifier.fillMaxWidth()) {
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.SpaceBetween,
            verticalAlignment = Alignment.CenterVertically
        ) {
            Text(
                text = label,
                style = MaterialTheme.typography.bodyLarge.copy(fontWeight = FontWeight.SemiBold),
                color = MaterialTheme.colorScheme.onSurface
            )
            Surface(
                shape = RoundedCornerShape(8.dp),
                color = MaterialTheme.colorScheme.primary.copy(alpha = 0.16f)
            ) {
                Text(
                    text = valueText,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.ExtraBold),
                    color = MaterialTheme.colorScheme.primary,
                    modifier = Modifier.padding(horizontal = 10.dp, vertical = 4.dp)
                )
            }
        }
        Slider(
            value = value,
            onValueChange = onValueChange,
            valueRange = valueRange,
            steps = steps,
            colors = SliderDefaults.colors(
                thumbColor = MaterialTheme.colorScheme.primary,
                activeTrackColor = MaterialTheme.colorScheme.primary,
                inactiveTrackColor = MaterialTheme.colorScheme.surfaceVariant
            ),
            modifier = Modifier
                .fillMaxWidth()
                .testTag(testTag)
        )
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/onboarding/WelcomeSlidesScreen.kt`

```kotlin
package com.example.ui.screens.onboarding

import androidx.activity.compose.BackHandler
import androidx.compose.animation.AnimatedContent
import androidx.compose.animation.core.FastOutSlowInEasing
import androidx.compose.animation.core.RepeatMode
import androidx.compose.animation.core.animateFloat
import androidx.compose.animation.core.infiniteRepeatable
import androidx.compose.animation.core.rememberInfiniteTransition
import androidx.compose.animation.core.tween
import androidx.compose.animation.fadeIn
import androidx.compose.animation.fadeOut
import androidx.compose.animation.togetherWith
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.Canvas
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.automirrored.filled.ArrowForward
import androidx.compose.material.icons.filled.Bolt
import androidx.compose.material.icons.filled.GraphicEq
import androidx.compose.material.icons.filled.Science
import androidx.compose.material.icons.filled.Verified
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.geometry.CornerRadius
import androidx.compose.ui.geometry.Offset
import androidx.compose.ui.geometry.Size
import androidx.compose.ui.graphics.Brush
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.StrokeCap
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.text.style.TextOverflow
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.ui.components.HomeFitButton
import com.example.ui.components.ProStatusBadgePill
import com.example.ui.components.animation.ExerciseAnimationVisualizer

@Composable
fun WelcomeSlidesScreen(
    currentSlide: Int,
    strings: AppStrings,
    onSlideChange: (Int) -> Unit,
    onFinishSlides: () -> Unit,
    onBack: () -> Unit,
    isProSubscribed: Boolean = false,
    selectedLanguage: Language = Language.BENGALI,
    onOpenProDialog: () -> Unit = {},
    modifier: Modifier = Modifier
) {
    BackHandler(enabled = currentSlide > 0) {
        onBack()
    }

    val infiniteTransition = rememberInfiniteTransition(label = "welcomeStudioAnim")
    val animPulse by infiniteTransition.animateFloat(
        initialValue = 0f,
        targetValue = 1f,
        animationSpec = infiniteRepeatable(
            animation = tween(2200, easing = FastOutSlowInEasing),
            repeatMode = RepeatMode.Reverse
        ),
        label = "animPulse"
    )

    val scrollState = rememberScrollState()

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(
                Brush.verticalGradient(
                    colors = listOf(
                        Color(0xFF050811),
                        Color(0xFF0B1324),
                        Color(0xFF060911)
                    )
                )
            )
            .verticalScroll(scrollState)
            .padding(horizontal = 20.dp, vertical = 18.dp)
            .testTag("welcome_slides_screen"),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.SpaceBetween
    ) {
        // Top Executive Bar: Studio Badge + Pro Code Pill + Fast-Track Setup Pill
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(top = 6.dp),
            horizontalArrangement = Arrangement.SpaceBetween,
            verticalAlignment = Alignment.CenterVertically
        ) {
            Row(
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                Surface(
                    shape = RoundedCornerShape(50),
                    color = Color(0xFF131D31),
                    border = BorderStroke(1.dp, Color(0xFF26354D))
                ) {
                    Row(
                        verticalAlignment = Alignment.CenterVertically,
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 6.dp)
                    ) {
                        Icon(
                            imageVector = Icons.Default.Verified,
                            contentDescription = null,
                            tint = Color(0xFF34D399),
                            modifier = Modifier.size(14.dp)
                        )
                        Spacer(modifier = Modifier.width(5.dp))
                        Text(
                            text = "HOMEFIT STUDIO",
                            style = MaterialTheme.typography.labelSmall.copy(
                                fontSize = 9.5.sp,
                                fontWeight = FontWeight.Black,
                                letterSpacing = 0.8.sp
                            ),
                            color = Color(0xFFF8FAFC)
                        )
                    }
                }

                ProStatusBadgePill(
                    isProSubscribed = isProSubscribed,
                    selectedLanguage = selectedLanguage,
                    onClick = onOpenProDialog
                )
            }

            if (currentSlide < 2) {
                Surface(
                    shape = RoundedCornerShape(50),
                    color = Color(0xFF172236),
                    border = BorderStroke(1.dp, Color(0xFF334766)),
                    modifier = Modifier
                        .clip(RoundedCornerShape(50))
                        .clickable { onFinishSlides() }
                        .testTag("skip_welcome_button")
                ) {
                    Row(
                        verticalAlignment = Alignment.CenterVertically,
                        modifier = Modifier.padding(horizontal = 12.dp, vertical = 7.dp)
                    ) {
                        Text(
                            text = strings.skipBtn,
                            style = MaterialTheme.typography.labelLarge.copy(
                                fontSize = 11.5.sp,
                                fontWeight = FontWeight.Bold
                            ),
                            color = Color(0xFF38BDF8),
                            maxLines = 1
                        )
                        Spacer(modifier = Modifier.width(4.dp))
                        Icon(
                            imageVector = Icons.AutoMirrored.Filled.ArrowForward,
                            contentDescription = null,
                            tint = Color(0xFF38BDF8),
                            modifier = Modifier.size(13.dp)
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(16.dp))

        // Animated Slide Showcase (Live 3D Humanistic Athlete Preview + Telemetry + Copywriting)
        AnimatedContent(
            targetState = currentSlide,
            transitionSpec = { fadeIn(tween(300)) togetherWith fadeOut(tween(200)) },
            label = "welcome_slide_transition",
            modifier = Modifier.fillMaxWidth()
        ) { slideIndex ->
            val title = when (slideIndex) {
                0 -> strings.slide1Title
                1 -> strings.slide2Title
                else -> strings.slide3Title
            }
            val desc = when (slideIndex) {
                0 -> strings.slide1Desc
                1 -> strings.slide2Desc
                else -> strings.slide3Desc
            }

            Column(
                horizontalAlignment = Alignment.CenterHorizontally,
                modifier = Modifier.fillMaxWidth()
            ) {
                LuxuryStudioHeroShowcase(
                    slideIndex = slideIndex,
                    pulse = animPulse,
                    isBengali = selectedLanguage == Language.BENGALI
                )

                Spacer(modifier = Modifier.height(20.dp))

                // Live Telemetry Feature Pills
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(8.dp, Alignment.CenterHorizontally)
                ) {
                    val badges = when (slideIndex) {
                        0 -> listOf("27 HUMAN 3D ANIMS", "MUSCLE HEATMAP", "PROPS & FORM")
                        1 -> listOf("WEIGHT: 25–160 KG", "EXACT ML / LITERS", "MIFFLIN-ST JEOR")
                        else -> listOf("VIP PRO: IshanX10", "30-DAY TROPHIES", "100% OFFLINE")
                    }
                    badges.forEach { badge ->
                        Surface(
                            shape = RoundedCornerShape(8.dp),
                            color = Color(0xFF111A2C),
                            border = BorderStroke(1.dp, Color(0xFF26354D))
                        ) {
                            Text(
                                text = badge,
                                style = MaterialTheme.typography.labelSmall.copy(
                                    fontSize = 9.5.sp,
                                    fontWeight = FontWeight.ExtraBold,
                                    letterSpacing = 0.5.sp
                                ),
                                color = Color(0xFF34D399),
                                maxLines = 1,
                                modifier = Modifier.padding(horizontal = 8.dp, vertical = 5.dp)
                            )
                        }
                    }
                }

                Spacer(modifier = Modifier.height(18.dp))

                Text(
                    text = title,
                    style = MaterialTheme.typography.headlineMedium.copy(
                        fontWeight = FontWeight.ExtraBold,
                        fontSize = 24.sp,
                        lineHeight = 32.sp
                    ),
                    color = Color(0xFFF8FAFC),
                    textAlign = TextAlign.Center,
                    modifier = Modifier.testTag("slide_title_$slideIndex")
                )

                Spacer(modifier = Modifier.height(10.dp))

                Text(
                    text = desc,
                    style = MaterialTheme.typography.bodyLarge.copy(
                        fontSize = 14.5.sp,
                        lineHeight = 22.sp
                    ),
                    color = Color(0xFF94A3B8),
                    textAlign = TextAlign.Center,
                    modifier = Modifier.padding(horizontal = 6.dp)
                )
            }
        }

        Spacer(modifier = Modifier.height(22.dp))

        Column(
            horizontalAlignment = Alignment.CenterHorizontally,
            modifier = Modifier.fillMaxWidth()
        ) {
            // Slide Indicator Dots
            Row(
                horizontalArrangement = Arrangement.spacedBy(8.dp),
                verticalAlignment = Alignment.CenterVertically
            ) {
                repeat(3) { index ->
                    val isSelected = index == currentSlide
                    Box(
                        modifier = Modifier
                            .height(8.dp)
                            .width(if (isSelected) 32.dp else 8.dp)
                            .clip(CircleShape)
                            .background(
                                if (isSelected) Color(0xFF10B981)
                                else Color(0xFF26354D)
                            )
                            .clickable { onSlideChange(index) }
                    )
                }
            }

            Spacer(modifier = Modifier.height(20.dp))

            // Primary Luxury Action Button
            val buttonLabel = if (currentSlide < 2) strings.nextBtn else strings.getStartedBtn
            HomeFitButton(
                text = buttonLabel,
                leadingIcon = if (currentSlide == 2) Icons.Default.Bolt else null,
                onClick = {
                    if (currentSlide < 2) {
                        onSlideChange(currentSlide + 1)
                    } else {
                        onFinishSlides()
                    }
                },
                testTag = "welcome_primary_button"
            )
        }
    }
}

@Composable
private fun LuxuryStudioHeroShowcase(
    slideIndex: Int,
    pulse: Float,
    isBengali: Boolean
) {
    var demoExerciseId by remember { mutableStateOf("push_up") }

    if (slideIndex == 0) {
        // Live Interactive 3D Humanistic Exercise Showcase on Landing Slide 0
        Column(
            horizontalAlignment = Alignment.CenterHorizontally,
            modifier = Modifier.fillMaxWidth()
        ) {
            ExerciseAnimationVisualizer(
                animKey = demoExerciseId,
                isPlaying = true,
                showInteractiveControls = true,
                isBengali = isBengali,
                modifier = Modifier
                    .fillMaxWidth()
                    .height(235.dp)
            )

            Spacer(modifier = Modifier.height(10.dp))

            // Quick Live Exercise Switcher Pills on Landing Screen
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(8.dp, Alignment.CenterHorizontally)
            ) {
                val demoOptions = listOf(
                    "push_up" to (if (isBengali) "পুশ-আপ" else "Push-Up"),
                    "bodyweight_squats" to (if (isBengali) "স্কোয়াট" else "Squat"),
                    "towel_bicep_curl" to (if (isBengali) "তোয়ালে কার্ল" else "Towel Curl"),
                    "chair_dips" to (if (isBengali) "চেয়ার ডিপস" else "Chair Dips")
                )
                demoOptions.forEach { (id, label) ->
                    val selected = demoExerciseId == id
                    Surface(
                        shape = RoundedCornerShape(50),
                        color = if (selected) Color(0xFF10B981).copy(alpha = 0.22f) else Color(0xFF131D31),
                        border = BorderStroke(1.dp, if (selected) Color(0xFF10B981) else Color(0xFF26354D)),
                        modifier = Modifier
                            .clip(RoundedCornerShape(50))
                            .clickable { demoExerciseId = id }
                    ) {
                        Text(
                            text = label,
                            style = MaterialTheme.typography.labelSmall.copy(
                                fontSize = 11.sp,
                                fontWeight = FontWeight.Bold
                            ),
                            color = if (selected) Color(0xFF34D399) else Color(0xFFCBD5E1),
                            maxLines = 1,
                            modifier = Modifier.padding(horizontal = 12.dp, vertical = 6.dp)
                        )
                    }
                }
            }
        }
        return
    }

    Box(
        modifier = Modifier
            .fillMaxWidth()
            .height(235.dp)
            .clip(RoundedCornerShape(26.dp))
            .background(
                Brush.verticalGradient(
                    colors = listOf(
                        Color(0xFF0E1729),
                        Color(0xFF080D18)
                    )
                )
            )
            .border(
                width = 1.5.dp,
                brush = Brush.linearGradient(
                    colors = listOf(
                        Color(0xFF10B981).copy(alpha = 0.6f),
                        Color(0xFF26354D),
                        Color(0xFFF59E0B).copy(alpha = 0.5f)
                    )
                ),
                shape = RoundedCornerShape(26.dp)
            )
    ) {
        Canvas(modifier = Modifier.fillMaxSize()) {
            val w = size.width
            val h = size.height

            val floorTopY = h * 0.68f
            drawLine(
                color = Color(0xFF1E293B),
                start = Offset(0f, floorTopY),
                end = Offset(w, floorTopY),
                strokeWidth = 1.5.dp.toPx()
            )
            for (i in -3..3) {
                val topX = w * 0.5f + (i * w * 0.12f)
                val botX = w * 0.5f + (i * w * 0.24f)
                drawLine(
                    color = Color(0xFF1E293B).copy(alpha = 0.6f),
                    start = Offset(topX, floorTopY),
                    end = Offset(botX, h),
                    strokeWidth = 1.dp.toPx()
                )
            }

            drawCircle(
                brush = Brush.radialGradient(
                    colors = listOf(
                        if (slideIndex == 1) Color(0xFF38BDF8).copy(alpha = 0.24f + pulse * 0.08f)
                        else Color(0xFFF59E0B).copy(alpha = 0.24f + pulse * 0.08f),
                        Color.Transparent
                    ),
                    center = Offset(w * 0.5f, h * 0.42f),
                    radius = w * 0.48f
                ),
                radius = w * 0.48f,
                center = Offset(w * 0.5f, h * 0.42f)
            )

            if (slideIndex == 1) {
                // Slide 1: Clinical Hydration & BMR/TDEE Weight-Curve Visualization
                val chartLeft = w * 0.14f
                val chartRight = w * 0.86f
                val chartBottom = h * 0.76f
                val barWidth = (chartRight - chartLeft) / 5.5f

                val weightsAndHeights = listOf(
                    Triple("30kg", 0.35f, Color(0xFF38BDF8)),
                    Triple("50kg", 0.54f, Color(0xFF0EA5E9)),
                    Triple("70kg", 0.74f, Color(0xFF10B981)),
                    Triple("95kg", 0.94f, Color(0xFFF59E0B))
                )
                weightsAndHeights.forEachIndexed { idx, (_, ratio, color) ->
                    val bx = chartLeft + idx * (barWidth * 1.42f)
                    val barH = (h * 0.48f) * ratio * (0.92f + pulse * 0.08f)
                    drawRoundRect(
                        brush = Brush.verticalGradient(
                            colors = listOf(color, color.copy(alpha = 0.25f))
                        ),
                        topLeft = Offset(bx, chartBottom - barH),
                        size = Size(barWidth, barH),
                        cornerRadius = CornerRadius(8.dp.toPx())
                    )
                }
            } else {
                // Slide 2: Pro Gym Audio Equalizer & 30-Day Championship Shield
                val centerY = h * 0.48f
                val barsCount = 19
                val totalW = w * 0.72f
                val startX = (w - totalW) / 2f
                val stepX = totalW / barsCount

                for (i in 0 until barsCount) {
                    val distFromCenter = kotlin.math.abs(i - barsCount / 2).toFloat() / (barsCount / 2f)
                    val wave = kotlin.math.sin((i * 0.6f) + (pulse * 3.14f)).toFloat()
                    val barH = (h * 0.44f * (1f - distFromCenter * 0.55f) * (0.55f + 0.45f * kotlin.math.abs(wave))).coerceAtLeast(12f)
                    val barColor = if (i % 2 == 0) Color(0xFF10B981) else Color(0xFFF59E0B)
                    drawLine(
                        color = barColor,
                        start = Offset(startX + i * stepX, centerY - barH / 2f),
                        end = Offset(startX + i * stepX, centerY + barH / 2f),
                        strokeWidth = 5.dp.toPx(),
                        cap = StrokeCap.Round
                    )
                }
            }
        }

        Surface(
            shape = RoundedCornerShape(12.dp),
            color = Color(0xFF0B1322).copy(alpha = 0.88f),
            border = BorderStroke(1.dp, Color(0xFF26354D)),
            modifier = Modifier
                .align(Alignment.TopStart)
                .padding(12.dp)
        ) {
            Row(
                verticalAlignment = Alignment.CenterVertically,
                modifier = Modifier.padding(horizontal = 10.dp, vertical = 6.dp)
            ) {
                Icon(
                    imageVector = if (slideIndex == 1) Icons.Default.Science else Icons.Default.GraphicEq,
                    contentDescription = null,
                    tint = Color(0xFFFBBF24),
                    modifier = Modifier.size(15.dp)
                )
                Spacer(modifier = Modifier.width(6.dp))
                Text(
                    text = if (slideIndex == 1) "HYDRATION: 35 ML/KG + SWEAT" else "VOICE DUCKING + VIP PRO",
                    style = MaterialTheme.typography.labelSmall.copy(
                        fontSize = 10.sp,
                        fontWeight = FontWeight.ExtraBold
                    ),
                    color = Color.White,
                    maxLines = 1,
                    overflow = TextOverflow.Ellipsis
                )
            }
        }

        Surface(
            shape = RoundedCornerShape(12.dp),
            color = Color(0xFF0B1322).copy(alpha = 0.88f),
            border = BorderStroke(1.dp, Color(0xFF10B981).copy(alpha = 0.45f)),
            modifier = Modifier
                .align(Alignment.BottomEnd)
                .padding(12.dp)
        ) {
            Text(
                text = if (slideIndex == 1) "30kg: 1.2L | 70kg: 2.7L | 95kg: 3.8L" else "OFFLINE STUDIO VAULT",
                style = MaterialTheme.typography.labelSmall.copy(
                    fontSize = 10.sp,
                    fontWeight = FontWeight.Bold
                ),
                color = Color(0xFF34D399),
                maxLines = 1,
                modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
            )
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/player/ActiveWorkoutPlayerScreen.kt`

```kotlin
package com.example.ui.screens.player

import android.app.Activity
import android.view.WindowManager
import androidx.activity.compose.BackHandler
import androidx.compose.animation.AnimatedVisibility
import androidx.compose.animation.core.animateFloatAsState
import androidx.compose.foundation.Canvas
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Check
import androidx.compose.material.icons.filled.Close
import androidx.compose.material.icons.filled.FastForward
import androidx.compose.material.icons.filled.FastRewind
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.Lightbulb
import androidx.compose.material.icons.filled.Pause
import androidx.compose.material.icons.filled.PlayArrow
import androidx.compose.material.icons.filled.Replay
import androidx.compose.material.icons.filled.VolumeOff
import androidx.compose.material.icons.filled.VolumeUp
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.FloatingActionButton
import androidx.compose.material3.FloatingActionButtonDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.runtime.DisposableEffect
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.StrokeCap
import androidx.compose.ui.graphics.drawscope.Stroke
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.compose.foundation.clickable
import com.example.core.audio.OfflineBeatPreset
import com.example.core.audio.WorkoutMusicState
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.data.local.entity.SavedMusicTrackEntity
import com.example.domain.model.ActiveWorkoutSession
import com.example.domain.model.WorkoutPhase
import com.example.ui.components.animation.ExerciseAnimationVisualizer

@Composable
fun ActiveWorkoutPlayerScreen(
    session: ActiveWorkoutSession,
    selectedLanguage: Language,
    strings: AppStrings,
    onPlayPauseToggle: () -> Unit,
    onSkipNext: () -> Unit,
    onPrevious: () -> Unit,
    onRestartCurrent: () -> Unit,
    onToggleMute: () -> Unit,
    onSkipRest: () -> Unit,
    onExitWorkout: () -> Unit,
    musicState: WorkoutMusicState = WorkoutMusicState(),
    savedMusicTracks: List<SavedMusicTrackEntity> = emptyList(),
    voiceRepCounterEnabled: Boolean = true,
    onToggleVoiceRepCounter: () -> Unit = {},
    onToggleMusicPlayPause: () -> Unit = {},
    onNextMusicTrack: () -> Unit = {},
    onAddMusicTrack: (String, String) -> Unit = { _, _ -> },
    onDeleteMusicTrack: (Long) -> Unit = {},
    onPlayMusicTrack: (SavedMusicTrackEntity) -> Unit = {},
    onSelectBeatPreset: (OfflineBeatPreset) -> Unit = {},
    onMusicVolumeChange: (Float) -> Unit = {},
    modifier: Modifier = Modifier
) {
    val context = LocalContext.current
    var showExitDialog by remember { mutableStateOf(false) }
    var showSequenceChecklist by remember { mutableStateOf(false) }
    var showMusicDialog by remember { mutableStateOf(false) }

    if (showMusicDialog) {
        WorkoutMusicDialog(
            musicState = musicState,
            savedTracks = savedMusicTracks,
            selectedLanguage = selectedLanguage,
            onDismiss = { showMusicDialog = false },
            onAddTrack = onAddMusicTrack,
            onDeleteTrack = onDeleteMusicTrack,
            onPlayTrack = onPlayMusicTrack,
            onSelectBeatPreset = onSelectBeatPreset,
            onVolumeChange = onMusicVolumeChange
        )
    }

    // Screen Wake-Lock: Keep screen on during active workout
    DisposableEffect(Unit) {
        val window = (context as? Activity)?.window
        window?.addFlags(WindowManager.LayoutParams.FLAG_KEEP_SCREEN_ON)
        onDispose {
            window?.clearFlags(WindowManager.LayoutParams.FLAG_KEEP_SCREEN_ON)
        }
    }

    // Intercept back button
    BackHandler {
        showExitDialog = true
    }

    // Exit Confirmation Dialog
    if (showExitDialog) {
        AlertDialog(
            onDismissRequest = { showExitDialog = false },
            title = {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "ওয়ার্কআউট বন্ধ করবেন?" else "Quit Workout?",
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                )
            },
            text = {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "আপনি কি নিশ্চিতভাবে এই ব্যায়ামটি মাঝপথে বন্ধ করতে চান? আপনার বর্তমান অগ্রগতি সংরক্ষিত নাও হতে পারে।"
                    else "Are you sure you want to quit? Your current session progress will not be completed.",
                    style = MaterialTheme.typography.bodyMedium
                )
            },
            confirmButton = {
                TextButton(
                    onClick = {
                        showExitDialog = false
                        onExitWorkout()
                    }
                ) {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "ব্যায়াম ছেড়ে দিন" else "Quit",
                        color = MaterialTheme.colorScheme.error,
                        fontWeight = FontWeight.Bold
                    )
                }
            },
            dismissButton = {
                TextButton(onClick = { showExitDialog = false }) {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "সেশনে ফিরে যান" else "Stay in Session",
                        fontWeight = FontWeight.Bold
                    )
                }
            }
        )
    }

    val currentEx = session.currentExercise
    val exerciseName = if (selectedLanguage == Language.BENGALI) currentEx.nameBn else currentEx.nameEn
    val targetMuscle = if (selectedLanguage == Language.BENGALI) currentEx.targetMusclesBn else currentEx.targetMusclesEn
    val formTip = if (selectedLanguage == Language.BENGALI) currentEx.formTipsBn.firstOrNull().orEmpty() else currentEx.formTipsEn.firstOrNull().orEmpty()

    val nextEx = session.nextExercise
    val nextExName = if (nextEx != null) {
        if (selectedLanguage == Language.BENGALI) nextEx.nameBn else nextEx.nameEn
    } else null

    val phaseColor = when (session.phase) {
        WorkoutPhase.PREPARE -> MaterialTheme.colorScheme.tertiary
        WorkoutPhase.EXERCISE -> MaterialTheme.colorScheme.primary
        WorkoutPhase.REST -> MaterialTheme.colorScheme.secondary
        WorkoutPhase.COMPLETED -> MaterialTheme.colorScheme.tertiary
    }

    val animatedProgress by animateFloatAsState(
        targetValue = session.progressFraction,
        label = "timer_progress"
    )

    Box(
        modifier = modifier
            .fillMaxSize()
            .background(Color(0xFF070A0F)) // Distraction-free athletic dark
            .padding(16.dp)
            .testTag("active_workout_player_screen")
    ) {
        Column(
            modifier = Modifier
                .fillMaxSize()
                .verticalScroll(rememberScrollState()),
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            // Top Navigation & Progress Bar
            Row(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(top = 8.dp),
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                IconButton(
                    onClick = { showExitDialog = true },
                    modifier = Modifier.testTag("exit_player_btn")
                ) {
                    Icon(
                        imageVector = Icons.Default.Close,
                        contentDescription = "Exit workout",
                        tint = Color.White
                    )
                }

                Surface(
                    onClick = { showSequenceChecklist = !showSequenceChecklist },
                    shape = RoundedCornerShape(12.dp),
                    color = Color(0xFF131B28)
                ) {
                    Row(
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 6.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Text(
                            text = "${session.currentExerciseIndex + 1} / ${session.plan.exercises.size}",
                            style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.primary
                        )
                        Spacer(modifier = Modifier.width(6.dp))
                        Text(
                            text = if (showSequenceChecklist) "▲" else "▼",
                            fontSize = 10.sp,
                            color = Color.LightGray
                        )
                    }
                }

                IconButton(
                    onClick = onToggleMute,
                    modifier = Modifier.testTag("toggle_mute_btn")
                ) {
                    Icon(
                        imageVector = if (session.isMuted) Icons.Default.VolumeOff else Icons.Default.VolumeUp,
                        contentDescription = "Toggle Mute",
                        tint = if (session.isMuted) Color.Gray else Color.White
                    )
                }
            }

            // Real-time Exercise Checklist Drawer
            AnimatedVisibility(visible = showSequenceChecklist) {
                Surface(
                    shape = RoundedCornerShape(14.dp),
                    color = Color(0xFF131B28),
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(vertical = 8.dp)
                ) {
                    Column(modifier = Modifier.padding(12.dp)) {
                        Text(
                            text = if (selectedLanguage == Language.BENGALI) "ওয়ার্কআউট অগ্রগতি তালিকা:" else "Workout Progress:",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold, color = Color.White)
                        )
                        Spacer(modifier = Modifier.height(6.dp))
                        session.plan.exercises.forEachIndexed { idx, ex ->
                            val isDone = idx < session.currentExerciseIndex
                            val isCurrent = idx == session.currentExerciseIndex
                            val name = if (selectedLanguage == Language.BENGALI) ex.nameBn else ex.nameEn

                            Row(
                                modifier = Modifier
                                    .fillMaxWidth()
                                    .padding(vertical = 2.dp),
                                verticalAlignment = Alignment.CenterVertically
                            ) {
                                if (isDone) {
                                    Icon(
                                        imageVector = Icons.Default.Check,
                                        contentDescription = "Done",
                                        tint = MaterialTheme.colorScheme.primary,
                                        modifier = Modifier.size(16.dp)
                                    )
                                } else if (isCurrent) {
                                    Text("➔", color = MaterialTheme.colorScheme.secondary, fontWeight = FontWeight.Black)
                                } else {
                                    Text("○", color = Color.Gray)
                                }
                                Spacer(modifier = Modifier.width(8.dp))
                                Text(
                                    text = name,
                                    style = MaterialTheme.typography.bodySmall.copy(
                                        color = if (isCurrent) Color.White else if (isDone) Color.Gray else Color.LightGray,
                                        fontWeight = if (isCurrent) FontWeight.Bold else FontWeight.Normal
                                    )
                                )
                            }
                        }
                    }
                }
            }

            Spacer(modifier = Modifier.height(6.dp))

            // Offline Workout Music & Smart Ducking Mini Bar
            WorkoutMusicMiniBar(
                musicState = musicState,
                selectedLanguage = selectedLanguage,
                onTogglePlayPause = onToggleMusicPlayPause,
                onNextTrack = onNextMusicTrack,
                onOpenMusicSheet = { showMusicDialog = true }
            )

            Spacer(modifier = Modifier.height(10.dp))

            // 1. Exercise Name
            Text(
                text = if (session.phase == WorkoutPhase.REST) (nextExName ?: exerciseName) else exerciseName,
                style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Black),
                color = Color.White,
                textAlign = TextAlign.Center
            )

            Spacer(modifier = Modifier.height(6.dp))

            // Current Phase Tag & Voice Rep Counter Toggle Row
            Row(
                horizontalArrangement = Arrangement.spacedBy(8.dp),
                verticalAlignment = Alignment.CenterVertically
            ) {
                Surface(
                    shape = RoundedCornerShape(10.dp),
                    color = phaseColor.copy(alpha = 0.2f)
                ) {
                    Text(
                        text = when (session.phase) {
                            WorkoutPhase.PREPARE -> if (selectedLanguage == Language.BENGALI) "প্রস্তুত হোন (Ready)" else "GET READY"
                            WorkoutPhase.EXERCISE -> "🎯 $targetMuscle"
                            WorkoutPhase.REST -> if (selectedLanguage == Language.BENGALI) "বিশ্রাম (Rest)" else "REST"
                            WorkoutPhase.COMPLETED -> if (selectedLanguage == Language.BENGALI) "সম্পন্ন!" else "COMPLETED!"
                        },
                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                        color = phaseColor,
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 4.dp)
                    )
                }

                Surface(
                    shape = RoundedCornerShape(10.dp),
                    color = if (voiceRepCounterEnabled) Color(0xFF10B981).copy(alpha = 0.22f) else Color(0xFF1E293B),
                    modifier = Modifier
                        .clickable { onToggleVoiceRepCounter() }
                        .testTag("toggle_voice_rep_counter_chip")
                ) {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) {
                            if (voiceRepCounterEnabled) "🗣️ রেপ কাউন্টার: চালু" else "🗣️ রেপ কাউন্টার: বন্ধ"
                        } else {
                            if (voiceRepCounterEnabled) "🗣️ Rep Count: ON" else "🗣️ Rep Count: OFF"
                        },
                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                        color = if (voiceRepCounterEnabled) Color(0xFF34D399) else Color.LightGray,
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 4.dp)
                    )
                }
            }

            Spacer(modifier = Modifier.height(10.dp))

            // 2. HERO ANIMATED EXERCISE DEMONSTRATION (Pinch-to-Zoom & Muscle Glow Enabled)
            Box(
                modifier = Modifier
                    .fillMaxWidth()
                    .height(200.dp),
                contentAlignment = Alignment.Center
            ) {
                if (session.phase == WorkoutPhase.REST && nextEx != null) {
                    ExerciseAnimationVisualizer(
                        exerciseId = nextEx.id,
                        size = 200.dp,
                        tintColor = MaterialTheme.colorScheme.secondary,
                        isPaused = session.isPaused,
                        isBengali = selectedLanguage == Language.BENGALI
                    )
                } else {
                    ExerciseAnimationVisualizer(
                        exerciseId = currentEx.id,
                        size = 200.dp,
                        tintColor = MaterialTheme.colorScheme.primary,
                        isPaused = session.isPaused,
                        isBengali = selectedLanguage == Language.BENGALI
                    )
                }
            }

            Spacer(modifier = Modifier.height(14.dp))

            // 3. Compact Circular Countdown Timer
            Box(
                modifier = Modifier.size(130.dp),
                contentAlignment = Alignment.Center
            ) {
                Canvas(modifier = Modifier.fillMaxSize()) {
                    val strokeWidth = 9.dp.toPx()
                    // Track
                    drawArc(
                        color = Color(0xFF1E2838),
                        startAngle = -90f,
                        sweepAngle = 360f,
                        useCenter = false,
                        style = Stroke(width = strokeWidth, cap = StrokeCap.Round)
                    )
                    // Progress
                    drawArc(
                        color = phaseColor,
                        startAngle = -90f,
                        sweepAngle = 360f * (1f - animatedProgress),
                        useCenter = false,
                        style = Stroke(width = strokeWidth, cap = StrokeCap.Round)
                    )
                }

                Column(horizontalAlignment = Alignment.CenterHorizontally) {
                    Text(
                        text = "${session.remainingSeconds}",
                        style = MaterialTheme.typography.displayMedium.copy(
                            fontSize = 44.sp,
                            fontWeight = FontWeight.Black
                        ),
                        color = Color.White
                    )
                    Text(
                        text = if (session.isPaused) "পজ" else if (selectedLanguage == Language.BENGALI) "সেকেন্ড" else "sec",
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontWeight = FontWeight.Bold,
                            color = if (session.isPaused) MaterialTheme.colorScheme.error else Color.LightGray
                        )
                    )
                }
            }

            Spacer(modifier = Modifier.height(12.dp))

            // 4. Form Cue / Up Next Box
            Surface(
                shape = RoundedCornerShape(14.dp),
                color = Color(0xFF131B28),
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(horizontal = 8.dp)
            ) {
                if (session.phase == WorkoutPhase.REST) {
                    Row(
                        modifier = Modifier.padding(12.dp),
                        verticalAlignment = Alignment.CenterVertically,
                        horizontalArrangement = Arrangement.SpaceBetween
                    ) {
                        Column(modifier = Modifier.weight(1f)) {
                            Text(
                                text = if (selectedLanguage == Language.BENGALI) "পরবর্তী ব্যায়াম:" else "UP NEXT:",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold, color = MaterialTheme.colorScheme.secondary)
                            )
                            Text(
                                text = nextExName ?: if (selectedLanguage == Language.BENGALI) "শেষ ব্যায়াম!" else "Final Exercise!",
                                style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold, color = Color.White)
                            )
                        }
                        Button(
                            onClick = onSkipRest,
                            shape = RoundedCornerShape(10.dp),
                            colors = ButtonDefaults.buttonColors(containerColor = MaterialTheme.colorScheme.secondary),
                            modifier = Modifier.height(34.dp)
                        ) {
                            Text(
                                text = if (selectedLanguage == Language.BENGALI) "শুরু করুন" else "Skip",
                                style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold, color = Color.Black)
                            )
                        }
                    }
                } else {
                    Row(
                        modifier = Modifier.padding(12.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Icon(
                            imageVector = Icons.Default.Lightbulb,
                            contentDescription = null,
                            tint = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.size(18.dp)
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text(
                            text = formTip.ifEmpty { "নিয়মিত শ্বাস-প্রশ্বাস বজায় রাখুন এবং সঠিক ফর্ম বজায় রাখুন।" },
                            style = MaterialTheme.typography.bodySmall.copy(color = Color.LightGray, fontSize = 12.sp),
                            lineHeight = 16.sp
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(18.dp))

            // 5. Player Controls Row
            Row(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(bottom = 16.dp),
                horizontalArrangement = Arrangement.SpaceEvenly,
                verticalAlignment = Alignment.CenterVertically
            ) {
                IconButton(
                    onClick = onRestartCurrent,
                    modifier = Modifier.size(44.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.Replay,
                        contentDescription = "Restart",
                        tint = Color.White
                    )
                }

                IconButton(
                    onClick = onPrevious,
                    enabled = session.currentExerciseIndex > 0,
                    modifier = Modifier.size(44.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.FastRewind,
                        contentDescription = "Previous",
                        tint = if (session.currentExerciseIndex > 0) Color.White else Color.DarkGray
                    )
                }

                FloatingActionButton(
                    onClick = onPlayPauseToggle,
                    shape = CircleShape,
                    containerColor = MaterialTheme.colorScheme.primary,
                    contentColor = Color.White,
                    elevation = FloatingActionButtonDefaults.elevation(6.dp),
                    modifier = Modifier
                        .size(64.dp)
                        .testTag("player_play_pause_fab")
                ) {
                    Icon(
                        imageVector = if (session.isPaused) Icons.Default.PlayArrow else Icons.Default.Pause,
                        contentDescription = if (session.isPaused) "Play" else "Pause",
                        modifier = Modifier.size(32.dp)
                    )
                }

                IconButton(
                    onClick = onSkipNext,
                    modifier = Modifier.size(44.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.FastForward,
                        contentDescription = "Next",
                        tint = Color.White
                    )
                }
            }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/player/WorkoutCardShareHelper.kt`

```kotlin
package com.example.ui.screens.player

import android.content.Context
import android.content.Intent
import android.graphics.Bitmap
import android.graphics.Canvas
import android.graphics.Color
import android.graphics.LinearGradient
import android.graphics.Paint
import android.graphics.RectF
import android.graphics.Shader
import android.graphics.Typeface
import android.widget.Toast
import androidx.core.content.FileProvider
import com.example.core.i18n.Language
import java.io.File
import java.io.FileOutputStream
import java.text.SimpleDateFormat
import java.util.Date
import java.util.Locale

object WorkoutCardShareHelper {

    fun shareWorkoutCard(
        context: Context,
        userName: String,
        workoutTitle: String,
        durationText: String,
        caloriesBurned: Int,
        exercisesCount: Int,
        streakDays: Int,
        language: Language
    ) {
        try {
            val width = 1080
            val height = 1350
            val bitmap = Bitmap.createBitmap(width, height, Bitmap.Config.ARGB_8888)
            val canvas = Canvas(bitmap)

            // 1. Deep Athletic Dark-Emerald Background Gradient
            val bgPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                shader = LinearGradient(
                    0f, 0f, width.toFloat(), height.toFloat(),
                    intArrayOf(
                        Color.parseColor("#0A121E"),
                        Color.parseColor("#0E232E"),
                        Color.parseColor("#0A1622")
                    ),
                    floatArrayOf(0f, 0.55f, 1f),
                    Shader.TileMode.CLAMP
                )
            }
            canvas.drawRect(0f, 0f, width.toFloat(), height.toFloat(), bgPaint)

            // 2. Outer Glow Border Frame
            val framePaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                style = Paint.Style.STROKE
                strokeWidth = 6f
                color = Color.parseColor("#10B981")
            }
            val outerRect = RectF(48f, 48f, width - 48f, height - 48f)
            canvas.drawRoundRect(outerRect, 48f, 48f, framePaint)

            // 3. Header Pill ("HOMEFIT OFFLINE PRO")
            val badgePaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#163832")
            }
            canvas.drawRoundRect(RectF(310f, 110f, 770f, 185f), 40f, 40f, badgePaint)

            val headerTextPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#10B981")
                textSize = 34f
                typeface = Typeface.create(Typeface.DEFAULT, Typeface.BOLD)
                textAlign = Paint.Align.CENTER
            }
            canvas.drawText("🏋️ HOMEFIT • 100% OFFLINE", width / 2f, 160f, headerTextPaint)

            // 4. Trophy Medallion Circle
            val trophyCirclePaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#1E3A34")
            }
            canvas.drawCircle(width / 2f, 340f, 110f, trophyCirclePaint)

            val trophyStrokePaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                style = Paint.Style.STROKE
                strokeWidth = 5f
                color = Color.parseColor("#F59E0B")
            }
            canvas.drawCircle(width / 2f, 340f, 110f, trophyStrokePaint)

            val trophyEmojiPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                textSize = 105f
                textAlign = Paint.Align.CENTER
            }
            canvas.drawText("🏆", width / 2f, 378f, trophyEmojiPaint)

            // 5. Title & Athlete Name
            val mainHeadingPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.WHITE
                textSize = 54f
                typeface = Typeface.create(Typeface.DEFAULT, Typeface.BOLD)
                textAlign = Paint.Align.CENTER
            }
            val completedBanner = if (language == Language.BENGALI) {
                "ওয়ার্কআউট সম্পন্ন!"
            } else {
                "WORKOUT COMPLETED!"
            }
            canvas.drawText(completedBanner, width / 2f, 540f, mainHeadingPaint)

            val planTitlePaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#34D399")
                textSize = 42f
                typeface = Typeface.create(Typeface.DEFAULT, Typeface.BOLD)
                textAlign = Paint.Align.CENTER
            }
            val safeWorkoutTitle = if (workoutTitle.length > 34) workoutTitle.take(32) + "…" else workoutTitle
            canvas.drawText(safeWorkoutTitle, width / 2f, 615f, planTitlePaint)

            if (userName.isNotBlank()) {
                val athletePaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                    color = Color.parseColor("#94A3B8")
                    textSize = 32f
                    textAlign = Paint.Align.CENTER
                }
                val athleteLabel = if (language == Language.BENGALI) "অ্যাথলেট: $userName" else "Athlete: $userName"
                canvas.drawText(athleteLabel, width / 2f, 675f, athletePaint)
            }

            // 6. Three Metric Cards Row
            val cardBgPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#152636")
            }
            val cardValuePaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.WHITE
                textSize = 46f
                typeface = Typeface.create(Typeface.DEFAULT, Typeface.BOLD)
                textAlign = Paint.Align.CENTER
            }
            val cardLabelPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#94A3B8")
                textSize = 28f
                textAlign = Paint.Align.CENTER
            }

            // Left Card: Duration
            canvas.drawRoundRect(RectF(90f, 740f, 380f, 960f), 32f, 32f, cardBgPaint)
            canvas.drawText(durationText, 235f, 845f, cardValuePaint)
            canvas.drawText(if (language == Language.BENGALI) "মোট সময়" else "Duration", 235f, 910f, cardLabelPaint)

            // Center Card: Calories
            canvas.drawRoundRect(RectF(395f, 740f, 685f, 960f), 32f, 32f, cardBgPaint)
            canvas.drawText("$caloriesBurned kcal", 540f, 845f, cardValuePaint)
            canvas.drawText(if (language == Language.BENGALI) "ক্যালরি বার্ন" else "Burned", 540f, 910f, cardLabelPaint)

            // Right Card: Exercises
            canvas.drawRoundRect(RectF(700f, 740f, 990f, 960f), 32f, 32f, cardBgPaint)
            canvas.drawText("$exercisesCount", 845f, 845f, cardValuePaint)
            canvas.drawText(if (language == Language.BENGALI) "টি ব্যায়াম" else "Exercises", 845f, 910f, cardLabelPaint)

            // 7. Streak Banner
            val streakCardPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#2A2415")
            }
            canvas.drawRoundRect(RectF(140f, 1015f, 940f, 1135f), 32f, 32f, streakCardPaint)
            val streakTextPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#FBBF24")
                textSize = 38f
                typeface = Typeface.create(Typeface.DEFAULT, Typeface.BOLD)
                textAlign = Paint.Align.CENTER
            }
            val streakMsg = if (language == Language.BENGALI) {
                "🔥 ধারাবাহিক স্ট্রিক: $streakDays দিন সক্রিয়!"
            } else {
                "🔥 Active Streak: $streakDays Day(s) Strong!"
            }
            canvas.drawText(streakMsg, width / 2f, 1088f, streakTextPaint)

            // 8. Date Footer
            val dateStr = SimpleDateFormat("dd MMM yyyy • hh:mm a", Locale.US).format(Date())
            val footerPaint = Paint(Paint.ANTI_ALIAS_FLAG).apply {
                color = Color.parseColor("#64748B")
                textSize = 26f
                textAlign = Paint.Align.CENTER
            }
            canvas.drawText("HomeFit Smart Fitness • $dateStr", width / 2f, 1235f, footerPaint)

            // Save to cacheDir/shared_cards/
            val dir = File(context.cacheDir, "shared_cards")
            if (!dir.exists()) dir.mkdirs()
            val outFile = File(dir, "homefit_progress_${System.currentTimeMillis()}.png")
            FileOutputStream(outFile).use { out ->
                bitmap.compress(Bitmap.CompressFormat.PNG, 100, out)
            }

            val uri = FileProvider.getUriForFile(
                context,
                "${context.packageName}.fileprovider",
                outFile
            )

            val shareText = if (language == Language.BENGALI) {
                "আমি আজ HomeFit অ্যাপে '$workoutTitle' সম্পন্ন করেছি! ($durationText, $caloriesBurned kcal বার্ন, স্ট্রিক: $streakDays দিন) 💪🔥"
            } else {
                "Just completed '$workoutTitle' on HomeFit! ($durationText, $caloriesBurned kcal burned, Streak: $streakDays days) 💪🔥"
            }

            val intent = Intent(Intent.ACTION_SEND).apply {
                type = "image/png"
                putExtra(Intent.EXTRA_STREAM, uri)
                putExtra(Intent.EXTRA_TEXT, shareText)
                addFlags(Intent.FLAG_GRANT_READ_URI_PERMISSION)
            }

            val chooserTitle = if (language == Language.BENGALI) "প্রগ্রেস কার্ড শেয়ার করুন" else "Share Progress Card"
            context.startActivity(Intent.createChooser(intent, chooserTitle))
        } catch (e: Exception) {
            Toast.makeText(
                context,
                if (language == Language.BENGALI) "কার্ড তৈরি করতে সমস্যা হয়েছে" else "Could not share card",
                Toast.LENGTH_SHORT
            ).show()
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/player/WorkoutCompletionScreen.kt`

```kotlin
package com.example.ui.screens.player

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.CheckCircle
import androidx.compose.material.icons.filled.EmojiEvents
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.LocalFireDepartment
import androidx.compose.material.icons.filled.Share
import androidx.compose.material.icons.filled.Timer
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.vector.ImageVector
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitCard
import com.example.ui.components.HomeFitOutlinedButton

@Composable
fun WorkoutCompletionScreen(
    planTitle: String,
    totalSeconds: Int,
    caloriesBurned: Int,
    exercisesCompletedCount: Int,
    selectedLanguage: Language,
    strings: AppStrings,
    onFinish: () -> Unit,
    userName: String = "",
    streakDays: Int = 1,
    modifier: Modifier = Modifier
) {
    val context = LocalContext.current
    val minutes = totalSeconds / 60
    val seconds = totalSeconds % 60
    val durationText = if (minutes > 0) "$minutes m $seconds s" else "$seconds s"

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(MaterialTheme.colorScheme.background)
            .padding(24.dp)
            .testTag("workout_completion_screen"),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {
        // Trophy Badge
        Box(
            modifier = Modifier
                .size(110.dp)
                .clip(CircleShape)
                .background(MaterialTheme.colorScheme.primaryContainer),
            contentAlignment = Alignment.Center
        ) {
            Icon(
                imageVector = Icons.Default.EmojiEvents,
                contentDescription = "Trophy",
                tint = MaterialTheme.colorScheme.primary,
                modifier = Modifier.size(62.dp)
            )
        }

        Spacer(modifier = Modifier.height(24.dp))

        Text(
            text = if (selectedLanguage == Language.BENGALI) "চমৎকার! ওয়ার্কআউট সম্পন্ন!" else "Awesome! Workout Completed!",
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Black),
            color = MaterialTheme.colorScheme.onBackground,
            textAlign = TextAlign.Center
        )

        Spacer(modifier = Modifier.height(8.dp))

        Text(
            text = planTitle,
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.primary,
            textAlign = TextAlign.Center
        )

        Spacer(modifier = Modifier.height(24.dp))

        // Summary Stats Grid
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(10.dp)
        ) {
            CompletionStatCard(
                icon = Icons.Default.Timer,
                value = durationText,
                label = if (selectedLanguage == Language.BENGALI) "মোট সময়" else "Duration",
                color = MaterialTheme.colorScheme.primary,
                modifier = Modifier.weight(1f)
            )

            CompletionStatCard(
                icon = Icons.Default.LocalFireDepartment,
                value = "$caloriesBurned kcal",
                label = if (selectedLanguage == Language.BENGALI) "পোড়ানো ক্যালরি" else "Burned",
                color = MaterialTheme.colorScheme.secondary,
                modifier = Modifier.weight(1f)
            )

            CompletionStatCard(
                icon = Icons.Default.FitnessCenter,
                value = "$exercisesCompletedCount",
                label = if (selectedLanguage == Language.BENGALI) "টি ব্যায়াম" else "Exercises",
                color = MaterialTheme.colorScheme.tertiary,
                modifier = Modifier.weight(1f)
            )
        }

        Spacer(modifier = Modifier.height(20.dp))

        // Success Confirmation Message
        HomeFitCard(borderColor = MaterialTheme.colorScheme.tertiary) {
            Row(verticalAlignment = Alignment.CenterVertically) {
                Icon(
                    imageVector = Icons.Default.CheckCircle,
                    contentDescription = null,
                    tint = MaterialTheme.colorScheme.tertiary,
                    modifier = Modifier.size(24.dp)
                )
                Spacer(modifier = Modifier.width(10.dp))
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "আপনার আজকের অগ্রগতি ডাটাবেসে সফলভাবে সংরক্ষিত হয়েছে এবং স্ট্রিক আপডেট হয়েছে!"
                    else "Your workout has been securely saved locally and your daily streak is updated!",
                    style = MaterialTheme.typography.bodyMedium,
                    color = MaterialTheme.colorScheme.onSurface
                )
            }
        }

        Spacer(modifier = Modifier.height(24.dp))

        HomeFitOutlinedButton(
            text = if (selectedLanguage == Language.BENGALI) "📸 প্রগ্রেস কার্ড শেয়ার করুন" else "📸 Share Progress Card",
            onClick = {
                WorkoutCardShareHelper.shareWorkoutCard(
                    context = context,
                    userName = userName,
                    workoutTitle = planTitle,
                    durationText = durationText,
                    caloriesBurned = caloriesBurned,
                    exercisesCount = exercisesCompletedCount,
                    streakDays = streakDays,
                    language = selectedLanguage
                )
            },
            testTag = "share_workout_card_btn"
        )

        Spacer(modifier = Modifier.height(12.dp))

        HomeFitButton(
            text = if (selectedLanguage == Language.BENGALI) "হোমে ফিরে যান" else "Return to Home",
            onClick = onFinish,
            testTag = "completion_home_btn"
        )
    }
}

@Composable
fun CompletionStatCard(
    icon: ImageVector,
    value: String,
    label: String,
    color: Color,
    modifier: Modifier = Modifier
) {
    Surface(
        shape = RoundedCornerShape(16.dp),
        color = MaterialTheme.colorScheme.surface,
        modifier = modifier
    ) {
        Column(
            modifier = Modifier.padding(12.dp),
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            Icon(
                imageVector = icon,
                contentDescription = null,
                tint = color,
                modifier = Modifier.size(24.dp)
            )
            Spacer(modifier = Modifier.height(6.dp))
            Text(
                text = value,
                style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Black),
                color = MaterialTheme.colorScheme.onSurface,
                textAlign = TextAlign.Center
            )
            Text(
                text = label,
                style = MaterialTheme.typography.labelSmall.copy(fontSize = 11.sp),
                color = MaterialTheme.colorScheme.onSurfaceVariant,
                textAlign = TextAlign.Center
            )
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/player/WorkoutMusicSheet.kt`

```kotlin
package com.example.ui.screens.player

import android.content.Context
import android.content.Intent
import android.net.Uri
import android.provider.OpenableColumns
import androidx.activity.compose.rememberLauncherForActivityResult
import androidx.activity.result.contract.ActivityResultContracts
import androidx.compose.foundation.background
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.heightIn
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.Delete
import androidx.compose.material.icons.filled.GraphicEq
import androidx.compose.material.icons.filled.LibraryMusic
import androidx.compose.material.icons.filled.MusicNote
import androidx.compose.material.icons.filled.Pause
import androidx.compose.material.icons.filled.PlayArrow
import androidx.compose.material.icons.filled.SkipNext
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Slider
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextOverflow
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.audio.OfflineBeatPreset
import com.example.core.audio.WorkoutMusicState
import com.example.core.i18n.Language
import com.example.data.local.entity.SavedMusicTrackEntity

@Composable
fun WorkoutMusicMiniBar(
    musicState: WorkoutMusicState,
    selectedLanguage: Language,
    onTogglePlayPause: () -> Unit,
    onNextTrack: () -> Unit,
    onOpenMusicSheet: () -> Unit,
    modifier: Modifier = Modifier
) {
    val isBn = selectedLanguage == Language.BENGALI
    val activeTitle = musicState.currentTrackTitle
        ?: if (isBn) "মিউজিক ও অফলাইন জিম বিটস" else "Workout Music & Offline Beats"

    Surface(
        shape = RoundedCornerShape(14.dp),
        color = Color(0xFF131D2E),
        modifier = modifier
            .fillMaxWidth()
            .clickable { onOpenMusicSheet() }
            .testTag("workout_music_mini_bar")
    ) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(horizontal = 12.dp, vertical = 8.dp),
            verticalAlignment = Alignment.CenterVertically,
            horizontalArrangement = Arrangement.SpaceBetween
        ) {
            Row(
                verticalAlignment = Alignment.CenterVertically,
                modifier = Modifier.weight(1f)
            ) {
                Box(
                    modifier = Modifier
                        .size(34.dp)
                        .clip(CircleShape)
                        .background(
                            if (musicState.isPlaying) MaterialTheme.colorScheme.primary.copy(alpha = 0.25f)
                            else Color(0xFF1E293B)
                        ),
                    contentAlignment = Alignment.Center
                ) {
                    Icon(
                        imageVector = if (musicState.isPlaying) Icons.Default.GraphicEq else Icons.Default.MusicNote,
                        contentDescription = null,
                        tint = if (musicState.isPlaying) MaterialTheme.colorScheme.primary else Color.LightGray,
                        modifier = Modifier.size(18.dp)
                    )
                }

                Spacer(modifier = Modifier.width(10.dp))

                Column(modifier = Modifier.weight(1f)) {
                    Text(
                        text = activeTitle,
                        style = MaterialTheme.typography.labelMedium.copy(
                            fontWeight = FontWeight.Bold,
                            color = Color.White
                        ),
                        maxLines = 1,
                        overflow = TextOverflow.Ellipsis
                    )
                    Text(
                        text = when {
                            musicState.isDucked -> if (isBn) "🔉 কোচ কথা বলছে (অটো ভলিউম ডাউন)" else "🔉 Coach speaking (Auto-Ducking)"
                            musicState.isPlaying -> if (isBn) "🎵 বাজছে • পরিবর্তন করতে ট্যাপ করুন" else "🎵 Playing • Tap to customize"
                            else -> if (isBn) "ফোনের গান বা জিম বিটস চালাতে ট্যাপ করুন" else "Tap to play phone songs or gym beats"
                        },
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontSize = 10.sp,
                            color = if (musicState.isDucked) Color(0xFFFBBF24) else Color(0xFF94A3B8)
                        ),
                        maxLines = 1,
                        overflow = TextOverflow.Ellipsis
                    )
                }
            }

            Row(verticalAlignment = Alignment.CenterVertically) {
                IconButton(
                    onClick = onTogglePlayPause,
                    modifier = Modifier.size(36.dp)
                ) {
                    Icon(
                        imageVector = if (musicState.isPlaying) Icons.Default.Pause else Icons.Default.PlayArrow,
                        contentDescription = "Play/Pause Music",
                        tint = MaterialTheme.colorScheme.primary
                    )
                }

                IconButton(
                    onClick = onNextTrack,
                    modifier = Modifier.size(36.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.SkipNext,
                        contentDescription = "Next Track",
                        tint = Color.LightGray
                    )
                }

                IconButton(
                    onClick = onOpenMusicSheet,
                    modifier = Modifier.size(36.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.LibraryMusic,
                        contentDescription = "Open Playlist",
                        tint = MaterialTheme.colorScheme.secondary
                    )
                }
            }
        }
    }
}

@Composable
fun WorkoutMusicDialog(
    musicState: WorkoutMusicState,
    savedTracks: List<SavedMusicTrackEntity>,
    selectedLanguage: Language,
    onDismiss: () -> Unit,
    onAddTrack: (uriString: String, title: String) -> Unit,
    onDeleteTrack: (Long) -> Unit,
    onPlayTrack: (SavedMusicTrackEntity) -> Unit,
    onSelectBeatPreset: (OfflineBeatPreset) -> Unit,
    onVolumeChange: (Float) -> Unit
) {
    val context = LocalContext.current
    val isBn = selectedLanguage == Language.BENGALI

    val audioPickerLauncher = rememberLauncherForActivityResult(
        contract = ActivityResultContracts.OpenMultipleDocuments()
    ) { uris: List<Uri> ->
        uris.forEach { uri ->
            try {
                context.contentResolver.takePersistableUriPermission(
                    uri,
                    Intent.FLAG_GRANT_READ_URI_PERMISSION
                )
            } catch (_: Exception) {
            }
            val displayName = resolveAudioFileName(context, uri)
            onAddTrack(uri.toString(), displayName)
        }
    }

    AlertDialog(
        onDismissRequest = onDismiss,
        title = {
            Column {
                Text(
                    text = if (isBn) "🎵 ওয়ার্কআউট মিউজিক ও জিম বিটস" else "🎵 Workout Music & Gym Beats",
                    style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Bold)
                )
                Spacer(modifier = Modifier.height(2.dp))
                Text(
                    text = if (isBn) "ভয়েস কোচ কথা বলার সময় গানের সাউন্ড অটোমেটিক কমে যাবে (Smart Audio Ducking)"
                    else "Music automatically ducks when the voice coach speaks",
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        },
        text = {
            Column(modifier = Modifier.fillMaxWidth()) {
                // Volume Slider
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    verticalAlignment = Alignment.CenterVertically,
                    horizontalArrangement = Arrangement.SpaceBetween
                ) {
                    Text(
                        text = if (isBn) "মিউজিক ভলিউম:" else "Music Volume:",
                        style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.Bold)
                    )
                    Text(
                        text = "${(musicState.volume * 100).toInt()}%",
                        style = MaterialTheme.typography.labelMedium,
                        color = MaterialTheme.colorScheme.primary
                    )
                }
                Slider(
                    value = musicState.volume,
                    onValueChange = onVolumeChange,
                    valueRange = 0.1f..1.0f,
                    modifier = Modifier.fillMaxWidth()
                )

                Spacer(modifier = Modifier.height(8.dp))

                // Section 1: Built-in Offline Gym Rhythm Beats
                Text(
                    text = if (isBn) "⚡ অফলাইন জিম রিদম বিটস (ইন্টারনেট বা ফাইল ছাড়া)" else "⚡ Built-in Offline Gym Beats",
                    style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.primary
                )
                Spacer(modifier = Modifier.height(6.dp))

                OfflineBeatPreset.values().filter { it != OfflineBeatPreset.NONE }.forEach { preset ->
                    val isSelected = musicState.activeBeatPreset == preset && musicState.isPlaying
                    Surface(
                        shape = RoundedCornerShape(12.dp),
                        color = if (isSelected) MaterialTheme.colorScheme.primaryContainer else MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.5f),
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(vertical = 3.dp)
                            .clickable {
                                if (isSelected) {
                                    onSelectBeatPreset(OfflineBeatPreset.NONE)
                                } else {
                                    onSelectBeatPreset(preset)
                                }
                            }
                    ) {
                        Row(
                            modifier = Modifier.padding(horizontal = 12.dp, vertical = 10.dp),
                            verticalAlignment = Alignment.CenterVertically,
                            horizontalArrangement = Arrangement.SpaceBetween
                        ) {
                            Column(modifier = Modifier.weight(1f)) {
                                Text(
                                    text = if (isBn) preset.titleBn else preset.titleEn,
                                    style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.Bold),
                                    color = MaterialTheme.colorScheme.onSurface
                                )
                            }
                            Icon(
                                imageVector = if (isSelected) Icons.Default.Pause else Icons.Default.PlayArrow,
                                contentDescription = null,
                                tint = MaterialTheme.colorScheme.primary
                            )
                        }
                    }
                }

                Spacer(modifier = Modifier.height(14.dp))

                // Section 2: User's Saved Phone Songs
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.SpaceBetween,
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Text(
                        text = if (isBn) "📱 আমার ফোনের সেভ করা গান (${savedTracks.size})" else "📱 My Phone Songs (${savedTracks.size})",
                        style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.secondary
                    )
                    Button(
                        onClick = { audioPickerLauncher.launch(arrayOf("audio/*")) },
                        shape = RoundedCornerShape(10.dp),
                        colors = ButtonDefaults.buttonColors(containerColor = MaterialTheme.colorScheme.primary),
                        modifier = Modifier.height(34.dp)
                    ) {
                        Icon(Icons.Default.Add, contentDescription = null, modifier = Modifier.size(16.dp))
                        Spacer(modifier = Modifier.width(4.dp))
                        Text(
                            text = if (isBn) "গান যোগ করুন" else "Add Songs",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(8.dp))

                if (savedTracks.isEmpty()) {
                    Surface(
                        shape = RoundedCornerShape(12.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.35f),
                        modifier = Modifier.fillMaxWidth()
                    ) {
                        Text(
                            text = if (isBn) "এখনো কোনো গান যোগ করা হয়নি। 'গান যোগ করুন' বাটনে ট্যাপ করে ফোনের মেমোরি থেকে আপনার পছন্দের গান সিলেক্ট করুন।"
                            else "No songs added yet. Tap 'Add Songs' to select your favorite MP3/Audio files from your phone.",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant,
                            modifier = Modifier.padding(12.dp)
                        )
                    }
                } else {
                    LazyColumn(
                        modifier = Modifier
                            .fillMaxWidth()
                            .heightIn(max = 180.dp),
                        verticalArrangement = Arrangement.spacedBy(6.dp)
                    ) {
                        items(savedTracks, key = { it.id }) { track ->
                            val isCurrent = musicState.currentTrackId == track.id && musicState.isPlaying
                            Surface(
                                shape = RoundedCornerShape(10.dp),
                                color = if (isCurrent) MaterialTheme.colorScheme.primaryContainer else MaterialTheme.colorScheme.surface,
                                modifier = Modifier
                                    .fillMaxWidth()
                                    .clickable { onPlayTrack(track) }
                            ) {
                                Row(
                                    modifier = Modifier.padding(horizontal = 10.dp, vertical = 8.dp),
                                    verticalAlignment = Alignment.CenterVertically,
                                    horizontalArrangement = Arrangement.SpaceBetween
                                ) {
                                    Row(
                                        verticalAlignment = Alignment.CenterVertically,
                                        modifier = Modifier.weight(1f)
                                    ) {
                                        Icon(
                                            imageVector = if (isCurrent) Icons.Default.GraphicEq else Icons.Default.MusicNote,
                                            contentDescription = null,
                                            tint = if (isCurrent) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.onSurfaceVariant,
                                            modifier = Modifier.size(18.dp)
                                        )
                                        Spacer(modifier = Modifier.width(8.dp))
                                        Text(
                                            text = track.title,
                                            style = MaterialTheme.typography.bodySmall.copy(
                                                fontWeight = if (isCurrent) FontWeight.Bold else FontWeight.Medium
                                            ),
                                            maxLines = 1,
                                            overflow = TextOverflow.Ellipsis
                                        )
                                    }
                                    IconButton(
                                        onClick = { onDeleteTrack(track.id) },
                                        modifier = Modifier.size(28.dp)
                                    ) {
                                        Icon(
                                            imageVector = Icons.Default.Delete,
                                            contentDescription = "Remove Track",
                                            tint = MaterialTheme.colorScheme.error,
                                            modifier = Modifier.size(16.dp)
                                        )
                                    }
                                }
                            }
                        }
                    }
                }
            }
        },
        confirmButton = {
            TextButton(onClick = onDismiss) {
                Text(if (isBn) "সম্পন্ন" else "Done", fontWeight = FontWeight.Bold)
            }
        }
    )
}

private fun resolveAudioFileName(context: Context, uri: Uri): String {
    var result: String? = null
    if (uri.scheme == "content") {
        try {
            context.contentResolver.query(uri, null, null, null, null)?.use { cursor ->
                if (cursor.moveToFirst()) {
                    val idx = cursor.getColumnIndex(OpenableColumns.DISPLAY_NAME)
                    if (idx >= 0) {
                        result = cursor.getString(idx)
                    }
                }
            }
        } catch (_: Exception) {
        }
    }
    if (result.isNullOrBlank()) {
        result = uri.lastPathSegment?.substringAfterLast('/') ?: "Workout Track"
    }
    return result.removeSuffix(".mp3").removeSuffix(".m4a").removeSuffix(".wav")
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/profile/ProfileScreen.kt`

```kotlin
package com.example.ui.screens.profile

import android.widget.Toast
import androidx.activity.compose.rememberLauncherForActivityResult
import androidx.activity.result.contract.ActivityResultContracts
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.PaddingValues
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.text.KeyboardOptions
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.DarkMode
import androidx.compose.material.icons.filled.DeleteForever
import androidx.compose.material.icons.filled.FileDownload
import androidx.compose.material.icons.filled.Language
import androidx.compose.material.icons.filled.LightMode
import androidx.compose.material.icons.filled.LockOpen
import androidx.compose.material.icons.filled.Person
import androidx.compose.material.icons.filled.Save
import androidx.compose.material.icons.filled.Verified
import androidx.compose.material.icons.filled.WorkspacePremium
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedButton
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.OutlinedTextFieldDefaults
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableFloatStateOf
import androidx.compose.runtime.mutableIntStateOf
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.input.KeyboardType
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.domain.model.UserProfile
import java.io.File
import java.io.FileInputStream
import kotlin.math.roundToInt

@Composable
fun ProfileScreen(
    userProfile: UserProfile?,
    selectedLanguage: Language,
    isDarkMode: Boolean,
    strings: AppStrings,
    isProSubscribed: Boolean,
    onOpenProDialog: () -> Unit,
    onToggleLanguage: () -> Unit,
    onToggleTheme: () -> Unit,
    onSaveProfile: (name: String, age: Int, heightCm: Float, weightKg: Float, goal: String, fitnessLevel: String) -> Unit,
    onResetAllData: () -> Unit,
    modifier: Modifier = Modifier
) {
    val context = LocalContext.current

    var name by remember(userProfile) { mutableStateOf(userProfile?.name ?: "Athlete") }
    var age by remember(userProfile) { mutableIntStateOf(userProfile?.age ?: 24) }
    var heightCm by remember(userProfile) { mutableFloatStateOf(userProfile?.heightCm ?: 175f) }
    var weightKg by remember(userProfile) { mutableFloatStateOf(userProfile?.weightKg ?: 68f) }
    var goal by remember(userProfile) { mutableStateOf(userProfile?.goal ?: "fitness") }
    var fitnessLevel by remember(userProfile) { mutableStateOf(userProfile?.fitnessLevel ?: "intermediate") }

    var showResetDialog by remember { mutableStateOf(false) }

    // APK Document export launcher
    val exportApkLauncher = rememberLauncherForActivityResult(
        contract = ActivityResultContracts.CreateDocument("application/vnd.android.package-archive")
    ) { uri ->
        if (uri != null) {
            try {
                val apkPath = context.applicationInfo.sourceDir
                val sourceFile = File(apkPath)
                if (sourceFile.exists()) {
                    context.contentResolver.openOutputStream(uri)?.use { output ->
                        FileInputStream(sourceFile).use { input ->
                            input.copyTo(output)
                        }
                    }
                    Toast.makeText(context, "HomeFit Pro v5.0 APK সফলভাবে সেভ হয়েছে!", Toast.LENGTH_LONG).show()
                } else {
                    Toast.makeText(context, "APK ফাইল পাওয়া যায়নি", Toast.LENGTH_SHORT).show()
                }
            } catch (e: Exception) {
                Toast.makeText(context, "এক্সপোর্ট ত্রুটি: ${e.localizedMessage}", Toast.LENGTH_SHORT).show()
            }
        }
    }

    if (showResetDialog) {
        AlertDialog(
            onDismissRequest = { showResetDialog = false },
            title = { Text(text = "সব ডেটা রিসেট করবেন?") },
            text = { Text(text = "আপনার সমস্ত সেভ করা ওয়ার্কআউট, ওয়াটার লগ ও প্রোফাইল ডাটা মুছে যাবে।") },
            confirmButton = {
                Button(
                    onClick = {
                        showResetDialog = false
                        onResetAllData()
                        Toast.makeText(context, "সব ডেটা রিসেট হয়েছে", Toast.LENGTH_SHORT).show()
                    },
                    colors = ButtonDefaults.buttonColors(containerColor = MaterialTheme.colorScheme.error)
                ) {
                    Text("রিসেট করুন")
                }
            },
            dismissButton = {
                TextButton(onClick = { showResetDialog = false }) {
                    Text("বাতিল")
                }
            }
        )
    }

    LazyColumn(
        modifier = modifier
            .fillMaxSize()
            .testTag("profile_screen"),
        contentPadding = PaddingValues(start = 20.dp, end = 20.dp, top = 16.dp, bottom = 100.dp)
    ) {
        // User Header Card
        item {
            Card(
                modifier = Modifier.fillMaxWidth(),
                shape = RoundedCornerShape(18.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                border = BorderStroke(1.dp, MaterialTheme.colorScheme.outlineVariant)
            ) {
                Row(
                    modifier = Modifier.padding(16.dp),
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Box(
                        modifier = Modifier
                            .size(54.dp)
                            .background(MaterialTheme.colorScheme.primary.copy(alpha = 0.15f), CircleShape)
                            .border(1.5.dp, MaterialTheme.colorScheme.primary, CircleShape),
                        contentAlignment = Alignment.Center
                    ) {
                        Icon(
                            imageVector = Icons.Default.Person,
                            contentDescription = "Profile",
                            tint = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.size(28.dp)
                        )
                    }

                    Spacer(modifier = Modifier.width(14.dp))

                    Column {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Text(
                                text = name,
                                style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Bold)
                            )
                            if (isProSubscribed) {
                                Spacer(modifier = Modifier.width(6.dp))
                                Icon(
                                    imageVector = Icons.Default.Verified,
                                    contentDescription = "VIP Pro",
                                    tint = Color(0xFFFFB300),
                                    modifier = Modifier.size(18.dp)
                                )
                            }
                        }
                        Text(
                            text = if (isProSubscribed) "HomeFit VIP Pro Member (Unlocked)" else "Free Member • Use IshanX10 to Unlock",
                            fontSize = 12.sp,
                            color = if (isProSubscribed) Color(0xFFFFB300) else MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            }
            Spacer(modifier = Modifier.height(16.dp))
        }

        // Pro VIP Subscription Card (with secret code IshanX10)
        item {
            Card(
                modifier = Modifier.fillMaxWidth(),
                shape = RoundedCornerShape(18.dp),
                colors = CardDefaults.cardColors(
                    containerColor = if (isProSubscribed) Color(0xFF1E283D) else MaterialTheme.colorScheme.surface
                ),
                border = BorderStroke(1.dp, if (isProSubscribed) Color(0xFFFFB300) else MaterialTheme.colorScheme.outlineVariant)
            ) {
                Column(modifier = Modifier.padding(16.dp)) {
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Icon(
                                imageVector = Icons.Default.WorkspacePremium,
                                contentDescription = "VIP Pro",
                                tint = Color(0xFFFFB300),
                                modifier = Modifier.size(22.dp)
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Text(
                                text = if (isProSubscribed) "VIP PRO মেম্বারশিপ সক্রিয়" else "HomeFit Pro সাবস্ক্রিপশন",
                                style = MaterialTheme.typography.titleMedium.copy(
                                    fontWeight = FontWeight.Bold,
                                    color = if (isProSubscribed) Color(0xFFFFB300) else MaterialTheme.colorScheme.onSurface
                                )
                            )
                        }

                        if (isProSubscribed) {
                            Text(
                                text = "ACTIVE",
                                color = Color(0xFF00E676),
                                fontSize = 11.sp,
                                fontWeight = FontWeight.Bold
                            )
                        }
                    }

                    Spacer(modifier = Modifier.height(8.dp))

                    Text(
                        text = if (isProSubscribed)
                            "গোপন কোড IshanX10 দিয়ে সমস্ত প্রিমিয়াম ওয়ার্কআউট, অ্যাডভান্সড ৩ডি ম্যানিকুইন অ্যানিমেশন এবং ভিআইপি ডায়েট চার্ট আনলক করা হয়েছে।"
                        else
                            "গোপন কোড (IshanX10) দিয়ে সমস্ত প্রিমিয়াম ফিচার ও অ্যাডভান্সড ৩ডি অ্যানিমেশন আনলক করুন।",
                        fontSize = 12.sp,
                        color = MaterialTheme.colorScheme.onSurfaceVariant,
                        lineHeight = 16.sp
                    )

                    Spacer(modifier = Modifier.height(12.dp))

                    Button(
                        onClick = onOpenProDialog,
                        colors = ButtonDefaults.buttonColors(containerColor = Color(0xFFFFB300)),
                        shape = RoundedCornerShape(10.dp),
                        modifier = Modifier
                            .fillMaxWidth()
                            .height(44.dp)
                            .testTag("redeem_pro_code_btn")
                    ) {
                        Icon(
                            imageVector = Icons.Default.LockOpen,
                            contentDescription = "Redeem",
                            tint = Color(0xFF080B10)
                        )
                        Spacer(modifier = Modifier.width(6.dp))
                        Text(
                            text = if (isProSubscribed) "প্রো কোড স্ট্যাটাস দেখুন" else "গোপন কোড দিয়ে প্রো আনলক করুন (IshanX10)",
                            color = Color(0xFF080B10),
                            fontWeight = FontWeight.Bold,
                            fontSize = 12.sp
                        )
                    }
                }
            }
            Spacer(modifier = Modifier.height(16.dp))
        }

        // APK Download & Export Card
        item {
            Card(
                modifier = Modifier.fillMaxWidth(),
                shape = RoundedCornerShape(18.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                border = BorderStroke(1.dp, MaterialTheme.colorScheme.outlineVariant)
            ) {
                Column(modifier = Modifier.padding(16.dp)) {
                    Text(
                        text = "HomeFit Pro v5.0 APK ইন্সটলার ও ডাউনলোড",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                    )
                    Spacer(modifier = Modifier.height(6.dp))
                    Text(
                        text = "ফোনে সরাসরি এই অ্যাপটি ইন্সটল করার জন্য সাইন্ড APK ফাইল এক্সপোর্ট করুন অথবা ক্রোম ব্রাউজার দিয়ে কোড ফোল্ডার থেকে HomeFit_v5.0.apk ফাইলটি ডাউনলোড করে নিন।",
                        fontSize = 12.sp,
                        color = MaterialTheme.colorScheme.onSurfaceVariant,
                        lineHeight = 16.sp
                    )

                    Spacer(modifier = Modifier.height(12.dp))

                    Button(
                        onClick = {
                            exportApkLauncher.launch("HomeFit_Pro_v5.0.apk")
                        },
                        colors = ButtonDefaults.buttonColors(containerColor = MaterialTheme.colorScheme.primary),
                        shape = RoundedCornerShape(10.dp),
                        modifier = Modifier
                            .fillMaxWidth()
                            .height(46.dp)
                            .testTag("export_homefit_apk_btn")
                    ) {
                        Icon(
                            imageVector = Icons.Default.FileDownload,
                            contentDescription = "Export APK",
                            tint = MaterialTheme.colorScheme.onPrimary
                        )
                        Spacer(modifier = Modifier.width(6.dp))
                        Text(
                            text = "EXPORT HOMEFIT PRO V5.0 APK",
                            color = MaterialTheme.colorScheme.onPrimary,
                            fontWeight = FontWeight.Bold,
                            fontSize = 12.sp
                        )
                    }
                }
            }
            Spacer(modifier = Modifier.height(16.dp))
        }

        // Biometrics Editor Card
        item {
            Card(
                modifier = Modifier.fillMaxWidth(),
                shape = RoundedCornerShape(18.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                border = BorderStroke(1.dp, MaterialTheme.colorScheme.outlineVariant)
            ) {
                Column(modifier = Modifier.padding(16.dp)) {
                    Text(
                        text = "শারীরিক তথ্য ও ক্যালকুলেশন এডিটর",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                    )
                    Spacer(modifier = Modifier.height(12.dp))

                    OutlinedTextField(
                        value = name,
                        onValueChange = { name = it },
                        label = { Text("নাম") },
                        modifier = Modifier.fillMaxWidth()
                    )
                    Spacer(modifier = Modifier.height(8.dp))

                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.spacedBy(10.dp)
                    ) {
                        OutlinedTextField(
                            value = age.toString(),
                            onValueChange = { age = it.toIntOrNull() ?: age },
                            label = { Text("বয়স (বছর)") },
                            keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Number),
                            modifier = Modifier.weight(1f)
                        )
                        OutlinedTextField(
                            value = weightKg.toString(),
                            onValueChange = { weightKg = it.toFloatOrNull() ?: weightKg },
                            label = { Text("ওজন (কেজি)") },
                            keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Decimal),
                            modifier = Modifier.weight(1f)
                        )
                    }
                    Spacer(modifier = Modifier.height(8.dp))

                    OutlinedTextField(
                        value = heightCm.toString(),
                        onValueChange = { heightCm = it.toFloatOrNull() ?: heightCm },
                        label = { Text("উচ্চতা (সেমি)") },
                        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Decimal),
                        modifier = Modifier.fillMaxWidth()
                    )

                    Spacer(modifier = Modifier.height(14.dp))

                    Button(
                        onClick = {
                            onSaveProfile(name, age, heightCm, weightKg, goal, fitnessLevel)
                            Toast.makeText(context, "প্রোফাইল তথ্য ও হাইড্রেশন লক্ষ্যমাত্রা আপডেট হয়েছে!", Toast.LENGTH_SHORT).show()
                        },
                        shape = RoundedCornerShape(10.dp),
                        modifier = Modifier.fillMaxWidth()
                    ) {
                        Icon(imageVector = Icons.Default.Save, contentDescription = "Save")
                        Spacer(modifier = Modifier.width(6.dp))
                        Text("তথ্য সংরক্ষণ ও হিসাব আপডেট")
                    }
                }
            }
            Spacer(modifier = Modifier.height(16.dp))
        }

        // App Preferences (Language & Theme)
        item {
            Card(
                modifier = Modifier.fillMaxWidth(),
                shape = RoundedCornerShape(18.dp),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                border = BorderStroke(1.dp, MaterialTheme.colorScheme.outlineVariant)
            ) {
                Column(modifier = Modifier.padding(16.dp)) {
                    Text(
                        text = "অ্যাপ সেটিংস",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                    )
                    Spacer(modifier = Modifier.height(10.dp))

                    Row(
                        modifier = Modifier
                            .fillMaxWidth()
                            .clickable { onToggleLanguage() }
                            .padding(vertical = 10.dp),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Icon(Icons.Default.Language, contentDescription = "Language", tint = MaterialTheme.colorScheme.primary)
                            Spacer(modifier = Modifier.width(10.dp))
                            Text("ভাষা (Language)")
                        }
                        Text(
                            text = if (selectedLanguage == Language.BENGALI) "বাংলা" else "English",
                            fontWeight = FontWeight.Bold,
                            color = MaterialTheme.colorScheme.primary
                        )
                    }

                    Row(
                        modifier = Modifier
                            .fillMaxWidth()
                            .clickable { onToggleTheme() }
                            .padding(vertical = 10.dp),
                        horizontalArrangement = Arrangement.SpaceBetween,
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Icon(
                                if (isDarkMode) Icons.Default.DarkMode else Icons.Default.LightMode,
                                contentDescription = "Theme",
                                tint = MaterialTheme.colorScheme.primary
                            )
                            Spacer(modifier = Modifier.width(10.dp))
                            Text("থিম মোড")
                        }
                        Text(
                            text = if (isDarkMode) "ডার্ক মোড (Dark)" else "লাইট মোড (Light)",
                            fontWeight = FontWeight.Bold,
                            color = MaterialTheme.colorScheme.primary
                        )
                    }

                    Spacer(modifier = Modifier.height(10.dp))

                    OutlinedButton(
                        onClick = { showResetDialog = true },
                        colors = ButtonDefaults.outlinedButtonColors(contentColor = MaterialTheme.colorScheme.error),
                        border = BorderStroke(1.dp, MaterialTheme.colorScheme.error),
                        shape = RoundedCornerShape(10.dp),
                        modifier = Modifier.fillMaxWidth()
                    ) {
                        Icon(Icons.Default.DeleteForever, contentDescription = "Reset", modifier = Modifier.size(16.dp))
                        Spacer(modifier = Modifier.width(6.dp))
                        Text("সমস্ত ডেটা রিসেট করুন")
                    }
                }
            }
            Spacer(modifier = Modifier.height(20.dp))
        }

        // Version Footer
        item {
            Column(
                modifier = Modifier.fillMaxWidth(),
                horizontalAlignment = Alignment.CenterHorizontally
            ) {
                Text(
                    text = "HomeFit Pro v5.0 • Made with ❤️ for Fitness",
                    fontSize = 12.sp,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
                Text(
                    text = "3D Anatomical Mannequin Edition",
                    fontSize = 11.sp,
                    color = MaterialTheme.colorScheme.primary
                )
            }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/progress/ProgressScreen.kt`

```kotlin
package com.example.ui.screens.progress

import android.content.ClipData
import android.content.ClipboardManager
import android.content.Context
import android.widget.Toast
import kotlinx.coroutines.launch
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.Backup
import androidx.compose.material.icons.filled.CheckCircle
import androidx.compose.material.icons.filled.ContentCopy
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.LocalFireDepartment
import androidx.compose.material.icons.filled.Scale
import androidx.compose.material.icons.filled.Timer
import androidx.compose.material.icons.filled.WaterDrop
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.data.local.entity.WaterLogEntity
import com.example.data.local.entity.WeightLogEntity
import com.example.data.local.entity.WorkoutLogEntity
import com.example.domain.model.UserProfile
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitCard
import com.example.ui.components.HomeFitOutlinedButton
import com.example.ui.components.charts.StreakCalendarHeatmap
import com.example.ui.components.charts.WaterIntakeBarChart
import com.example.ui.components.charts.WeightTrendChart
import com.example.ui.screens.player.CompletionStatCard
import java.text.SimpleDateFormat
import java.util.Date
import java.util.Locale

import androidx.compose.foundation.BorderStroke
import com.example.data.local.entity.ChallengeProgressEntity
import com.example.ui.screens.player.WorkoutCardShareHelper

@Composable
fun ProgressScreen(
    userProfile: UserProfile?,
    weightLogs: List<WeightLogEntity>,
    waterLogs: List<WaterLogEntity>,
    workoutLogs: List<WorkoutLogEntity>,
    todayWaterGlasses: Int,
    streakDays: Int,
    selectedLanguage: Language,
    strings: AppStrings,
    onOpenWeightDialog: () -> Unit,
    onAddWaterGlass: () -> Unit,
    onExportBackup: suspend () -> String,
    onImportBackup: suspend (String) -> Boolean,
    challengeProgressList: List<ChallengeProgressEntity> = emptyList(),
    customWorkoutsCount: Int = 0,
    todayNutritionCount: Int = 0,
    modifier: Modifier = Modifier
) {
    val context = LocalContext.current
    val scrollState = rememberScrollState()
    val coroutineScope = androidx.compose.runtime.rememberCoroutineScope()

    var showExportDialog by remember { mutableStateOf(false) }
    var exportedJsonContent by remember { mutableStateOf("") }
    var showImportDialog by remember { mutableStateOf(false) }
    var importJsonInput by remember { mutableStateOf("") }
    var importError by remember { mutableStateOf<String?>(null) }

    val totalWorkouts = workoutLogs.size
    val totalCalories = workoutLogs.sumOf { it.caloriesBurned }
    val totalSeconds = workoutLogs.sumOf { it.durationSeconds }
    val totalMinutes = totalSeconds / 60

    val completedDatesIso = remember(workoutLogs) {
        workoutLogs.map {
            SimpleDateFormat("yyyy-MM-dd", Locale.US).format(Date(it.completedAtMillis))
        }.toSet()
    }

    // Export Backup Dialog
    if (showExportDialog) {
        AlertDialog(
            onDismissRequest = { showExportDialog = false },
            title = {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "অফলাইন JSON ব্যাকআপ" else "Offline JSON Backup",
                    style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Bold)
                )
            },
            text = {
                Column(modifier = Modifier.fillMaxWidth()) {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "আপনার সকল ওয়ার্কআউট, ওজন ও পানি লগ নিরাপদে এনকোড করা হয়েছে। এটি কপি করে সংরক্ষণ করতে পারেন।"
                        else "All your data has been exported to offline JSON. Copy and keep it safe.",
                        style = MaterialTheme.typography.bodySmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Spacer(modifier = Modifier.height(10.dp))
                    OutlinedTextField(
                        value = exportedJsonContent,
                        onValueChange = {},
                        readOnly = true,
                        maxLines = 8,
                        modifier = Modifier.fillMaxWidth()
                    )
                }
            },
            confirmButton = {
                Button(
                    onClick = {
                        val clipboard = context.getSystemService(Context.CLIPBOARD_SERVICE) as ClipboardManager
                        val clip = ClipData.newPlainText("HomeFit Backup", exportedJsonContent)
                        clipboard.setPrimaryClip(clip)
                        Toast.makeText(context, if (selectedLanguage == Language.BENGALI) "ক্লিপবোর্ডে কপি হয়েছে!" else "Copied to clipboard!", Toast.LENGTH_SHORT).show()
                        showExportDialog = false
                    }
                ) {
                    Icon(imageVector = Icons.Default.ContentCopy, contentDescription = null, modifier = Modifier.size(16.dp))
                    Spacer(modifier = Modifier.width(6.dp))
                    Text(text = if (selectedLanguage == Language.BENGALI) "কপি করুন" else "Copy JSON")
                }
            },
            dismissButton = {
                TextButton(onClick = { showExportDialog = false }) {
                    Text(text = if (selectedLanguage == Language.BENGALI) "বন্ধ করুন" else "Close")
                }
            }
        )
    }

    // Import Backup Dialog
    if (showImportDialog) {
        AlertDialog(
            onDismissRequest = { showImportDialog = false },
            title = {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "ডাটা রিস্টোর ইমপোর্ট" else "Restore Backup JSON",
                    style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Bold)
                )
            },
            text = {
                Column(modifier = Modifier.fillMaxWidth()) {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "পূর্বে এক্সপোর্ট করা ব্যাকআপ JSON কোডটি নিচে পেস্ট করুন:"
                        else "Paste your previously exported backup JSON content below:",
                        style = MaterialTheme.typography.bodySmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Spacer(modifier = Modifier.height(10.dp))
                    OutlinedTextField(
                        value = importJsonInput,
                        onValueChange = {
                            importJsonInput = it
                            importError = null
                        },
                        placeholder = { Text("{\n  \"version\": 1...\n}") },
                        isError = importError != null,
                        supportingText = { if (importError != null) Text(importError!!, color = MaterialTheme.colorScheme.error) },
                        maxLines = 8,
                        modifier = Modifier.fillMaxWidth()
                    )
                }
            },
            confirmButton = {
                Button(
                    onClick = {
                        if (importJsonInput.isBlank()) {
                            importError = "দয়া করে JSON কোড পেস্ট করুন।"
                        } else {
                            coroutineScope.launch {
                                val success = onImportBackup(importJsonInput.trim())
                                if (success) {
                                    Toast.makeText(context, if (selectedLanguage == Language.BENGALI) "ডাটা সফলভাবে রিস্টোর হয়েছে!" else "Data restored successfully!", Toast.LENGTH_LONG).show()
                                    showImportDialog = false
                                } else {
                                    importError = "ভুল বা অকার্যকর JSON ফরম্যাট।"
                                }
                            }
                        }
                    }
                ) {
                    Text(text = if (selectedLanguage == Language.BENGALI) "রিস্টোর করুন" else "Restore")
                }
            },
            dismissButton = {
                TextButton(onClick = { showImportDialog = false }) {
                    Text(text = if (selectedLanguage == Language.BENGALI) "বাতিল" else "Cancel")
                }
            }
        )
    }

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(MaterialTheme.colorScheme.background)
            .padding(16.dp)
            .verticalScroll(scrollState)
            .testTag("progress_screen")
    ) {
        // Top Header
        Text(
            text = if (selectedLanguage == Language.BENGALI) "অগ্রগতি ও অ্যানালিটিক্স" else "Progress & Analytics",
            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(14.dp))

        // 4 KPI Summary Cards Grid
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            CompletionStatCard(
                icon = Icons.Default.FitnessCenter,
                value = "$totalWorkouts",
                label = if (selectedLanguage == Language.BENGALI) "ওয়ার্কআউট" else "Workouts",
                color = MaterialTheme.colorScheme.primary,
                modifier = Modifier.weight(1f)
            )

            CompletionStatCard(
                icon = Icons.Default.Timer,
                value = "$totalMinutes m",
                label = if (selectedLanguage == Language.BENGALI) "মোট সময়" else "Minutes",
                color = MaterialTheme.colorScheme.tertiary,
                modifier = Modifier.weight(1f)
            )

            CompletionStatCard(
                icon = Icons.Default.LocalFireDepartment,
                value = "$totalCalories",
                label = if (selectedLanguage == Language.BENGALI) "ক্যালরি" else "Calories",
                color = MaterialTheme.colorScheme.secondary,
                modifier = Modifier.weight(1f)
            )
        }

        Spacer(modifier = Modifier.height(12.dp))

        HomeFitOutlinedButton(
            text = if (selectedLanguage == Language.BENGALI) "📸 সামগ্রিক প্রগ্রেস কার্ড শেয়ার করুন" else "📸 Share Overall Progress Card",
            onClick = {
                WorkoutCardShareHelper.shareWorkoutCard(
                    context = context,
                    userName = userProfile?.name.orEmpty(),
                    workoutTitle = if (selectedLanguage == Language.BENGALI) "মোট $totalWorkouts টি সেশন সম্পন্ন" else "$totalWorkouts Total Workouts",
                    durationText = "$totalMinutes m",
                    caloriesBurned = totalCalories,
                    exercisesCount = workoutLogs.sumOf { it.exercisesCompleted },
                    streakDays = streakDays,
                    language = selectedLanguage
                )
            },
            testTag = "share_overall_progress_card_btn"
        )

        Spacer(modifier = Modifier.height(20.dp))

        // Achievement Badges & Trophy Cabinet
        val totalChallengeDays = remember(challengeProgressList) {
            challengeProgressList.sumOf { entity ->
                entity.completedDaysCsv.split(",").count { it.trim().toIntOrNull() != null }
            }
        }
        AchievementTrophyCabinetCard(
            totalWorkouts = totalWorkouts,
            totalCalories = totalCalories,
            streakDays = streakDays,
            todayWaterGlasses = todayWaterGlasses,
            totalChallengeDays = totalChallengeDays,
            customWorkoutsCount = customWorkoutsCount,
            todayNutritionCount = todayNutritionCount,
            selectedLanguage = selectedLanguage
        )

        Spacer(modifier = Modifier.height(20.dp))

        // 1. Streak Calendar
        StreakCalendarHeatmap(
            streakDays = streakDays,
            completedWorkoutDatesIso = completedDatesIso,
            selectedLanguage = selectedLanguage
        )

        Spacer(modifier = Modifier.height(20.dp))

        // 2. Weight Trend & Tracker
        WeightTrendChart(
            weightLogs = weightLogs,
            selectedLanguage = selectedLanguage
        )

        Spacer(modifier = Modifier.height(10.dp))

        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.SpaceBetween,
            verticalAlignment = Alignment.CenterVertically
        ) {
            Text(
                text = "${if (selectedLanguage == Language.BENGALI) "বর্তমান ওজন:" else "Current:"} ${userProfile?.weightKg ?: 65f} kg",
                style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                color = MaterialTheme.colorScheme.onBackground
            )

            HomeFitButton(
                text = if (selectedLanguage == Language.BENGALI) "+ ওজন লগ করুন" else "+ Log Weight",
                onClick = onOpenWeightDialog,
                modifier = Modifier.width(160.dp),
                testTag = "log_weight_progress_btn"
            )
        }

        Spacer(modifier = Modifier.height(20.dp))

        // 3. Water Intake History
        WaterIntakeBarChart(
            waterLogs = waterLogs,
            todayGlasses = todayWaterGlasses,
            selectedLanguage = selectedLanguage
        )

        Spacer(modifier = Modifier.height(10.dp))

        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.SpaceBetween,
            verticalAlignment = Alignment.CenterVertically
        ) {
            Text(
                text = "${if (selectedLanguage == Language.BENGALI) "আজকের পানি:" else "Today:"} $todayWaterGlasses ${if (selectedLanguage == Language.BENGALI) "গ্লাস" else "glasses"}",
                style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                color = MaterialTheme.colorScheme.onBackground
            )

            HomeFitButton(
                text = if (selectedLanguage == Language.BENGALI) "+ ১ গ্লাস পানি" else "+ 1 Glass",
                onClick = onAddWaterGlass,
                modifier = Modifier.width(160.dp),
                testTag = "add_water_progress_btn"
            )
        }

        Spacer(modifier = Modifier.height(24.dp))

        // 4. Workout History Log (Recent completed workouts)
        Text(
            text = if (selectedLanguage == Language.BENGALI) "সাম্প্রতিক ওয়ার্কআউট সেশনসমূহ (${workoutLogs.size})" else "Recent Workout History (${workoutLogs.size})",
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(10.dp))

        if (workoutLogs.isEmpty()) {
            HomeFitCard {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "এখনো কোনো ওয়ার্কআউট সম্পন্ন করা হয়নি। আজই আপনার প্রথম সেশনটি শুরু করুন!"
                    else "No workouts completed yet. Start your first session today!",
                    style = MaterialTheme.typography.bodyMedium,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        } else {
            Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                workoutLogs.take(5).forEach { log ->
                    val dateStr = SimpleDateFormat("dd MMM, hh:mm a", Locale.getDefault()).format(Date(log.completedAtMillis))
                    HomeFitCard {
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            verticalAlignment = Alignment.CenterVertically,
                            horizontalArrangement = Arrangement.SpaceBetween
                        ) {
                            Column(modifier = Modifier.weight(1f)) {
                                Text(
                                    text = log.workoutTitle,
                                    style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                                    color = MaterialTheme.colorScheme.onSurface
                                )
                                Spacer(modifier = Modifier.height(2.dp))
                                Text(
                                    text = dateStr,
                                    style = MaterialTheme.typography.bodySmall.copy(fontSize = 11.sp),
                                    color = MaterialTheme.colorScheme.onSurfaceVariant
                                )
                            }
                            Column(horizontalAlignment = Alignment.End) {
                                Text(
                                    text = "🔥 ${log.caloriesBurned} kcal",
                                    style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                    color = MaterialTheme.colorScheme.primary
                                )
                                Text(
                                    text = "⏱️ ${log.durationSeconds / 60}m ${log.durationSeconds % 60}s",
                                    style = MaterialTheme.typography.bodySmall.copy(fontSize = 11.sp),
                                    color = MaterialTheme.colorScheme.secondary
                                )
                            }
                        }
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(24.dp))

        // 5. Offline JSON Backup & Restore Card
        HomeFitCard(borderColor = MaterialTheme.colorScheme.tertiary) {
            Column {
                Row(verticalAlignment = Alignment.CenterVertically) {
                    Icon(
                        imageVector = Icons.Default.Backup,
                        contentDescription = null,
                        tint = MaterialTheme.colorScheme.tertiary,
                        modifier = Modifier.size(24.dp)
                    )
                    Spacer(modifier = Modifier.width(8.dp))
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "অফলাইন লোকাল ব্যাকআপ ও রিস্টোর" else "Offline Local Backup & Restore",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                    )
                }

                Spacer(modifier = Modifier.height(6.dp))

                Text(
                    text = if (selectedLanguage == Language.BENGALI) "ইন্টারনেট ছাড়া সম্পূর্ণ অফলাইনে আপনার সমস্ত ইতিহাস, ওজন, ফেভারিট ও রুটিন এক্সপোর্ট বা রিস্টোর করুন।"
                    else "Export or restore all your history, weights, and custom routines 100% offline via JSON.",
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )

                Spacer(modifier = Modifier.height(14.dp))

                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    HomeFitButton(
                        text = if (selectedLanguage == Language.BENGALI) "এক্সপোর্ট JSON" else "Export JSON",
                        onClick = {
                            coroutineScope.launch {
                                exportedJsonContent = onExportBackup()
                                showExportDialog = true
                            }
                        },
                        modifier = Modifier.weight(1f)
                    )

                    HomeFitOutlinedButton(
                        text = if (selectedLanguage == Language.BENGALI) "রিস্টোর JSON" else "Restore JSON",
                        onClick = { showImportDialog = true },
                        modifier = Modifier.weight(1f)
                    )
                }
            }
        }

        Spacer(modifier = Modifier.height(30.dp))
    }
}

private data class TrophyBadgeItem(
    val emoji: String,
    val titleBn: String,
    val titleEn: String,
    val descBn: String,
    val descEn: String,
    val isUnlocked: Boolean
)

@Composable
fun AchievementTrophyCabinetCard(
    totalWorkouts: Int,
    totalCalories: Int,
    streakDays: Int,
    todayWaterGlasses: Int,
    totalChallengeDays: Int,
    customWorkoutsCount: Int,
    todayNutritionCount: Int,
    selectedLanguage: Language
) {
    val isBn = selectedLanguage == Language.BENGALI

    val badges = listOf(
        TrophyBadgeItem(
            emoji = "🥇",
            titleBn = "প্রথম পদক্ষেপ",
            titleEn = "First Step",
            descBn = "১ম ওয়ার্কআউট সম্পন্ন",
            descEn = "Complete 1st workout",
            isUnlocked = totalWorkouts >= 1
        ),
        TrophyBadgeItem(
            emoji = "🔥",
            titleBn = "স্ট্রিক যোদ্ধা",
            titleEn = "Streak Warrior",
            descBn = "৩+ দিনের ধারাবাহিকতা",
            descEn = "3+ Day Active Streak",
            isUnlocked = streakDays >= 3
        ),
        TrophyBadgeItem(
            emoji = "⚡",
            titleBn = "ক্যালরি ক্রাশার",
            titleEn = "Calorie Crusher",
            descBn = "৫০০+ ক্যালরি বার্ন",
            descEn = "Burn 500+ total kcal",
            isUnlocked = totalCalories >= 500
        ),
        TrophyBadgeItem(
            emoji = "💧",
            titleBn = "হাইড্রেশন হিরো",
            titleEn = "Hydration Hero",
            descBn = "দিনে ৮ গ্লাস পানি",
            descEn = "8 glasses water/day",
            isUnlocked = todayWaterGlasses >= 8
        ),
        TrophyBadgeItem(
            emoji = "🏆",
            titleBn = "চ্যালেঞ্জ চ্যাম্পিয়ন",
            titleEn = "Challenge Star",
            descBn = "৩০-দিন চ্যালেঞ্জে অংশগ্রহণ",
            descEn = "Log 30-Day Challenge",
            isUnlocked = totalChallengeDays >= 1
        ),
        TrophyBadgeItem(
            emoji = "🛠️",
            titleBn = "কাস্টম কোচ",
            titleEn = "Custom Architect",
            descBn = "নিজস্ব রুটিন তৈরি",
            descEn = "Create custom routine",
            isUnlocked = customWorkoutsCount >= 1
        ),
        TrophyBadgeItem(
            emoji = "🥗",
            titleBn = "পুষ্টি সচেতন",
            titleEn = "Nutrition Pro",
            descBn = "দৈনিক খাবার ও প্রোটিন লগ",
            descEn = "Log daily meal macros",
            isUnlocked = todayNutritionCount >= 1
        ),
        TrophyBadgeItem(
            emoji = "👑",
            titleBn = "হোমফিট লিজেন্ড",
            titleEn = "HomeFit Legend",
            descBn = "১০+ ওয়ার্কআউট সম্পন্ন",
            descEn = "Complete 10+ workouts",
            isUnlocked = totalWorkouts >= 10
        )
    )

    val unlockedCount = badges.count { it.isUnlocked }

    HomeFitCard(borderColor = MaterialTheme.colorScheme.secondary) {
        Column {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column(modifier = Modifier.weight(1f)) {
                    Text(
                        text = if (isBn) "🏆 অ্যাচিভমেন্ট ব্যাজ ও ট্রফি কেবিনেট" else "🏆 Achievement Trophy Cabinet",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                    Text(
                        text = if (isBn) "অফলাইনে শরীরচর্চা চালিয়ে ব্যাজগুলো আনলক করুন"
                        else "Unlock offline milestones through consistent training",
                        style = MaterialTheme.typography.bodySmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }

                Surface(
                    shape = RoundedCornerShape(10.dp),
                    color = MaterialTheme.colorScheme.secondary.copy(alpha = 0.18f)
                ) {
                    Text(
                        text = "$unlockedCount / ${badges.size}",
                        style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.Black),
                        color = MaterialTheme.colorScheme.secondary,
                        modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                    )
                }
            }

            Spacer(modifier = Modifier.height(12.dp))

            // 2 rows x 4 columns grid of badges
            Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                badges.chunked(2).forEach { pair ->
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.spacedBy(8.dp)
                    ) {
                        pair.forEach { badge ->
                            Surface(
                                shape = RoundedCornerShape(12.dp),
                                color = if (badge.isUnlocked) {
                                    MaterialTheme.colorScheme.primaryContainer.copy(alpha = 0.65f)
                                } else {
                                    MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.35f)
                                },
                                border = BorderStroke(
                                    width = 1.dp,
                                    color = if (badge.isUnlocked) MaterialTheme.colorScheme.primary else Color.Transparent
                                ),
                                modifier = Modifier.weight(1f)
                            ) {
                                Row(
                                    modifier = Modifier.padding(10.dp),
                                    verticalAlignment = Alignment.CenterVertically
                                ) {
                                    Box(
                                        modifier = Modifier
                                            .size(36.dp)
                                            .clip(CircleShape)
                                            .background(
                                                if (badge.isUnlocked) MaterialTheme.colorScheme.primary.copy(alpha = 0.22f)
                                                else Color.Gray.copy(alpha = 0.15f)
                                            ),
                                        contentAlignment = Alignment.Center
                                    ) {
                                        Text(
                                            text = if (badge.isUnlocked) badge.emoji else "🔒",
                                            fontSize = 18.sp
                                        )
                                    }
                                    Spacer(modifier = Modifier.width(8.dp))
                                    Column(modifier = Modifier.weight(1f)) {
                                        Text(
                                            text = if (isBn) badge.titleBn else badge.titleEn,
                                            style = MaterialTheme.typography.labelMedium.copy(
                                                fontWeight = FontWeight.Bold,
                                                fontSize = 12.sp
                                            ),
                                            color = if (badge.isUnlocked) MaterialTheme.colorScheme.onSurface else MaterialTheme.colorScheme.onSurfaceVariant
                                        )
                                        Text(
                                            text = if (isBn) badge.descBn else badge.descEn,
                                            style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp),
                                            color = MaterialTheme.colorScheme.onSurfaceVariant,
                                            maxLines = 1
                                        )
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}

```

---

## FILE: `app/src/main/java/com/example/ui/screens/splash/SplashScreen.kt`

```kotlin
package com.example.ui.screens.splash

import androidx.compose.animation.core.Animatable
import androidx.compose.animation.core.FastOutSlowInEasing
import androidx.compose.animation.core.LinearEasing
import androidx.compose.animation.core.RepeatMode
import androidx.compose.animation.core.animateFloat
import androidx.compose.animation.core.infiniteRepeatable
import androidx.compose.animation.core.rememberInfiniteTransition
import androidx.compose.animation.core.tween
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.Canvas
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Bolt
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material3.CircularProgressIndicator
import androidx.compose.material3.Icon
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.getValue
import androidx.compose.runtime.remember
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.alpha
import androidx.compose.ui.draw.clip
import androidx.compose.ui.draw.scale
import androidx.compose.ui.geometry.Offset
import androidx.compose.ui.graphics.Brush
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.StrokeCap
import androidx.compose.ui.graphics.drawscope.Stroke
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import kotlinx.coroutines.delay

@Composable
fun SplashScreen(
    strings: AppStrings,
    onFinished: () -> Unit,
    modifier: Modifier = Modifier
) {
    val scale = remember { Animatable(0.75f) }
    val alpha = remember { Animatable(0f) }

    val infiniteTransition = rememberInfiniteTransition(label = "splashPulse")
    val ringPulse by infiniteTransition.animateFloat(
        initialValue = 0.92f,
        targetValue = 1.12f,
        animationSpec = infiniteRepeatable(
            animation = tween(1600, easing = FastOutSlowInEasing),
            repeatMode = RepeatMode.Reverse
        ),
        label = "ringPulse"
    )
    val sweepAngle by infiniteTransition.animateFloat(
        initialValue = 0f,
        targetValue = 360f,
        animationSpec = infiniteRepeatable(
            animation = tween(4000, easing = LinearEasing),
            repeatMode = RepeatMode.Restart
        ),
        label = "sweepAngle"
    )

    LaunchedEffect(Unit) {
        scale.animateTo(
            targetValue = 1f,
            animationSpec = tween(durationMillis = 700, easing = FastOutSlowInEasing)
        )
    }

    LaunchedEffect(Unit) {
        alpha.animateTo(
            targetValue = 1f,
            animationSpec = tween(durationMillis = 600)
        )
        delay(1200)
        onFinished()
    }

    Box(
        modifier = modifier
            .fillMaxSize()
            .background(
                Brush.verticalGradient(
                    colors = listOf(
                        Color(0xFF04070E),
                        Color(0xFF0B1322),
                        Color(0xFF060911)
                    )
                )
            )
            .testTag("splash_screen"),
        contentAlignment = Alignment.Center
    ) {
        // Atmospheric Dark Luxury Studio Lighting Canvas
        Canvas(modifier = Modifier.fillMaxSize()) {
            val w = size.width
            val h = size.height
            drawCircle(
                brush = Brush.radialGradient(
                    colors = listOf(
                        Color(0xFF10B981).copy(alpha = 0.16f),
                        Color(0xFFF59E0B).copy(alpha = 0.06f),
                        Color.Transparent
                    ),
                    center = Offset(w * 0.5f, h * 0.42f),
                    radius = w * 0.68f * ringPulse
                ),
                radius = w * 0.68f * ringPulse,
                center = Offset(w * 0.5f, h * 0.42f)
            )
        }

        Column(
            horizontalAlignment = Alignment.CenterHorizontally,
            verticalArrangement = Arrangement.Center,
            modifier = Modifier
                .scale(scale.value)
                .alpha(alpha.value)
                .padding(horizontal = 28.dp)
        ) {
            // Luxury Architectural Studio Emblem
            Box(
                modifier = Modifier.size(148.dp),
                contentAlignment = Alignment.Center
            ) {
                Canvas(modifier = Modifier.fillMaxSize()) {
                    val strokePx = 3.dp.toPx()
                    drawCircle(
                        color = Color(0xFF26354D),
                        style = Stroke(width = 1.5.dp.toPx())
                    )
                    drawArc(
                        brush = Brush.sweepGradient(
                            colors = listOf(
                                Color.Transparent,
                                Color(0xFF10B981),
                                Color(0xFFF59E0B),
                                Color.Transparent
                            )
                        ),
                        startAngle = sweepAngle,
                        sweepAngle = 220f,
                        useCenter = false,
                        style = Stroke(width = strokePx, cap = StrokeCap.Round)
                    )
                }

                Box(
                    modifier = Modifier
                        .size(112.dp)
                        .clip(CircleShape)
                        .background(
                            Brush.linearGradient(
                                colors = listOf(
                                    Color(0xFF132238),
                                    Color(0xFF09101D)
                                )
                            )
                        )
                        .border(
                            width = 1.5.dp,
                            brush = Brush.linearGradient(
                                colors = listOf(
                                    Color(0xFF34D399),
                                    Color(0xFFFBBF24)
                                )
                            ),
                            shape = CircleShape
                        ),
                    contentAlignment = Alignment.Center
                ) {
                    Icon(
                        imageVector = Icons.Default.FitnessCenter,
                        contentDescription = strings.appName,
                        tint = Color(0xFF34D399),
                        modifier = Modifier.size(54.dp)
                    )
                }
            }

            Spacer(modifier = Modifier.height(24.dp))

            // Elite Studio Badge
            Surface(
                shape = RoundedCornerShape(50),
                color = Color(0xFF10B981).copy(alpha = 0.14f),
                border = BorderStroke(1.dp, Color(0xFF10B981).copy(alpha = 0.45f))
            ) {
                Row(
                    verticalAlignment = Alignment.CenterVertically,
                    modifier = Modifier.padding(horizontal = 14.dp, vertical = 5.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.Bolt,
                        contentDescription = null,
                        tint = Color(0xFFFBBF24),
                        modifier = Modifier.size(15.dp)
                    )
                    Spacer(modifier = Modifier.width(6.dp))
                    Text(
                        text = "DARK LUXURY GYM • VERSION 5.0",
                        style = MaterialTheme.typography.labelSmall.copy(
                            fontSize = 10.sp,
                            fontWeight = FontWeight.ExtraBold,
                            letterSpacing = 1.4.sp
                        ),
                        color = Color(0xFFFBBF24)
                    )
                }
            }

            Spacer(modifier = Modifier.height(14.dp))

            Text(
                text = strings.appName,
                style = MaterialTheme.typography.displayLarge.copy(
                    fontWeight = FontWeight.Black,
                    fontSize = 42.sp,
                    letterSpacing = 1.5.sp
                ),
                color = Color.White
            )

            Spacer(modifier = Modifier.height(8.dp))

            Text(
                text = strings.splashSubtitle,
                style = MaterialTheme.typography.bodyMedium.copy(
                    fontWeight = FontWeight.Medium,
                    lineHeight = 20.sp
                ),
                color = Color(0xFF94A3B8),
                textAlign = TextAlign.Center
            )

            Spacer(modifier = Modifier.height(40.dp))

            CircularProgressIndicator(
                color = Color(0xFF10B981),
                trackColor = Color(0xFF1E293B),
                strokeWidth = 3.dp,
                modifier = Modifier.size(30.dp)
            )

            Spacer(modifier = Modifier.height(12.dp))

            Text(
                text = strings.splashLoading,
                style = MaterialTheme.typography.labelSmall,
                color = Color(0xFF64748B),
                textAlign = TextAlign.Center
            )
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/workouts/ChallengesAndTabataContent.kt`

```kotlin
package com.example.ui.screens.workouts

import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Check
import androidx.compose.material.icons.filled.EmojiEvents
import androidx.compose.material.icons.filled.LocalFireDepartment
import androidx.compose.material.icons.filled.PlayArrow
import androidx.compose.material.icons.filled.RecordVoiceOver
import androidx.compose.material.icons.filled.Timer
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.FilterChip
import androidx.compose.material3.FilterChipDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.LinearProgressIndicator
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Switch
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableIntStateOf
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.audio.OfflineBeatPreset
import com.example.core.i18n.Language
import com.example.data.local.entity.ChallengeProgressEntity
import com.example.data.seed.ExerciseLibraryData
import com.example.domain.model.Exercise
import com.example.domain.model.ExerciseCategory
import com.example.domain.model.WorkoutPlan
import com.example.ui.components.AthleticChoiceChip
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitCard

data class ChallengeSpec(
    val id: String,
    val titleBn: String,
    val titleEn: String,
    val subtitleBn: String,
    val subtitleEn: String,
    val badgeEmoji: String,
    val category: ExerciseCategory
)

val offlineChallenges = listOf(
    ChallengeSpec(
        id = "full_body_30",
        titleBn = "৩০ দিনের ফুল বডি ট্রান্সফরমেশন",
        titleEn = "30-Day Full Body Transformation",
        subtitleBn = "প্রতিদিন ধাপে ধাপে পুরো শরীরের স্ট্যামিনা ও ফিটনেস বৃদ্ধি",
        subtitleEn = "Progressive daily full-body conditioning & fat burn",
        badgeEmoji = "🔥",
        category = ExerciseCategory.FULL_BODY
    ),
    ChallengeSpec(
        id = "abs_core_30",
        titleBn = "৩০ দিনের অ্যাবস ও কোর চ্যালেঞ্জ",
        titleEn = "30-Day Six-Pack & Core Challenge",
        subtitleBn = "পেটের মেদ কমানো এবং কোর পেশি শক্তিশালী করার বিশেষ রুটিন",
        subtitleEn = "Sculpt abdominal muscles and build rock-solid core stability",
        badgeEmoji = "⚡",
        category = ExerciseCategory.ABS_CORE
    ),
    ChallengeSpec(
        id = "pushup_upper_30",
        titleBn = "৩০ দিনের পুশ-আপ ও চেস্ট মাস্টারি",
        titleEn = "30-Day Push-Up & Upper Body Mastery",
        subtitleBn = "বুক, কাঁধ ও ট্রাইসেপস শক্তিশালী করার ঘরোয়া চ্যালেঞ্জ",
        subtitleEn = "Build chest, shoulder, and arm strength without gym weights",
        badgeEmoji = "💪",
        category = ExerciseCategory.CHEST
    )
)

@Composable
fun ChallengesAndTabataContent(
    challengeProgressList: List<ChallengeProgressEntity>,
    voiceRepCounterEnabled: Boolean,
    selectedLanguage: Language,
    onToggleChallengeDay: (challengeId: String, dayNumber: Int) -> Unit,
    onToggleVoiceRepCounter: () -> Unit,
    onSelectBeatPreset: (OfflineBeatPreset) -> Unit,
    onStartWorkoutPlan: (WorkoutPlan) -> Unit,
    onStartTabataSession: (
        titleBn: String,
        titleEn: String,
        workSeconds: Int,
        restSeconds: Int,
        rounds: Int,
        exercisesPool: List<Exercise>
    ) -> Unit,
    modifier: Modifier = Modifier
) {
    val isBn = selectedLanguage == Language.BENGALI
    val scrollState = rememberScrollState()

    var selectedChallengeId by remember { mutableStateOf(offlineChallenges.first().id) }
    val currentChallenge = offlineChallenges.firstOrNull { it.id == selectedChallengeId } ?: offlineChallenges.first()

    val completedDaysSet = remember(challengeProgressList, selectedChallengeId) {
        val rawCsv = challengeProgressList.firstOrNull { it.challengeId == selectedChallengeId }?.completedDaysCsv.orEmpty()
        rawCsv.split(",")
            .mapNotNull { it.trim().toIntOrNull() }
            .toSet()
    }

    val nextUnfinishedDay = (1..30).firstOrNull { !completedDaysSet.contains(it) } ?: 30
    val progressFraction = (completedDaysSet.size / 30f).coerceIn(0f, 1f)

    // Custom HIIT / Tabata Timer States
    var workSeconds by remember { mutableIntStateOf(30) }
    var restSeconds by remember { mutableIntStateOf(15) }
    var rounds by remember { mutableIntStateOf(6) }
    var tabataFocus by remember { mutableStateOf("hiit_cardio") }
    var selectedBeatForTabata by remember { mutableStateOf(OfflineBeatPreset.HIIT_128) }

    Column(
        modifier = modifier
            .fillMaxSize()
            .padding(horizontal = 16.dp)
            .verticalScroll(scrollState)
            .testTag("challenges_and_tabata_content")
    ) {
        // =====================================================================
        // SECTION 1: 30-DAY OFFLINE CHALLENGE TRACKER
        // =====================================================================
        Row(
            verticalAlignment = Alignment.CenterVertically,
            modifier = Modifier.padding(top = 4.dp)
        ) {
            Icon(
                imageVector = Icons.Default.EmojiEvents,
                contentDescription = null,
                tint = MaterialTheme.colorScheme.secondary,
                modifier = Modifier.size(26.dp)
            )
            Spacer(modifier = Modifier.width(8.dp))
            Column {
                Text(
                    text = if (isBn) "৩০ দিনের অফলাইন চ্যালেঞ্জ বোর্ড" else "30-Day Offline Challenge Board",
                    style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Black),
                    color = MaterialTheme.colorScheme.onBackground
                )
                Text(
                    text = if (isBn) "প্রতিদিনের চ্যালেঞ্জ শেষ করে দিনগুলোতে টিক চিহ্ন দিন ও ট্রফি আনলক করুন"
                    else "Complete daily challenges, mark off days, and unlock trophies",
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        }

        Spacer(modifier = Modifier.height(12.dp))

        // Challenge Selector Chips
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            offlineChallenges.forEach { spec ->
                val isSelected = spec.id == selectedChallengeId
                Surface(
                    onClick = { selectedChallengeId = spec.id },
                    shape = RoundedCornerShape(14.dp),
                    color = if (isSelected) MaterialTheme.colorScheme.primaryContainer else MaterialTheme.colorScheme.surface,
                    border = BorderStroke(
                        width = 1.dp,
                        color = if (isSelected) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.outline.copy(alpha = 0.3f)
                    ),
                    modifier = Modifier.weight(1f)
                ) {
                    Column(
                        modifier = Modifier.padding(horizontal = 8.dp, vertical = 10.dp),
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        Text(spec.badgeEmoji, fontSize = 18.sp)
                        Spacer(modifier = Modifier.height(4.dp))
                        Text(
                            text = if (isBn) spec.titleBn.removePrefix("৩০ দিনের ") else spec.titleEn.removePrefix("30-Day "),
                            style = MaterialTheme.typography.labelSmall.copy(
                                fontWeight = FontWeight.Bold,
                                fontSize = 11.sp
                            ),
                            color = if (isSelected) MaterialTheme.colorScheme.onPrimaryContainer else MaterialTheme.colorScheme.onSurface,
                            textAlign = TextAlign.Center,
                            maxLines = 2
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(14.dp))

        // Interactive 30-Day Board Card
        HomeFitCard(borderColor = MaterialTheme.colorScheme.primary) {
            Column {
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.SpaceBetween,
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Column(modifier = Modifier.weight(1f)) {
                        Text(
                            text = "${currentChallenge.badgeEmoji} ${if (isBn) currentChallenge.titleBn else currentChallenge.titleEn}",
                            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.onSurface
                        )
                        Spacer(modifier = Modifier.height(2.dp))
                        Text(
                            text = if (isBn) currentChallenge.subtitleBn else currentChallenge.subtitleEn,
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }

                    Surface(
                        shape = RoundedCornerShape(10.dp),
                        color = MaterialTheme.colorScheme.primary.copy(alpha = 0.15f)
                    ) {
                        Text(
                            text = "${completedDaysSet.size}/30 ${if (isBn) "দিন" else "Days"}",
                            style = MaterialTheme.typography.labelMedium.copy(fontWeight = FontWeight.Black),
                            color = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.padding(horizontal = 10.dp, vertical = 5.dp)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(10.dp))

                LinearProgressIndicator(
                    progress = { progressFraction },
                    color = MaterialTheme.colorScheme.primary,
                    trackColor = MaterialTheme.colorScheme.surfaceVariant,
                    modifier = Modifier
                        .fillMaxWidth()
                        .height(8.dp)
                        .clip(RoundedCornerShape(50))
                )

                Spacer(modifier = Modifier.height(14.dp))

                // 30-Day Grid (5 rows x 6 columns)
                Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                    for (row in 0 until 5) {
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.spacedBy(8.dp)
                        ) {
                            for (col in 1..6) {
                                val dayNum = row * 6 + col
                                val isDone = completedDaysSet.contains(dayNum)
                                val isCurrentTarget = dayNum == nextUnfinishedDay && !isDone

                                Box(
                                    modifier = Modifier
                                        .weight(1f)
                                        .height(44.dp)
                                        .clip(RoundedCornerShape(10.dp))
                                        .background(
                                            when {
                                                isDone -> MaterialTheme.colorScheme.primary
                                                isCurrentTarget -> MaterialTheme.colorScheme.secondary.copy(alpha = 0.22f)
                                                else -> MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.55f)
                                            }
                                        )
                                        .border(
                                            width = if (isCurrentTarget) 1.5.dp else 0.dp,
                                            color = if (isCurrentTarget) MaterialTheme.colorScheme.secondary else Color.Transparent,
                                            shape = RoundedCornerShape(10.dp)
                                        )
                                        .clickable {
                                            onToggleChallengeDay(currentChallenge.id, dayNum)
                                        }
                                        .testTag("challenge_day_${dayNum}"),
                                    contentAlignment = Alignment.Center
                                ) {
                                    if (isDone) {
                                        Row(verticalAlignment = Alignment.CenterVertically) {
                                            Icon(
                                                imageVector = Icons.Default.Check,
                                                contentDescription = "Completed",
                                                tint = Color.White,
                                                modifier = Modifier.size(14.dp)
                                            )
                                            Spacer(modifier = Modifier.width(2.dp))
                                            Text(
                                                text = "$dayNum",
                                                style = MaterialTheme.typography.labelSmall.copy(
                                                    fontWeight = FontWeight.Black,
                                                    color = Color.White
                                                )
                                            )
                                        }
                                    } else {
                                        Text(
                                            text = if (isBn) "দিন $dayNum" else "D$dayNum",
                                            style = MaterialTheme.typography.labelSmall.copy(
                                                fontWeight = if (isCurrentTarget) FontWeight.Bold else FontWeight.Medium,
                                                fontSize = 11.sp
                                            ),
                                            color = if (isCurrentTarget) MaterialTheme.colorScheme.secondary else MaterialTheme.colorScheme.onSurfaceVariant
                                        )
                                    }
                                }
                            }
                        }
                    }
                }

                Spacer(modifier = Modifier.height(14.dp))

                // Start Next Challenge Day Button
                Button(
                    onClick = {
                        val pool = ExerciseLibraryData.allExercises.filter {
                            currentChallenge.category == ExerciseCategory.FULL_BODY || it.category == currentChallenge.category
                        }.ifEmpty { ExerciseLibraryData.allExercises }

                        // Scale duration slightly as days progress
                        val bonusSeconds = ((nextUnfinishedDay - 1) / 5) * 5
                        val dayExercises = pool.take(6).map { ex ->
                            ex.copy(defaultDurationSeconds = (ex.defaultDurationSeconds + bonusSeconds).coerceAtMost(60))
                        }

                        if (!completedDaysSet.contains(nextUnfinishedDay)) {
                            onToggleChallengeDay(currentChallenge.id, nextUnfinishedDay)
                        }

                        onStartWorkoutPlan(
                            WorkoutPlan(
                                id = "${currentChallenge.id}_day_$nextUnfinishedDay",
                                titleBn = "${currentChallenge.titleBn} • দিন $nextUnfinishedDay",
                                titleEn = "${currentChallenge.titleEn} • Day $nextUnfinishedDay",
                                descriptionBn = currentChallenge.subtitleBn,
                                descriptionEn = currentChallenge.subtitleEn,
                                level = if (nextUnfinishedDay > 20) "advanced" else if (nextUnfinishedDay > 10) "intermediate" else "beginner",
                                durationDays = 30,
                                durationMinutesPerDay = 12 + (nextUnfinishedDay / 3),
                                exercises = dayExercises
                            )
                        )
                    },
                    shape = RoundedCornerShape(14.dp),
                    colors = ButtonDefaults.buttonColors(containerColor = MaterialTheme.colorScheme.primary),
                    modifier = Modifier
                        .fillMaxWidth()
                        .height(50.dp)
                        .testTag("start_challenge_day_btn")
                ) {
                    Icon(Icons.Default.PlayArrow, contentDescription = null)
                    Spacer(modifier = Modifier.width(8.dp))
                    Text(
                        text = if (isBn) "দিন $nextUnfinishedDay-এর চ্যালেঞ্জ ওয়ার্কআউট শুরু করুন ⚡"
                        else "Start Day $nextUnfinishedDay Challenge Workout ⚡",
                        style = MaterialTheme.typography.labelLarge.copy(fontWeight = FontWeight.Bold)
                    )
                }
            }
        }

        Spacer(modifier = Modifier.height(26.dp))

        // =====================================================================
        // SECTION 2: CUSTOM HIIT / TABATA TIMER & VOICE REP COUNTER STUDIO
        // =====================================================================
        Row(verticalAlignment = Alignment.CenterVertically) {
            Icon(
                imageVector = Icons.Default.Timer,
                contentDescription = null,
                tint = MaterialTheme.colorScheme.primary,
                modifier = Modifier.size(26.dp)
            )
            Spacer(modifier = Modifier.width(8.dp))
            Column {
                Text(
                    text = if (isBn) "কাস্টম HIIT / টাবাটা টাইমার ও ভয়েস রেপ কাউন্টার"
                    else "Custom HIIT / Tabata Timer & Voice Rep Counter",
                    style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Black),
                    color = MaterialTheme.colorScheme.onBackground
                )
                Text(
                    text = if (isBn) "নিজের মতো কাজের সময়, বিশ্রাম, রাউন্ড এবং বাংলা ভয়েস কাউন্টিং সেট করুন"
                    else "Configure custom work/rest intervals, rounds, and live voice rep counting",
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        }

        Spacer(modifier = Modifier.height(12.dp))

        HomeFitCard(borderColor = MaterialTheme.colorScheme.secondary) {
            Column {
                // 1. Work Seconds
                Text(
                    text = if (isBn) "🔥 কাজের সময় (Work Interval): $workSeconds সেকেন্ড"
                    else "🔥 Work Interval: $workSeconds sec",
                    style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold)
                )
                Spacer(modifier = Modifier.height(8.dp))
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    listOf(20, 30, 40, 45, 60).forEach { sec ->
                        AthleticChoiceChip(
                            label = "${sec}s",
                            selected = workSeconds == sec,
                            onClick = { workSeconds = sec },
                            modifier = Modifier.weight(1f)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(14.dp))

                // 2. Rest Seconds
                Text(
                    text = if (isBn) "💧 বিশ্রামের সময় (Rest Interval): $restSeconds সেকেন্ড"
                    else "💧 Rest Interval: $restSeconds sec",
                    style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold)
                )
                Spacer(modifier = Modifier.height(8.dp))
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    listOf(10, 15, 20, 30).forEach { sec ->
                        AthleticChoiceChip(
                            label = "${sec}s",
                            selected = restSeconds == sec,
                            onClick = { restSeconds = sec },
                            modifier = Modifier.weight(1f)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(14.dp))

                // 3. Total Rounds
                Text(
                    text = if (isBn) "🔄 মোট রাউন্ড সংখ্যা (Rounds): $rounds রাউন্ড"
                    else "🔄 Total Rounds: $rounds rounds",
                    style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold)
                )
                Spacer(modifier = Modifier.height(8.dp))
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    listOf(4, 6, 8, 10, 12).forEach { r ->
                        AthleticChoiceChip(
                            label = "$r",
                            selected = rounds == r,
                            onClick = { rounds = r },
                            modifier = Modifier.weight(1f)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(14.dp))

                // 4. Target Focus Area (Spacious Full-Width Cards so Bengali/English text never wraps mid-word)
                Text(
                    text = if (isBn) "🎯 টাবাটা ফোকাস এরিয়া:" else "🎯 Tabata Focus Area:",
                    style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold)
                )
                Spacer(modifier = Modifier.height(8.dp))
                Column(
                    modifier = Modifier.fillMaxWidth(),
                    verticalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    val focusOptions = listOf(
                        Triple(
                            "hiit_cardio",
                            if (isBn) "ফ্যাট বার্ন HIIT কার্ডিও" else "Fat Burn HIIT Cardio",
                            if (isBn) "জাম্পিং জ্যাকস, বার্পিস ও হাই নি" else "Jumping jacks, burpees & high knees"
                        ),
                        Triple(
                            "core_abs",
                            if (isBn) "অ্যাবস ও কোর স্কাল্পট" else "Abs & Core Sculpt",
                            if (isBn) "প্ল্যাঙ্ক, মাউন্টেন ক্লাইম্বার ও ক্রাঞ্চেস" else "Planks, mountain climbers & crunches"
                        ),
                        Triple(
                            "strength",
                            if (isBn) "পাওয়ার স্ট্রেংথ ও মাসল" else "Power Strength & Muscle",
                            if (isBn) "পুশ-আপ, স্কোয়াট ও ডাম্বেল কার্ল" else "Push-ups, squats & dumbbell curls"
                        )
                    )
                    focusOptions.forEach { (key, label, sub) ->
                        com.example.ui.components.LuxurySelectionOptionCard(
                            title = label,
                            subtitle = sub,
                            selected = tabataFocus == key,
                            onClick = { tabataFocus = key }
                        )
                    }
                }

                Spacer(modifier = Modifier.height(14.dp))

                // 5. Offline Gym Rhythm Beat Selector for Tabata
                Text(
                    text = if (isBn) "🎵 ব্যাকগ্রাউন্ড অফলাইন জিম বিট:" else "🎵 Background Offline Gym Beat:",
                    style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold)
                )
                Spacer(modifier = Modifier.height(6.dp))
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.spacedBy(6.dp)
                ) {
                    listOf(
                        OfflineBeatPreset.HIIT_128 to "128 BPM",
                        OfflineBeatPreset.POWER_110 to "110 BPM",
                        OfflineBeatPreset.FLOW_85 to "85 BPM",
                        OfflineBeatPreset.NONE to (if (isBn) "বন্ধ" else "Off")
                    ).forEach { (preset, shortLabel) ->
                        FilterChip(
                            selected = selectedBeatForTabata == preset,
                            onClick = { selectedBeatForTabata = preset },
                            label = { Text(shortLabel, fontSize = 11.sp, fontWeight = FontWeight.Bold) },
                            colors = FilterChipDefaults.filterChipColors(
                                selectedContainerColor = MaterialTheme.colorScheme.primaryContainer,
                                selectedLabelColor = MaterialTheme.colorScheme.onPrimaryContainer
                            ),
                            modifier = Modifier.weight(1f)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(12.dp))

                // 6. Voice Rep Counter Switch
                Surface(
                    shape = RoundedCornerShape(12.dp),
                    color = MaterialTheme.colorScheme.surfaceVariant.copy(alpha = 0.45f),
                    modifier = Modifier.fillMaxWidth()
                ) {
                    Row(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(horizontal = 12.dp, vertical = 8.dp),
                        verticalAlignment = Alignment.CenterVertically,
                        horizontalArrangement = Arrangement.SpaceBetween
                    ) {
                        Row(
                            verticalAlignment = Alignment.CenterVertically,
                            modifier = Modifier.weight(1f)
                        ) {
                            Icon(
                                imageVector = Icons.Default.RecordVoiceOver,
                                contentDescription = null,
                                tint = MaterialTheme.colorScheme.primary,
                                modifier = Modifier.size(20.dp)
                            )
                            Spacer(modifier = Modifier.width(10.dp))
                            Column {
                                Text(
                                    text = if (isBn) "ভয়েস রেপ কাউন্টার (১, ২, ৩... গণনা)" else "Voice Rep Counter (1, 2, 3...)",
                                    style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.Bold)
                                )
                                Text(
                                    text = if (isBn) "কোচ প্রতি ৩ সেকেন্ডে বাংলায় রেপ গুনে শোনাবে"
                                    else "Coach counts every rep out loud during exercise",
                                    style = MaterialTheme.typography.labelSmall,
                                    color = MaterialTheme.colorScheme.onSurfaceVariant
                                )
                            }
                        }
                        Switch(
                            checked = voiceRepCounterEnabled,
                            onCheckedChange = { onToggleVoiceRepCounter() }
                        )
                    }
                }

                Spacer(modifier = Modifier.height(16.dp))

                val totalDurationSec = (workSeconds + restSeconds) * rounds
                val totalMin = totalDurationSec / 60
                val remSec = totalDurationSec % 60

                HomeFitButton(
                    text = if (isBn) "⚡ টাবাটা শুরু করুন ($totalMin মিঃ ${remSec} সেঃ)"
                    else "⚡ Start Tabata ($totalMin m ${remSec} s)",
                    onClick = {
                        if (selectedBeatForTabata != OfflineBeatPreset.NONE) {
                            onSelectBeatPreset(selectedBeatForTabata)
                        }
                        val exercisesPool = ExerciseLibraryData.allExercises.filter { ex ->
                            when (tabataFocus) {
                                "core_abs" -> ex.category == ExerciseCategory.ABS_CORE
                                "strength" -> ex.category == ExerciseCategory.CHEST || ex.category == ExerciseCategory.ARMS || ex.category == ExerciseCategory.LEGS
                                else -> ex.category == ExerciseCategory.FULL_BODY || ex.category == ExerciseCategory.LEGS
                            }
                        }
                        onStartTabataSession(
                            "কাস্টম টাবাটা (${workSeconds}s/${restSeconds}s • $rounds রাউন্ড)",
                            "Custom Tabata (${workSeconds}s/${restSeconds}s • $rounds Rounds)",
                            workSeconds,
                            restSeconds,
                            rounds,
                            exercisesPool
                        )
                    },
                    testTag = "start_custom_tabata_btn"
                )
            }
        }

        Spacer(modifier = Modifier.height(36.dp))
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/workouts/WorkoutPreviewScreen.kt`

```kotlin
package com.example.ui.screens.workouts

import androidx.compose.foundation.background
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.itemsIndexed
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.automirrored.filled.ArrowBack
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.LocalFireDepartment
import androidx.compose.material.icons.filled.PlayArrow
import androidx.compose.material.icons.filled.Timer
import androidx.compose.material.icons.filled.Whatshot
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.ExperimentalMaterial3Api
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.material3.TopAppBar
import androidx.compose.material3.TopAppBarDefaults
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.domain.model.Exercise
import com.example.domain.model.WorkoutPlan
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitOutlinedButton
import com.example.ui.components.animation.ExerciseAnimationVisualizer

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun WorkoutPreviewScreen(
    plan: WorkoutPlan,
    selectedLanguage: Language,
    strings: AppStrings,
    onStartWorkout: () -> Unit,
    onExerciseClick: (Exercise) -> Unit,
    onBrowseOtherWorkouts: () -> Unit,
    onBack: () -> Unit,
    modifier: Modifier = Modifier
) {
    val title = if (selectedLanguage == Language.BENGALI) plan.titleBn else plan.titleEn
    val desc = if (selectedLanguage == Language.BENGALI) plan.descriptionBn else plan.descriptionEn
    val estimatedCalories = (plan.durationMinutesPerDay * 9.5f).toInt()

    Scaffold(
        topBar = {
            TopAppBar(
                title = {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "ওয়ার্কআউট প্রিভিউ" else "Workout Overview",
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                    )
                },
                navigationIcon = {
                    IconButton(onClick = onBack) {
                        Icon(imageVector = Icons.AutoMirrored.Filled.ArrowBack, contentDescription = "Back")
                    }
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.background,
                    titleContentColor = MaterialTheme.colorScheme.onBackground
                )
            )
        },
        bottomBar = {
            Surface(
                color = MaterialTheme.colorScheme.surface,
                shadowElevation = 8.dp,
                modifier = Modifier.fillMaxWidth()
            ) {
                Column(modifier = Modifier.padding(16.dp)) {
                    HomeFitButton(
                        text = if (selectedLanguage == Language.BENGALI) "ওয়ার্কআউট শুরু করুন ⚡" else "Start Workout ⚡",
                        onClick = onStartWorkout,
                        leadingIcon = Icons.Default.PlayArrow,
                        testTag = "start_workout_preview_btn"
                    )
                    Spacer(modifier = Modifier.height(8.dp))
                    HomeFitOutlinedButton(
                        text = if (selectedLanguage == Language.BENGALI) "অন্যান্য ওয়ার্কআউট দেখুন" else "Browse Other Workouts",
                        onClick = onBrowseOtherWorkouts,
                        testTag = "browse_other_workouts_btn"
                    )
                }
            }
        },
        containerColor = MaterialTheme.colorScheme.background,
        modifier = modifier.testTag("workout_preview_screen")
    ) { innerPadding ->
        LazyColumn(
            modifier = Modifier
                .fillMaxSize()
                .padding(innerPadding)
                .padding(horizontal = 16.dp),
            verticalArrangement = Arrangement.spacedBy(14.dp)
        ) {
            item {
                // Hero Plan Card
                Card(
                    shape = RoundedCornerShape(20.dp),
                    colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                    modifier = Modifier.fillMaxWidth()
                ) {
                    Column(modifier = Modifier.padding(18.dp)) {
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.SpaceBetween,
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Surface(
                                shape = RoundedCornerShape(8.dp),
                                color = MaterialTheme.colorScheme.primaryContainer
                            ) {
                                Row(
                                    modifier = Modifier.padding(horizontal = 8.dp, vertical = 4.dp),
                                    verticalAlignment = Alignment.CenterVertically
                                ) {
                                    Icon(
                                        imageVector = Icons.Default.Whatshot,
                                        contentDescription = null,
                                        tint = MaterialTheme.colorScheme.primary,
                                        modifier = Modifier.size(15.dp)
                                    )
                                    Spacer(modifier = Modifier.width(4.dp))
                                    Text(
                                        text = plan.level.uppercase(),
                                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                        color = MaterialTheme.colorScheme.onPrimaryContainer
                                    )
                                }
                            }

                            Text(
                                text = "${plan.exercises.size} ${if (selectedLanguage == Language.BENGALI) "টি ব্যায়াম" else "exercises"}",
                                style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.SemiBold),
                                color = MaterialTheme.colorScheme.secondary
                            )
                        }

                        Spacer(modifier = Modifier.height(12.dp))

                        Text(
                            text = title,
                            style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Black),
                            color = MaterialTheme.colorScheme.onSurface
                        )

                        Spacer(modifier = Modifier.height(6.dp))

                        Text(
                            text = desc,
                            style = MaterialTheme.typography.bodyMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )

                        Spacer(modifier = Modifier.height(16.dp))

                        // Duration, Calories metrics
                        Row(horizontalArrangement = Arrangement.spacedBy(18.dp)) {
                            Row(verticalAlignment = Alignment.CenterVertically) {
                                Icon(
                                    imageVector = Icons.Default.Timer,
                                    contentDescription = null,
                                    tint = MaterialTheme.colorScheme.primary,
                                    modifier = Modifier.size(18.dp)
                                )
                                Spacer(modifier = Modifier.width(4.dp))
                                Text(
                                    text = "${plan.durationMinutesPerDay} ${strings.minutesUnit}",
                                    style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.Bold)
                                )
                            }

                            Row(verticalAlignment = Alignment.CenterVertically) {
                                Icon(
                                    imageVector = Icons.Default.LocalFireDepartment,
                                    contentDescription = null,
                                    tint = MaterialTheme.colorScheme.primary,
                                    modifier = Modifier.size(18.dp)
                                )
                                Spacer(modifier = Modifier.width(4.dp))
                                Text(
                                    text = "~$estimatedCalories ${strings.caloriesUnit}",
                                    style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.Bold)
                                )
                            }
                        }
                    }
                }
            }

            item {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "অন্তর্ভুক্ত ব্যায়ামের ক্রম ও অ্যানিমেশন (${plan.exercises.size})"
                    else "Exercise Sequence & Demonstration (${plan.exercises.size})",
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onBackground
                )
            }

            // Exercise items with animated thumbnails
            itemsIndexed(plan.exercises, key = { index, ex -> "${ex.id}_$index" }) { index, exercise ->
                val exName = if (selectedLanguage == Language.BENGALI) exercise.nameBn else exercise.nameEn
                val target = if (selectedLanguage == Language.BENGALI) exercise.targetMusclesBn else exercise.targetMusclesEn

                Card(
                    modifier = Modifier
                        .fillMaxWidth()
                        .clickable { onExerciseClick(exercise) }
                        .testTag("preview_exercise_item_$index"),
                    shape = RoundedCornerShape(16.dp),
                    colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface)
                ) {
                    Row(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(10.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        // Animated Vector Thumbnail
                        ExerciseAnimationVisualizer(
                            exerciseId = exercise.id,
                            size = 72.dp
                        )

                        Spacer(modifier = Modifier.width(14.dp))

                        Column(modifier = Modifier.weight(1f)) {
                            Text(
                                text = "${index + 1}. $exName",
                                style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.onSurface
                            )
                            Spacer(modifier = Modifier.height(2.dp))
                            Text(
                                text = target,
                                style = MaterialTheme.typography.bodySmall.copy(fontSize = 11.sp),
                                color = MaterialTheme.colorScheme.onSurfaceVariant
                            )
                            Spacer(modifier = Modifier.height(6.dp))
                            Surface(
                                shape = RoundedCornerShape(6.dp),
                                color = MaterialTheme.colorScheme.surfaceVariant
                            ) {
                                Text(
                                    text = "⏱️ ${exercise.defaultDurationSeconds}s",
                                    style = MaterialTheme.typography.labelSmall.copy(
                                        fontSize = 10.sp,
                                        fontWeight = FontWeight.Bold,
                                        color = MaterialTheme.colorScheme.primary
                                    ),
                                    modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                                )
                            }
                        }
                    }
                }
            }

            item { Spacer(modifier = Modifier.height(80.dp)) }
        }
    }
}
```

---

## FILE: `app/src/main/java/com/example/ui/screens/workouts/WorkoutsScreen.kt`

```kotlin
package com.example.ui.screens.workouts

import androidx.compose.animation.AnimatedVisibility
import androidx.compose.animation.animateContentSize
import androidx.compose.foundation.BorderStroke
import androidx.compose.foundation.background
import androidx.compose.foundation.clickable
import androidx.compose.foundation.horizontalScroll
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.heightIn
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.LazyRow
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.AutoAwesome
import androidx.compose.material.icons.filled.Bookmark
import androidx.compose.material.icons.filled.Check
import androidx.compose.material.icons.filled.Close
import androidx.compose.material.icons.filled.Delete
import androidx.compose.material.icons.filled.Favorite
import androidx.compose.material.icons.filled.FavoriteBorder
import androidx.compose.material.icons.filled.FitnessCenter
import androidx.compose.material.icons.filled.Info
import androidx.compose.material.icons.filled.PlayArrow
import androidx.compose.material.icons.filled.Search
import androidx.compose.material.icons.filled.Timer
import androidx.compose.material.icons.filled.WarningAmber
import androidx.compose.material.icons.filled.Whatshot
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.FilterChip
import androidx.compose.material3.FilterChipDefaults
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.OutlinedTextFieldDefaults
import androidx.compose.material3.ScrollableTabRow
import androidx.compose.material3.Surface
import androidx.compose.material3.Tab
import androidx.compose.material3.TabRowDefaults
import androidx.compose.material3.TabRowDefaults.tabIndicatorOffset
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableIntStateOf
import androidx.compose.runtime.mutableStateListOf
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.core.i18n.AppStrings
import com.example.core.i18n.Language
import com.example.data.local.entity.CustomWorkoutEntity
import com.example.data.seed.ExerciseLibraryData
import com.example.domain.model.Exercise
import com.example.domain.model.ExerciseCategory
import com.example.domain.model.WorkoutPlan
import com.example.domain.recommendation.SmartPlanGenerator
import com.example.ui.components.AthleticChoiceChip
import com.example.ui.components.HomeFitButton
import com.example.ui.components.HomeFitCard
import com.example.ui.components.HomeFitOutlinedButton

import com.example.core.audio.OfflineBeatPreset
import com.example.core.audio.WorkoutMusicState
import com.example.data.local.entity.ChallengeProgressEntity
import com.example.data.local.entity.SavedMusicTrackEntity
import com.example.ui.screens.player.WorkoutMusicDialog
import com.example.ui.screens.player.WorkoutMusicMiniBar

enum class WorkoutsSubTab(val titleBn: String, val titleEn: String) {
    EXERCISES("ব্যায়াম লাইব্রেরি", "Exercise Library"),
    CHALLENGES_TABATA("৩০-দিন ও টাবাটা", "30-Day & Tabata"),
    READY_PLANS("রেডি প্ল্যান", "Ready Plans"),
    CUSTOM_FAVORITES("কাস্টম ও ফেভারিট", "Custom & Favorites"),
    SMART_GENERATOR("স্মার্ট জেনারেটর", "Smart Generator")
}

@Composable
fun WorkoutsScreen(
    favoriteExerciseIds: List<String>,
    customWorkouts: List<CustomWorkoutEntity>,
    selectedLanguage: Language,
    strings: AppStrings,
    onToggleFavorite: (String) -> Unit,
    onSaveCustomWorkout: (String, List<String>, Int, Int) -> Unit,
    onDeleteCustomWorkout: (Long) -> Unit,
    onStartWorkoutPlan: (WorkoutPlan) -> Unit,
    challengeProgressList: List<ChallengeProgressEntity> = emptyList(),
    voiceRepCounterEnabled: Boolean = true,
    musicState: WorkoutMusicState = WorkoutMusicState(),
    savedMusicTracks: List<SavedMusicTrackEntity> = emptyList(),
    onToggleChallengeDay: (String, Int) -> Unit = { _, _ -> },
    onToggleVoiceRepCounter: () -> Unit = {},
    onStartTabataSession: (String, String, Int, Int, Int, List<Exercise>) -> Unit = { _, _, _, _, _, _ -> },
    onToggleMusicPlayPause: () -> Unit = {},
    onNextMusicTrack: () -> Unit = {},
    onAddMusicTrack: (String, String) -> Unit = { _, _ -> },
    onDeleteMusicTrack: (Long) -> Unit = {},
    onPlayMusicTrack: (SavedMusicTrackEntity) -> Unit = {},
    onSelectBeatPreset: (OfflineBeatPreset) -> Unit = {},
    onMusicVolumeChange: (Float) -> Unit = {},
    isProSubscribed: Boolean = false,
    onOpenProDialog: () -> Unit = {},
    modifier: Modifier = Modifier
) {
    var selectedSubTab by remember { mutableStateOf(WorkoutsSubTab.EXERCISES) }
    var searchQuery by remember { mutableStateOf("") }
    var selectedCategory by remember { mutableStateOf(ExerciseCategory.ALL) }
    var selectedExerciseForDetail by remember { mutableStateOf<Exercise?>(null) }
    var isCreateCustomDialogOpen by remember { mutableStateOf(false) }
    var isMusicDialogOpen by remember { mutableStateOf(false) }

    if (isMusicDialogOpen) {
        WorkoutMusicDialog(
            musicState = musicState,
            savedTracks = savedMusicTracks,
            selectedLanguage = selectedLanguage,
            onDismiss = { isMusicDialogOpen = false },
            onAddTrack = onAddMusicTrack,
            onDeleteTrack = onDeleteMusicTrack,
            onPlayTrack = onPlayMusicTrack,
            onSelectBeatPreset = onSelectBeatPreset,
            onVolumeChange = onMusicVolumeChange
        )
    }

    // Exercise Detail Dialog
    if (selectedExerciseForDetail != null) {
        val ex = selectedExerciseForDetail!!
        ExerciseDetailDialog(
            exercise = ex,
            isFavorite = favoriteExerciseIds.contains(ex.id),
            selectedLanguage = selectedLanguage,
            strings = strings,
            onToggleFavorite = { onToggleFavorite(ex.id) },
            onStartExercise = { targetEx ->
                selectedExerciseForDetail = null
                if (targetEx.difficulty == "advanced" && !isProSubscribed) {
                    onOpenProDialog()
                } else {
                    onStartWorkoutPlan(
                        WorkoutPlan(
                            id = "single_${targetEx.id}",
                            titleBn = targetEx.nameBn,
                            titleEn = targetEx.nameEn,
                            descriptionBn = "সিঙ্গেল এক্সারসাইজ সেশন",
                            descriptionEn = "Single Exercise Session",
                            level = targetEx.difficulty,
                            durationDays = 1,
                            durationMinutesPerDay = 1,
                            exercises = listOf(targetEx)
                        )
                    )
                }
            },
            onDismiss = { selectedExerciseForDetail = null },
            isProSubscribed = isProSubscribed
        )
    }

    // Create Custom Workout Dialog
    if (isCreateCustomDialogOpen) {
        CreateCustomWorkoutDialog(
            allExercises = ExerciseLibraryData.allExercises,
            selectedLanguage = selectedLanguage,
            strings = strings,
            onDismiss = { isCreateCustomDialogOpen = false },
            onSave = { title, selectedIds, dur, rest ->
                onSaveCustomWorkout(title, selectedIds, dur, rest)
                isCreateCustomDialogOpen = false
            }
        )
    }

    Column(
        modifier = modifier
            .fillMaxSize()
            .background(MaterialTheme.colorScheme.background)
            .testTag("workouts_screen")
    ) {
        // Top Search Bar
        Box(modifier = Modifier.padding(horizontal = 16.dp, vertical = 8.dp)) {
            OutlinedTextField(
                value = searchQuery,
                onValueChange = { searchQuery = it },
                placeholder = {
                    Text(
                        if (selectedLanguage == Language.BENGALI) "ব্যায়াম খুঁজুন (যেমন: পুশ-আপ, স্কোয়াট)..."
                        else "Search exercises (e.g. push-up, squat)..."
                    )
                },
                leadingIcon = {
                    Icon(
                        imageVector = Icons.Default.Search,
                        contentDescription = null,
                        tint = MaterialTheme.colorScheme.primary
                    )
                },
                trailingIcon = {
                    if (searchQuery.isNotEmpty()) {
                        IconButton(onClick = { searchQuery = "" }) {
                            Icon(imageVector = Icons.Default.Close, contentDescription = "Clear")
                        }
                    }
                },
                singleLine = true,
                shape = RoundedCornerShape(16.dp),
                colors = OutlinedTextFieldDefaults.colors(
                    focusedContainerColor = MaterialTheme.colorScheme.surface,
                    unfocusedContainerColor = MaterialTheme.colorScheme.surface,
                    focusedBorderColor = MaterialTheme.colorScheme.primary,
                    unfocusedBorderColor = MaterialTheme.colorScheme.outline.copy(alpha = 0.4f)
                ),
                modifier = Modifier
                    .fillMaxWidth()
                    .testTag("exercise_search_field")
            )
        }

        // Offline Workout Music & Smart Ducking Mini Bar
        Box(modifier = Modifier.padding(horizontal = 16.dp, vertical = 4.dp)) {
            WorkoutMusicMiniBar(
                musicState = musicState,
                selectedLanguage = selectedLanguage,
                onTogglePlayPause = onToggleMusicPlayPause,
                onNextTrack = onNextMusicTrack,
                onOpenMusicSheet = { isMusicDialogOpen = true }
            )
        }

        // Sub Tabs Scrollable
        ScrollableTabRow(
            selectedTabIndex = selectedSubTab.ordinal,
            containerColor = MaterialTheme.colorScheme.background,
            contentColor = MaterialTheme.colorScheme.primary,
            edgePadding = 16.dp,
            indicator = { tabPositions ->
                TabRowDefaults.SecondaryIndicator(
                    modifier = Modifier.tabIndicatorOffset(tabPositions[selectedSubTab.ordinal]),
                    color = MaterialTheme.colorScheme.primary
                )
            }
        ) {
            WorkoutsSubTab.entries.forEach { tab ->
                val title = if (selectedLanguage == Language.BENGALI) tab.titleBn else tab.titleEn
                Tab(
                    selected = selectedSubTab == tab,
                    onClick = { selectedSubTab = tab },
                    text = {
                        Text(
                            text = title,
                            style = MaterialTheme.typography.labelLarge.copy(
                                fontWeight = if (selectedSubTab == tab) FontWeight.Bold else FontWeight.Medium
                            )
                        )
                    }
                )
            }
        }

        Spacer(modifier = Modifier.height(10.dp))

        // Content according to selected SubTab
        when (selectedSubTab) {
            WorkoutsSubTab.EXERCISES -> {
                ExercisesLibraryContent(
                    searchQuery = searchQuery,
                    selectedCategory = selectedCategory,
                    favoriteExerciseIds = favoriteExerciseIds,
                    selectedLanguage = selectedLanguage,
                    isProSubscribed = isProSubscribed,
                    onCategoryChange = { selectedCategory = it },
                    onExerciseClick = { selectedExerciseForDetail = it },
                    onToggleFavorite = onToggleFavorite
                )
            }
            WorkoutsSubTab.CHALLENGES_TABATA -> {
                ChallengesAndTabataContent(
                    challengeProgressList = challengeProgressList,
                    voiceRepCounterEnabled = voiceRepCounterEnabled,
                    selectedLanguage = selectedLanguage,
                    onToggleChallengeDay = onToggleChallengeDay,
                    onToggleVoiceRepCounter = onToggleVoiceRepCounter,
                    onSelectBeatPreset = onSelectBeatPreset,
                    onStartWorkoutPlan = onStartWorkoutPlan,
                    onStartTabataSession = onStartTabataSession
                )
            }
            WorkoutsSubTab.READY_PLANS -> {
                ReadyPlansContent(
                    selectedLanguage = selectedLanguage,
                    strings = strings,
                    isProSubscribed = isProSubscribed,
                    onOpenProDialog = onOpenProDialog,
                    onStartPlan = onStartWorkoutPlan
                )
            }
            WorkoutsSubTab.CUSTOM_FAVORITES -> {
                CustomAndFavoritesContent(
                    favoriteExerciseIds = favoriteExerciseIds,
                    customWorkouts = customWorkouts,
                    allExercises = ExerciseLibraryData.allExercises,
                    selectedLanguage = selectedLanguage,
                    strings = strings,
                    onOpenCreateDialog = { isCreateCustomDialogOpen = true },
                    onExerciseClick = { selectedExerciseForDetail = it },
                    onToggleFavorite = onToggleFavorite,
                    onDeleteCustomWorkout = onDeleteCustomWorkout,
                    onStartPlan = onStartWorkoutPlan
                )
            }
            WorkoutsSubTab.SMART_GENERATOR -> {
                SmartPlanGeneratorContent(
                    selectedLanguage = selectedLanguage,
                    strings = strings,
                    onPlanGenerated = onStartWorkoutPlan
                )
            }
        }
    }
}

@Composable
fun ExercisesLibraryContent(
    searchQuery: String,
    selectedCategory: ExerciseCategory,
    favoriteExerciseIds: List<String>,
    selectedLanguage: Language,
    onCategoryChange: (ExerciseCategory) -> Unit,
    onExerciseClick: (Exercise) -> Unit,
    onToggleFavorite: (String) -> Unit,
    isProSubscribed: Boolean = false
) {
    val categories = ExerciseCategory.entries

    // Filter exercises
    val filteredExercises = remember(searchQuery, selectedCategory) {
        ExerciseLibraryData.allExercises.filter { ex ->
            val matchesCategory = selectedCategory == ExerciseCategory.ALL || ex.category == selectedCategory
            val matchesSearch = if (searchQuery.isBlank()) true else {
                ex.nameBn.contains(searchQuery, ignoreCase = true) ||
                        ex.nameEn.contains(searchQuery, ignoreCase = true) ||
                        ex.targetMusclesBn.contains(searchQuery, ignoreCase = true) ||
                        ex.targetMusclesEn.contains(searchQuery, ignoreCase = true)
            }
            matchesCategory && matchesSearch
        }
    }

    Column(modifier = Modifier.fillMaxSize()) {
        // Category Filter Chips
        LazyRow(
            modifier = Modifier
                .fillMaxWidth()
                .padding(horizontal = 16.dp, vertical = 6.dp),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            items(categories) { category ->
                val isSelected = selectedCategory == category
                val label = if (selectedLanguage == Language.BENGALI) category.nameBn else category.nameEn
                FilterChip(
                    selected = isSelected,
                    onClick = { onCategoryChange(category) },
                    label = { Text(text = label, fontWeight = if (isSelected) FontWeight.Bold else FontWeight.Normal) },
                    colors = FilterChipDefaults.filterChipColors(
                        selectedContainerColor = MaterialTheme.colorScheme.primary,
                        selectedLabelColor = Color.White
                    ),
                    shape = RoundedCornerShape(12.dp)
                )
            }
        }

        // Exercise Cards List
        if (filteredExercises.isEmpty()) {
            Box(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(32.dp),
                contentAlignment = Alignment.Center
            ) {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "কোনো ব্যায়াম পাওয়া যায়নি।" else "No exercises found.",
                    style = MaterialTheme.typography.bodyLarge,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        } else {
            LazyColumn(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(horizontal = 16.dp, vertical = 6.dp),
                verticalArrangement = Arrangement.spacedBy(10.dp)
            ) {
                items(filteredExercises, key = { it.id }) { exercise ->
                    ExerciseCardItem(
                        exercise = exercise,
                        isFavorite = favoriteExerciseIds.contains(exercise.id),
                        selectedLanguage = selectedLanguage,
                        isProSubscribed = isProSubscribed,
                        onClick = { onExerciseClick(exercise) },
                        onToggleFavorite = { onToggleFavorite(exercise.id) }
                    )
                }
                item { Spacer(modifier = Modifier.height(24.dp)) }
            }
        }
    }
}

@Composable
fun ExerciseCardItem(
    exercise: Exercise,
    isFavorite: Boolean,
    selectedLanguage: Language,
    onClick: () -> Unit,
    onToggleFavorite: () -> Unit,
    isProSubscribed: Boolean = false
) {
    val name = if (selectedLanguage == Language.BENGALI) exercise.nameBn else exercise.nameEn
    val target = if (selectedLanguage == Language.BENGALI) exercise.targetMusclesBn else exercise.targetMusclesEn

    Card(
        modifier = Modifier
            .fillMaxWidth()
            .clickable { onClick() }
            .testTag("exercise_card_${exercise.id}"),
        shape = RoundedCornerShape(16.dp),
        colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
        border = BorderStroke(1.dp, MaterialTheme.colorScheme.outline.copy(alpha = 0.25f))
    ) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(14.dp),
            verticalAlignment = Alignment.CenterVertically
        ) {
            // Exercise Animated Visualizer Thumbnail
            com.example.ui.components.animation.ExerciseAnimationVisualizer(
                exerciseId = exercise.id,
                size = 68.dp
            )

            Spacer(modifier = Modifier.width(14.dp))

            Column(modifier = Modifier.weight(1f)) {
                Text(
                    text = name,
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                    color = MaterialTheme.colorScheme.onSurface
                )
                Spacer(modifier = Modifier.height(4.dp))
                Text(
                    text = target,
                    style = MaterialTheme.typography.bodyMedium.copy(fontSize = 12.sp),
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
                Spacer(modifier = Modifier.height(6.dp))
                Row(horizontalArrangement = Arrangement.spacedBy(6.dp)) {
                    Surface(
                        shape = RoundedCornerShape(6.dp),
                        color = MaterialTheme.colorScheme.surfaceVariant
                    ) {
                        Text(
                            text = "${exercise.defaultDurationSeconds}s",
                            style = MaterialTheme.typography.labelSmall.copy(fontSize = 10.sp, fontWeight = FontWeight.Bold),
                            modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                        )
                    }
                    if (exercise.equipmentRequired != "none") {
                        Surface(
                            shape = RoundedCornerShape(6.dp),
                            color = MaterialTheme.colorScheme.secondary.copy(alpha = 0.15f)
                        ) {
                            Text(
                                text = "Equip: ${exercise.equipmentRequired}",
                                style = MaterialTheme.typography.labelSmall.copy(
                                    fontSize = 10.sp,
                                    fontWeight = FontWeight.Bold,
                                    color = MaterialTheme.colorScheme.secondary
                                ),
                                modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                            )
                        }
                    }
                    if (exercise.difficulty == "advanced") {
                        Surface(
                            shape = RoundedCornerShape(6.dp),
                            color = if (isProSubscribed) Color(0xFF064E3B) else Color(0xFF3B2806)
                        ) {
                            Text(
                                text = if (isProSubscribed) "PRO UNLOCKED" else "PRO VIP",
                                style = MaterialTheme.typography.labelSmall.copy(
                                    fontSize = 9.5.sp,
                                    fontWeight = FontWeight.Black,
                                    color = if (isProSubscribed) Color(0xFF34D399) else Color(0xFFFBBF24)
                                ),
                                modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                            )
                        }
                    }
                }
            }

            IconButton(
                onClick = onToggleFavorite,
                modifier = Modifier.testTag("fav_btn_${exercise.id}")
            ) {
                Icon(
                    imageVector = if (isFavorite) Icons.Default.Favorite else Icons.Default.FavoriteBorder,
                    contentDescription = "Favorite",
                    tint = if (isFavorite) MaterialTheme.colorScheme.error else MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        }
    }
}

@Composable
fun ReadyPlansContent(
    selectedLanguage: Language,
    strings: AppStrings,
    onStartPlan: (WorkoutPlan) -> Unit,
    isProSubscribed: Boolean = false,
    onOpenProDialog: () -> Unit = {}
) {
    var selectedLevelFilter by remember { mutableStateOf("all") }
    val scrollState = rememberScrollState()

    val filteredPlans = remember(selectedLevelFilter) {
        if (selectedLevelFilter == "all") ExerciseLibraryData.readyPlans
        else ExerciseLibraryData.readyPlans.filter { it.level == selectedLevelFilter }
    }

    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(horizontal = 16.dp)
            .verticalScroll(scrollState)
    ) {
        // Quick Workouts Header
        Text(
            text = if (selectedLanguage == Language.BENGALI) "কুইক ওয়ার্কআউট (৫-১৫ মিনিট)" else "Quick Workouts (5-15 min)",
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(10.dp))

        // Quick Workouts row
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            ExerciseLibraryData.quickWorkouts.forEach { plan ->
                val title = if (selectedLanguage == Language.BENGALI) plan.titleBn else plan.titleEn
                Surface(
                    onClick = { onStartPlan(plan) },
                    shape = RoundedCornerShape(16.dp),
                    color = MaterialTheme.colorScheme.surface,
                    border = BorderStroke(1.dp, MaterialTheme.colorScheme.primary.copy(alpha = 0.4f)),
                    modifier = Modifier.weight(1f)
                ) {
                    Column(
                        modifier = Modifier.padding(12.dp),
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        Icon(
                            imageVector = Icons.Default.Timer,
                            contentDescription = null,
                            tint = MaterialTheme.colorScheme.primary,
                            modifier = Modifier.size(24.dp)
                        )
                        Spacer(modifier = Modifier.height(6.dp))
                        Text(
                            text = title,
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            textAlign = TextAlign.Center,
                            maxLines = 2
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(20.dp))

        // Household Equipment Workouts
        Text(
            text = if (selectedLanguage == Language.BENGALI) "ঘরোয়া সরঞ্জাম ওয়ার্কআউট" else "Household Equipment Routines",
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )
        Spacer(modifier = Modifier.height(10.dp))
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(10.dp)
        ) {
            ExerciseLibraryData.equipmentWorkouts.forEach { plan ->
                val title = if (selectedLanguage == Language.BENGALI) plan.titleBn else plan.titleEn
                Card(
                    modifier = Modifier
                        .weight(1f)
                        .clickable { onStartPlan(plan) },
                    shape = RoundedCornerShape(16.dp),
                    colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surface),
                    border = BorderStroke(1.dp, MaterialTheme.colorScheme.secondary.copy(alpha = 0.4f))
                ) {
                    Column(modifier = Modifier.padding(12.dp)) {
                        Text(
                            text = title,
                            style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.onSurface
                        )
                        Spacer(modifier = Modifier.height(4.dp))
                        Text(
                            text = "${plan.durationMinutesPerDay} min • ${plan.exercises.size} items",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.secondary
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(24.dp))

        // Multi-Day Plans Header & Level Filter
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.SpaceBetween,
            verticalAlignment = Alignment.CenterVertically
        ) {
            Text(
                text = if (selectedLanguage == Language.BENGALI) "৭, ১৪ ও ৩০ দিনের পূর্ণাঙ্গ প্ল্যান" else "7, 14 & 30-Day Complete Plans",
                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                color = MaterialTheme.colorScheme.onBackground
            )
        }

        Spacer(modifier = Modifier.height(10.dp))

        // Level chips
        Row(horizontalArrangement = Arrangement.spacedBy(8.dp)) {
            listOf("all" to "সব", "beginner" to "বিগিনার", "intermediate" to "ইন্টারমিডিয়েট", "advanced" to "অ্যাডভান্সড").forEach { (code, label) ->
                val isSelected = selectedLevelFilter == code
                Surface(
                    onClick = { selectedLevelFilter = code },
                    shape = RoundedCornerShape(10.dp),
                    color = if (isSelected) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.surfaceVariant,
                    modifier = Modifier.heightIn(min = 34.dp)
                ) {
                    Box(modifier = Modifier.padding(horizontal = 10.dp, vertical = 6.dp)) {
                        Text(
                            text = label,
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = if (isSelected) Color.White else MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(14.dp))

        // Ready Plans Cards
        Column(verticalArrangement = Arrangement.spacedBy(12.dp)) {
            filteredPlans.forEach { plan ->
                val title = if (selectedLanguage == Language.BENGALI) plan.titleBn else plan.titleEn
                val desc = if (selectedLanguage == Language.BENGALI) plan.descriptionBn else plan.descriptionEn
                val isProPlan = plan.level == "intermediate" || plan.level == "advanced"
                val isLocked = isProPlan && !isProSubscribed

                HomeFitCard {
                    Column {
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.SpaceBetween,
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Text(
                                text = title,
                                style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                                color = MaterialTheme.colorScheme.onSurface,
                                modifier = Modifier.weight(1f)
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Row(horizontalArrangement = Arrangement.spacedBy(6.dp), verticalAlignment = Alignment.CenterVertically) {
                                if (isProPlan) {
                                    Surface(
                                        shape = RoundedCornerShape(8.dp),
                                        color = if (isProSubscribed) Color(0xFF064E3B) else Color(0xFF3B2806)
                                    ) {
                                        Text(
                                            text = if (isProSubscribed) "PRO UNLOCKED" else "PRO VIP",
                                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Black, fontSize = 9.5.sp),
                                            color = if (isProSubscribed) Color(0xFF34D399) else Color(0xFFFBBF24),
                                            modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                                        )
                                    }
                                }
                                Surface(
                                    shape = RoundedCornerShape(8.dp),
                                    color = MaterialTheme.colorScheme.primaryContainer
                                ) {
                                    Text(
                                        text = "${plan.durationDays} Days",
                                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                                        color = MaterialTheme.colorScheme.onPrimaryContainer,
                                        modifier = Modifier.padding(horizontal = 6.dp, vertical = 2.dp)
                                    )
                                }
                            }
                        }

                        Spacer(modifier = Modifier.height(6.dp))

                        Text(
                            text = desc,
                            style = MaterialTheme.typography.bodyMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )

                        Spacer(modifier = Modifier.height(10.dp))

                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.SpaceBetween,
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Text(
                                text = "${plan.durationMinutesPerDay} মিনিট/দিন • ${plan.exercises.size}টি ব্যায়াম",
                                style = MaterialTheme.typography.bodySmall.copy(fontWeight = FontWeight.SemiBold),
                                color = MaterialTheme.colorScheme.primary
                            )

                            Button(
                                onClick = {
                                    if (isLocked) onOpenProDialog() else onStartPlan(plan)
                                },
                                shape = RoundedCornerShape(12.dp),
                                colors = ButtonDefaults.buttonColors(
                                    containerColor = if (isLocked) Color(0xFFFBBF24) else MaterialTheme.colorScheme.primary,
                                    contentColor = if (isLocked) Color(0xFF090D16) else Color.White
                                )
                            ) {
                                Text(
                                    text = if (isLocked) {
                                        if (selectedLanguage == Language.BENGALI) "প্রো আনলক করুন" else "Unlock Pro"
                                    } else {
                                        if (selectedLanguage == Language.BENGALI) "শুরু করুন" else "Start Plan"
                                    },
                                    style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.ExtraBold)
                                )
                            }
                        }
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(30.dp))
    }
}

@Composable
fun CustomAndFavoritesContent(
    favoriteExerciseIds: List<String>,
    customWorkouts: List<CustomWorkoutEntity>,
    allExercises: List<Exercise>,
    selectedLanguage: Language,
    strings: AppStrings,
    onOpenCreateDialog: () -> Unit,
    onExerciseClick: (Exercise) -> Unit,
    onToggleFavorite: (String) -> Unit,
    onDeleteCustomWorkout: (Long) -> Unit,
    onStartPlan: (WorkoutPlan) -> Unit
) {
    val scrollState = rememberScrollState()
    val favoriteExercises = remember(favoriteExerciseIds) {
        allExercises.filter { favoriteExerciseIds.contains(it.id) }
    }

    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(horizontal = 16.dp)
            .verticalScroll(scrollState)
    ) {
        // Create Custom Routine Button
        HomeFitButton(
            text = if (selectedLanguage == Language.BENGALI) "+ নতুন নিজস্ব রুটিন তৈরি করুন" else "+ Create Custom Routine",
            onClick = onOpenCreateDialog,
            leadingIcon = Icons.Default.Add,
            testTag = "create_custom_routine_btn"
        )

        Spacer(modifier = Modifier.height(24.dp))

        // Custom Workouts Section
        Text(
            text = if (selectedLanguage == Language.BENGALI) "আপনার তৈরি করা রুটিনসমূহ (${customWorkouts.size})" else "Your Custom Routines (${customWorkouts.size})",
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(10.dp))

        if (customWorkouts.isEmpty()) {
            HomeFitCard {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "এখনো কোনো কাস্টম রুটিন তৈরি করা হয়নি। উপরের বাটন চেপে নিজের পছন্দমতো ব্যায়াম দিয়ে রুটিন সাজান।"
                    else "No custom routines created yet. Tap the button above to build your personalized workout.",
                    style = MaterialTheme.typography.bodyMedium,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        } else {
            Column(verticalArrangement = Arrangement.spacedBy(10.dp)) {
                customWorkouts.forEach { custom ->
                    val ids = custom.exerciseIdsCsv.split(",").filter { it.isNotBlank() }
                    val exercisesForCustom = allExercises.filter { ids.contains(it.id) }

                    HomeFitCard {
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            verticalAlignment = Alignment.CenterVertically,
                            horizontalArrangement = Arrangement.SpaceBetween
                        ) {
                            Column(modifier = Modifier.weight(1f)) {
                                Text(
                                    text = custom.title,
                                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                                    color = MaterialTheme.colorScheme.onSurface
                                )
                                Spacer(modifier = Modifier.height(4.dp))
                                Text(
                                    text = "${exercisesForCustom.size}টি ব্যায়াম • প্রতিটিতে ${custom.durationSecondsPerExercise}s • রেস্ট ${custom.restSeconds}s",
                                    style = MaterialTheme.typography.bodySmall,
                                    color = MaterialTheme.colorScheme.primary
                                )
                            }

                            Row(verticalAlignment = Alignment.CenterVertically) {
                                IconButton(onClick = { onDeleteCustomWorkout(custom.id) }) {
                                    Icon(
                                        imageVector = Icons.Default.Delete,
                                        contentDescription = "Delete",
                                        tint = MaterialTheme.colorScheme.error
                                    )
                                }
                                IconButton(
                                    onClick = {
                                        val plan = WorkoutPlan(
                                            id = "custom_${custom.id}",
                                            titleBn = custom.title,
                                            titleEn = custom.title,
                                            descriptionBn = "কাস্টম রুটিন",
                                            descriptionEn = "Custom Routine",
                                            level = "intermediate",
                                            durationDays = 1,
                                            durationMinutesPerDay = (exercisesForCustom.size * (custom.durationSecondsPerExercise + custom.restSeconds)) / 60,
                                            exercises = exercisesForCustom,
                                            isCustom = true
                                        )
                                        onStartPlan(plan)
                                    }
                                ) {
                                    Icon(
                                        imageVector = Icons.Default.PlayArrow,
                                        contentDescription = "Start",
                                        tint = MaterialTheme.colorScheme.primary
                                    )
                                }
                            }
                        }
                    }
                }
            }
        }

        Spacer(modifier = Modifier.height(28.dp))

        // Favorites Section
        Text(
            text = if (selectedLanguage == Language.BENGALI) "ফেভারিট ব্যায়ামসমূহ (${favoriteExercises.size})" else "Favorite Exercises (${favoriteExercises.size})",
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
            color = MaterialTheme.colorScheme.onBackground
        )

        Spacer(modifier = Modifier.height(10.dp))

        if (favoriteExercises.isEmpty()) {
            HomeFitCard {
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "কোনো প্রিয় ব্যায়াম ফেভারিট করা নেই। লাইব্রেরি থেকে হার্ট আইকনে ট্যাপ করে ফেভারিট করুন।"
                    else "No favorite exercises bookmarked yet. Tap the heart icon on any exercise card to save it here.",
                    style = MaterialTheme.typography.bodyMedium,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        } else {
            Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                favoriteExercises.forEach { ex ->
                    ExerciseCardItem(
                        exercise = ex,
                        isFavorite = true,
                        selectedLanguage = selectedLanguage,
                        onClick = { onExerciseClick(ex) },
                        onToggleFavorite = { onToggleFavorite(ex.id) }
                    )
                }
            }
        }

        Spacer(modifier = Modifier.height(30.dp))
    }
}

@Composable
fun SmartPlanGeneratorContent(
    selectedLanguage: Language,
    strings: AppStrings,
    onPlanGenerated: (WorkoutPlan) -> Unit
) {
    var goal by remember { mutableStateOf("fitness") }
    var level by remember { mutableStateOf("beginner") }
    var minutes by remember { mutableIntStateOf(15) }
    var equipment by remember { mutableStateOf("none") }
    var generatedPlan by remember { mutableStateOf<WorkoutPlan?>(null) }

    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(16.dp)
            .verticalScroll(rememberScrollState())
    ) {
        Row(verticalAlignment = Alignment.CenterVertically) {
            Icon(
                imageVector = Icons.Default.AutoAwesome,
                contentDescription = null,
                tint = MaterialTheme.colorScheme.primary
            )
            Spacer(modifier = Modifier.width(8.dp))
            Text(
                text = if (selectedLanguage == Language.BENGALI) "স্মার্ট প্ল্যান জেনারেটর" else "Smart Plan Generator",
                style = MaterialTheme.typography.headlineMedium.copy(fontWeight = FontWeight.Bold),
                color = MaterialTheme.colorScheme.onBackground
            )
        }

        Spacer(modifier = Modifier.height(8.dp))

        Text(
            text = if (selectedLanguage == Language.BENGALI) "আপনার লক্ষ্য ও সময় অনুযায়ী অফলাইন অ্যালগরিদমের মাধ্যমে তৎক্ষণাৎ কাস্টম রুটিন তৈরি করুন।"
            else "Algorithmically synthesize a personalized workout routine tailored to your goals and schedule without internet.",
            style = MaterialTheme.typography.bodyMedium,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )

        Spacer(modifier = Modifier.height(20.dp))

        // Goal Selection
        Text(
            text = strings.goalLabel,
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
        )
        Spacer(modifier = Modifier.height(8.dp))
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            AthleticChoiceChip(
                text = strings.goalWeightLoss,
                selected = goal == "weight_loss",
                onClick = { goal = "weight_loss" },
                modifier = Modifier.weight(1f)
            )
            AthleticChoiceChip(
                text = strings.goalMuscleBuilding,
                selected = goal == "muscle_building",
                onClick = { goal = "muscle_building" },
                modifier = Modifier.weight(1f)
            )
            AthleticChoiceChip(
                text = strings.goalGeneralFitness,
                selected = goal == "fitness",
                onClick = { goal = "fitness" },
                modifier = Modifier.weight(1f)
            )
        }

        Spacer(modifier = Modifier.height(18.dp))

        // Level
        Text(
            text = strings.levelLabel,
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
        )
        Spacer(modifier = Modifier.height(8.dp))
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            AthleticChoiceChip(
                text = strings.levelBeginner,
                selected = level == "beginner",
                onClick = { level = "beginner" },
                modifier = Modifier.weight(1f)
            )
            AthleticChoiceChip(
                text = strings.levelIntermediate,
                selected = level == "intermediate",
                onClick = { level = "intermediate" },
                modifier = Modifier.weight(1f)
            )
            AthleticChoiceChip(
                text = strings.levelAdvanced,
                selected = level == "advanced",
                onClick = { level = "advanced" },
                modifier = Modifier.weight(1f)
            )
        }

        Spacer(modifier = Modifier.height(18.dp))

        // Available Minutes
        Text(
            text = if (selectedLanguage == Language.BENGALI) "দৈনিক সময়: $minutes মিনিট" else "Available Time: $minutes min",
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
        )
        Spacer(modifier = Modifier.height(8.dp))
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            listOf(10, 15, 20, 30).forEach { mins ->
                AthleticChoiceChip(
                    text = "$mins m",
                    selected = minutes == mins,
                    onClick = { minutes = mins },
                    modifier = Modifier.weight(1f)
                )
            }
        }

        Spacer(modifier = Modifier.height(18.dp))

        // Equipment
        Text(
            text = strings.equipmentLabel,
            style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
        )
        Spacer(modifier = Modifier.height(8.dp))
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.spacedBy(8.dp)
        ) {
            AthleticChoiceChip(
                text = strings.equipNone,
                selected = equipment == "none",
                onClick = { equipment = "none" },
                modifier = Modifier.weight(1f)
            )
            AthleticChoiceChip(
                text = strings.equipBasic,
                selected = equipment == "basic",
                onClick = { equipment = "basic" },
                modifier = Modifier.weight(1f)
            )
        }

        Spacer(modifier = Modifier.height(24.dp))

        HomeFitButton(
            text = if (selectedLanguage == Language.BENGALI) "প্ল্যান তৈরি করুন ⚡" else "Generate Plan ⚡",
            onClick = {
                generatedPlan = SmartPlanGenerator.generatePlan(
                    goal = goal,
                    fitnessLevel = level,
                    availableMinutes = minutes,
                    equipment = equipment
                )
            }
        )

        // Show generated plan preview
        if (generatedPlan != null) {
            Spacer(modifier = Modifier.height(24.dp))
            HomeFitCard(borderColor = MaterialTheme.colorScheme.primary) {
                Column {
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) "প্রস্তুতকৃত স্মার্ট প্ল্যান" else "Generated Smart Plan",
                        style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold, color = MaterialTheme.colorScheme.primary)
                    )
                    Spacer(modifier = Modifier.height(4.dp))
                    Text(
                        text = if (selectedLanguage == Language.BENGALI) generatedPlan!!.titleBn else generatedPlan!!.titleEn,
                        style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.onSurface
                    )
                    Spacer(modifier = Modifier.height(6.dp))
                    Text(
                        text = "অন্তর্ভুক্ত ব্যায়াম (${generatedPlan!!.exercises.size}টি):",
                        style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.SemiBold)
                    )
                    Spacer(modifier = Modifier.height(4.dp))
                    generatedPlan!!.exercises.forEachIndexed { i, ex ->
                        val exName = if (selectedLanguage == Language.BENGALI) ex.nameBn else ex.nameEn
                        Text(
                            text = "${i + 1}. $exName (${ex.defaultDurationSeconds}s)",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                    Spacer(modifier = Modifier.height(14.dp))
                    HomeFitButton(
                        text = if (selectedLanguage == Language.BENGALI) "এই ওয়ার্কআউটটি শুরু করুন" else "Start This Workout",
                        onClick = { onPlanGenerated(generatedPlan!!) }
                    )
                }
            }
        }

        Spacer(modifier = Modifier.height(30.dp))
    }
}

@Composable
fun ExerciseDetailDialog(
    exercise: Exercise,
    isFavorite: Boolean,
    selectedLanguage: Language,
    strings: AppStrings,
    onToggleFavorite: () -> Unit,
    onStartExercise: (Exercise) -> Unit,
    onDismiss: () -> Unit,
    isProSubscribed: Boolean = false
) {
    val name = if (selectedLanguage == Language.BENGALI) exercise.nameBn else exercise.nameEn
    val instructions = if (selectedLanguage == Language.BENGALI) exercise.instructionsBn else exercise.instructionsEn
    val formTips = if (selectedLanguage == Language.BENGALI) exercise.formTipsBn else exercise.formTipsEn
    val commonMistakes = if (selectedLanguage == Language.BENGALI) exercise.commonMistakesBn else exercise.commonMistakesEn
    val safetyNotice = if (selectedLanguage == Language.BENGALI) exercise.safetyNoticeBn else exercise.safetyNoticeEn

    AlertDialog(
        onDismissRequest = onDismiss,
        title = {
            Row(
                modifier = Modifier.fillMaxWidth(),
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Text(
                    text = name,
                    style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Bold),
                    modifier = Modifier.weight(1f)
                )
                IconButton(onClick = onToggleFavorite) {
                    Icon(
                        imageVector = if (isFavorite) Icons.Default.Favorite else Icons.Default.FavoriteBorder,
                        contentDescription = "Favorite",
                        tint = if (isFavorite) MaterialTheme.colorScheme.error else MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }
            }
        },
        text = {
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .verticalScroll(rememberScrollState())
            ) {
                // 1. HERO ANIMATED DEMONSTRATION
                Box(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(bottom = 12.dp),
                    contentAlignment = Alignment.Center
                ) {
                    com.example.ui.components.animation.ExerciseAnimationVisualizer(
                        animKey = exercise.id,
                        isPlaying = true,
                        showInteractiveControls = true,
                        isBengali = selectedLanguage == Language.BENGALI,
                        modifier = Modifier
                            .fillMaxWidth()
                            .height(215.dp)
                    )
                }

                // Muscles Target & Timing Row
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.SpaceBetween,
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Text(
                        text = "🎯 ${if (selectedLanguage == Language.BENGALI) exercise.targetMusclesBn else exercise.targetMusclesEn}",
                        style = MaterialTheme.typography.bodyMedium.copy(fontWeight = FontWeight.Bold),
                        color = MaterialTheme.colorScheme.primary,
                        modifier = Modifier.weight(1f)
                    )

                    Surface(
                        shape = RoundedCornerShape(8.dp),
                        color = MaterialTheme.colorScheme.primaryContainer
                    ) {
                        Text(
                            text = "⏱️ ${exercise.defaultDurationSeconds}s",
                            style = MaterialTheme.typography.labelSmall.copy(fontWeight = FontWeight.Bold),
                            color = MaterialTheme.colorScheme.onPrimaryContainer,
                            modifier = Modifier.padding(horizontal = 8.dp, vertical = 3.dp)
                        )
                    }
                }

                Spacer(modifier = Modifier.height(12.dp))

                // Safety Warning if applicable
                if (safetyNotice != null) {
                    Surface(
                        shape = RoundedCornerShape(10.dp),
                        color = MaterialTheme.colorScheme.error.copy(alpha = 0.12f),
                        modifier = Modifier.fillMaxWidth()
                    ) {
                        Row(modifier = Modifier.padding(10.dp)) {
                            Icon(
                                imageVector = Icons.Default.WarningAmber,
                                contentDescription = null,
                                tint = MaterialTheme.colorScheme.error
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Text(
                                text = safetyNotice,
                                style = MaterialTheme.typography.bodySmall.copy(color = MaterialTheme.colorScheme.error, fontWeight = FontWeight.SemiBold)
                            )
                        }
                    }
                    Spacer(modifier = Modifier.height(12.dp))
                }

                // Instructions
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "কীভাবে করবেন:" else "How to perform:",
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold)
                )
                Spacer(modifier = Modifier.height(6.dp))
                instructions.forEachIndexed { index, step ->
                    Text(
                        text = "${index + 1}. $step",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurface,
                        modifier = Modifier.padding(vertical = 2.dp)
                    )
                }

                Spacer(modifier = Modifier.height(14.dp))

                // Form Tips
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "গুরুত্বপূর্ণ টিপস:" else "Form Tips:",
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold, color = MaterialTheme.colorScheme.primary)
                )
                Spacer(modifier = Modifier.height(4.dp))
                formTips.forEach { tip ->
                    Text(
                        text = "• $tip",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurface
                    )
                }

                Spacer(modifier = Modifier.height(14.dp))

                // Common Mistakes
                Text(
                    text = if (selectedLanguage == Language.BENGALI) "যে ভুলগুলো পরিহার করবেন:" else "Common Mistakes:",
                    style = MaterialTheme.typography.titleMedium.copy(fontWeight = FontWeight.Bold, color = MaterialTheme.colorScheme.error)
                )
                Spacer(modifier = Modifier.height(4.dp))
                commonMistakes.forEach { mistake ->
                    Text(
                        text = "⚠️ $mistake",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurface
                    )
                }
            }
        },
        confirmButton = {
            val isProLocked = exercise.difficulty == "advanced" && !isProSubscribed
            Button(
                onClick = { onStartExercise(exercise) },
                shape = RoundedCornerShape(12.dp),
                colors = ButtonDefaults.buttonColors(
                    containerColor = if (isProLocked) Color(0xFFFBBF24) else MaterialTheme.colorScheme.primary,
                    contentColor = if (isProLocked) Color(0xFF090D16) else Color.White
                )
            ) {
                Text(
                    text = if (isProLocked) {
                        if (selectedLanguage == Language.BENGALI) "প্রো কোড দিয়ে আনলক করুন" else "Unlock with Pro Code"
                    } else {
                        if (selectedLanguage == Language.BENGALI) "এই ব্যায়ামটি শুরু করুন" else "Start Exercise"
                    },
                    fontWeight = FontWeight.Bold
                )
            }
        },
        dismissButton = {
            TextButton(onClick = onDismiss) {
                Text(text = if (selectedLanguage == Language.BENGALI) "বন্ধ করুন" else "Close")
            }
        }
    )
}

@Composable
fun CreateCustomWorkoutDialog(
    allExercises: List<Exercise>,
    selectedLanguage: Language,
    strings: AppStrings,
    onDismiss: () -> Unit,
    onSave: (String, List<String>, Int, Int) -> Unit
) {
    var title by remember { mutableStateOf("") }
    val selectedIds = remember { mutableStateListOf<String>() }
    var durationSec by remember { mutableIntStateOf(30) }
    var restSec by remember { mutableIntStateOf(15) }
    var errorMsg by remember { mutableStateOf<String?>(null) }

    AlertDialog(
        onDismissRequest = onDismiss,
        title = {
            Text(
                text = if (selectedLanguage == Language.BENGALI) "নতুন কাস্টম রুটিন তৈরি" else "Create Custom Routine",
                style = MaterialTheme.typography.titleLarge.copy(fontWeight = FontWeight.Bold)
            )
        },
        text = {
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .verticalScroll(rememberScrollState())
            ) {
                OutlinedTextField(
                    value = title,
                    onValueChange = {
                        title = it
                        errorMsg = null
                    },
                    label = { Text(if (selectedLanguage == Language.BENGALI) "রুটিনের নাম লিখুন" else "Routine Title") },
                    singleLine = true,
                    isError = errorMsg != null,
                    supportingText = { if (errorMsg != null) Text(errorMsg!!, color = MaterialTheme.colorScheme.error) },
                    modifier = Modifier.fillMaxWidth()
                )

                Spacer(modifier = Modifier.height(14.dp))

                Text(
                    text = if (selectedLanguage == Language.BENGALI) "ব্যায়াম নির্বাচন করুন (${selectedIds.size}টি নির্বাচিত):" else "Select Exercises (${selectedIds.size} selected):",
                    style = MaterialTheme.typography.titleSmall.copy(fontWeight = FontWeight.Bold)
                )

                Spacer(modifier = Modifier.height(8.dp))

                Column(verticalArrangement = Arrangement.spacedBy(6.dp)) {
                    allExercises.take(15).forEach { ex ->
                        val isChecked = selectedIds.contains(ex.id)
                        val exName = if (selectedLanguage == Language.BENGALI) ex.nameBn else ex.nameEn
                        Surface(
                            onClick = {
                                if (isChecked) selectedIds.remove(ex.id) else selectedIds.add(ex.id)
                            },
                            shape = RoundedCornerShape(10.dp),
                            color = if (isChecked) MaterialTheme.colorScheme.primaryContainer else MaterialTheme.colorScheme.surfaceVariant,
                            modifier = Modifier.fillMaxWidth()
                        ) {
                            Row(
                                modifier = Modifier.padding(10.dp),
                                verticalAlignment = Alignment.CenterVertically
                            ) {
                                Icon(
                                    imageVector = if (isChecked) Icons.Default.Check else Icons.Default.Add,
                                    contentDescription = null,
                                    tint = if (isChecked) MaterialTheme.colorScheme.primary else MaterialTheme.colorScheme.onSurfaceVariant
                                )
                                Spacer(modifier = Modifier.width(8.dp))
                                Text(
                                    text = exName,
                                    style = MaterialTheme.typography.bodyMedium.copy(fontWeight = if (isChecked) FontWeight.Bold else FontWeight.Normal)
                                )
                            }
                        }
                    }
                }
            }
        },
        confirmButton = {
            TextButton(
                onClick = {
                    if (title.isBlank()) {
                        errorMsg = "দয়া করে রুটিনের একটি নাম দিন।"
                    } else if (selectedIds.isEmpty()) {
                        errorMsg = "কমপক্ষে একটি ব্যায়াম নির্বাচন করুন।"
                    } else {
                        onSave(title.trim(), selectedIds.toList(), durationSec, restSec)
                    }
                }
            ) {
                Text(text = strings.saveBtn, fontWeight = FontWeight.Bold)
            }
        },
        dismissButton = {
            TextButton(onClick = onDismiss) {
                Text(text = strings.cancelBtn)
            }
        }
    )
}
```

---

## FILE: `app/src/main/java/com/example/ui/theme/Color.kt`

```kotlin
package com.example.ui.theme

import androidx.compose.ui.graphics.Color

// Ultra-Dark Luxury Studio Palette
val ApexBackground = Color(0xFF080B10)
val ApexSurface = Color(0xFF111622)
val ApexSurfaceElevated = Color(0xFF182030)
val ApexCardBorder = Color(0xFF1E283D)

// Neon Muscle Heatmap & Energy Accents
val ApexCyan = Color(0xFF00F0FF)       // Primary movers / Core
val ApexAmber = Color(0xFFFFB300)      // Secondary stabilization
val ApexMint = Color(0xFF00E676)       // Success / Hydration
val ApexRed = Color(0xFFFF3366)        // Peak intensity
val ApexPurple = Color(0xFFBD00FF)     // Explosive power

// Monochromes & Typography
val ApexTextPrimary = Color(0xFFFFFFFF)
val ApexTextSecondary = Color(0xFF94A3B8)
val ApexTextTertiary = Color(0xFF64748B)

// Glassmorphism overlays
val ApexGlassBg = Color(0xCC111622)
val ApexGlassStroke = Color(0x4000F0FF)
val ApexGlowCyan = Color(0x4000F0FF)
```

---

## FILE: `app/src/main/java/com/example/ui/theme/Theme.kt`

```kotlin
package com.example.ui.theme

import androidx.compose.foundation.isSystemInDarkTheme
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.darkColorScheme
import androidx.compose.material3.lightColorScheme
import androidx.compose.runtime.Composable
import androidx.compose.ui.graphics.Color

private val DarkColorScheme = darkColorScheme(
    primary = Color(0xFF10B981),        // HomeFit Emerald Green
    onPrimary = Color(0xFF021B12),
    primaryContainer = Color(0xFF0F2E22),
    onPrimaryContainer = Color(0xFF6EE7B7),
    secondary = Color(0xFF38BDF8),      // Electric Sky
    onSecondary = Color(0xFF082F49),
    secondaryContainer = Color(0xFF0C4A6E),
    onSecondaryContainer = Color(0xFFBAE6FD),
    tertiary = Color(0xFFFBBF24),       // VIP Gold
    onTertiary = Color(0xFF451A03),
    background = Color(0xFF080C14),     // Dark Luxury Canvas
    onBackground = Color(0xFFF8FAFC),
    surface = Color(0xFF0F172A),        // Dark Slate Surface
    onSurface = Color(0xFFF8FAFC),
    surfaceVariant = Color(0xFF1E293B),
    onSurfaceVariant = Color(0xFF94A3B8),
    outline = Color(0xFF334155),
    outlineVariant = Color(0xFF1E293B)
)

private val LightColorScheme = lightColorScheme(
    primary = Color(0xFF059669),
    onPrimary = Color.White,
    primaryContainer = Color(0xFFD1FAE5),
    onPrimaryContainer = Color(0xFF064E3B),
    secondary = Color(0xFF0284C7),
    onSecondary = Color.White,
    tertiary = Color(0xFFD97706),
    background = Color(0xFFF8FAFC),
    onBackground = Color(0xFF0F172A),
    surface = Color.White,
    onSurface = Color(0xFF0F172A),
    surfaceVariant = Color(0xFFF1F5F9),
    onSurfaceVariant = Color(0xFF475569),
    outline = Color(0xFFCBD5E1),
    outlineVariant = Color(0xFFE2E8F0)
)

@Composable
fun HomeFitTheme(
    darkTheme: Boolean = true,
    content: @Composable () -> Unit
) {
    val colorScheme = if (darkTheme) DarkColorScheme else LightColorScheme
    MaterialTheme(
        colorScheme = colorScheme,
        typography = Typography,
        content = content
    )
}
```

---

## FILE: `app/src/main/java/com/example/ui/theme/Type.kt`

```kotlin
package com.example.ui.theme

import androidx.compose.material3.Typography
import androidx.compose.ui.text.TextStyle
import androidx.compose.ui.text.font.FontFamily
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.sp

val Typography = Typography(
    headlineLarge = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.Bold,
        fontSize = 28.sp,
        lineHeight = 34.sp,
        letterSpacing = (-0.5).sp,
        color = ApexTextPrimary
    ),
    headlineMedium = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.Bold,
        fontSize = 22.sp,
        lineHeight = 28.sp,
        letterSpacing = (-0.3).sp,
        color = ApexTextPrimary
    ),
    headlineSmall = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.SemiBold,
        fontSize = 18.sp,
        lineHeight = 24.sp,
        color = ApexTextPrimary
    ),
    titleLarge = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.SemiBold,
        fontSize = 16.sp,
        lineHeight = 22.sp,
        color = ApexTextPrimary
    ),
    titleMedium = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.Medium,
        fontSize = 14.sp,
        lineHeight = 20.sp,
        color = ApexTextPrimary
    ),
    bodyLarge = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.Normal,
        fontSize = 15.sp,
        lineHeight = 22.sp,
        color = ApexTextSecondary
    ),
    bodyMedium = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.Normal,
        fontSize = 13.sp,
        lineHeight = 18.sp,
        color = ApexTextSecondary
    ),
    labelLarge = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.SemiBold,
        fontSize = 13.sp,
        lineHeight = 18.sp,
        color = ApexTextPrimary
    ),
    labelSmall = TextStyle(
        fontFamily = FontFamily.Default,
        fontWeight = FontWeight.Medium,
        fontSize = 11.sp,
        lineHeight = 14.sp,
        color = ApexTextTertiary
    )
)
```

---

## FILE: `app/src/main/res/drawable/ic_launcher_background.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:aapt="http://schemas.android.com/aapt"
    android:width="108dp"
    android:height="108dp"
    android:viewportWidth="108"
    android:viewportHeight="108">
    <path android:pathData="M0,0h108v108h-108z">
        <aapt:attr name="android:fillColor">
            <gradient
                android:angle="315"
                android:endColor="#001824"
                android:startColor="#080C14"
                android:type="linear" />
        </aapt:attr>
    </path>
</vector>
```

---

## FILE: `app/src/main/res/drawable/ic_launcher_foreground.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="108dp"
    android:height="108dp"
    android:viewportWidth="108"
    android:viewportHeight="108">
    <!-- Apex Hexagon Crest -->
    <path
        android:fillColor="#121D2D"
        android:strokeColor="#00F0FF"
        android:strokeWidth="2.5"
        android:pathData="M54,22 L78,36 L78,66 L54,80 L30,66 L30,36 Z" />
    
    <!-- Neon Apex Chevron / Arrow -->
    <path
        android:fillColor="#00F0FF"
        android:pathData="M54,28 L72,48 L64,48 L54,37 L44,48 L36,48 Z" />

    <!-- Calisthenics Core & Dumbbell / Bar Motif -->
    <path
        android:fillColor="#FFB300"
        android:pathData="M38,55 L70,55 L70,59 L38,59 Z" />

    <path
        android:fillColor="#00F0FF"
        android:pathData="M35,51 L38,51 L38,63 L35,63 Z" />
    <path
        android:fillColor="#00F0FF"
        android:pathData="M70,51 L73,51 L73,63 L70,63 Z" />

    <!-- Athletic Anatomical Core Diamond -->
    <path
        android:fillColor="#00F0FF"
        android:pathData="M54,63 L60,69 L54,75 L48,69 Z" />
</vector>
```

---

## FILE: `app/src/main/res/mipmap-anydpi-v26/ic_launcher.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<adaptive-icon xmlns:android="http://schemas.android.com/apk/res/android">
    <background android:drawable="@drawable/ic_launcher_background" />
    <foreground android:drawable="@drawable/ic_launcher_foreground" />
</adaptive-icon>
```

---

## FILE: `app/src/main/res/mipmap-anydpi-v26/ic_launcher_round.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<adaptive-icon xmlns:android="http://schemas.android.com/apk/res/android">
    <background android:drawable="@drawable/ic_launcher_background" />
    <foreground android:drawable="@drawable/ic_launcher_foreground" />
</adaptive-icon>
```

---

## FILE: `app/src/main/res/values/colors.xml`

```xml
<resources>
    <color name="apex_black">#080B10</color>
    <color name="apex_surface">#121721</color>
    <color name="apex_cyan">#00F0FF</color>
    <color name="apex_amber">#FFB300</color>
    <color name="apex_mint">#00E676</color>
    <color name="apex_white">#FFFFFF</color>
</resources>
```

---

## FILE: `app/src/main/res/values/strings.xml`

```xml
<resources>
    <string name="app_name">HomeFit</string>
    <string name="nav_home">Home</string>
    <string name="nav_workouts">Workouts</string>
    <string name="nav_diet">Diet</string>
    <string name="nav_progress">Progress</string>
    <string name="nav_profile">Profile</string>
</resources>
```

---

## FILE: `app/src/main/res/values/themes.xml`

```xml
<resources>
    <style name="Theme.ApexGym" parent="android:Theme.Material.NoActionBar">
        <item name="android:statusBarColor">@android:color/transparent</item>
        <item name="android:navigationBarColor">@android:color/transparent</item>
        <item name="android:windowBackground">@color/apex_black</item>
    </style>
</resources>
```

---

## FILE: `app/src/main/res/xml/backup_rules.xml`

```xml
<?xml version="1.0" encoding="utf-8"?><!--
   Sample backup rules file; uncomment and customize as necessary.
   See https://developer.android.com/guide/topics/data/autobackup
   for details.
   Note: This file is ignored for devices older than API 31
   See https://developer.android.com/about/versions/12/backup-restore
-->
<full-backup-content>
    <!--
   <include domain="sharedpref" path="."/>
   <exclude domain="sharedpref" path="device.xml"/>
-->
</full-backup-content>
```

---

## FILE: `app/src/main/res/xml/data_extraction_rules.xml`

```xml
<?xml version="1.0" encoding="utf-8"?><!--
   Sample data extraction rules file; uncomment and customize as necessary.
   See https://developer.android.com/about/versions/12/backup-restore#xml-changes
   for details.
-->
<data-extraction-rules>
    <cloud-backup>
        <!-- TODO: Use <include> and <exclude> to control what is backed up.
        <include .../>
        <exclude .../>
        -->
    </cloud-backup>
    <!--
    <device-transfer>
        <include .../>
        <exclude .../>
    </device-transfer>
    -->
</data-extraction-rules>
```

---

## FILE: `app/src/main/res/xml/file_paths.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<paths xmlns:android="http://schemas.android.com/apk/res/android">
    <cache-path
        name="shared_cards"
        path="shared_cards/" />
</paths>
```

---

## FILE: `app/src/test/java/com/example/ExampleRobolectricTest.kt`

```kotlin
package com.example

import android.content.Context
import androidx.test.core.app.ApplicationProvider
import org.junit.Assert.assertEquals
import org.junit.Test
import org.junit.runner.RunWith
import org.robolectric.RobolectricTestRunner
import org.robolectric.annotation.Config

@RunWith(RobolectricTestRunner::class)
@Config(sdk = [36])
class ExampleRobolectricTest {

  @Test
  fun `read string from context`() {
    val context = ApplicationProvider.getApplicationContext<Context>()
    val appName = context.getString(R.string.app_name)
    assertEquals("HomeFit", appName)
  }
}
```

---

## FILE: `app/src/test/java/com/example/ExampleUnitTest.kt`

```kotlin
package com.example

import com.example.core.i18n.Language
import com.example.core.i18n.TranslationManager
import com.example.data.seed.ExerciseLibraryData
import com.example.domain.calculations.HealthCalculations
import com.example.domain.coach.CoachTipType
import com.example.domain.coach.SmartCoachEngine
import com.example.domain.model.ExerciseCategory
import com.example.domain.model.UserProfile
import com.example.domain.recommendation.SmartPlanGenerator
import com.example.domain.recommendation.WorkoutRecommendationEngine
import org.junit.Assert.assertEquals
import org.junit.Assert.assertNotNull
import org.junit.Assert.assertTrue
import org.junit.Test
import org.junit.runner.RunWith
import org.robolectric.RobolectricTestRunner

@RunWith(RobolectricTestRunner::class)
class ExampleUnitTest {

    @Test
    fun testBmiCalculation_accurate() {
        val bmi = HealthCalculations.calculateBMI(68f, 170f)
        assertEquals(23.5f, bmi, 0.1f)
    }

    @Test
    fun testBmiCategories_bengali_and_english() {
        val normalCategoryBn = HealthCalculations.getBMICategory(22.0f, Language.BENGALI)
        val normalCategoryEn = HealthCalculations.getBMICategory(22.0f, Language.ENGLISH)

        assertEquals("আদর্শ ওজন", normalCategoryBn)
        assertEquals("Normal Weight", normalCategoryEn)

        val overweightBn = HealthCalculations.getBMICategory(27.5f, Language.BENGALI)
        assertEquals("অতিরিক্ত ওজন", overweightBn)
    }

    @Test
    fun testEstimatedCaloriesCalculation() {
        val calories = HealthCalculations.calculateEstimatedDailyCalories(
            weightKg = 70f,
            heightCm = 175f,
            age = 25,
            gender = "male",
            goal = "weight_loss",
            workoutDaysPerWeek = 4
        )
        assertTrue("Calories should be between 1600 and 2600", calories in 1600..2600)
    }

    @Test
    fun testWorkoutRecommendation_alternation() {
        val profile = UserProfile(
            name = "Test",
            goal = "fitness",
            fitnessLevel = "beginner"
        )
        val recUpper = WorkoutRecommendationEngine.getTodayRecommendation(
            userProfile = profile,
            lastTrainedCategory = "legs",
            daysStreak = 1
        )
        assertEquals("chest_arms", recUpper.category)
        assertTrue(recUpper.durationMinutes > 0)
        assertTrue(recUpper.rationaleBn.isNotEmpty())

        val recRest = WorkoutRecommendationEngine.getTodayRecommendation(
            userProfile = profile,
            lastTrainedCategory = "full_body",
            daysStreak = 4
        )
        assertEquals("stretching", recRest.category)
    }

    @Test
    fun testSmartCoachEngine_rules() {
        val tipStreak = SmartCoachEngine.evaluateTips(
            streakDays = 3,
            lastWorkoutDaysAgo = 0,
            daysSinceLastWeightLog = 0,
            todayWaterGlasses = 5,
            totalCompletedWorkouts = 10
        )
        assertEquals(CoachTipType.RECOVERY, tipStreak.type)

        val tipInactive = SmartCoachEngine.evaluateTips(
            streakDays = 0,
            lastWorkoutDaysAgo = 2,
            daysSinceLastWeightLog = 0,
            todayWaterGlasses = 5,
            totalCompletedWorkouts = 5
        )
        assertEquals(CoachTipType.ENCOURAGEMENT, tipInactive.type)

        val tipHydration = SmartCoachEngine.evaluateTips(
            streakDays = 1,
            lastWorkoutDaysAgo = 0,
            daysSinceLastWeightLog = 1,
            todayWaterGlasses = 2,
            totalCompletedWorkouts = 2
        )
        assertEquals(CoachTipType.HYDRATION, tipHydration.type)
    }

    @Test
    fun testExerciseLibrary_completeness() {
        val exercises = ExerciseLibraryData.allExercises
        // Must contain at least 25-30 exercises (we have 27+ seeded)
        assertTrue("Exercise count should be >= 25", exercises.size >= 25)

        // Check category representations
        assertTrue(exercises.any { it.category == ExerciseCategory.CHEST })
        assertTrue(exercises.any { it.category == ExerciseCategory.ARMS })
        assertTrue(exercises.any { it.category == ExerciseCategory.ABS_CORE })
        assertTrue(exercises.any { it.category == ExerciseCategory.LEGS })
        assertTrue(exercises.any { it.category == ExerciseCategory.BACK })
        assertTrue(exercises.any { it.category == ExerciseCategory.FULL_BODY })
        assertTrue(exercises.any { it.category == ExerciseCategory.WARMUP_COOLDOWN })

        // Check instructions and tips exist for every single exercise
        for (ex in exercises) {
            assertTrue("Instructions should not be empty for ${ex.id}", ex.instructionsBn.isNotEmpty())
            assertTrue("Form tips should not be empty for ${ex.id}", ex.formTipsBn.isNotEmpty())
            assertTrue("Common mistakes should not be empty for ${ex.id}", ex.commonMistakesBn.isNotEmpty())
        }
    }

    @Test
    fun testSmartPlanGenerator_offlineSynthesis() {
        val plan = SmartPlanGenerator.generatePlan(
            goal = "weight_loss",
            fitnessLevel = "beginner",
            availableMinutes = 15,
            equipment = "none"
        )
        assertNotNull(plan)
        assertTrue("Generated plan must have exercises", plan.exercises.isNotEmpty())
        assertEquals(15, plan.durationMinutesPerDay)
        assertTrue(plan.titleBn.contains("15"))
    }

    @Test
    fun testReadyPlans_structure() {
        val plans = ExerciseLibraryData.readyPlans
        assertTrue(plans.any { it.level == "beginner" && it.durationDays == 7 })
        assertTrue(plans.any { it.level == "beginner" && it.durationDays == 14 })
        assertTrue(plans.any { it.level == "beginner" && it.durationDays == 30 })
        assertTrue(plans.any { it.level == "intermediate" && it.durationDays == 30 })
        assertTrue(plans.any { it.level == "advanced" && it.durationDays == 30 })

        val quicks = ExerciseLibraryData.quickWorkouts
        assertEquals(3, quicks.size) // 5, 10, 15 min
    }

    @Test
    fun testActiveWorkoutSession_timerAndProgress() {
        val plan = ExerciseLibraryData.quickWorkouts.first()
        val session = com.example.domain.model.ActiveWorkoutSession(
            plan = plan,
            currentExerciseIndex = 0,
            phase = com.example.domain.model.WorkoutPhase.EXERCISE,
            remainingSeconds = 15,
            totalSecondsInPhase = 30
        )

        assertEquals(0.5f, session.progressFraction, 0.01f)
        assertNotNull(session.currentExercise)
        assertNotNull(session.nextExercise)

        // At last exercise
        val lastSession = session.copy(currentExerciseIndex = plan.exercises.size - 1)
        org.junit.Assert.assertNull(lastSession.nextExercise)
    }

    @Test
    fun testExerciseAnimationVisualizer_mapping() {
        assertEquals(com.example.ui.components.animation.ExerciseAnimType.SQUAT, com.example.ui.components.animation.getAnimTypeForExercise("bodyweight_squats"))
        assertEquals(com.example.ui.components.animation.ExerciseAnimType.PUSH_UP, com.example.ui.components.animation.getAnimTypeForExercise("push_up"))
        assertEquals(com.example.ui.components.animation.ExerciseAnimType.CHAIR_DIPS, com.example.ui.components.animation.getAnimTypeForExercise("chair_dips"))
        assertEquals(com.example.ui.components.animation.ExerciseAnimType.PLANK, com.example.ui.components.animation.getAnimTypeForExercise("plank_hold"))
        assertEquals(com.example.ui.components.animation.ExerciseAnimType.JUMPING_JACKS, com.example.ui.components.animation.getAnimTypeForExercise("jumping_jacks"))
        assertEquals(com.example.ui.components.animation.ExerciseAnimType.BICEP_CURL, com.example.ui.components.animation.getAnimTypeForExercise("towel_bicep_curl"))
    }

    @Test
    fun testLocalBackupJsonStructure() {
        val root = org.json.JSONObject()
        root.put("version", 1)
        root.put("exportedAtMillis", 1727940000000L)
        val arr = org.json.JSONArray()
        arr.put(org.json.JSONObject().apply {
            put("workoutTitle", "Full Body")
            put("durationSeconds", 600)
            put("caloriesBurned", 120)
        })
        root.put("workouts", arr)

        val jsonStr = root.toString(2)
        assertTrue(jsonStr.contains("version"))
        assertTrue(jsonStr.contains("Full Body"))
        assertTrue(jsonStr.contains("120"))

        val parsed = org.json.JSONObject(jsonStr)
        assertEquals(1, parsed.getInt("version"))
        assertEquals("Full Body", parsed.getJSONArray("workouts").getJSONObject(0).getString("workoutTitle"))
    }

    @Test
    fun testFoodDatabaseAndDietPlans() {
        val foods = com.example.data.seed.FoodDatabaseData.allFoods
        assertTrue("Foods list should have >= 10 items", foods.size >= 10)
        assertTrue(foods.any { it.category == com.example.data.seed.FoodCategory.PROTEIN })
        assertTrue(foods.any { it.category == com.example.data.seed.FoodCategory.CARBS })
        assertTrue(foods.any { it.category == com.example.data.seed.FoodCategory.HEALTHY_FATS })

        val studentPlan = com.example.data.seed.BudgetDietPlans.studentBudgetPlan
        assertTrue(studentPlan.meals.isNotEmpty())
        assertTrue(studentPlan.totalProteinEstimate.isNotEmpty())

        val weight = 70f
        val ml = (weight * 35f).toInt()
        assertEquals(2450, ml)
        val glasses = (ml / 250f).toInt()
        assertEquals(9, glasses)
    }

    @Test
    fun testTranslationsCompleteness() {
        val bn = TranslationManager.get(Language.BENGALI)
        val en = TranslationManager.get(Language.ENGLISH)

        assertTrue(bn.appName.isNotEmpty())
        assertTrue(en.appName.isNotEmpty())
        assertEquals(bn.appName, en.appName)
        assertTrue(bn.todayWorkoutTitle.isNotEmpty())
        assertTrue(en.todayWorkoutTitle.isNotEmpty())
        assertTrue(bn.startWorkoutBtn.isNotEmpty())
        assertTrue(en.startWorkoutBtn.isNotEmpty())
    }

    @Test
    fun testOffline2_MuscleHighlightAndChallengesAndBeats() {
        // 1. Muscle highlight metadata
        val squatLabelBn = com.example.ui.components.animation.getMuscleTargetLabel(
            com.example.ui.components.animation.ExerciseAnimType.SQUAT,
            isBengali = true
        )
        val squatLabelEn = com.example.ui.components.animation.getMuscleTargetLabel(
            com.example.ui.components.animation.ExerciseAnimType.SQUAT,
            isBengali = false
        )
        assertTrue(squatLabelBn.isNotEmpty())
        assertTrue(squatLabelEn.isNotEmpty())

        val pushUpLabelBn = com.example.ui.components.animation.getMuscleTargetLabel(
            com.example.ui.components.animation.ExerciseAnimType.PUSH_UP,
            isBengali = true
        )
        val pushUpLabelEn = com.example.ui.components.animation.getMuscleTargetLabel(
            com.example.ui.components.animation.ExerciseAnimType.PUSH_UP,
            isBengali = false
        )
        assertTrue(pushUpLabelBn.contains("বুক"))
        assertTrue(pushUpLabelEn.contains("Chest"))

        // 2. 30-day offline challenge blueprints
        val challenges = com.example.ui.screens.workouts.offlineChallenges
        assertEquals(3, challenges.size)
        assertTrue(challenges.any { it.id == "full_body_30" })
        assertTrue(challenges.any { it.id == "abs_core_30" })
        assertTrue(challenges.any { it.id == "pushup_upper_30" })

        // 3. Offline rhythm beat presets
        val activePresets = com.example.core.audio.OfflineBeatPreset.values().filter {
            it != com.example.core.audio.OfflineBeatPreset.NONE
        }
        assertEquals(3, activePresets.size)
        assertTrue(activePresets.all { it.bpm >= 80 })
    }
}

```

---

## FILE: `gradle/libs.versions.toml`

```toml
[versions]
agp = "9.1.1"
kotlin = "2.2.10"
coreKtx = "1.18.0"
lifecycleRuntimeKtx = "2.8.7"
activityCompose = "1.10.1"
composeBom = "2024.09.00"
material3 = "1.3.0"
materialIconsExtended = "1.7.0"
room = "2.7.0"
ksp = "2.3.5"

[libraries]
androidx-core-ktx = { group = "androidx.core", name = "core-ktx", version.ref = "coreKtx" }
androidx-lifecycle-runtime-ktx = { group = "androidx.lifecycle", name = "lifecycle-runtime-ktx", version.ref = "lifecycleRuntimeKtx" }
androidx-lifecycle-viewmodel-compose = { group = "androidx.lifecycle", name = "lifecycle-viewmodel-compose", version.ref = "lifecycleRuntimeKtx" }
androidx-activity-compose = { group = "androidx.activity", name = "activity-compose", version.ref = "activityCompose" }
androidx-compose-bom = { group = "androidx.compose", name = "compose-bom", version.ref = "composeBom" }
androidx-ui = { group = "androidx.compose.ui", name = "ui" }
androidx-ui-graphics = { group = "androidx.compose.ui", name = "ui-graphics" }
androidx-ui-tooling = { group = "androidx.compose.ui", name = "ui-tooling" }
androidx-ui-tooling-preview = { group = "androidx.compose.ui", name = "ui-tooling-preview" }
androidx-material3 = { group = "androidx.compose.material3", name = "material3", version.ref = "material3" }
androidx-material-icons-extended = { group = "androidx.compose.material", name = "material-icons-extended", version.ref = "materialIconsExtended" }
androidx-room-runtime = { group = "androidx.room", name = "room-runtime", version.ref = "room" }
androidx-room-ktx = { group = "androidx.room", name = "room-ktx", version.ref = "room" }
androidx-room-compiler = { group = "androidx.room", name = "room-compiler", version.ref = "room" }

[plugins]
android-application = { id = "com.android.application", version.ref = "agp" }
kotlin-compose = { id = "org.jetbrains.kotlin.plugin.compose", version.ref = "kotlin" }
ksp = { id = "com.google.devtools.ksp", version.ref = "ksp" }
```

---

## FILE: `gradle/wrapper/gradle-wrapper.properties`

```properties
distributionBase=GRADLE_USER_HOME
distributionPath=wrapper/dists
distributionUrl=https\://services.gradle.org/distributions/gradle-9.3.1-bin.zip
networkTimeout=10000
validateDistributionUrl=true
zipStoreBase=GRADLE_USER_HOME
zipStorePath=wrapper/dists
```

---

