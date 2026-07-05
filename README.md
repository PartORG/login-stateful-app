# login_stateful_app

A simple Flutter app - login page that uses StateFulWidget approach.

[![Dart](https://img.shields.io/badge/language-Dart-blue.svg)] [![Flutter](https://img.shields.io/badge/framework-Flutter-green.svg)] [![License](https://img.shields.io/badge/license-MIT-yellow.svg)] [![GitHub stars](https://img.shields.io/github/stars/PartORG/login-stateful-app?style=social)] [![GitHub forks](https://img.shields.io/github/forks/PartORG/login-stateful-app?style=social)]

## Introduction

Welcome to `login_stateful_app`, a simple Flutter application that demonstrates the use of StateFulWidget for creating a login page. This project is designed to be a starting point for developers looking to understand how to build stateful widgets in Flutter.

The app supports multiple platforms, including Android, iOS, Linux, macOS, web, and Windows. It provides a clean and intuitive user interface for users to log in using their credentials.

## Table of Contents

- [Features](#features)
- [How It Works](#how-it-works)
- [Technology Stack](#technology-stack)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Development](#development)
- [Testing](#testing)
- [Limitations](#limitations)
- [License](#license)

## Features

### Login Page with StateFulWidget

- **What it does**: Provides a user interface for logging in.
- **Why it exists**: To demonstrate the use of stateful widgets in Flutter.
- **Why it is useful**: Simplifies the management of widget state, making it easier to maintain and update.

## How It Works

The app uses Flutter's StateFulWidget to manage the login page. The stateful widget maintains its own state, which includes the user's input and any validation errors.

```dart
class LoginScreen extends StatefulWidget {
  @override
  _LoginScreenState createState() => _LoginScreenState();
}

class _LoginScreenState extends State<LoginScreen> {
  final _formKey = GlobalKey<FormState>();
  String _email = '';
  String _password = '';

  void _submitForm() {
    if (_formKey.currentState!.validate()) {
      // Handle login logic here
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Login')),
      body: Form(
        key: _formKey,
        child: Padding(
          padding: const EdgeInsets.all(16.0),
          child: Column(
            children: <Widget>[
              TextFormField(
                decoration: InputDecoration(labelText: 'Email'),
                validator: (value) {
                  if (value == null || value.isEmpty) {
                    return 'Please enter your email';
                  }
                  return null;
                },
                onSaved: (value) => _email = value!,
              ),
              TextFormField(
                decoration: InputDecoration(labelText: 'Password'),
                obscureText: true,
                validator: (value) {
                  if (value == null || value.isEmpty) {
                    return 'Please enter your password';
                  }
                  return null;
                },
                onSaved: (value) => _password = value!,
              ),
              SizedBox(height: 20),
              ElevatedButton(
                onPressed: _submitForm,
                child: Text('Login'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

## Technology Stack

| Technology | Purpose |
|------------|---------|
| Flutter | The framework used for building the app. |
| Dart | The programming language used for development. |
| StateFulWidget | Manages the state of the login page. |

## Requirements

- Flutter SDK
- Android Studio (for Android development)
- Xcode (for iOS development)

## Installation

To install and run this project, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/PartORG/login-stateful-app.git
   ```

2. Navigate to the project directory:
   ```sh
   cd login-stateful-app
   ```

3. Install dependencies:
   ```sh
   flutter pub get
   ```

4. Run the app on your desired platform:
   - For Android:
     ```sh
     flutter run --target=android
     ```
   - For iOS:
     ```sh
     flutter run --target=ios
     ```
   - For web:
     ```sh
     flutter run --target=web
     ```

## Configuration

No additional configuration is required for this project.

## Quick Start

To quickly start using the app, follow these steps:

1. Clone the repository.
2. Install dependencies.
3. Run the app on your desired platform.

## Usage

The app provides a simple login interface where users can enter their email and password. Upon submission, the form will validate the input and handle the login logic.

```dart
void _submitForm() {
  if (_formKey.currentState!.validate()) {
    // Handle login logic here
    ScaffoldMessenger.of(context).showSnackBar(
      SnackBar(content: Text('Login successful!')),
    );
  }
}
```

## Project Structure

```
login_stateful_app/
├── android/
│   ├── app/
│   │   └── src/
│   │       └── main/
│   │           └── kotlin/
│   │               └── com/example/login_stateful_app/
│   │                   └── MainActivity.kt
├── ios/
│   └── Runner/
│       ├── AppDelegate.swift
│       └── Assets.xcassets/
├── lib/
│   ├── main.dart
│   ├── src/
│   │   ├── app.dart
│   │   ├── mixins/
│   │   │   └── validation_mixin.dart
│   │   └── screens/
│   │       └── login_screen.dart
├── test/
│   └── widget_test.dart
└── web/
    ├── favicon.png
    ├── icons/
    ├── index.html
    └── manifest.json
```

## Development

The project uses Flutter's state management features to handle the login page. The `LoginScreen` class is a stateful widget that manages its own state, including user input and validation errors.

## Testing

This project includes basic unit tests for the widgets:

```dart
import 'package:flutter/material.dart';
import 'package:flutter_test/flutter_test.dart';
import 'package:login_stateful_app/src/screens/login_screen.dart';

void main() {
  testWidgets('LoginScreen has correct initial state', (WidgetTester tester) async {
    await tester.pumpWidget(MaterialApp(home: LoginScreen()));
    expect(find.text('Email'), findsOneWidget);
    expect(find.text('Password'), findsOneWidget);
    expect(find.byType(ElevatedButton), findsOneWidget);
  });
}
```

## Limitations

- The app does not include actual authentication logic.
- No support for additional user roles or permissions.

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more details.