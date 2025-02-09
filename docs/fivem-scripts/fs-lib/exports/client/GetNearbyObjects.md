---
sidebar_position: 7
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Finds the objects within a specified distance from the player's current location.

### Parameters
- `maxDistance`: The maximum distance within which to search for the model (number).

### Returns
- A table of all objects

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local objects = exports['FS-Lib']:GetNearbyObjects(10.0)

    for _, data in ipairs(objects) do
        print(data.object)
        print(data.objCoords)
        print(data.dist)
    end
    ```
  </TabItem>
</Tabs>