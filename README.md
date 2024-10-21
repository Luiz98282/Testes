local scriptUrl = "https://raw.githubusercontent.com/antonioluiz679/SeuScript/main/blox_fruits.lua"
local script = game:HttpGet(scriptUrl)
loadstring(script)()

local function zeusHubScript()
    print("Iniciando ZeusHub...")

    while true do
        local player = game.Players.LocalPlayer
        local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
        
        if humanoid then
            local closestEnemy = nil
            local closestDistance = math.huge
            
            for _, enemy in ipairs(workspace:GetChildren()) do
                if enemy:IsA("Model") and enemy:FindFirstChild("Humanoid") then
                    local distance = (enemy.HumanoidRootPart.Position - player.Character.HumanoidRootPart.Position).Magnitude
                    
                    if distance < 50 then
                        humanoid:MoveTo(enemy.HumanoidRootPart.Position)
                        wait(0.5)
                        player.Character:FindFirstChildOfClass("Tool"):Activate()
                    end
                end
            end
        end
        
        wait(1)
    end
end

zeusHubScript()# Testes
