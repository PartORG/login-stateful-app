# login_stateful_app

A simple Flutter app - login page that uses StateFulWidget approach.

[![language](https://img.shields.io/badge/language-Dart-blue.svg)] [![runtime](https://img.shields.io/badge/runtime-Flutter-green.svg)] [![license](https://img.shields.io/badge/license-MIT-yellow.svg)] [![package manager](https://img.shields.io/badge/package%20manager-pub-orange.svg)] [![testing](https://img.shields.io/badge/testing-flutter_test-blue.svg)] [![important technologies](https://img.shields.io/badge/technologies-Flutter%2C%20StatefulWidget-green.svg)]

## Introduction

This project is a simple Flutter application that demonstrates the use of StatefulWidgets for creating a login page. It provides a basic structure and can be extended with additional features as needed.

The primary workflow involves setting up a Flutter environment, creating a new project, and implementing the login functionality using StatefulWidgets. The app includes validation mixins to ensure user input is correct before submission.

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

### StatefulWidget Approach

The app uses Flutter's StatefulWidgets to manage the state of the login page. This allows for dynamic updates and interactions without needing to rebuild the entire widget tree.

### Validation Mixin

A validation mixin is included to ensure that user input meets certain criteria before submission. This helps in preventing invalid data from being processed.

## How It Works

The app consists of a single screen, `LoginScreen`, which uses a StatefulWidget to manage its state. The login form includes fields for username and password, along with validation logic.

### Architecture Diagram

```
+-------------------+
|  LoginScreen      |
|                   |
| +---------------+ |
| | UsernameField | |
| +---------------+ |
| +---------------+ |
| | PasswordField | |
| +---------------+ |
| +---------------+ |
| | SubmitButton  | |
| +---------------+ |
+-------------------+
```

## Technology Stack

| Technology | Purpose |
|------------|---------|
| Flutter    | The UI software development kit used to build the app. |
| StatefulWidget | Manages the state of the login page dynamically. |
| ValidationMixin | Ensures user input is valid before submission. |

## Requirements

- Flutter SDK (version 2.5.0 or higher)
- Dart SDK (version 2.14.0 or higher)

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

3. Get dependencies:
   ```sh
   flutter pub get
   ```

4. Run the app on an emulator or physical device:
   ```sh
   flutter run
   ```

## Configuration

No additional configuration is required for this project.

## Quick Start

To quickly start using the login page, follow these steps:

1. Open `lib/src/screens/login_screen.dart`.
2. Implement your custom logic in the `LoginScreen` class.
3. Run the app to see the login page in action.

## Usage

Here are some example commands and usage scenarios:

- Build the project:
  ```sh
  flutter build apk
  ```

- Test the app:
  ```sh
  flutter test
  ```

## Project Structure

```
login_stateful_app/
├── android/
│   ├── ...
├── ios/
│   ├── ...
├── lib/
│   ├── main.dart
│   └── src/
│       ├── app.dart
│       ├── mixins/
│       │   └── validation_mixin.dart
│       └── screens/
│           └── login_screen.dart
├── test/
│   └── widget_test.dart
└── web/
    ├── ...
```

- `lib/main.dart`: The entry point of the Flutter app.
- `lib/src/app.dart`: Contains the main application logic.
- `lib/src/mixins/validation_mixin.dart`: Provides validation functionality for forms.
- `lib/src/screens/login_screen.dart`: Implements the login page using a StatefulWidget.

## Development

To contribute to this project, follow these steps:

1. Fork the repository.
2. Create a new branch:
   ```sh
   git checkout -b feature/your-feature-name
   ```
3. Make your changes and commit them.
4. Push your changes to your forked repository.
5. Open a pull request.

## Testing

This project includes unit tests for the login screen:

```sh
flutter test
```

## Limitations

- The app does not include user authentication logic.
- No support for dark mode or localization.

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more details.