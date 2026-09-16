# eCard - Project Documentation

## 📱 Project Overview

**eCard** is an Android mobile application built with **Kotlin** and **Jetpack Compose** that provides digital business card management functionality. The project uses modern Android architecture.

- **Repository**: [lvtdel/eCard](https://github.com/lvtdel/eCard)
- **Primary Language**: Kotlin (100%)
- **Created**: April 16, 2023

---

## 🏗️ Project Architecture

### Layered Structure

```
app/src/main/java/com/example/ecard/
├── app/                          # Application layer
│   ├── MainActivity.kt            # Main entry point
│   ├── ECardApp.kt
│   ├── ECardApplication.kt
│   └── theme/                     # Theme configuration
├── presentation/                 # UI Layer (Jetpack Compose)
│   ├── AppViewModelProvider.kt    # ViewModel factory
│   ├── TopAppBar.kt
│   ├── BottomAppBar.kt
│   ├── home/                      # Home screen
│   ├── contact/                   # Contact management
│   ├── edit/                      # Edit card screens
│   ├── scan/                      # QR code scanning
│   ├── setting/                   # Settings screen
│   ├── share/                     # Sharing functionality
│   ├── sign_in/                   # Authentication
│   └── navigation/                # Navigation logic
├── data/                          # Data Layer
│   ├── AppContainer.kt            # Dependency injection
│   ├── DataResource.kt
│   ├── dao/                       # Database Access Objects
│   ├── database/                  # Room database
│   ├── model/                     # Data models
│   └── repository/                # Repository implementations
└── util/                          # Utility classes
```

---

## 🛠️ Technology Stack

### Build & Framework
- **Gradle**: Build system
- **Android SDK**: minSdk 27, targetSdk 33, compileSdk 33
- **Kotlin Version**: 1.8.0

### Core Libraries
| Library | Version | Purpose |
|---------|---------|---------|
| **Jetpack Compose UI** | 1.2.0 | Declarative UI framework |
| **Compose Compiler** | 1.4.0 | Kotlin compiler extension |
| **Material Design 3** | 1.0.1 | UI design system |
| **Lifecycle** | 2.5.1 | Lifecycle-aware components |
| **Navigation Compose** | 2.5.3 | In-app navigation |
| **Room** | 2.5.0 | Local SQLite database |

### Authentication & QR
| Library | Version | Purpose |
|---------|---------|---------|
| **Firebase Auth KTX** | 32.0.0 BOM | Firebase authentication |
| **Google Play Services Auth** | 20.5.0 | Google Sign-In |
| **ZXing Core** | 3.4.1 | QR code encoding/decoding |
| **ZXing Android Embedded** | 4.2.0 | Barcode scanner |
| **Play Services Code Scanner** | 16.0.0 | ML Kit barcode scanning |

### UI & Utilities
| Library | Version | Purpose |
|---------|---------|---------|
| **Coil Compose** | 2.2.2 | Image loading |
| **Accompanist SystemUI** | 0.27.0 | System UI control |
| **Sheets Dialogs** | 1.1.1 | Dialog components |
| **Gson** | 2.10.1 | JSON serialization |

---

## 📦 Key Components

### Application Layer
- **MainActivity**: Entry point, initializes Google Sign-In
- **ECardApp**: Root composable for navigation and state
- **ECardApplication**: Application class with DI container

### Presentation Layer (Jetpack Compose)
- **HomeScreen**: Display business card collection
- **EditScreen**: Create/modify card information
- **ScanScreen**: QR code scanning
- **SettingScreen**: User preferences
- **ShareScreen**: Share functionality
- **SignInScreen**: Google authentication
- **Navigation**: Screen routing and transitions

### Data Layer
- **AppContainer**: Dependency injection interface
- **Repositories**: UserRepository, SocialRepository
- **ECardDatabase**: Room database configuration
- **Models**: Data classes for business cards

---

## 🔐 Core Features

### 1. Digital Business Card Management
- Create and edit business cards
- Local storage via Room database
- Display card collection

### 2. QR Code Integration
- Scan QR codes from other cards
- Generate QR codes from card data
- Multiple libraries for reliability

### 3. Authentication
- Google Sign-In integration
- Firebase Authentication
- One-Tap Sign-In UI

### 4. Card Sharing
- Share digital business cards
- Multiple format support

### 5. UI Features
- Material Design 3 components
- Jetpack Compose interface
- Image loading with Coil
- Calendar picker and dialogs

---

## 📋 Build Configuration

### Android Manifest
```xml
- Minimum SDK: API 27 (Android 8.1)
- Target SDK: API 33 (Android 13)
- Internet permission required
- ML Kit barcode dependencies
- ZXing scanner activity configured
```

### Gradle Setup
- **JVM memory**: 2048m
- **Kotlin code style**: official
- **AndroidX**: enabled
- **ProGuard**: enabled for release
- **R class namespacing**: enabled

---

## 🔄 Data Flow Architecture

```
UI Screen (Jetpack Compose)
    ↓
ViewModel (AppViewModelProvider)
    ↓
Repository (UserRepository, SocialRepository)
    ↓
DAO (Database Access)
    ↓
Room Database → SQLite Storage
```

### Dependency Injection
```
MainActivity
    ↓
ECardApplication
    ↓
AppDataContainer
    ↓
Repositories + DAOs
```

---

*Documentation for eCard - Kotlin Android Business Card App*
