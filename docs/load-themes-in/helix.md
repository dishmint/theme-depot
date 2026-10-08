# Loading Themes in Helix

## Install a Theme

1. Copy a theme file into your Helix themes directory:

   ```sh
   cp helix/<theme-name>/<variant>.toml ~/.config/helix/themes/
   ```

   For example, to install the Future Earth dark variant:

   ```sh
   cp helix/future-earth/future-earth-dark.toml ~/.config/helix/themes/
   ```

   Helix only loads themes whose filename ends in `.toml`, so keep the extension.

2. Reference the theme in your Helix config (`~/.config/helix/config.toml`):

   ```toml
   theme = "future-earth-dark"
   ```

3. Restart Helix, or apply it live with `:theme future-earth-dark`.

## Switch Between Light and Dark Variants

Copy both variants into `~/.config/helix/themes/` first.

### Automatic (unreleased Helix)

> Requires a Helix build from `master`. Released versions up to 25.07.1 do
> not support this; use manual switching below.

Replace the `theme = "..."` line in `~/.config/helix/config.toml` with:

```toml
[theme]
dark = "future-earth-dark"
light = "future-earth-light"
# Optional. Used if the terminal doesn't report a preference.
# Defaults to the `dark` theme if not set.
# fallback = "future-earth-dark"
```

Helix reads the light/dark mode from the terminal, so the terminal must
support [mode 2031 dark/light detection](https://github.com/contour-terminal/contour/blob/master/docs/vt-extensions/color-palette-update-notifications.md).

### Manual

Swap variants with `:theme`:

```
:theme future-earth-light
:theme future-earth-dark
```
