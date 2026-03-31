-- Script GUI: Speed, Infinite Jump, Fly, Invisible Platform
-- Interface preta e cinza

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local rootPart = character:WaitForChild("HumanoidRootPart")

-- Variáveis de controle
local infiniteJumpEnabled = false
local flyEnabled = false
local flyBodyVelocity = nil
local originalSpeed = 16 -- Velocidade padrão do Roblox
local speedMultiplier = 1
local platform = nil

-- Criar ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "AdminGUI"
screenGui.Parent = player:WaitForChild("PlayerGui")

-- Frame principal (preto)
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 300, 0, 400)
mainFrame.Position = UDim2.new(0, 10, 0, 10)
mainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
mainFrame.BackgroundTransparency = 0
mainFrame.BorderSizePixel = 0
mainFrame.Parent = screenGui

-- Título (cinza)
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 40)
title.Position = UDim2.new(0