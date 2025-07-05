---
title: setMoney
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

### `setMoney`

:::info
Sets the player's balance for the specified money type.

:::
### Parameters

- `moneyType` - The type of money to set (`'cash'`, `'bank'`, `'dirty'`, `'pokerchips'`).
- `source` - The player's server ID.
- `amount` - The new balance to assign.

### Returns

Returns `true` if the update was successful, otherwise `false`.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>

```lua
exports['FS-Money']:setMoney('bank', source, 1500)
```

  </TabItem>
  <TabItem value="js" label="Javascript">

```js
exports['FS-Money'].setMoney('bank', source, 1500)
```

  </TabItem>
</Tabs>
