# Dissolve Effect
API for achieving a Dissolve Effect on Instances that have BasePart's as children.

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

### Setup

Somewhere in studio, like ReplicatedStorage or ServerStorage, have `Dissolvify` be the main Module and `Partify` and `Utility` are the children of the main file.

![](https://i.gyazo.com/4b0233129580488ecd22675e5b1dcd24.png)

Then all that's left is to require `Dissolvify` and call `dissolve` and passing in any Instance that has children of BasePart type.

#### NOTE: Inside of `Utility` there's a `DefaultSize` property for the default size of the parts that are being generated, feel free to change the size.
