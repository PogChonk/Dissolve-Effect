# Dissolve Effect
API for achieving a Dissolve Effect on Characters or any Model.

Simply store the Modules in some location, I generally do it in ReplicatedStorage since you can do this Client-sided and Server-sided.
#

##### In both of these examples, the modules are stored inside of `ReplicatedStorage`.


Example from the Server

```lua
--// ServerScript in ServerScriptService

local dissolvify = require(game:GetService("ReplicatedStorage").Dissolvify)

game:GetService("Players").PlayerAdded:Connect(function(player)
	player.Chatted:Connect(function(msg)
		if msg:lower() == "dissolve" then
			if player.Character then
				dissolvify.dissolve(player.Character)
			end
		end
	end)
end)
```
#

Example from the Client

```lua
--// LocalScript in StarterCharacterScripts

local dissolvify = require(game:GetService("ReplicatedStorage").Dissolvify)

wait(5)
dissolvify.dissolve(script.Parent)
```
#
