---
id: configure
title: Configuring FS-LoadingScreenV2
sidebar_label: Configuration
description: How to configure FS-LoadingScreenV2
---

#  Guide

:::tip
Customize your server's loading experience with music, tips and spawn selector integration.
:::

This file configures various features for the FS-LoadingScreenV2 script including spawn selector support, music playback, server tips, background slideshow, and server branding.

---

## 🎮 Spawn Selector Integration

### `useFearlessStudiosSpawnSelector` (boolean)

* **Description:** Enables support for the \[FS-SpawnSelector] resource by Fearless Studios. Set to `true` if you are using that resource.

> ✅ You must also set `Config.manuallyTrigger = true` inside the FS-SpawnSelector config.

**Example:** `true` or `false`

### `useWXSpawnSelector` (boolean)

* **Description:** Enables support for the [WX Spawn Selector](https://github.com/nwvh/wx_spawnselector). Only enable if that resource is installed.

**Example:** `true` or `false`

### `useCanXSpawnSelector` (boolean)

* **Description:** Enables compatibility with the [CanX Spawn Selector](https://github.com/CanX-Script/spawn-selector). Set to `true` only if you're using that resource.

**Example:** `true` or `false`

---

## 🏷️ `serverName` (string)

* **Description:** The name of your server shown in welcome messages and dynamic placeholders.

**Example:** `"Fearless Roleplay"` or `"My Alaskan Server"`

---

## 👋 `useWelcomePrefix` (boolean)

* **Description:** When true, the loading screen will say "Welcome PlayerName". When false, it just shows the player's name.

**Example:** `true` or `false`

---

## 🎵 `musicFiles` (array of objects)

* **Description:** List of music tracks to play during the loading screen. Each track must include a `displayName` and `fileName`.

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

> 📂 Place all `.mp3` files inside `/nui/music`

> ⚠️ Music will not play unless at least one valid file is defined.

---

## 💡 `serverTips` (array of strings)

* **Description:** Rotating tips shown during the loading screen. Each must be under 128 characters.

### 🔹 Structure

```lua
Config.serverTips = {
  "Remember to /register at City Hall!",
  "Check /help for useful commands.",
  "Use your map to find starter jobs."
}
```

> ℹ️ This section is optional. If left empty, the tips box will be hidden.

---

## 🖼️ Background Slideshow

### `useRandomImageOrder` (boolean)

* **Description:** When true, background images are shuffled randomly and never repeat back-to-back.

**Example:** `true` or `false`

### `backgroundImageChangeInterval` (number)

* **Description:** Delay in milliseconds between background image transitions.

**Example:** `4000` (4 seconds)

---

## 💬 Tip Rotation Timing

### `serverTipChangeInterval` (number)

* **Description:** Delay in milliseconds between server tip changes.

**Example:** `6000` (6 seconds)

---

## 📁 Folder Overview

| Folder        | Purpose                                      |
| ------------- | -------------------------------------------- |
| `/nui/music`  | Background music files (`.mp3`)              |
| `/nui/images` | Slideshow background images (`.jpg`, `.png`) |

> 📸 Images are automatically cycled and require no manual config.
