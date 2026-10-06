# Duels
D4SHIE
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local duplicateEvent = ReplicatedStorage:WaitForChild("DuplicateWeapon")
testButton.Text = "🎁 DUPLICAR"
testButton.MouseButton1Click:Connect(function()
	if typeof(selected) ~= "string" or selected == "" then
		title.Text = "❌ Selecciona un arma válida"
		return
	end
	local backpack = game.Players.LocalPlayer:FindFirstChildOfClass("Backpack")
	local weapon = backpack and backpack:FindFirstChild(selected)
	if not weapon or not weapon:IsA("Tool") then
		title.Text = "❌ El arma no existe en tu inventario"
		return
	end
	duplicateEvent:FireServer(selected)
	title.Text = "✅ Duplicada: " .. selected
end)
