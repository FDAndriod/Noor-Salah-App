# 🌙 Noor Salah - Comprehensive Islamic Companion App

A modern, feature-rich native Android application designed to provide an all-in-one Islamic companion experience[cite: 7]. Built with 100% **Kotlin** and **Jetpack Compose**, adhering to **Clean MVVM Architecture**, modular design principles, and native background audio/location services[cite: 7].

---

## 🌟 Key Features

### 📖 Quran & Audio Playback
- **Complete Holy Quran**: Full text reading with Surah browsing, page bookmarks, personal notes, and customizable daily reading goals[cite: 7].
- **Word-by-Word Analysis**: Integrated word-by-word structural breakdown and Tafsir modules.
- **Media3 ExoPlayer Integration**: High-performance audio streaming with multi-reciter selection, background audio playback via Media Session APIs, and offline audio downloads.

### 🕌 Prayer Times & Qibla Direction
- **Location-Based Timings**: Precise daily prayer schedules using GPS/IP location, supporting global calculation methods[cite: 7].
- **Smart Reminders**: Precise notification alarms using `AlarmManager` and Foreground Services for accurate Athan alerts[cite: 7].
- **Qibla Compass**: Hardware-based real-time 3D Qibla direction locator[cite: 7].

### 🤖 AI Islamic Assistant
- **AI-Powered Guidance**: Integrated conversational AI assistant using **OpenRouter API** to answer contextual Islamic questions[cite: 7].
- **Chat History**: Local persistence of previous conversation threads and queries.

### 📿 Azkar, Tasbih & Daily Duas
- **Supplication Library**: Categorized collection of authentic daily Azkar, Morning/Evening Adhkar, and Duas[cite: 7].
- **Digital Tasbih**: Interactive touch-based counter for Dhikr with haptic feedback.
- **Favorites Management**: Instant bookmarking for quick access to frequently recited Duas and Surahs.

### 🕋 Hajj & Umrah Guides
- **Step-by-Step Workflows**: Interactive tabbed guides detailing rituals and supplications for Hajj and Umrah performance.

### 📅 Hijri Calendar & Islamic Events
- **Islamic Calendar**: Interactive Hijri date synchronization with major Islamic event listings[cite: 7].
- **Ramadhan & Event Countdowns**: Live countdown timers for Ramadhan, Eid, and special Islamic occasions[cite: 7].

### 🌤️ Weather Integration
- **Contextual Planning**: Real-time local weather updates integrated into the dashboard for daily prayer travel planning.

### 💾 Offline & Download Management
- **Media Download Manager**: Robust background audio download queue for full offline Surah listening.

### 💎 Premium Upgrades & Updates
- **In-App Purchases**: Seamless integration with **Google Play Billing Library** for premium features/ad-free upgrades.
- **In-App Updates**: Flexible and immediate App Update API integration.



## 🛠️ Detailed Tech Stack

### 🎨 UI & Presentation Layer
- **Jetpack Compose:** Modern declarative UI toolkit for building responsive, high-performance Android interfaces[cite: 7].
- **Material Design 3:** Built using Material 3 design tokens, components, dynamic color palettes, and typography[cite: 7, 8].
- **Material Icons Extended:** Extended set of vector icons for crisp visual navigation.
- **Accompanist System UI Controller:** Dynamic status bar and navigation bar styling control.
- **Lottie Animations:** Smooth vector animations (`lottie-compose`) for interactive feedback and splash screens[cite: 8, 9].
- **Dots Indicator:** Custom page indicators for viewpagers, onboardings, and tabbed workflows.

---

### 🏗️ Architecture & Dependency Injection
- **MVVM Architecture:** Clean separation of concerns with Model-View-ViewModel pattern for testability and maintainability[cite: 7, 8, 9].
- **Dagger Hilt:** Standardized dependency injection framework simplifying scope management across Activities, ViewModels, and WorkManagers[cite: 7, 8, 9].

---

### 💾 Local Database & Storage
- **Room Database:** Robust ORM providing local offline data persistence, backed by Kotlin Coroutines & `Flow` for reactive data streams[cite: 7, 8, 9].
- **AndroidX Security Crypto:** Encrypted SharedPreferences and file handling for securing sensitive app data and API keys.

---

### 🌐 Networking & REST APIs
- **Retrofit & OkHttp3:** Type-safe HTTP client with custom `HttpLoggingInterceptor` for REST API communication[cite: 7].
- **Gson:** Efficient JSON serialization and deserialization for API responses.

---

### ⚡ Asynchronous Operations & State Management
- **Kotlin Coroutines:** Asynchronous, non-blocking thread management[cite: 7, 8, 9].
- **StateFlow & SharedFlow:** Reactive streams for state management and UI events[cite: 7, 9].

