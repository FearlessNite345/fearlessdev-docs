---
id: configure
title: Configuring FS-Money
sidebar_label: Configuration
description: How to configure FS-Money
sidebar_position: 0
---

# Configuration Guide

:::tip
Tweak how cash, bank, and dirty money behave on your server by editing `config.lua`.
:::

This guide explains how to configure the `config.lua` file for **FS-Money**, customizing how the money system works on your FiveM server.

## 🚀 Quick Start

1. Place the `fs-money` folder in your `resources` directory.
2. Edit `config.lua` to enable or disable the features you need.
3. Restart the resource (or the whole server) to apply your changes.

---

## 📂 File Location

You can find the configuration file here:  

```
resources/[fs-money]/config.lua
```

---

## ⚙️ General Settings

### `Config.debug`
- **Type:** `boolean`
- **Default:** `false`
- **Description:**  
  Enables debug mode for logging detailed messages. Useful for development and troubleshooting.

---

### `Config.AllowManualMoneyControl`
- **Type:** `boolean`
- **Default:** `true`
- **Description:**  
  Allows players to manually change their own money values using commands.  

  > ⚠️ Only enable this in development or test environments.

---

### `Config.ManualMoneyPermissions`
- **Type:** `table`
- **Default:**
  ```lua
  {
      setcash = true,
      setbank = true,
      setdirtymoney = true,
      setpokerchips = true
  }
  ```
- **Description:**  
  Permissions for self-modification commands. Active only if `AllowManualMoneyControl` is enabled.

  **Supported Commands:**
  - `/setcash`
  - `/setbank`
  - `/setdirtymoney`
  - `/setpokerchips`

---

### `Config.adminAcePerm`
- **Type:** `string`
- **Default:** `'fs_money.admin'`
- **Description:**  
  ACE permission required for admin-level commands (e.g., setting another player's cash/bank).

---

### `Config.bankName`
- **Type:** `string`
- **Default:** `"Fearless Bank"`
- **Description:**  
  The name displayed in UI and notifications for bank-related actions.

---

## 💵 Paycheck Settings

### `Config.Paychecks`
- **Type:** `table`
- **Default:**
  ```lua
  {
      Enable = false,
      PaycheckInterval = 30,
      PaycheckAmount = 1500,
      PaycheckName = "[Paycheck]"
  }
  ```
- **Fields:**
  - **`Enable`**: Enable/disable the automatic paycheck system.  
  - **`PaycheckInterval`**: Time (in minutes) between paychecks.  
  - **`PaycheckAmount`**: Amount of cash awarded per cycle.  
  - **`PaycheckName`**: Title of the paycheck notification.

---

## 💸 Starting Balances

### `Config.InitialCash`
- **Type:** `number`
- **Default:** `500`
- **Description:**  
  Starting cash for new players.

### `Config.InitialBank`
- **Type:** `number`
- **Default:** `1500`
- **Description:**  
  Starting bank balance for new players.

---

## 📱 Phone Integration

### `Config.useLBPhoneIntegration`
- **Type:** `boolean`
- **Default:** `false`
- **Description:**  
  Enables integration with LB Phone using the provided FS-Money app.  

  Set this to `true` **only if you are using the custom app** included with FS-Money.

---

### `Config.showDefaultNotifications`
- **Type:** `boolean`
- **Default:** `true`
- **Description:**  
  Show default GTA notifications. Disable this if using LB Phone integration.

---

## 🏧 ATM Configuration

### `Config.ATM`
- **Type:** `table`
- **Default Example:**
  ```lua
  {
      Increment = 10,
      Fee = 2.5,
      UseKey = 38,
      AdditionalModels = {
          {
              hash = -960287005,
              verticalOffset = 0.0,
              interactDistance = 0.8,
              rotationOffset = 90.0,
              swapXY = true,
              standingOffset = -0.4
          },
      }
  }
  ```
- **Fields:**
  - **`Increment`**: Minimum transaction amount for deposits/withdrawals.  
  - **`Fee`**: Flat fee per ATM use.  
  - **`UseKey`**: Key code to interact with ATMs (default: `E`).  
  - **`AdditionalModels`**: Define custom ATM models and settings.

---

## 🤝 Player-to-Player Payments

### `Config.PayPlayerKey`
- **Type:** `number`
- **Default:** `38` (`E`)
- **Description:**  
  Key to initiate payment to another nearby player.

### `Config.PayPlayerCancelKey`
- **Type:** `number`
- **Default:** `73` (`X`)
- **Description:**  
  Key to cancel an in-progress player payment.

---

## 🖥️ Client HUD Update

### `Config.ClientUpdate`
- **Type:** `table`
- **Default:**
  ```lua
  {
      Enable = true,
      Type = "event",
      ResourceName = "",
      Name = "FS-Money:UpdateMoney"
  }
  ```
- **Description:**  
  Controls how the client-side **Money HUD** updates are triggered.  

  **Fields:**
  - **`Enable`**: Enable HUD update triggers.  
  - **`Type`**: `"event"` (trigger a client event) or `"export"` (call an export function).  
  - **`ResourceName`**: Required only if using `"export"`.  
  - **`Name`**: Event/export name to update the player’s money display.

---

## 💻 Money HUD Settings

### `Config.MoneyHUD`
- **Type:** `table`
- **Default:**
  ```lua
  {
      Enable = true,
      showKey = 48
  }
  ```
- **Fields:**
  - **`Enable`**: Toggles Money HUD on/off.  
  - **`showKey`**: Key code (`48` = `Z`) for players to toggle the HUD visibility.
