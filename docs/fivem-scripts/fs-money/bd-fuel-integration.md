---
id: bdfuelintegration
sidebar_label: BigDaddy-Fuel Integration
sidebar_position: 1
---

# FS-Money Integration with BigDaddy-Fuel

This guide explains how to integrate **BigDaddy-Fuel** with your server using **FS-Money** as the money system. Once configured, fuel purchases will deduct funds from player bank balances managed by FS-Money.

---

## Step 1: Locate the `server.lua` File

Navigate to the **BigDaddy-Fuel** resource folder and open the `server.lua` file in your code editor.

---

## Step 2: Set the Framework to Custom

In `server.lua`, set the `framework` variable to `custom`. This instructs BigDaddy-Fuel to use FS-Money for all monetary operations.

```lua
framework = 'custom'     --VALUES CAN BE 'nat', 'qb', 'esx', 'nd', 'bigdaddy' or 'custom'
```

You may also configure the following parameters:  

```lua
reason = 'Fuel Purchase' --reason for the transaction will notify using framework methods

useSociety = false       -- Set to true if payments should go to a society account.
toSocietyaccount = ''    -- Name of the society account (if applicable).
local currencySymbol = '$' -- Symbol used in notifications.
```

---

## Step 3: Add FS-Money Integration Code

Copy and paste the following code into your `server.lua`, replacing or merging it with any existing framework logic. This integration handles both credit checks and payment processing using FS-Money’s API.

```lua
framework = 'custom'     --VALUES CAN BE 'nat', 'qb', 'esx', 'nd', 'bigdaddy' or 'custom'

reason = 'Fuel Purchase' --reason for the transaction will notify using framework methods

useSociety = false       -- Set to true if payments should go to a society account.
toSocietyaccount = ''    -- Name of the society account (if applicable).
local currencySymbol = '$' -- Symbol used in notifications.

if framework == 'nat' then
    print('Framework set to nat')
elseif framework == 'qb' then
    QBCore = exports['qb-core']:GetCoreObject()
elseif framework == 'esx' then
    ESX = exports["es_extended"]:getSharedObject()
elseif framework == 'nd' then
    NDCore = exports["ND_Core"]
elseif framework == 'bigdaddy' then
    print('Framework set to Big Daddy')
elseif framework == 'custom' then
    print('LOAD CORE OBJECT HERE IF REQUIRED, if not then you may disregard this statement.')
else
    print('FRAMEWORK IS NOT SET PROPERLY FOR RESOURCE! Check server.lua in ' ..
        GetCurrentResourceName() ..
        ' for money events. The current value is set to ' .. framework .. ', and this is not a valid selection.')
end

RegisterNetEvent('BigDaddy-Fuel:CreditCheck', function(playerId)
    local src = source
    if framework == 'nat' then
        local account = exports.money:getaccount(src)
        if (tonumber(account.bank) <= 75) then
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, false)
        else
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, true)
        end
    elseif framework == 'qb' then
        local Player = QBCore.Functions.GetPlayer(src)
        if (Player.Functions.GetMoney('bank') <= 75) then
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, false)
        else
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, true)
        end
    elseif framework == 'esx' then
        local xPlayer = ESX.GetPlayerFromId(src)
        local account = xPlayer.getAccount('bank')
        if (account.money <= 75) then
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, false)
        else
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, true)
        end
    elseif framework == 'nd' then
        local Player = NDCore:getPlayer(src)
        if (tonumber(Player.bank) <= 75) then
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, false)
        else
            TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, true)
        end
    elseif framework == 'bigdaddy' then
        local account = exports['BigDaddy-Money']:GetAccounts(src, playerId, -1)
        if account ~= "" then
            local data = json.decode(account)
            if (tonumber(data.bank) <= 75) then
                TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, false)
            else
                TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, true)
            end
        end
    elseif framework == 'custom' then
        local bank = exports['FS-Money']:getMoney('bank', src)
        if bank then
            if tonumber(bank) <= 75 then
                TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, false)
            else
                TriggerClientEvent('BigDaddy-Fuel:CreditCheckResult', src, true)
            end
        end
    else
        print('FRAMEWORK IS NOT SET PROPERLY FOR RESOURCE! Check server.lua in ' ..
            GetCurrentResourceName() ..
            ' for money events. The current value is set to ' .. framework .. ', and this is not a valid selection.')
    end
end)

RegisterNetEvent('BigDaddy-Fuel:Pay', function(amount, playerId)
    local src = source

    if framework == 'nat' then
        local account = exports.money:getaccount(src)
        local newbalance = tonumber(account.bank) - tonumber(amount)
        exports.money:updateaccount(src, { cash = account.amount, bank = newbalance })
        exports.money:bankNotify(src, reason .. ' ' .. currencySymbol .. amount)
    elseif framework == 'qb' then
        local Player = QBCore.Functions.GetPlayer(src)
        Player.Functions.RemoveMoney('bank', tonumber(amount), reason)
        if (useSociety) then
            exports['qb-management']:AddMoney(toSocietyaccount, tonumber(amount))
        end
        TriggerClientEvent('QBCore:Notify', src, reason, 'primary', 5000)
    elseif framework == 'esx' then
        local xPlayer = ESX.GetPlayerFromId(src)
        xPlayer.removeAccountMoney('bank', tonumber(amount))
        xPlayer.showNotification(reason)
    elseif framework == 'nd' then
        local Player = NDCore:getPlayer(src)
        Player.DeductMoney('bank', amount, reason)
    elseif framework == 'bigdaddy' then
        local account = exports["BigDaddy-Money"]:GetAccounts(src, playerId)
        if account ~= "" then
            local data = json.decode(account)
            local newbalance = tonumber(data.bank) - tonumber(amount)
            exports['BigDaddy-Money']:UpdateTotals(src, newbalance, data.cash, data.dirty, -1)
            TriggerClientEvent("BigDaddy-Money:Notify", src,
                'Paid ' .. currencySymbol .. string.format("%.2f", amount) .. ' ' .. reason)
        end
    elseif framework == 'custom' then
        exports['FS-Money']:removeMoney('bank', src, amount, reason)
    else
        print('FRAMEWORK IS NOT SET PROPERLY FOR RESOURCE! Check server.lua in ' ..
            GetCurrentResourceName() ..
            ' for money events. The current value is set to ' .. framework .. ', and this is not a valid selection.')
    end
end)
```

---

## Step 4: Save and Restart

1. Save the changes to `server.lua`.  
2. Restart the **BigDaddy-Fuel** resource.  
3. Ensure **FS-Money** is started before BigDaddy-Fuel on your server.  

At this point, FS-Money is fully integrated, and players can use their FS-Money bank accounts for fuel purchases.
