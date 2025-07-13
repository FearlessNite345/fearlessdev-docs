---

id: configure
title: Configuring FS-NowOpen
sidebar\_label: Configuration
description: How to set up and configure the FS-NowOpen business directory system
---------------------------------------------------------------------------------

## 🚀 Quick Start

1. Place `fs-nowopen` in your `resources` folder.
2. Edit `config.lua` to customize permissions, phone integration, and database options.
3. Restart the script to enable the business directory.

## ⚙️ Basic Setup

To configure `FS-NowOpen`, open the `config.lua` file inside the resource folder. Below is an example configuration with explanations for each option:

```lua
Config = {}

-- If true, players need `Config.acePerm` to open a business. Does NOT affect admin permissions.
Config.useAcePerms = false

-- Permission required to open a business (only when `useAcePerms` is true).
Config.acePerm = 'nowopen.use'

-- Always required for admin actions like deleting businesses not owned by the player.
-- This is checked regardless of `useAcePerms`.
Config.adminAcePermission = 'fs_nowopen.admin'

-- LB Phone Integration Settings
Config.LB_Phone = {
    -- Enable LB Phone integration
    Enable = false,

    -- Notification options (only effective if Enable = true)
    useNotifications = true,
    sendOpenNotifications = true,
    sendCloseNotifications = true,
}

-- Default Notification options (if not using LB Phone notifications)
Config.useDefaultNotifications = true

-- What happens when a player leaves the server:
-- Options:
-- 'delete' = Remove the business entirely
-- 'close'  = Mark the business as closed but keep it in the directory
-- 'none'   = Do nothing; leave the business state unchanged
Config.onLeaveAction = 'delete'

-- Database Persistence --
-- When enabled, open businesses will be saved to a database and restored on resource start.
-- Uses `oxmysql` and the `fs_nowopen_businesses` table.
-- ⚠️ Note: Persistence only applies if Config.onLeaveAction is set to 'close' or 'none'.
-- If onLeaveAction is 'delete', businesses will still be removed on player leave, even if persistence is enabled.
Config.useDatabase = false

-- Enable debug logging on server and client
Config.debug = false
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
Config.LB_Phone.Enable = true
Config.LB_Phone.useNotifications = true
Config.LB_Phone.sendOpenNotifications = true
Config.LB_Phone.sendCloseNotifications = true
```

Players will be able to:

* Call businesses directly from the directory
* Receive notifications when businesses open or close

Make sure LB Phone is properly installed and running for this integration to work.

---

## 🧼 Auto-Cleanup

To configure what happens when players leave or crash, set `Config.onLeaveAction`:

* `delete`: Completely removes the business
* `close`: Marks the business as closed, keeping it in the directory
* `none`: Leaves the business state as-is

```lua
Config.onLeaveAction = 'delete'
```

If you want businesses to persist across server restarts, enable database persistence:

```lua
Config.useDatabase = true
```

---

## 🛠️ Debugging

Enable debug logs on both client and server:

```lua
Config.debug = true
```

This can help during development or troubleshooting.
