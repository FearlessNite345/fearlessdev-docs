---
title: getMoney
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

### `getMoney`

:::info
Retrieves the current balance for a given player and money type.

:::
Use this export in your scripts.

### Parameters

- `moneyType` - The type of money to retrieve (`'cash'`, `'bank'`, `'dirty'`, `'pokerchips'`).

### Returns

Returns the player's current cached balance as a number.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>

```lua
exports['FS-Money']:getMoney('cash')
```

  </TabItem>
  <TabItem value="js" label="Javascript">

```js
exports["FS-Money"].getMoney("cash");
```

  </TabItem>
</Tabs>
