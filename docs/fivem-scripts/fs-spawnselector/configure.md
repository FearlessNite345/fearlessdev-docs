---
id: configure
title: Configuring FS-SpawnSelector
sidebar\_label: Configuration
description: How to set up and configure the FS-SpawnSelector resource
---

:::tip
Configure spawn points and control when the selector appears.
:::

## 🚀 Quick Start

1. Install `fs-spawnselector` in your `resources` folder.
2. Edit `config.lua` to add spawn points and choose automatic or manual triggering.
3. Restart the resource to load your spawn list.

## 📦 Basic Setup

To configure the `FS-SpawnSelector`, open the `config.lua` file inside the resource folder. Below is an example configuration with explanations for each option:

```lua
Config = {}

-- Allows players to re-open the spawn menu using /spawnselector
Config.enableSpawnSelectorCommand = true

-- If false, the spawn selector automatically opens when players connect (if no last location is saved)
-- If true, it must be manually triggered via an export or event
Config.manuallyTrigger = false

Config.Spawns = {
  {
    id = "sandy_airfield", -- Unique identifier for this spawn
    name = "Sandy Shores Airfield", -- Name displayed in the UI
    description = "Out in the desert, near the airstrip.", -- Description under the name
    coords = vector3(1658.7671, 3258.2312, 40.7533), -- Spawn coordinates
    heading = 0.0, -- Player heading after spawn
    image = "sandy_airfield.png", -- Must exist inside `nui/images/`
    color = "#29B6F6", -- Accent color used in the UI

    -- Optional category label used to group spawns in the UI.
    -- Spawns with the same category will be displayed together.
    -- Example: 'Civilian Spawns', 'Law Enforcement Spawns', 'Event Locations Spawns'
    category = 'Civilian Spawns',

    accessControl = {
      enabled = false, -- Set to true to restrict access with ACE permissions
      permission = 'fs.spawn.sandy_airfield' -- Required ACE permission if enabled
    }
  }
}
```

---

## 🖼 Image Files

Make sure your images are located in:

```
nui/images/
```

The filename must match what you provide in the `image` field, such as `sandy_airfield.png`.

---

## 🔐 ACE Permissions

To restrict a spawn location, set `enabled = true` and define a permission name like:

```lua
accessControl = {
  enabled = true,
  permission = 'fs.spawn.sandy_airfield'
}
```

You can then grant it in your `server.cfg`:

```
add_ace group.admin fs.spawn.sandy_airfield allow
```

> Tip: Replace `group.admin` with the appropriate group or identifier.

---
