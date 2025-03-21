# GRM Economy Gamemode Documentation

**For further assistance, updates or support visit our [**Discord Server**](https://discord.gg/bsepA3pmQP).**

---

## ESX Compatibility Overview

This gamemode supports various ESX scripts, with different levels of functionality:

- **Fully Functional:**
  - `esx_status`
  - `esx_vehicleshop`
- **Partially Functional:**
  - `esx_addonaccount`

---

## Vehicle Key Management

Manage vehicle keys dynamically within the game.

```lua
-- Generate keys for a vehicle
exports['cfx-grm_economy-core']:generateVehicleKeys(entity)

-- Remove keys from a vehicle
exports['cfx-grm_economy-core']:removeVehicleKeys(entity)
```

---

## Payment Processing

Handle in-game transactions securely.

```lua
-- Process a payment
local success = exports['cfx-grm_economy-core']:payment(price, product)
if success then
    print("Payment successful!")
else
    print("Payment failed.")
end
```

---

## Logging System

Log important in-game events efficiently.

```lua
exports['cfx-grm_economy-core']:log({
    channel = "server-logs", -- Define log channel
    webhook = nil, -- Optional: Direct webhook URL
    header = "Event Log", -- Log title
    username = "GRM Logger", -- Log sender name
    color = 16711680, -- Log color (red in decimal)
    content = "A player performed an action.", -- Log message
    player = 1 -- (Optional) Attach player details
})
```

---

## Marker System

Create and manage interactive markers in the game world.

```lua
-- Remove an existing marker
exports['cfx-grm_economy-core']:removeMarker(markerID)

-- Register a new marker
local markerData = exports['cfx-grm_economy-core']:registerMarker({
    id = "unique_marker_1", -- Unique marker ID
    coords = vector3(100.0, 200.0, 300.0),
    onPress = function()
        print("Pressed!")
    end,
    nearby = function()
        return true -- Show marker only when this function returns true
    end,
    msg = "Join House", -- UI text
    icon = "house", -- UI icon
    marker = "fastfood" -- Marker texture
})
```
