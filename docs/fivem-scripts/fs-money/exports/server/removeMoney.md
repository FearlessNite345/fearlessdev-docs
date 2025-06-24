---
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

### `removeMoney`

Removes money from a player's balance.

### Parameters

- `moneyType` - The type of money to deduct from (`'cash'`, `'bank'`, `'dirty'`, `'pokerchips'`).
- `source` - The player's server ID.
- `amount` - The amount to remove.
- `reason` (optional)` - A reason to show in the player's notification.

### Returns

Returns `true` if the deduction succeeded, otherwise `false`.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>

```lua
exports['FS-Money']:removeMoney('bank', source, 250, 'Purchase')
```

  </TabItem>
  <TabItem value="js" label="Javascript">

```js
exports['FS-Money'].removeMoney('bank', source, 250, 'Purchase')
```

  </TabItem>
</Tabs>
