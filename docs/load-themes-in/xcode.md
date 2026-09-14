# Loading Themes in Xcode

Two formats ship in `xcode/future-earth/`:

| Files | Format | Target |
|---|---|---|
| `future-earth-dark.xcworkspacecolortheme`, `future-earth-light.xcworkspacecolortheme` | Workspace theme recipe (JSON) | Xcode 27 |
| `future-earth-dark.xccolortheme`, `future-earth-light.xccolortheme` | Classic font and color theme (plist) | Xcode 26 and earlier; also importable into Xcode 27 as a Classic Preset |

## Xcode 27

Xcode 27 replaces the **Themes** pane with **Settings** > **Appearance**, which has **Theme**, **Fonts**, and **Editor** tabs. The `.xcworkspacecolortheme` files carry the full Appearance recipe: base palette, background, and every per-token override.

### Install

Xcode 27 reads workspace themes from the same directory as classic themes:

```sh
mkdir -p ~/Library/Developer/Xcode/UserData/FontAndColorThemes
cp xcode/future-earth/*.xcworkspacecolortheme ~/Library/Developer/Xcode/UserData/FontAndColorThemes/
```

Importing through the UI (**Settings** > **Appearance** > **Theme** > **Choose…** > **Import…**) should also work but hasn't been tested with `.xcworkspacecolortheme` files.

### Activate

1. Open Xcode 27
2. Go to **Settings** > **Appearance** (or press <kbd>Cmd</kbd> + <kbd>,</kbd>)
3. In the **Theme** section click **Choose…** and select **future-earth-dark** or **future-earth-light**

Xcode picks the dark or light recipe to match the **Appearance** setting at the top of the panel (System, Light, Dark).

### Fonts

Xcode 27 stores fonts separately from the theme. In the **Fonts** tab set the **Code** font to `ZedMonoNFP` (or your monospace of choice). The light variant relies on bold functions and semibold types, which come from the font, not the recipe.

### Per-workspace themes

Xcode 27 can assign a different theme to each workspace. With that workspace frontmost, pick **future-earth-dark** or **future-earth-light** from the same **Theme** section.

## Xcode 26 and earlier

### Install

Copy the `.xccolortheme` files to Xcode's themes directory:

```sh
mkdir -p ~/Library/Developer/Xcode/UserData/FontAndColorThemes
cp xcode/future-earth/*.xccolortheme ~/Library/Developer/Xcode/UserData/FontAndColorThemes/
```

### Activate

1. Open Xcode
2. Go to **Settings** > **Themes** (or press <kbd>Cmd</kbd> + <kbd>,</kbd>)
3. Select **future-earth-dark** or **future-earth-light** from the theme list
