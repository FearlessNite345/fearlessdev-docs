---
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

### `transferMoney`

Transfers money from one player to another.

### Parameters

- `moneyType` - The type of money to transfer (`'cash'`, `'bank'`, `'dirty'`, `'pokerchips'`).
- `fromSrc` - The sender's player ID.
- `toSrc` - The receiver's player ID.
- `amount` - The amount to transfer.

### Returns

Returns `true` if the transfer was successful, otherwise `false`.

### Usage

<Tabs>
  <TabItem value="lua" label="Lua" default>

```lua
exports['FS-Money']:transferMoney('cash', source, target, 50)
```

  </TabItem>
  <TabItem value="js" label="Javascript">

```js
exports['FS-Money'].transferMoney('cash', source, target, 50)
```

  </TabItem>
</Tabs>
