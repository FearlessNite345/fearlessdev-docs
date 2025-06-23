---
sidebar_position: 15
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Checks if a target entity is within a specified distance.

### Parameters

- `targetEntity`: The entity to check against (number).
- `maxDistance`: Maximum distance in game units (number).
- `fromEntity`: Entity to measure from; defaults to the player's ped (number, optional).

### Returns

- `boolean`: Whether the distance is within the limit.
- `number`: The actual distance between entities.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local withinRange, distance = exports['FS-Lib']:IsEntityWithinDistance(targetEntity, 5.0)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const [withinRange, distance] = exports['FS-Lib'].IsEntityWithinDistance(targetEntity, 5.0);
    ```
  </TabItem>
</Tabs>
