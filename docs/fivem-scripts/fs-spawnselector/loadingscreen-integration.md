---

id: LoadingScreenV2-integration
title: LoadingScreenV2 Integration
sidebar\_label: Loading Screen
description: How to integrate FS-SpawnSelector with the Fearless Studios loading screen
---

## ⚙️ Setup with FS-LoadingScreenV2

To integrate `FS-SpawnSelector` with the **Fearless Studios Loading Screen V2**, follow these steps:

---

### 1. Enable Export Triggering in the Spawn Selector

In the `config.lua` of `FS-SpawnSelector`, set:

```lua
Config.manuallyTrigger = true
```

This disables the automatic spawn menu and instead allows it to be triggered by the loading screen once loading is finished.

---

### 2. Enable Integration in the Loading Screen

In your `FS-LoadingScreenV2` config file, make sure the following is set:

```lua
Config.useFearlessStudiosSpawnSelector = true
```

This tells the loading screen to call the spawn selector once the player finishes loading in.

---

## ✅ Result

Once both configs are set properly:

- The spawn selector **will not appear** until the loading screen finishes.
- After loading is complete, it will **automatically trigger** the selector using the internal export:

  ```lua
  exports["FS-SpawnSelector"]:chooseSpawn()
  ```

---

## 📌 Note

If `Config.manuallyTrigger` is not set to `true` in the spawn selector, it will show immediately — before your loading screen finishes.
