--// RJ Key System v3 — Purple Glow Edition
--// Clean Code • Smooth Animations • RJ Branding
 
local TweenService = game:GetService("TweenService")
local Players = game:GetService("Players")
local player = Players.LocalPlayer
 
-- CONFIG
local CorrectKey = "RJ-ACCESS-2024"
 
-- BLUR EFFECT
local blur = Instance.new("BlurEffect", game.Lighting)
blur.Size = 0
TweenService:Create(blur, TweenInfo.new(0.6, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {Size = 12}):Play()
 
-- SCREEN GUI
local gui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
gui.IgnoreGuiInset = true
gui.ResetOnSpawn = false
 
-- MAIN FRAME
local frame = Instance.new("Frame", gui)
frame.Size = UDim2.new(0, 420, 0, 260)
frame.Position = UDim2.new(0.5, -210, 0.5, -130)
frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
frame.BackgroundTransparency = 1
frame.ClipsDescendants = true
 
Instance.new("UICorner", frame).CornerRadius = UDim.new(0, 12)
 
-- GLOW BORDER
local glow = Instance.new("UIStroke", frame)
glow.Thickness = 2
glow.Color = Color3.fromRGB(140, 60, 255)
glow.Transparency = 0.4
 
-- GLOW ANIMATION
task.spawn(function()
while frame.Parent do
TweenService:Create(glow, TweenInfo.new(1.2, Enum.EasingStyle.Sine), {Transparency = 0.1}):Play()
task.wait(1.2)
TweenService:Create(glow, TweenInfo.new(1.2, Enum.EasingStyle.Sine), {Transparency = 0.4}):Play()
task.wait(1.2)
end
end)
 
-- TITLE
local title = Instance.new("TextLabel", frame)
title.Size = UDim2.new(1, 0, 0, 40)
title.BackgroundTransparency = 1
title.Text = "RJ Scripts — Key System"
title.Font = Enum.Font.GothamBold
title.TextSize = 22
title.TextColor3 = Color3.fromRGB(200, 160, 255)
 
-- KEY BOX
local keyBox = Instance.new("TextBox", frame)
keyBox.Size = UDim2.new(1, -40, 0, 40)
keyBox.Position = UDim2.new(0, 20, 0, 70)
keyBox.PlaceholderText = "Enter Key..."
keyBox.Font = Enum.Font.Gotham
keyBox.TextSize = 18
keyBox.Text = ""
keyBox.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
keyBox.TextColor3 = Color3.fromRGB(255, 255, 255)
Instance.new("UICorner", keyBox).CornerRadius = UDim.new(0, 8)
 
-- UNLOCK BUTTON
local unlockBtn = Instance.new("TextButton", frame)
unlockBtn.Size = UDim2.new(1, -40, 0, 40)
unlockBtn.Position = UDim2.new(0, 20, 0, 130)
unlockBtn.Text = "Unlock"
unlockBtn.Font = Enum.Font.GothamBold
unlockBtn.TextSize = 20
unlockBtn.BackgroundColor3 = Color3.fromRGB(140, 60, 255)
unlockBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
Instance.new("UICorner", unlockBtn).CornerRadius = UDim.new(0, 8)
 
-- DISCORD BUTTON
local discord = Instance.new("TextButton", frame)
discord.Size = UDim2.new(1, -40, 0, 36)
discord.Position = UDim2.new(0, 20, 0, 180)
discord.Text = "Join Discord"
discord.Font = Enum.Font.Gotham
discord.TextSize = 18
discord.BackgroundColor3 = Color3.fromRGB(40, 20, 60)
discord.TextColor3 = Color3.fromRGB(200, 160, 255)
Instance.new("UICorner", discord).CornerRadius = UDim.new(0, 8)
 
-- DISCORD GLOW PULSE
task.spawn(function()
while discord.Parent do
TweenService:Create(discord, TweenInfo.new(1.4), {BackgroundColor3 = Color3.fromRGB(60, 30, 90)}):Play()
task.wait(1.4)
TweenService:Create(discord, TweenInfo.new(1.4), {BackgroundColor3 = Color3.fromRGB(40, 20, 60)}):Play()
task.wait(1.4)
end
end)
 
-- ERROR SHAKE
local function shake()
for i = 1, 4 do
TweenService:Create(frame, TweenInfo.new(0.05), {Position = frame.Position + UDim2.new(0, 6, 0, 0)}):Play()
task.wait(0.05)
TweenService:Create(frame, TweenInfo.new(0.05), {Position = frame.Position - UDim2.new(0, 6, 0, 0)}):Play()
task.wait(0.05)
end
end
 
-- UNLOCK LOGIC
unlockBtn.MouseButton1Click:Connect(function()
if keyBox.Text == CorrectKey then
TweenService:Create(frame, TweenInfo.new(0.4), {BackgroundTransparency = 1}):Play()
TweenService:Create(glow, TweenInfo.new(0.4), {Transparency = 1}):Play()
TweenService:Create(blur, TweenInfo.new(0.6), {Size = 0}):Play()
 
task.wait(0.4)
gui:Destroy()
 
-- LOAD HUB AFTER KEY IS CORRECT
loadstring(game:HttpGet("https://pastebin.com/raw/6Qr1Y0VV"))()
else
shake()
end
end)
 
discord.MouseButton1Click:Connect(function()
setclipboard("https://discord.gg/YOURSERVER")
end)
 
TweenService:Create(frame, TweenInfo.new(0.6, Enum.EasingStyle.Quad), {BackgroundTransparency = 0}):Play()
