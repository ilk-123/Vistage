# Vistage

Vistage is a standalone framework for Roblox that simplifies working with player data.
Documentation is in README module under Vistage.
Already used in some small games.

# Pros

  1. Working from the box, just edit the PlayerDataTemplate.
  2. Any changes in server player data instantly replicates to client.
  3. Simple API and syntax.
  4. Decent intellisense.
  5. Uses ProfileStore under hood (credits to @loleris).

# Install

 1. Get [Vistage](https://create.roblox.com/store/asset/72071157778621/Vistage) from the Roblox library or [Releases](https://github.com/ilk-123/Vistage/releases).
 2. Place Vistage under ReplicatedStorage.

# Basic Usage

```lua
--Server
local Vistage = require(game:GetService("ReplicatedStorage").Packages.Vistage)
local PlayerData = Vistage:GetPlayerData(Player) --works both on client and server
PlayerData.Cash += 5

--Client
local Vistage = require(game:GetService("ReplicatedStorage").Packages.Vistage)
local PlayerData = Vistage:GetClientData()
PlayerData.KeyChanged("Cash", function(ChangedData)
    print(`Cash changed: {ChangedData.OldValue} -> {ChangedData.NewValue}`)
end)
```
