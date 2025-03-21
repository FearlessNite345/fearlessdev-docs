---
sidebar_position: 1
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Checks latest github release version vs the current resource version

### Parameters
- `resourceName`: The name of the resource for printing purposes
- `githubRepo`: This is the actual repo to check must be in `'username/repo'` format

### Usage
<Tabs>
  <TabItem value="lua" label="Lua" default>
    ```lua
    exports['FS-Lib']:VersionCheck('FS-Lib', 'fearlessnite345/fs-lib')
    ```
  </TabItem>
  <TabItem value="js" label="Javascript">
    ```js
    exports['FS-Lib'].VersionCheck('FS-Lib', 'fearlessnite345/fs-lib')
    ```
  </TabItem>
</Tabs>