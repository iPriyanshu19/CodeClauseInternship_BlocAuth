# BlocAuth

BlocAuth is a Flutter application that integrates authentication with multiple providers such as Google, Facebook, GitHub, and Phone using Firebase. The app is built with a clean, modular architecture and includes state management using Provider.

## Features

- Login with Google
- Login with Facebook
- Login with GitHub
- Phone authentication
- Firebase integration for authentication
- Modular and scalable architecture

## Getting Started

### Prerequisites

Before starting, ensure you have the following installed:

- [Flutter](https://flutter.dev/docs/get-started/install) (v3.0.0 or higher)
- [Dart](https://dart.dev/get-dart)
- [Firebase CLI](https://firebase.google.com/docs/cli#install_the_firebase_cli)
- Android Studio / Xcode for running on mobile devices

### Firebase Setup

1. Go to [Firebase Console](https://console.firebase.google.com/) and create a new project.
2. Enable Authentication in Firebase, and set up the following providers:
   - Google
   - Facebook
   - Phone
   - GitHub
3. Download the `google-services.json` (for Android) and `GoogleService-Info.plist` (for iOS) and place them in the respective project directories.

### Clone the Repository

Clone this repository locally:

```bash
git clone https://github.com/iPriyanshu19/CodeClauseInternship_BlocAuth.git
cd blocauth
```

### Install Dependencies

Run the following command to install the necessary dependencies:

```bash
flutter pub get
```

### Configuration

#### Google Sign-In

- Enable Google Sign-In in Firebase.
- Add the SHA-1 key in Firebase settings.
- For iOS, ensure `GoogleService-Info.plist` is correctly configured and the URL types are added in `Info.plist`.

#### Facebook Login

- Create a Facebook app via the [Facebook Developers Portal](https://developers.facebook.com/apps).
- Add Facebook credentials to Firebase.
- For iOS, configure the `Info.plist` and add the required permissions.

#### GitHub Authentication

- Create a GitHub OAuth app from [GitHub Developer Settings](https://github.com/settings/developers).
- Add the client ID and secret to Firebase Authentication under the GitHub provider.

#### Phone Authentication

- Enable Phone authentication in Firebase.
- Make sure to configure the reCAPTCHA settings for web and the necessary permissions in `Info.plist` for iOS.

### Run the Application

To run the application on an Android/iOS device or emulator:

```bash
flutter run
```

## Project Structure

The project uses a simple architecture with a focus on provider-based state management. Below is the basic folder structure:

```plaintext
lib/
│
├── providers/          # State management using Provider
│   ├── sign_in_provider.dart
│   └── internet_provider.dart
│
├── screens/            # UI layer (screens and widgets)
│   ├── login_screen.dart
│   ├── splash_screen.dart
│   ├── phoneauth_screen.dart
│   └── home_screen.dart
│
├── utils/              # Utility functions
├── main.dart           # Application entry point
└── ...
```

## Dependencies

Below are the main dependencies used in this project:

- [firebase_core](https://pub.dev/packages/firebase_core): Firebase core plugin for initialization
- [firebase_auth](https://pub.dev/packages/firebase_auth): Firebase Authentication SDK
- [google_sign_in](https://pub.dev/packages/google_sign_in): Google Sign-In plugin
- [flutter_facebook_auth](https://pub.dev/packages/flutter_facebook_auth): Facebook login SDK
- [github_oauth](https://pub.dev/packages/github_oauth): GitHub OAuth login integration
- [provider](https://pub.dev/packages/provider): State management package
- [shared_preferences](https://pub.dev/packages/shared_preferences): To store key-value pairs locally
- [rounded_loading_button](https://pub.dev/packages/rounded_loading_button): Button with loading animation

To add these dependencies, update the `pubspec.yaml` file:

```yaml
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8
  firebase_core: ^3.5.0
  firebase_auth: ^5.3.0
  google_sign_in: ^6.2.1
  flutter_facebook_auth: ^7.1.1
  github_oauth: ^0.0.2
  provider: ^6.1.2
  shared_preferences: ^2.3.2
  rounded_loading_button: ^2.1.0
  cloud_firestore: ^5.4.2
  connectivity_plus: ^6.0.5
  font_awesome_flutter: ^10.7.0
```

## How It Works

This app uses the **Provider** package for state management and Firebase for authentication. Here's a general overview of the flow:

1. **Login Providers**: Users can log in using Google, Facebook, GitHub, or Phone authentication.
2. **Auth Service**: The `AuthService` handles the interaction with Firebase for login and registration.
3. **Provider State**: `AuthProvider` listens for authentication changes and updates the UI accordingly.
4. **UI**: The app provides a simple interface where users can log in and see their profile after authentication.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for review.