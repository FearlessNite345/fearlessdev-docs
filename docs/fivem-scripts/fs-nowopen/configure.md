---
id: configure
title: Configuring FS-NowOpen
sidebar_label: Configuration
description: How to set up and configure the FS-NowOpen business directory system
---

:::tip
Display which businesses are open and manage listings with simple commands.
:::

## ⚙️ Basic Setup

To configure `FS-NowOpen`, open the `config.lua` file inside the resource folder. Below is an example configuration with explanations for each option:

```lua
Config = {}

Config.useAcePerms = false
-- If true, players must have the ACE permission defined in `Config.acePerm` to open a business.
-- This does *not* affect admin permissions.

Config.acePerm = 'nowopen.use'
-- The ACE permission required to open a business (only used if `useAcePerms` is true).

Config.adminAcePermission = 'fs_nowopen.admin'
-- This permission is *always* required for admin-level actions like deleting other players’ businesses.
-- This is checked regardless of the `useAcePerms` setting.

Config.useLBPhone = false
-- Enable this if you're using LB Phone. It allows players to call businesses and receive open/close alerts.

-- These apply only if `Config.useLBPhone` is true:
Config.useLBPhoneNotifications = true
-- Enables business open/close notifications via LB Phone.

Config.sendLBPhoneOpenNotifications = true
-- Send an LB Phone alert to all users when a business is opened.

Config.sendLBPhoneCloseNotifications = true
-- Send an LB Phone alert when a business is closed.

Config.useDefaultNotifications = true
-- Enables built-in fallback notifications if LB Phone is not in use.

Config.deleteBusinessOnLeave = true
-- Automatically removes a player's business when they disconnect or crash.
```

---

## 🔐 ACE Permissions

To restrict business creation:

1. Set `Config.useAcePerms = true`
2. Set the required permission name via `Config.acePerm`
3. Add the permission in your `server.cfg`:

```
add_ace group.admin nowopen.use allow
```

For admin privileges (required regardless of the above):

```
add_ace group.admin fs_nowopen.admin allow
```

> Tip: You can replace `group.admin` with a specific identifier or group based on your server's permission setup.

---

## 📱 LB Phone Integration

If you're using [LB Phone](https://store.lbscripts.com/package/5356987), you can enable direct business calls and alerts:

```lua
Config.useLBPhone = true
Config.useLBPhoneNotifications = true
Config.sendLBPhoneOpenNotifications = true
Config.sendLBPhoneCloseNotifications = true
```

Players will be able to:
- Call businesses directly from the directory
- Receive notifications when businesses open or close

Make sure LB Phone is properly installed and running for this integration to work.

---

## 🧼 Auto-Cleanup

To automatically clean up businesses for players who leave or crash:

```lua
Config.deleteBusinessOnLeave = true
```

This helps prevent outdated or inactive businesses from cluttering your server’s directory.

---
