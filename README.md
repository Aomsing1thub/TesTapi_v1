dataname = {}
Mydata = {}

for i,v in pairs (game:GetService("Players").LocalPlayer.PlayerGui.Tranformar.Characters:GetChildren()) do
	if v:IsA("ImageLabel") then
		-- print(v)
		table.insert(dataname,v.Name)
		-- game:GetService("ReplicatedStorage"):WaitForChild("SkillEvent"):FireServer(v.Name)
	end
end

for key, v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Tranformar.TrocarPersonagem.ScrollingFrame:GetChildren()) do
	if v:IsA("ImageLabel") then
		table.insert(dataname,v.Name)
	end
end

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("TITLE", "Synapse")
local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("Section Name")

Section:NewDropdown("Characters", "DropdownInf", dataname, function(currentOption)
    Charac = currentOption
end)

Section:NewDropdown("Characters", "DropdownInf", dataname, function(currentOption)
    Charac = currentOption
firesignal(game:GetService("Players").LocalPlayer.PlayerGui.Tranformar.Characters[currentOption].Transform.MouseButton1Click)
end)


Section:NewButton("Use Characters", "Check", function() -- Buttton
	game:GetService("ReplicatedStorage"):WaitForChild("MorphRequest"):FireServer(Charac)
end)

Section:NewToggle("Auto Skill", "ToggleInfo", function(state)
    a1 = state
    if not a1 then

    end
end)

Section:NewToggle("Anti hit", "ToggleInfo", function(state)
    a2 = state
    if not a2 then

    end
end)

task.spawn(function()
while task.wait() do
if a2 then
pcall(function()

end)
end
end
end)

task.spawn(function()
while task.wait() do
if a1 then
pcall(function()
	for key, v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Tranformar.TrocarPersonagem.ScrollingFrame:GetChildren()) do
		if v:IsA("ImageButton") then
			if v.Visible then
				game:GetService("ReplicatedStorage"):WaitForChild("SkillEvent"):FireServer(v.Name)
				wait()
				game:GetService("ReplicatedStorage"):WaitForChild("SkillEvent"):FireServer(v.Name.."2")
			end
		end
	end
    fireproximityprompt(workspace.Daily.AwardPrize.AwardPrompt)
	game:GetService("ReplicatedStorage"):WaitForChild("ClaimChestFunc"):InvokeServer()
	fireproximityprompt(workspace.SecretQuest.NetherPortal1.ProximityPrompt)
end)
end
end
end)
