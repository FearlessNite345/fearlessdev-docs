---
title: GetClosestVehicle
sidebar_position: 5
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Finds the closest vehicle within a specified distance from the player's current location.

:::
Use this export in your scripts.

### Parameters
- `maxDistance`: The maximum distance within which to search for pedestrians (number).

### Returns
- `closestVeh`: The vehicle it found
- `closestDist`: The distance to that vehicle
- `closestCoords`: The coords of the vehicle

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local closestVeh, closestDist, closestCoords = exports['FS-Lib']:GetClosestVehicle(10.0)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const [closestPed, closestDist, closestCoords] = exports['FS-Lib'].GetClosestVehicle(10.0)
    ```
  </TabItem>
</Tabs>