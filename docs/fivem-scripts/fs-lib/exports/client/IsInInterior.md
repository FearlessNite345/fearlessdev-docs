---
title: IsInInterior
sidebar_position: 11
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Returns true or false if the current player is in a interior

:::
### Returns
- `boolean`

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local isInInterior = exports['FS-Lib']:IsInInterior()
    print(tostring(isInInterior))
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const isInInterior = exports['FS-Lib'].IsInInterior()
    console.log(tostring(isInInterior))
    ```
  </TabItem>
</Tabs>