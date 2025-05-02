# Configuration Guide

This file configures various features for the FS-LoadingScreenV2 script including spawn selector support, music playback, server tips, and branding.

---

## 🎮 `useCanXSpawnSelector` (boolean)

- **Description:** Enables compatibility with the [CanX Spawn Selector](https://github.com/CanX-Script/spawn-selector).  
Set to `true` **only if** you're using the CanX resource.

> 🟢 **Default:** `false`

**Example:** `true` or `false`

---

## 🏷️ `serverName` (string)

- **Description:** The name of your server shown in welcome messages and dynamic placeholders.

**Example:** `"Fearless Roleplay"` or `"My Alaskan Server"`

---

## 🎵 `musicFiles` (array of objects)

- **Description:** List of music tracks to play during the loading screen.  
Each entry must include a `displayName` and `fileName`.

### 🔹 Structure

```lua
Config.musicFiles = {
  {
    displayName = "Chill Vibes",
    fileName = "chillvibes.mp3"
  },
  {
    displayName = "Night Drive",
    fileName = "nightdrive.mp3"
  }
}
```

> 📂 **Note:** All `.mp3` files must be placed inside `/nui/music`

> ⚠️ **Warning:** Music will not play unless at least one valid file is listed here.

---

## 💡 `serverTips` (array of strings)

- **Description:** Rotating tips shown during loading. These are limited to 128 characters each.

### 🔹 Structure

```lua
Config.serverTips = {
  "Tip 1",
  "Tip 2",
  "Tip 3",
}
```

> ℹ️ **Tips are optional** — the section will be hidden if left empty.

---

## 🖼️ Image Slideshow

- **Description:** To add background slideshow images, place your `.jpg` or `.png` files in:

```
/nui/images
```

> 📁 Images are automatically cycled through and require no config entry.

---

## 📁 Folder Overview

| Folder         | Purpose                              |
|----------------|--------------------------------------|
| `/nui/music`   | Background music files (`.mp3`)      |
| `/nui/images`  | Slideshow background images          |

---
