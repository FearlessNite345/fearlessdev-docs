---
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

### `addMoney`

Adds money to a player's balance.

### Parameters

- `moneyType` - The type of money to add to (`'cash'`, `'bank'`, `'dirty'`).
- `source` - The player's server ID.
- `amount` - The amount to add.
- `reason` (optional)` - A reason to show in the player's notification.

### Returns

Returns `true` if successful.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>

```lua
exports['FS-Lib']:addMoney('cash', source, 100, 'Job Payout')
```

  </TabItem>
  <TabItem value="js" label="Javascript">

```js
exports['FS-Lib'].addMoney('cash', source, 100, 'Job Payout')
```

  </TabItem>
</Tabs>
