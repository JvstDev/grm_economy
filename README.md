
## ESX Provieders
Grm Economy gamemode provide a backward for the old esx scripts:
- esx_staus
- esx_addonaccount
- esx_vehicleshop

----

## Vehicle keys system:
```lua
---@return void
exports['cfx-grm_economy-core']:generateVehicleKeys(entity: string|number)

---@return void
exports['cfx-grm_economy-core']:removeVehicleKeys(entity: string|number) 
```

## Payments system:
```lua
---@return boolean
exports['cfx-grm_economy-core']:payment(price: number, product: string) 
```

## Logs system:
```lua
---@return void
exports['cfx-grm_economy-core']:log({
    channel: string, -- channel name (grm_core.cfg/grm:logs)
    webhook: string|nil, -- use direct webhook or predefined channels
    header: string, -- embed header
    username: string, -- sender name
    color: number, -- embed color (decimal)
    content: string, -- embed content
    player: number -- (optional) player source, show all player stats
})
```

## Payments system:
```lua
---@return boolean
exports['cfx-grm_economy-core']:payment(price: number, product: string) 
```

## Markers system:
```lua
---@return void
exports['cfx-grm_economy-core']:removeMarker(id: string|number)

---@return table
exports['cfx-grm_economy-core']:registerMarker({
    id: string|number, -- need to be unique
    coords: vector3,
    onPress: function() -- on press [E] callback
    
    end,
    nearby: function() -- if return true inside the function and other will be displayed, else no

    end,
    msg: string, -- textui
    icon: string, -- textui icon
    marker: string, -- marker texture (markers.ytd)
})
```
