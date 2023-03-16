# dynamic_theme_nullsafe

## Dynamically changing your theme without hassle

![](https://github.com/ehtsham623/dynamic_theme_nullsafe/blob/main/assets/theme.png)

This packages manages changing your theme during runtime and persiting that theme.

## Include in your project

```
dependencies:
  dynamic_theme_nullsafe: ^1.0.5
```

run packages get and import it

```
import 'package:dynamic_theme_nullsafe/dynamic_theme_nullsafe.dart';
```

## Usage

Wrap your material app like this:

```dart

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return DynamicThemeNullsafe(
      defaultThemeMode: ThemeMode.light,
      loadThemeOnStart: true,
      data: (mode) => ThemeData(
        primarySwatch: Colors.indigo,
        brightness: mode == ThemeMode.dark ? Brightness.dark : Brightness.light,
      ),
      themedWidgetBuilder: (
        BuildContext context,
        ThemeMode mode,
        ThemeData? data,
      ) {
        return MaterialApp(
          themeMode: mode,
          title: 'Flutter Demo',
          theme: data,
          home: const MyHomePage(title: 'Flutter Demo Home Page'),
        );
      },
    );
  }
}

```

Change the theme like this:

```dart
  void changeBrightness() {
    DynamicThemeNullsafe.of(context).toggleThemeMode();
  }

  void changeColor() {
    DynamicThemeNullsafe.of(context).setThemeMode(ThemeMode.dark);
  }

```

When changing the ThemeMode with `ThemeMode`, it is additionally stored in the shared preferences.

## Getting Started

For help getting started with Flutter, view our online [documentation](https://flutter.io/).

For help on editing package code, view the [documentation](https://flutter.io/developing-packages/).
