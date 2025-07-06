---
id: configure
title: Configuring FS-NameSync
sidebar_label: Configuration
description: How to configure FS-NameSync
---

# Configuration Guide

:::tip
Enforce consistent player names and optional Discord synchronization.
:::

This guide explains how to configure **FS-NameSync**, a resource that ensures players' Discord names match their FiveM names and verifies that their FiveM names follow a specific regex pattern.

## 🚀 Quick Start

1. Place `fs-namesync` in your `resources` folder.
2. Adjust the settings in `config.json` to suit your naming rules.
3. Restart the resource for changes to take effect.

:::info
**FS-NameSync** helps maintain consistency across your server by synchronizing player names with Discord and enforcing naming standards through regex validation.
:::

### ⚙️ Configuring FS-NameSync
The configuration is managed via the `config.json` file. Here’s the basic structure:

```json
{
    "regexPattern": "\\d{3} \\| ((\\w\\. \\w+)|(\\w+ \\w\\.)|(Mr\\. \\w+)|(Ms\\. \\w+))",
    "invalidMessage": "Invalid PlayerName format.",
    "notMatchDiscord": "Your PlayerName does not match your discord nickname",
    "enforceDiscordNameSync": true
}
```

#### Configuration Options:
- **`regexPattern`**: Defines the regex pattern that FiveM names must match.  
  - Example Pattern: `\d{3} \| ((\w\. \w+)|(\w+ \w\.)|(Mr\. \w+)|(Ms\. \w+))`
  - This allows formats like:
    - `123 | J. Doe`
    - `456 | John D.`
    - `789 | Mr. Smith`
    - `321 | Ms. Taylor`
  - Customize the pattern to fit your server's roleplay or naming requirements.
:::warning  
When defining regex patterns in `.json`, use double backslashes (`\\`) instead of a single backslash. For example: `\\d{3}`.  
:::

- **`invalidMessage`**: Message displayed when a player’s name doesn’t match the regex pattern.

- **`notMatchDiscord`**: Message shown when a player’s FiveM name doesn’t match their Discord nickname.

- **`enforceDiscordNameSync`**:  
  - `true`: Enforces that the player’s FiveM name matches their Discord nickname.  
  - `false`: Disables Discord name synchronization, allowing independent names.

### 🔗 Setting Up Discord Integration
To synchronize names with Discord, ensure the following:

1. **Badger_Discord_API** is installed and properly configured.
2. The bot has permissions to read member nicknames.

No additional Discord setup is required beyond ensuring `Badger_Discord_API` functions correctly.

### ❗ Troubleshooting
- **"Invalid PlayerName format."**  
  - Your in-game name doesn’t match the required pattern. Review the regex and adjust your name accordingly.

- **"Your PlayerName does not match your discord nickname."**  
  - Ensure your Discord nickname matches your in-game name exactly when `enforceDiscordNameSync` is enabled.

- **"Could not fetch your Discord name. Please ensure Discord is open."**  
  - Check if Discord is running, and make sure you’re connected to the server with the correct permissions.

- **Unexpected Errors**  
  - Review your server console logs for errors.  
  - Ensure `Badger_Discord_API` is functional, and the `FS-NameSync` resource is up-to-date.