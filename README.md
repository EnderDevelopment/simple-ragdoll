# Simple Ragdoll Script for Roblox

This script creates a basic ragdoll effect when a player's character dies. The script is placed in the ServerScriptService.

## Install

1. Open Roblox Studio.
2. Create a new script in the ServerScriptService.
3. Copy and paste the following code into the script:

```lua
-- Simple Ragdoll Script for Roblox

local Players = game:GetService("Players")

local function onCharacterAdded(character)
    local humanoid = character:WaitForChild("Humanoid")
    local rootPart = character:WaitForChild("HumanoidRootPart")

    humanoid.Died:Connect(function()
        humanoid:ChangeState(Enum.HumanoidStateType.Dead)

        for _, part in ipairs(character:GetDescendants()) do
            if part:IsA("BasePart") then
                part.Anchored = false
                part.CanCollide = true
            end
        end
    end)
end

Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(onCharacterAdded)
end)

-- End of Ragdoll Script
```

## Use

1. Save the script in the ServerScriptService.
2. Play the game in Roblox Studio or publish it to Roblox.
3. When a player's character dies, the script will create a basic ragdoll effect.

---

More Roblox script projects by EnderDevelopment: https://github.com/EnderDevelopment

Project page: https://dash.enderdevelopment.com/community/1ff4b228-d792-4e5c-be2f-47d5989df87b?utm_source=github&utm_medium=readme&utm_campaign=auto_publish&utm_content=1ff4b228-d792-4e5c-be2f-47d5989df87b
