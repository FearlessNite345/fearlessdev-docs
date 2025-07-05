---
title: HeadingToCardinal
sidebar_position: 10
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Converts a heading value to a cardinal direction.

:::
### Parameters
- `heading`: The heading angle (number).

### Returns
- The cardinal direction as a string (string).

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local direction = exports['FS-Lib']:HeadingToCardinal(45)
    print("Cardinal Direction: " .. direction)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const direction = exports['FS-Lib'].HeadingToCardinal(45)
    console.log(`Cardinal Direction: ${direction}`)
    ```
  </TabItem>
</Tabs>