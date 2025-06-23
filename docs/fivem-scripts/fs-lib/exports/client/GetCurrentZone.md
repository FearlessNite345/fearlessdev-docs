---
sidebar_position: 14
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Returns the zone name for the player's current location.

### Parameters

This export takes no parameters.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local zoneName = exports['FS-Lib']:GetCurrentZone()
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const zoneName = exports['FS-Lib'].GetCurrentZone();
    ```
  </TabItem>
</Tabs>
