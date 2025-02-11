---
sidebar_position: 13
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Sends a toast notification to the player

:::warning
This export is not available yet. It will be released in version 1.5.0. Please stay tuned for updates.
:::

### Parameters
- `title`: The title you want to show to the player
- `message`: The message you want to show to the player
- `duration`: The duration you want the message to be shown for in seconds

### Optional Parameters:
- `type`: The type can be either 'info' or 'success' or 'error' or 'warn' anything else provided will just default to the info type

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    exports['FS-Lib']:Notify('This is a test title', 'This is a test message', 5, 'police')
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    exports['FS-Lib'].Notify('This is a test title', 'This is a test message', 5, 'police')
    ```
  </TabItem>
</Tabs>