# CHANGE LOG

## 1.0.1

- Update local_storage dependency to latest 0.5.0
- Added and fixed linter rules
- Fixed default Dark mode problem from PRs

## 1.0.3

- Null safe feature added

## 1.0.4

- Now use the [ThemeMode] instead of [Brightness]
- [ThemedWidgetBuilder] themedWidgetBuilder takes now the following parameters: [BuildContext], [ThemeMode], [ThemeData].
- [data] parameter is now optional and has the type [ThemeDataWithThemeModeBuilder].
- defaultBrightness became [defaultThemeMode] and use by default [ThemeMode.system].
- [loadBrightnessOnStart] became [loadThemeOnStart].
- import [package:dynamic_theme/dynamic_theme.dart] for both [DynamicTheme] and [BrightnessSwitcherDialog].