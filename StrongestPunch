--[[ Created by Ezpi#0474 ]]--

--// Services \\--
local Players = game:GetService("Players")
local Workspace = game:GetService("Workspace")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

--// Variables \\--
local Player = Players.LocalPlayer
local Boosts = Workspace:WaitForChild("Map"):WaitForChild("Stages"):WaitForChild("Boosts")
local World = Player:WaitForChild("leaderstats"):WaitForChild("WORLD")
local RemoteEvent = ReplicatedStorage:WaitForChild("RemoteEvent")

--// Loop! \\--
while wait(Delay) do
    --// Get Highest Value Target \\--
    local Current_World = Boosts[World.Value]
    local Collectable = nil
    local Highest = 0
    for _, A_1 in next, Current_World:GetChildren() do
        local A_2 = A_1.Name
        local Number = tonumber(A_2:sub(#A_2, #A_2))
        if Number > Highest then
            Highest = Number
            Collectable = A_1
        end
    end
    --// Collect Highest Value \\--
    if Collectable ~= nil then
        pcall(function()
            Player.Character.PrimaryPart.CFrame = Collectable.PrimaryPart.CFrame
            firetouchinterest(Player.Character.PrimaryPart, Collectable.PrimaryPart, 0)
            firetouchinterest(Player.Character.PrimaryPart, Collectable.PrimaryPart, 1)
        end)
    end
    --// Next Area \\--
    if AutoTeleport then
        RemoteEvent:FireServer({
            "WarpPlrToOtherMap", 
            "Next"
        })
    end
end
