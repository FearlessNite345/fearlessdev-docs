---
title: DrawText2D
sidebar_position: 9
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Draws 2D text at specified screen coordinates.

:::
Use this export in your scripts.

### Parameters
- `x`: X coordinate of the text on the screen (number).
- `y`: Y coordinate of the text on the screen (number).
- `text`: The text to display (string).
- `scale`: Scale of the text (number).
- `center`: Whether to center the text (boolean).

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    exports['FS-Lib']:DrawText2D(0.5, 0.8, "2D Text", 0.6, true)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    exports['FS-Lib'].DrawText2D(0.5, 0.8, "2D Text", 0.6, true)
    ```
  </TabItem>
</Tabs>