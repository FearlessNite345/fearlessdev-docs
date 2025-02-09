---
sidebar_position: 4
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Finds the closest pedestrian (NPC or player) within a specified distance from the player's current location.

### Parameters
- `maxDistance`: The maximum distance within which to search for pedestrians (number).
- `searchType`: Type of pedestrian to search for. Use "players" to find players or "npcs" to find NPCs or "both" to find both (string).

### Returns
- `closestPed`: The ped it found
- `closestDist`: The distance to that ped
- `closestCoords`: The coords of the ped

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local closestPed, closestDist, closestCoords = exports['FS-Lib']:GetClosestPed(10.0, "players")
    ```
  </TabItem>
  <TabItem value="js" label="JS">
    ```js
    const [closestPed, closestDist, closestCoords] = exports['FS-Lib'].GetClosestPed(10.0, "players")
    ```
  </TabItem>
</Tabs>