---

### 🎵 Media & Background Services
- **AndroidX Media3 (ExoPlayer):** Modern audio player stack supporting high-performance background audio streaming and notification media sessions[cite: 9].
- **WorkManager (Hilt Integrated):** Guaranteed background task execution and offline sync managed directly via Hilt dependency injection[cite: 7, 9].



# 🗂️ Project Directory Structure

```text
com.example.noorsalahjetpackcompose/
│
├── data/
│   ├── dao/                 # Room Database Data Access Objects (Ayah, Bookmark, Prayer, Surah, etc.)
│   ├── dataclasses/         # UI States, API Response models, and Data classes
│   ├── entities/            # Room Database Entities (Database Tables)
│   ├── remote/              # Retrofit API Services (AlQuran, Aladhan, Prayer, Qibla, Weather, Tafsir)
│   └── repository/          # Repositories abstracting data sources (Prayer, Quran, Dua, OpenRouter, etc.)
│
├── di/                      # Dagger Hilt Modules & Entry Points (DatabaseModule, etc.)
│
├── ui/
│   └── components/
│       ├── aichatcomp/      # AI Chat screen, history drawer, and ViewModel
│       ├── bookmarkcomp/    # Bookmark management screens
│       ├── calendarcomp/    # Hijri Calendar views and top sections
│       ├── duascreencomp/   # Dua lists, tabs, and ViewModels
│       ├── favscreencomp/   # Favorites screen and ViewModel
│       ├── homescreencomp/  # Dashboard widgets, daily dua/verse, prayer sheets, and ViewModels
│       └── hucomp/          # Hajj & Umrah step-by-step screens and tabs
│
├── IslamicCalenderApp.kt    # Custom Application class (Hilt annotated)
└── MainActivity.kt          # Single-Activity entry point hosting Compose navigation


## 📋 System Requirements & Environment

### ⚙️ SDK & JVM Configuration
- **Minimum SDK (`minSdk`):** 24 (Android 7.0 Nougat)
- **Target SDK (`targetSdk`):** 36 (Android 16+)
- **Compile SDK (`compileSdk`):** 36
- **Language / JVM Target:** Kotlin / Java 21 *(with core library desugaring enabled)*

---

### 🛡️ Runtime Permissions
- `ACCESS_FINE_LOCATION` / `ACCESS_COARSE_LOCATION` *(Precise GPS & Network location for prayer times & Qibla direction finder)*
- `INTERNET` / `ACCESS_NETWORK_STATE` *(REST API data fetching, audio streaming, & AI Chat connectivity)*
- `POST_NOTIFICATIONS` *(Athan alerts, daily Azkar, and event reminders)*
- `FOREGROUND_SERVICE` / `WAKE_LOCK` *(Uninterrupted background audio playback via Media3 & scheduled WorkManager tasks)*

---

### 🔑 Environment Setup (`local.properties`)
To run the application locally, ensure the following API keys are configured inside your `local.properties` file:

```properties
OPENROUTER_API_KEY="your_openrouter_api_key_here"
ISLAMIC_API_KEY="your_islamic_services_api_key_here"



## 📱 App Screenshots

<div align="center">

| Home Screen | Quran Reader |
| :---: | :---: |
| ![Home](screenshots/salahhomepageimg1.jpg) | ![Quran](screenshots/salahquranpageimg2.jpg) |
| *Dashboard & Prayer Times* | *Surah Browsing & Reader* |

| AI Assistant | AI Chat Details |
| :---: | :---: |
| ![AI Assistant](screenshots/salahaiassitentimg3.jpg) | ![AI Chat](screenshots/salahassistentimg4.jpg) |
| *AI Chatbot UI* | *Smart Queries & History* |

| All Features & Tools | Islamic Calendar |
| :---: | :---: |
| ![All Img](screenshots/salahallimg5.jpg) | ![Calendar](screenshots/salahislamiccalendering6.jpg) |
| *App Overview* | *Hijri Dates & Events* |

| Holy Quran View | Arabic Font Display |
| :---: | :---: |
| ![Holy Quran](screenshots/salahholyguranimg7.jpg) | ![Arabic Font](screenshots/salaharabicfontimg8.jpg) |
| *Reading View* | *Custom Typography* |

| Juz-wise Quran | App Settings |
| :---: | :---: |
| ![Juz](screenshots/salahjuzwisequranimg9.jpg) | ![Settings](screenshots/salahsettingsimg10.jpg) |
| *Juz Index Navigation* | *Configurations & Preferences* |

</div>

