---
sidebar_position: 2
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Finds the closest object within a specified distance from the player's current location.

### Parameters
- `maxDistance`: The maximum distance within which to search for the model (number).

### Returns
- `closestObj`: The object it found
- `closestDist`: The distance to that object
- `closestCoords`: The coords of the object

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local closestPed, closestDist, closestCoords = exports['FS-Lib']:GetClosestObject(10.0)
    ```
  </TabItem>
  <TabItem value="js" label="JS">
    ```js
    const [closestPed, closestDist, closestCoords] = exports['FS-Lib'].GetClosestObject(10.0)
    ```
  </TabItem>
</Tabs>