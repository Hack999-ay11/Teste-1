-- Tela de carregamento com aviso inicial (90 segundos)

local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Criar GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "LoadingScreen"
screenGui.Parent = playerGui

-- Texto principal
local loadingText = Instance.new("TextLabel")
loadingText.Size = UDim2.new(0, 500, 0, 50)
loadingText.Position = UDim2.new(0, 10, 0, 10) -- canto superior esquerdo
loadingText.BackgroundTransparency = 0.3
loadingText.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
loadingText.TextColor3 = Color3.fromRGB(255, 255, 255)
loadingText.TextScaled = true
loadingText.Font = Enum.Font.SourceSansBold
loadingText.Parent = screenGui

-- Mensagem inicial
loadingText.Text = "Por favor execute o script antes de chamar alguém para o duelo"
task.wait(5)

-- Tempo total de carregamento
local totalTime = 90
local steps = 100
local waitTime = totalTime / steps

-- Contagem de 1 a 100
for i = 1, steps do
    loadingText.Text = "Script carregando... " .. i .. "%"
    task.wait(waitTime)
end

-- Finalização
loadingText.Text = "Script carregado!"
task.wait(2)
screenGui:Destroy()
