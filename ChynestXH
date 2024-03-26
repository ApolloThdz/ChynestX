local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "ChynestX", HidePremium = false, Premium = true, SaveConfig = true, ConfigFolder = "OrionTest", IntroEnabled = true})
local Tab = Window:MakeTab({
    Name = "AutoFarming",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})
local Tab2 = Window:MakeTab({
    Name = "Status",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

local isScriptActive = false
local CombatFramework = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
local Camera = require(game:GetService("ReplicatedStorage").Util.CameraShaker)
local stepConnection

local function activateScript()
    if not isScriptActive then
        isScriptActive = true
        Camera:Stop()
        stepConnection = game:GetService("RunService").Stepped:Connect(function()
            if getupvalues(CombatFramework)[2]['activeController'].timeToNextAttack then
                getupvalues(CombatFramework)[2]['activeController'].timeToNextAttack = 0
                getupvalues(CombatFramework)[2]['activeController'].hitboxMagnitude = 50
                getupvalues(CombatFramework)[2]['activeController']:attack()
            end
        end)
    end
end

local function deactivateScript()
    if isScriptActive then
        isScriptActive = false
        Camera:Stop()
        if stepConnection then
            stepConnection:Disconnect()
        end
    end
end

local function AutoMelee()
    spawn(function()
        while true do
            if Mad then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Melee", SelectPoint)
            end
            wait(0.1)
        end
    end)
end

local AutoMeleeEnabled = false

Tab2:AddToggle({
    Name = "Auto Melee",
    Default = false,
    Callback = function(Value)
        AutoMeleeEnabled = Value
        if AutoMeleeEnabled then
            AutoMelee()
        end
    end
})

Tab:AddToggle({
    Name = "Fast Attack",
    Default = false,
    Callback = function(Value)
        if Value then
            activateScript()
        else
            deactivateScript()
        end
    end
})
  
Tab:AddToggle({
    Name = "Auto Farming",
    Default = false,
    Callback = function()
        -- Aqui você pode adicionar a lógica para a função Auto Farming
    end
})

Tab:AddButton({
    Name = "Reedem Codes",
    Callback = function()
        local function UseCode(Text)
            game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
        end
        
        UseCode("BIGNEWS")
        UseCode("THEGREATACE")
        UseCode("StrawHatMaine")
        UseCode("Sub2OfficialNoobie")
        UseCode("SUB2NOOBMASTER123")
        UseCode("Sub2Daigrock")
        UseCode("Axiore")
        UseCode("TantaiGaming")
        UseCode("STRAWHATMAINE") 
        UseCode("24NOADMIN")
        UseCode("JCWK")
        UseCode("MagicBus")
        UseCode("Sub2Fer999")
        UseCode("kittgaming")
        UseCode("REWARDFUN")
        UseCode("StarcodeHEO")
        UseCode("Bluxxy")
        UseCode("KITT_RESET")
        UseCode("SUB2GAMERROBOT_RESET1")
    end
})

Tab:AddButton({
    Name = "Refund Stats [2500 F]",
    Callback = function()
      game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
      game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
  end
})

Tab:AddButton({
    Name = "Reroll Race [3000 F]",
    Callback = function()
      game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","1")
      game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","2")
  end
})
