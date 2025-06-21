# Configuration Guide

This guide explains how to configure **FS-LBPhoneNumAssigner**, a resource that sets the player's phone number to a custom number based on their member number for LB Phone.

:::info
**FS-LBPhoneNumAssigner** helps streamline player identification by assigning unique phone numbers based on their in-game member numbers.
:::

### ⚙️ Configuring FS-LBPhoneNumAssigner
The configuration is controlled via the `config.json`. Here's the basic configuration structure:

```json
{
    "lbphoneNumberFormat": "221555{membernumber}"
}
```

- **`lbphoneNumberFormat`**: Defines the phone number format.
  - Use `{membernumber}` as a placeholder for the player's member number. Example 001 | Fearless
  - Example: `221555{membernumber}` will result in phone numbers like `2215550001`, `2215550002`, etc.

:::tip
Choose a format that fits your community's needs. Consistency ensures better recognition and fewer conflicts.
:::

### 📲 Configuring LB-Phone for Compatibility
To ensure **LB-Phone** supports the custom number format, update its configuration as follows:

1. Navigate to `lb-phone -> config -> config.lua`.
2. Adjust the phone number settings:

```lua
Config.PhoneNumber = {}
Config.PhoneNumber.Format = "({3}) {3}-{4}"
Config.PhoneNumber.Length = 7
Config.PhoneNumber.Prefixes = {}
```

- **`Format`**: Controls the phone number's display format. Only modify if you're familiar with the formatting rules.
- **`Length`**: Set to match the phone number length without the prefix. For the example `2215550001`, the length is `7`.

:::warning
**DO NOT** modify the `Prefixes` section. It must remain empty for FS-LBPhoneNumAssigner to function properly.
:::

### ❗ Troubleshooting
- **"Your name must start with a number."**: Ensure your in-game name starts with a numerical prefix.
- **"Failed to fetch your license."**: Reconnect to the server; if the issue persists, contact support.
- **Database Errors**: Check your MySQL database connection and ensure the `phone_phones` table exists.