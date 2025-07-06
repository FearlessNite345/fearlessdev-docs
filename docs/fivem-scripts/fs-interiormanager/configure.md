---
id: configure
title: Configuring FS-InteriorManager
sidebar_label: Configuration
description: How to configure FS-InteriorManager
---

# Configuration Guide

:::tip
Manage interior teleports, entity sets, and IPLs from a single `config.lua` file.
:::

This document describes how to configure and extend the Interior Manager using the `config.lua` file.

## 🚀 Quick Start

1. Drop the `fs-interiormanager` folder into your `resources` directory.
2. Edit `config.lua` to define interior folders and presets.
3. Restart your server to load the new settings.

---

## 🔧 Global 

### `Config.menuCommand` (string)

- The command used to open the Interior Manager menu in-game.
- **Default:** `'interiormanager'`

### `Config.acePermissionForAdmin` (string)

- The ACE permission required to access admin-only interiors or controls.
- **Default:** `'entitysetloader.access'`

---

## 📂 Interior Folders

### `Config.InteriorFolders`

Organize interiors into named folders for easier navigation in the UI.

#### Structure:

```lua
Config.InteriorFolders = {
  {
    folder = "Sandy Houses", -- Display name of the folder
    interiors = { ... }       -- List of interiors (see below)
  }
}
```

Each `interiors` array contains interior definitions.

---

## 🏠 Interior Structure

Each interior entry can have the following fields:

### Required Fields:

- `id` *(string)* – A unique identifier for the interior
- `name` *(string)* – Display name shown in the UI
- `coords` *(vector3)* – The location for teleportation or reference

### Optional Fields:

- `adminOnly` *(boolean)* – If true, only users with ACE permission can access it
- `defaults.sets` *(string[])* – Sets that are enabled by default on load
- `entitySets` *(object[])* – A list of toggleable entity sets (see below)
- `ipls` *(object[])* – A list of IPLs related to the interior (for loading/removing props or structures)
- `presets` *(object[])* – Preset s to quickly switch between styles or states

:::tip
You must define **at least one** of `entitySets` or `ipls`.
:::

### Example Entry:

```lua
{
  id = "prompts_sandy_house1",
  name = "House 1",
  coords = vec3(1812.367, 3762.021, 34.21988),
  adminOnly = false,
  defaults = {
    sets = { "wallframe2", "windowframe1" }
  },
  entitySets = {
    { label = "Wall Frame 2", set = "wallframe2" },
    { label = "Window Frame 1", set = "windowframe1" },
  },
  presets = {
    {
      label = "Clean",
      sets = { "wallframe2", "windowframe1" },
      ipls = {}
    }
  }
}
```

---

## 🧩 Entity Sets

### `entitySets`

An array of named toggleable entity sets available in the interior. Used to dynamically enable or disable objects in the game world.

#### Example:

```lua
{ label = "Kitchen Light", set = "kitchenlight" }
```

---

## 🌐 IPLs

### `ipls`

A list of IPL props or features to enable when the preset is loaded. You can include multiple IPLs per preset.

#### Example:

```lua
{ label = "Wedding Venue", name = "p_prompt_sandy_cityhall_wedding_venue" }
```

These IPLs are used for large structural or prop changes such as chairs, coffins, or entire venues.

---

## 🎛️ Presets

### `presets`

Preconfigured selections of entity sets and IPLs that users can toggle with one click.

Each preset should have:

- `label` *(string)*: Name of the preset (e.g., "Clean", "Lights Off")
- `sets` *(string[])*: Entity sets to enable
- `ipls` *(string[])*: IPLs to load

:::info
Entity sets and IPLs not listed in a preset will be disabled when that preset is applied.
:::

---

## 🛑 Admin-Only Interiors

### `adminOnly` = true

Restrict access to specific interiors via ACE permissions.

:::warning
Players **without** the correct ACE will not see or access these interiors in the menu.
:::

---

## 🏛️ Example Admin-Only Setup

```lua
{
  id = "prompts_sandy_cityhall",
  name = "Sandy Cityhall Interior",
  coords = vec3(1753.6223, 3804.6450, 35.4474),
  adminOnly = true,
  ipls = {
    { label = "Wedding Chairs", name = "p_prompt_sandy_cityhall_wedding_chairs" },
    ...
  },
  presets = {
    {
      label = "Wedding Ceremony",
      sets = {},
      ipls = {
        "p_prompt_sandy_cityhall_wedding_chairs",
        "p_prompt_sandy_cityhall_wedding_venue"
      }
    }
  }
}
```

---

## 💡 Notes

- `sets` are primarily used for entitySet toggling.
- `ipls` are useful for complex map modifications.
- Every interior can have a mix of both or just one type.
- Ensure all IDs are **unique** and use **vec3** properly formatted for locations.

---

## ✅ Example Folder Setup

```lua
Config.InteriorFolders = {
  {
    folder = "Sandy Houses",
    interiors = {
      -- See individual interior entries above
    }
  }
}
```

---

## 🗂 Config.Interiors

This section is used for globally defined interiors that are **not part of a folder**. They behave the same way but are shown independently in the UI.

```lua
Config.Interiors = {
  {
    id = "gcom_logistics",
    name = "Logistics Interior",
    coords = vec3(1885.3466, 3147.4792, 44.6878),
    adminOnly = true,
    entitySets = {
      { label = "Garage with Storage", set = "gcom_lc_garage_2" }
    }
  }
}
```
