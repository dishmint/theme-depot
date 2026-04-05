# Loading Themes in Ghostty

## Install a Theme

1. Copy a theme file into your Ghostty themes directory:

   ```sh
   cp ghostty/<theme-name>/<variant> ~/.config/ghostty/themes/
   ```

   For example, to install the Future Earth dark variant:

   ```sh
   cp ghostty/future-earth/future-earth-dark ~/.config/ghostty/themes/
   ```

2. Reference the theme in your Ghostty config (`~/.config/ghostty/config`):

   ```
   theme = future-earth-dark
   ```

3. Restart Ghostty or reload the config.

## Switch Between Light and Dark Variants

Ghostty supports automatic light/dark switching. To use both variants:

```
theme = light:future-earth-light,dark:future-earth-dark
```

Make sure both theme files are copied into `~/.config/ghostty/themes/`.

## Recommended Settings for Light Themes

Light themes can cause dim/faint text (e.g., diff context lines) to become unreadable. Add the following to your Ghostty config:

```
minimum-contrast = 1.1
```

This ensures all text meets a minimum contrast ratio against the background.
