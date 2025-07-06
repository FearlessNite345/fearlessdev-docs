---
title: GetVehicleTypeInfo
sidebar_position: 12
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Returns classification details for a vehicle entity.

:::
Use this export in your scripts.

### Parameters

- `vehicle`: Vehicle entity ID to inspect (number).

### Returns

A table with fields:

- `class`: Vehicle class number.
- `seatCount`: Number of seats.
- `isBoat`: Whether the model is a boat.
- `isHeli`: Whether the model is a helicopter.
- `isPlane`: Whether the model is a plane.
- `isBike`: Whether the model is a bike.
- `isCar`: Whether the model is a car.
- `isQuadbike`: Whether the model is a quadbike.
- `isBicycle`: Whether the model is a bicycle.
- `isTrain`: Whether the model is a train.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    local info = exports['FS-Lib']:GetVehicleTypeInfo(vehicle)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    const info = exports['FS-Lib'].GetVehicleTypeInfo(vehicle);
    ```
  </TabItem>
</Tabs>
