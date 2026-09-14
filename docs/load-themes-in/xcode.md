# Loading Themes in Xcode

Two sets of files ship in `xcode/future-earth/`:

| Files | Target |
|---|---|
| `future-earth-dark.xccolortheme`, `future-earth-light.xccolortheme` | Xcode 26 and earlier |
| `future-earth-xcode27-dark.xccolortheme`, `future-earth-xcode27-light.xccolortheme` | Xcode 27 |

## Xcode 26 and earlier

### Install

Copy the `.xccolortheme` files to Xcode's themes directory:

```sh
mkdir -p ~/Library/Developer/Xcode/UserData/FontAndColorThemes
cp xcode/future-earth/future-earth-dark.xccolortheme xcode/future-earth/future-earth-light.xccolortheme \
  ~/Library/Developer/Xcode/UserData/FontAndColorThemes/
```

### Activate

1. Open Xcode
2. Go to **Settings** > **Themes** (or press <kbd>Cmd</kbd> + <kbd>,</kbd>)
3. Select **future-earth-dark** or **future-earth-light** from the theme list

## Xcode 27

Xcode 27 replaces the **Themes** pane with **Settings** > **Appearance**, which has **Theme**, **Fonts**, and **Editor** tabs. Themes are imported through the Appearance panel instead of being copied into `FontAndColorThemes`.

### Import

1. Open Xcode 27
2. Go to **Settings** > **Appearance** (or press <kbd>Cmd</kbd> + <kbd>,</kbd>)
3. In the **Theme** section click **Choose…**
4. Under **Classic Presets** click **Import…**
5. Select `xcode/future-earth/future-earth-xcode27-dark.xccolortheme`, then repeat for `future-earth-xcode27-light.xccolortheme`

### Recommended Appearance settings

Xcode 27 generates every editor color from a base palette plus two sliders. After importing, tune these in the **Theme** tab so the whole workspace matches Future Earth:

| Setting | Dark | Light |
|---|---|---|
| Background tint | `#1B1B1E` | `#FBFFFE` |
| Text color intensity | Medium | Low |
| Background intensity | Low–medium | Low |
| Background gradient | Off | Off |

Any color you edit by hand in the Theme tab is locked and no longer follows the palette sliders; use **Reset** on a value to hand it back to the palette.

### Fonts

Xcode 27 stores font settings separately from the theme. The **Fonts** tab exposes base fonts for **Code**, **Prose**, and **Console**, and the rest of the editor fonts are generated from those. The theme files still carry per-token weights (bold functions, semibold types in the light variant), so set the Code font to `ZedMonoNFP` to keep the light variant's weight-based distinctions.

### Per-workspace themes

Xcode 27 can assign a different theme to each workspace. Pick **future-earth-xcode27-dark** or **future-earth-xcode27-light** for a workspace from the same **Theme** section while that workspace is frontmost.
