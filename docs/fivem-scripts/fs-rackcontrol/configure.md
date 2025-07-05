---
id: configure
title: Configuring FS-RackControl
sidebar_label: Configuration
description: How to configure FS-RackControl
---

# Configuration Guide

:::tip
Fine-tune weapon racking, notifications, and loadouts via `config.lua`.
:::

This file configures various behavior for the weapon racking script including language support, notification system, weapon definitions, and loadouts.

---

## 🔤 `language` (string)

- **Description:** Sets the active language file used for localized strings.

:::tip Default
`"en"`
:::

**Example:** `"en"`, `"de"`, `"fr"`

---

## 📢 `executeMeCommandOnRackAction` (boolean)

- **Description:** If `true`, it will execute a `/me` command when racking or unracking weapons.

**Example:** `true` or `false`

---

## 🔔 `notificationSettings` (object)

Settings that control how notifications are shown to players.

### ▸ `useNotifications` (boolean)

- **Description:** Enables or disables the notification system entirely.

**Example:** `true`

### ▸ `notificationSystem` (string)

- **Description:** Specifies which notification system to use.

:::info Allowed Values

- `"default"` – Uses GTA's native notification.
- `"ox_lib"` – Uses the ox_lib notification system.
- `"bigdaddy"` – Uses the big daddy notification system.
  :::

**Example:** `"default"`

:::warning
If you enter an invalid notification system, a console error will be triggered.
:::

---

## 🔫 `rifle` (object)

Settings for the rifle weapon used in rack/unrack logic.

### ▸ `hash` (number)

- **Description:** Weapon hash for the rifle.

**Example:** `-2084633992`

### ▸ `name` (string, optional)

- **Description:** Display name of the rifle.

**Example:** `"Carbine Rifle"`

### ▸ `ammoCount` (number, optional)

- **Description:** Amount of ammo to give when unracking.

:::tip Default
`100` if not specified.
:::

---

## 🔫 `shotgun` (object)

Same structure and behavior as `rifle`, but for the shotgun.

---

## 🧰 `loadout` (object)

Defines the default weapons given via the `/loadout` command.

Each item follows the `Weapon` structure:

- `hash` (number): Weapon hash.
- `name` (string, optional): Display name (for logging or debugging).
- `ammoCount` (number, optional): Ammo amount (defaults to 100).

### ▸ `pistol`

### ▸ `flashlight`

### ▸ `nightstick`

### ▸ `stungun`

### ▸ `knife`

---

## 📌 Example `config.json`:

```json
{
  "language": "en",
  "executeMeCommandOnRackAction": true,
  "notificationSettings": {
    "useNotifications": true,
    "notificationSystem": "ox_lib"
  },
  "rifle": {
    "hash": -2084633992,
    "name": "Carbine Rifle",
    "ammoCount": 120
  },
  "shotgun": {
    "hash": 487013001,
    "name": "Pump Shotgun",
    "ammoCount": 40
  },
  "loadout": {
    "pistol": { "hash": 453432689 },
    "flashlight": { "hash": 2343591895 },
    "nightstick": { "hash": 1737195953 },
    "stungun": { "hash": 911657153 },
    "knife": { "hash": 2578778090 }
  }
}
```
