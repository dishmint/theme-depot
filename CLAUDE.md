# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Theme Depot is a collection of custom color themes for terminal emulators and other applications. Themes are organized by application, with each theme having light and dark variants.

## Repository Structure

- `<app>/<theme-name>/` — Theme files per application (e.g., `ghostty/<theme-name>/`)
- `docs/load-themes-in/` — Per-application installation guides

## Theme File Formats

### Xcode

XML plist files (`.xccolortheme`) following Apple's `DVTFontAndColorTheme` schema. Each theme defines:
- Syntax colors (`DVTSourceTextSyntaxColors`) — RGBA values in `"R G B A"` format (0–1 range)
- Syntax fonts (`DVTSourceTextSyntaxFonts`) — `"FontName - Size"` format
- Editor chrome — background, selection, cursor, line highlight, scrollbar markers, invisibles
- Console colors — debugger input/output, prompt, background, cursor
- Markup colors — headings, links, code, emphasis

Light and dark variants follow the palette's design principles: dark mode uses color distinctions, light mode uses font weight distinctions (bold for functions, semibold for types) with minimal color.

Xcode 27 variants (`future-earth-xcode27-dark` / `-light`) live alongside the base files. They keep every base value and add the keys Xcode 27's Appearance panel reads on import: `DVTDebuggerInstructionPointerColor`, `DVTFontSizeModifier`, `DVTMarkupTextFont`, and `xcode.syntax.markup.aside.kind` (color and font). Xcode 27 imports them via **Settings > Appearance > Theme > Choose… > Classic Presets > Import…** rather than the `FontAndColorThemes` directory. When changing a base color, apply the same change to the Xcode 27 variant.

### Ghostty

Plain-text config files (no extension) using `key = value` syntax. Each theme defines:
- 16-color ANSI palette (`palette = 0=#HEX` through `palette = 15=#HEX`)
- `background`, `foreground`, `cursor-color`, `cursor-text`, `selection-background`, `selection-foreground`

Light and dark variants share the same palette structure but swap background/foreground and adjust color intensity for readability on each background.

## Adding a New Theme

1. Create `<app>/<theme-name>/<theme-name>-dark` and `<theme-name>-light`
2. Add an installation guide at `docs/load-themes-in/<app>.md` if the app isn't covered yet
3. List the theme in `README.md` under **Themes**

## Adding a New Application

1. Create a new top-level directory named after the application (e.g., `ghostty/`)
2. Add theme files following that application's config format
3. Add a corresponding doc in `docs/load-themes-in/`
