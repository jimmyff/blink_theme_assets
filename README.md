# blink_theme_assets

Bundled TOML theme definitions for Blink applications. Contains the default dark and light themes shipped with Cache and Blink Editor.

## Included Themes

- **twilight-sandstone.toml** - Default dark theme with muted colors optimized for low-light environments
- **hoarfrost-sandstone.toml** - Default light theme with high contrast for bright environments

## File Structure

Each theme file follows the blink_theme TOML format:

```toml
[metadata]
name = "Theme Name"
author = "Author"

[scopes]
# Hierarchical scope definitions
"*" = { fg = "$foreground" }
"syntax.keyword" = { fg = "$magenta" }
"ui.editor.background" = { bg = "$bg" }
"ui.chrome.navbar.item.text:active" = { fg = "$accent" }

[palette]
# Color definitions
foreground = "#d4d4d4"
bg = "#1e1e1e"
magenta = "#c678dd"
```

## Usage

Applications reference these themes by filename in their default settings:

```dart
// apps/notes/lib/app_defaults.dart
const notesDefaults = AppDefaults(
  theme: ThemeDefaults(
    mode: 'system',
    dark: 'twilight-sandstone.toml',
    light: 'hoarfrost-sandstone.toml',
  ),
);
```

The `blink_theme` package handles parsing and applying these TOML files.

## See Also

- **blink_theme package** (`../../packages/blink_theme/`) - Theme parsing, API, and scope system documentation
- **THEME_SCOPE_SYSTEM.md** - Complete scope specification and guidelines
