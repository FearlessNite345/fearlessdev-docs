---
title: GetStreetName
sidebar_position: 12
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Returns the street name at the coords provided

:::
Use this export in your scripts.

### Parameters
- `x`: The x coordinate
- `y`: The y coordinate
- `z`: The z coordinate

### Returns
- The street name at those coords

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local streetName = exports['FS-Lib']:GetStreetName(0, 0, 0)
    print("Street Name: " .. streetName)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const streetName = exports['FS-Lib'].GetStreetName(0, 0, 0)
    console.log(`Street Name: ${streetName}`)
    ```
  </TabItem>
</Tabs>