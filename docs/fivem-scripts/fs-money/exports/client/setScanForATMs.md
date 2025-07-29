---
title: setScanForATMs
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

### `setScanForATMs`

:::info
Enables or disables ATM scanning for a player. This controls whether ATM interaction prompts (such as text UI) are shown.  
Primarily used in conjunction with scripts like `FS-Robberies`.
:::

Use this export in your scripts to toggle ATM scanning functionality.

### Parameters

- `CanScan` _(boolean)_ – Whether the script should allow ATM interactions (e.g., show prompts and enable usage).
  - `true`: Enables scanning for nearby ATMs.
  - `false`: Disables scanning and hides interaction prompts.

### Returns

This function does not return a value.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>

```lua
exports['FS-Money']:setScanForATMs(true)
```

  </TabItem>
  <TabItem value="js" label="Javascript">

```js
exports["FS-Money"].setScanForATMs(true);
```

  </TabItem>
</Tabs>
