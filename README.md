# 📝 Blog App - Clean Architecture

A modern personal blog application built with Flutter following Clean Architecture principles. Create, manage, and share blog posts with full offline support and real-time synchronization.

## 📋 Overview

Blog App is a feature-rich blogging platform that enables users to create, read, and manage blog posts with a beautiful UI. The app provides seamless offline functionality, multi-topic categorization, and automated content insights through reading time calculations.

**Repository**: [ThienPhu04/blog-app-clean-architecture-master](https://github.com/ThienPhu04/blog-app-clean-architecture-master)

## ✨ Key Features

- **🔐 User Authentication**: Email sign-up and login with session management via Cubit and Firebase
- **📝 Blog Creation**: Create posts with title, content, cover images, and multiple topic tags
- **☁️ Cloud Backend**: Supabase integration for authentication, database, and cloud storage
- **📱 Offline-First**: Hive local NoSQL storage with automatic synchronization when online
- **🌐 Connectivity Aware**: Real-time network monitoring with offline mode handling
- **🎨 Modern UI/UX**: Gradient buttons, image picker, loading states, and real-time snackbar notifications
- **📊 Smart Utilities**: Automatic date formatting and reading time estimation based on content
- **⚡ Responsive Design**: Smooth animations and adaptive layouts for all screen sizes

## 🏗️ Architecture

The project follows **Clean Architecture** with clear separation of concerns:

```
Presentation Layer (Blocs, Pages, Widgets)
    ↓
Domain Layer (Entities, Repositories, UseCases)
    ↓
Data Layer (DataSources, Models, Repositories)
    ↓
Core Layer (Theme, Utils, Network, Services)
```

### Technology Stack

| Category | Technologies |
|----------|--------------|
| **State Management** | Bloc/Cubit |
| **Dependency Injection** | GetIt |
| **HTTP Client** | Supabase Flutter |
| **Local Database** | Hive |
| **Authentication** | Supabase Auth |
| **Cloud Storage** | Supabase Storage |
| **Image Handling** | Image Picker |
| **Network Monitoring** | Internet Connection Checker Plus |
| **Date/Time** | Intl |
| **Functional Programming** | FPDart |

## 📦 Prerequisites

- Flutter 3.3.0+
- Dart 3.3.0+
- Supabase account with configured project
- iOS: Xcode 14+
- Android: Android Studio with API 21+

## 🚀 Getting Started

### 1. Clone Repository
```bash
git clone https://github.com/ThienPhu04/blog-app-clean-architecture-master.git
cd blog-app-clean-architecture-master
```

### 2. Install Dependencies
```bash
flutter pub get
```

### 3. Configure Supabase
- Create a Supabase project at [supabase.com](https://supabase.com)
- Update Supabase credentials in `lib/core/secrets/app_secrets.dart`
- Configure authentication providers and database rules

### 4. Set Environment Variables
Create `.env` file in project root:
```env
SUPABASE_URL=your_supabase_url
SUPABASE_ANON_KEY=your_anon_key
```

### 5. Build & Run
```bash
# Install dependencies
flutter pub get

# Run the app
flutter run
```

## 📁 Project Structure

```
lib/
├── main.dart                          # App entry point
├── init_dependencies.dart             # Dependency injection setup
├── init_dependencies.main.dart        # Main flavor config
│
├── core/                              # Shared resources
│   ├── common/
│   │   ├── cubits/                    # Global cubits (AppUserCubit)
│   │   ├── entities/                  # Shared entities (User)
│   │   └── widgets/                   # Reusable widgets (Loader)
│   ├── constants/                     # App constants
│   ├── error/                         # Error handling (Failures, Exceptions)
│   ├── network/                       # Network configuration
│   ├── secrets/                       # API keys and secrets
│   ├── theme/                         # Colors, themes, typography
│   └── utils/                         # Utility functions
│
├── features/                          # Feature modules
│   ├── auth/                          # Authentication feature
│   │   ├── data/
│   │   │   ├── datasources/
│   │   │   ├── models/
│   │   │   └── repositories/
│   │   ├── domain/
│   │   │   ├── repository/
│   │   │   └── usecases/
│   │   └── presentation/
│   │       ├── bloc/
│   │       ├── pages/
│   │       └── widgets/
│   │
│   └── blog/                          # Blog feature
│       ├── data/
│       │   ├── datasources/
│       │   ├── models/
│       │   └── repositories/
│       ├── domain/
│       │   ├── entities/
│       │   ├── repositories/
│       │   └── usecases/
│       └── presentation/
│           ├── bloc/
│           ├── pages/
│           └── widgets/
```

## 🔐 Features Breakdown

### Authentication
- Email-based sign-up with validation
- Secure login with session persistence
- Automatic session recovery on app launch
- Logout with session cleanup

### Blog Management
- **Create Posts**: Title, rich content editor, cover image upload
- **Multi-Topic Support**: Tag posts with multiple topics for organization
- **Blog Viewing**: Display blog list with cover images and metadata
- **Post Details**: Full post view with formatted date and calculated reading time
- **Local Storage**: Blog posts cached locally with Hive

### Offline Support
- **Hive Database**: Local NoSQL storage for all blog data
- **Auto-Sync**: Automatic synchronization when internet connection restored
- **Offline Mode**: Full access to cached blog posts without internet

### Smart Features
- **Date Formatting**: Intelligent date display (e.g., "12 Mar, 2025")
- **Reading Time**: Automatic calculation based on word count
- **Image Handling**: Gallery image picker for blog cover images
- **Network Awareness**: Graceful offline scenario handling with user feedback

## 🛠️ Development Commands

```bash
# Run app with hot reload
flutter run

# Format code
dart format lib/

# Analyze code
flutter analyze

# Create a production build
flutter build apk --release
flutter build ipa --release
```

## 📝 State Management

The app uses **Bloc/Cubit** pattern with the following state managers:

| Bloc/Cubit | Responsibility |
|------------|-----------------|
| `AppUserCubit` | Global user state and authentication status |
| `AuthBloc` | Authentication operations (login, signup, recovery) |
| `BlogBloc` | Blog operations (create, fetch, upload) |

## 🌐 API Integration

### Supabase
- **Authentication**: Email/password sign-up and login
- **Database**: Blog posts, user profiles storage
- **Storage**: Blog cover images and media files
- **Real-time**: Subscribe to database changes

## 📱 Platform Support

- ✅ Android (API 21+)
- ✅ iOS (13.0+)

## 📄 License

This project is private. For inquiries, contact the repository owner.

## 👤 Author

**Đoàn Thiên Phú**

- GitHub: [@ThienPhu04](https://github.com/ThienPhu04)
- Blog Project: https://github.com/ThienPhu04/blog-app-clean-architecture-master

## 🤝 Contributing

This is a private project. For contributions or inquiries, please contact the repository owner.

---

**Last Updated**: March 2026
