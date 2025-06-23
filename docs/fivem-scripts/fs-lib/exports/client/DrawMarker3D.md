---
sidebar_position: 13
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Wrapper around `DrawMarker` for simple 3D markers.

### Parameters

- `markerType`: Marker ID; defaults to 1 if not provided (number, optional).
- `x`: X world coordinate (number).
- `y`: Y world coordinate (number).
- `z`: Z world coordinate (number).
- `sx`: Marker scale on the X axis (number, optional).
- `sy`: Marker scale on the Y axis (number, optional).
- `sz`: Marker scale on the Z axis (number, optional).
- `r`: Red color value (0-255, optional).
- `g`: Green color value (0-255, optional).
- `b`: Blue color value (0-255, optional).
- `a`: Alpha value (0-255, optional).

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    exports['FS-Lib']:DrawMarker3D(1, 0.0, 0.0, 72.0, 1.0, 1.0, 1.0, 255, 0, 0, 200)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    exports['FS-Lib'].DrawMarker3D(1, 0.0, 0.0, 72.0, 1.0, 1.0, 1.0, 255, 0, 0, 200);
    ```
  </TabItem>
</Tabs>
