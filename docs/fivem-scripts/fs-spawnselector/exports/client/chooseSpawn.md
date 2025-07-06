---

id: chooseSpawn
title: chooseSpawn
sidebar\_label: chooseSpawn
description: chooseSpawn export docs
------------------------------------

## `chooseSpawn`

:::info
Triggers the spawn selector UI manually. Useful if you’re integrating with external systems like a loading screen or character creator.
:::
Use this export in your scripts.


Call this export from another resource once a player has loaded in:

```lua
exports['FS-SpawnSelector']:chooseSpawn()
```

---

### 🔧 Usage

```lua
exports["FS-SpawnSelector"]:chooseSpawn()
```

---

### 📋 Notes

* You do **not** need to set `Config.manuallyTrigger = true` to use this export.
* However, setting `Config.manuallyTrigger = true` **prevents the UI from showing automatically**, allowing full control over when it appears.

---

### 💡 When to Use

* After your loading screen finishes loading the player
* After selecting a character in a multicharacter system
* When using a manual command or interaction to trigger spawn selection

---

### 🧪 Internal Reference

This export runs the internal `chooseSpawn()` function:

```lua
exports("chooseSpawn", function()
    chooseSpawn()
end)
```

This allows the selector to be triggered from any external resource.