# dynamic_theme_nullsafe

## Dynamically changing your theme without hassle

![](https://github.com/ehtsham623/dynamic_theme_nullsafe/blob/main/assets/theme.png)

This packages manages changing your theme during runtime and persiting that theme.

## Include in your project

```
dependencies:
  dynamic_theme_nullsafe: ^1.0.3
```

run packages get and import it

```
import 'package:dynamic_theme_nullsafe/dynamic_theme_nullsafe.dart';
```

if you want the dialog:

```
import 'package:dynamic_theme_nullsafe/theme_switcher_widgets.dart';
```

## Usage

Wrap your material app like this:

```dart

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return new DynamicTheme(
      defaultBrightness: Brightness.light,
      data: (brightness) => new ThemeData(
        primarySwatch: Colors.indigo,
        brightness: brightness,
      ),
      themedWidgetBuilder: (context, theme) {
        return new MaterialApp(
          title: 'Flutter Demo',
          theme: theme,
          home: new MyHomePage(title: 'Flutter Demo Home Page'),
        );
      }
    );
  }
}

```

Change the theme like this:

```dart
  void changeBrightness() {
    DynamicTheme.of(context).setBrightness(Theme.of(context).brightness == Brightness.dark? Brightness.light: Brightness.dark);
  }

  void changeColor() {
    DynamicTheme.of(context).setThemeData(new ThemeData(
        primaryColor: Theme.of(context).primaryColor == Colors.indigo? Colors.red: Colors.indigo
    ));
  }

```

When changing the brightness with `setBrightness`, it is additionally stored in the shared preferences.

## Getting Started

For help getting started with Flutter, view our online [documentation](https://flutter.io/).

For help on editing package code, view the [documentation](https://flutter.io/developing-packages/).
