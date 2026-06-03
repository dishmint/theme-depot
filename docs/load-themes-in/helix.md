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

Helix has no automatic light/dark switching. Copy both variants into
`~/.config/helix/themes/` and swap with `:theme` as needed:

```
:theme future-earth-light
:theme future-earth-dark
```
