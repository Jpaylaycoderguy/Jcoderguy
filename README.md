local replicatedStorage = game:GetService("ReplicatedStorage")
local remoteData = game:GetService("ServerStorage"):WaitForChild("RemoteData")

local cooldown = 1

replicatedStorage.Remotes.Lift.OnServerEvent:Connect(function(player)
	
	if not remoteData:FindFirstChild(player.Name)then return "NoFolder" end
	
	local debounce = remoteData[player.Name].Debounce
	
	if not debounce.Value then
		
		
		debounce.Value = true
		
		player.leaderstats.Strength.Value = player.leaderstrats.Strength.Value + 25 * (player.leaderstats.Rebirths.Value + 1)
		
		wait(cooldown)
		
		debounce.Value = false		
	
	end
		
end) 
