---
title: GetClosestTrailerToHitch
sidebar_position: 6
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Finds the closest trailer within a specified distance from the vehicle's hitch location.

:::
Use this export in your scripts.

### Parameters
- `maxDistance`: The maximum distance within which to search for trailers (number).

### Returns
- `closestTrailer`: The trailer it found

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local closestTrailer = exports['FS-Lib']:GetClosestTrailerToHitch(1.2)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const closestTrailer = exports['FS-Lib'].GetClosestTrailerToHitch(1.2)
    ```
  </TabItem>
</Tabs>