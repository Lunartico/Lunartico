local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

local Window = OrionLib:MakeWindow({
    Name = "[NEW] KITSUNE HUB | HADES RNG", 
    HidePremium = false, 
    SaveConfig = true, 
    ConfigFolder = "OrionTest", 
    IntroEnabled = true, 
    IntroText = "Kitsune Hub...",
    IntroIcon = "rbxassetid://4483345998", 
    CloseCallback = function() end
  })

    local Tab = Window:MakeTab({
	Name = "Principal",
	Icon = "rbxassetid://3750055370",
	PremiumOnly = false
}) 

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local addCashRemote = ReplicatedStorage.Remotes.AddCash
local saveMaxAuraRemote = ReplicatedStorage:WaitForChild("Remotes"):WaitForChild("SaveMaxAura")
local auraEquipRemote = ReplicatedStorage:WaitForChild("Remotes"):WaitForChild("AuraEquip")
_G.WS = "70"; 

local spamming = false

local function spamSaveMaxAura()
    local args = { [1] = 0 }
    while spamming do
        saveMaxAuraRemote:FireServer(unpack(args))
        task.wait()
    end
end

local Section = Tab:AddSection({
	Name = "Farm"
})

Tab:AddButton({
	Name = "Auto Roll",
	Callback = function()
      		print("button pressed")
      while true do
game:GetService("ReplicatedStorage").Remotes.SpinEvent:FireServer()
wait()
      end
  	end    
})

Tab:AddButton({
	Name = "Quick Roll Grátis",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = game:GetService("Players").LocalPlayer
}

game:GetService("ReplicatedStorage").Remotes.EnableQuick:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Auto Equip [Ligado]",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 1
}

game:GetService("Players").LocalPlayer.PlayerGui.SettingsUI.SettingsFrame.AutoEquip.TextBox.RemoteEvent:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Auto Equip [Desligado]",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 0
}

game:GetService("Players").LocalPlayer.PlayerGui.SettingsUI.SettingsFrame.AutoEquip.TextBox.RemoteEvent:FireServer(unpack(args))
  	end    
})

local Section = Tab:AddSection({
	Name = "Outros"
})

Tab:AddButton({
	Name = "Universal Aura Giver",
	Callback = function()
      		print("button pressed")
      loadstring(game:HttpGet("https://raw.githubusercontent.com/Amivictim/AuraGiver/main/omfg"))()
  	end    
})

Tab:AddToggle({
    Name = "Compre Aura Slots de Graça",
    Default = false,
    Callback = function(Value)
        spamming = Value
        if spamming then
            task.spawn(spamSaveMaxAura)
        end
    end
})

local aurasOwned = game:GetService("Players").LocalPlayer:WaitForChild("AurasOwned"):GetChildren()
local auraNames = {}

for _, aura in ipairs(aurasOwned) do
    table.insert(auraNames, aura.Name)
end

Tab:AddToggle({
    Name = "Desbloquear Tudo na Coleção",
    Default = false,
    Callback = function(Value)
        for _, aura in ipairs(aurasOwned) do
            if aura:IsA("BoolValue") then
                aura.Value = Value
            end
        end
    end
})

Tab:AddButton({
	Name = "Anti Afk",
	Callback = function()
      		print("button pressed")
            loadstring(game:HttpGet("https://raw.githubusercontent.com/brosula123/Anti-afk/main/Bl%C3%B8xzScript"))() 
  	end    
})

local Tab = Window:MakeTab({
	Name = "Itens",
	Icon = "rbxassetid://3750055370",
	PremiumOnly = false
})

local Section = Tab:AddSection({
	Name = "Luvas"
})

Tab:AddButton({
	Name = "Epic Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Epic Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Yellow Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Yellow Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Exoflex Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Exoflex Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Green Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Green Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Legendary Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Legendary Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Mythics Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Mythics Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Unique Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Unique Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Meme Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Meme Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Godly Glove",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Godly Glove"
}

game:GetService("ReplicatedStorage").Remotes.AddGear:FireServer(unpack(args))
  	end    
})

local Section = Tab:AddSection({
	Name = "Poções"
})

Tab:AddButton({
	Name = "Potion",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Potion"
}

game:GetService("ReplicatedStorage").Remotes.AddItem:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Luck Potion I",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Luck Potion I"
}

game:GetService("ReplicatedStorage").Remotes.AddItem:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Luck Potion II",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Luck Potion II"
}

game:GetService("ReplicatedStorage").Remotes.AddItem:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Luck Potion III",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Luck Potion III"
}

game:GetService("ReplicatedStorage").Remotes.AddItem:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Huge Luck Potion I",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Huge Luck Potion I"
}

game:GetService("ReplicatedStorage").Remotes.AddItem:FireServer(unpack(args))
  	end    
})

local Tab = Window:MakeTab({
	Name = "Giver",
	Icon = "rbxassetid://3750055370",
	PremiumOnly = false
})

local Section = Tab:AddSection({
	Name = "Dinheiro"
})

Tab:AddButton({
	Name = "Dar 1k",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 1000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 10k",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 10000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 100k",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 100000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 1Mi",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 1000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 10Mi",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 10000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 100Mi",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 100000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 1Bi",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 1000000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 10Bi",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 10000000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "100Bi",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 100000000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 1T",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 1000000000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Dar 10T",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = 10000000000000,
    [2] = 1,
    [3] = "Coin"
}

game:GetService("ReplicatedStorage").Remotes.AddCash:FireServer(unpack(args))
  	end    
})

local Section = Tab:AddSection({
	Name = "Sorte"
})

Tab:AddButton({
	Name = "Sorte I",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Luck Potion I",
    [2] = 999999
}

game:GetService("ReplicatedStorage").Remotes.AddEffect:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Sorte II",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Luck Potion II",
    [2] = 999999
}

game:GetService("ReplicatedStorage").Remotes.AddEffect:FireServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Sorte III",
	Callback = function()
      		print("button pressed")
      local args = {
    [1] = "Luck Potion III",
    [2] = 999999
}

game:GetService("ReplicatedStorage").Remotes.AddEffect:FireServer(unpack(args))
  	end    
})

local Tab = Window:MakeTab({
	Name = "Extra",
	Icon = "rbxassetid://3750055370",
	PremiumOnly = false
})

Tab:AddButton({
	Name = "FLY HUB v3",
	Callback = function()
      		print("button pressed")
      loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-fly-gui-dark-18061"))()
  	end    
})

Tab:AddButton({
	Name = "Infinite Yield",
	Callback = function()
      		print("button pressed")
      loadstring(game:HttpGet("https://raw.githubusercontent.com/KeanXR/INF-YIELD/main/v6.0.0"))()
  	end    
})

Tab:AddButton({
	Name = "Walkspeed Modifier",
	Callback = function()
      		print("button pressed")
      loadstring(game:HttpGet("https://pastebin.com/raw/1BEgf70g"))()
  	end    
})
