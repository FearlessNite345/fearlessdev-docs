---
title: GetKeyString
sidebar_position: 2
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Retrieves the name of the key corresponding to the provided key ID. This function returns the key name based on the current input device (keyboard or controller).

:::
### Parameters
- `keyID`: The ID of the key. For a list of key IDs, refer to the [FiveM Documentation](https://docs.fivem.net/docs/game-references/controls/).

### Returns
- `string`: The string will be the KEY name.

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local keyName = exports['FS-Lib']:GetKeyString(38)
    print("Key Name: " .. keyName)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const keyName = exports['FS-Lib'].GetKeyString(38)
    console.log(`Key Name: ${keyName}`)
    ```
  </TabItem>
</Tabs>