---
title: DrawText3D
sidebar_position: 8
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Draws 3D text at specified world coordinates.

:::
### Parameters
- `x`: X coordinate of the text (number).
- `y`: Y coordinate of the text (number).
- `z`: Z coordinate of the text (number).
- `scale`: Scale of the text (number).
- `text`: The text to display (string).

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    exports['FS-Lib']:DrawText3D(100.0, 200.0, 300.0, 0.6, "3D Text")
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    exports['FS-Lib'].DrawText3D(100.0, 200.0, 300.0, 0.6, "3D Text")
    ```
  </TabItem>
</Tabs>