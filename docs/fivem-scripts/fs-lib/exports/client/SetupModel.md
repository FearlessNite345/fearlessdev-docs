---
title: SetupModel
sidebar_position: 7
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::info
Loads and sets up a model for use in the game.

:::
### Parameters
- `model`: The model to load (number or string).

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    exports['FS-Lib']:SetupModel(123456)
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    exports['FS-Lib'].SetupModel(123456)
    ```
  </TabItem>
</Tabs>