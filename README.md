
# 📱 Flutter Project Structure SOP

This document defines the **standard folder structure and practices** for building and maintaining Flutter applications.

---

## 📁 Project Structure

```
lib/
├── main.dart                # Entry point of the application
└── src/
    ├── app.dart             # Root App widget and MaterialApp setup
    ├── bloc/                # State management using BLoC/Cubit
    ├── constants/           # All static constants used in the app
    ├── model/               # Data models with JSON parsing
    ├── service/             # API calls, local DB, notifications
    ├── utils/               # Helpers, extensions, navigators
    ├── view/                # UI Screens (grouped by feature)
    ├── widgets/             # Common reusable widgets
    └── app_export.dart      # Centralized export of constants, utils, models
```

---

## 🔹 File Descriptions

### `main.dart`
- Located in the root `lib/` folder.
- Entry point of the app.
- Initializes services like Hive, Firebase, and runs the `App()` widget.

### `app.dart`
- Located at `lib/src/app.dart`
- Contains `MaterialApp`, theme setup, route setup, and localization configuration.

### `app_export.dart`
- Located at `lib/src/app_export.dart`
- Exports:
  - Constants (colors, strings, icons, themes, text styles)
  - Utilities (extensions, navigation helpers)
  - Services (API, local storage)
  - Widgets (dialogs, sheets, etc.)
  - Models

> 💡 Use this in files to reduce import clutter:
```dart
import 'package:your_project_name/src/app_export.dart';
```

---

## 📂 Folder Breakdown

| Folder       | Purpose |
|--------------|---------|
| `bloc/`      | Cubits/BLoCs per feature (`.bloc.dart`, `.event.dart`, `.state.dart`) |
| `constants/` | All constant files: `app_colors.dart`, `app_strings.dart`, etc. |
| `model/`     | Data models with `fromJson` and `toJson` |
| `service/`   | API services, Hive/local DB, notification handlers |
| `utils/`     | Extensions, navigation, validators, file helpers |
| `view/`      | UI screens organized by feature (`login/`, `home/`, etc.) |
| `widgets/`   | Common reusable widgets (dialogs, loaders, buttons, etc.) |

---

## ✅ Best Practices

- 🧠 Separate logic (bloc/service) from UI (view).
- 🌍 Use `flutter_bloc`, `freezed`, `json_serializable`.
- 📦 Reuse components via `widgets/` and export all via `app_export.dart`.
- 🧪 Write unit, widget, and integration tests.
- 📐 Use responsive layouts and centralized themes.
- 🌐 Add localization support from the start.
- 🚀 Optimize using lint rules and clean architecture.

---

## 📚 Recommended Packages

| Purpose             | Package                    |
|---------------------|----------------------------|
| State Management    | `flutter_bloc`, `equatable` |
| API                 | `http`              |
| Local Storage       | `hive`, `shared_preferences` |
| UI/UX               | `flutter_svg`, `google_fonts`, `shimmer` |
| Notification        | `firebase_messaging`, `flutter_local_notifications` |

---

## 🧩 Usage

Every new feature should have:
- 📂 Folder inside `view/feature_name/`
- 🎯 Corresponding BLoC or Cubit in `bloc/`
- 🧾 API logic in `service/`
- 📦 Reusable components in `widgets/`

---

> Authored by Zeel Sojitra
