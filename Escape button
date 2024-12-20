local function createESP(obj)
    -- Cria um BillboardGui para exibir o nome
    local billboard = Instance.new("BillboardGui")
    billboard.Adornee = obj
    billboard.Size = UDim2.new(4, 0, 1, 0)
    billboard.StudsOffset = Vector3.new(0, 3, 0)
    billboard.AlwaysOnTop = true

    -- Cria o TextLabel para mostrar o nome do botão
    local textLabel = Instance.new("TextLabel", billboard)
    textLabel.Size = UDim2.new(1, 0, 1, 0)
    textLabel.BackgroundTransparency = 1
    textLabel.Text = string.upper(obj.Name) -- Converte o nome para letras maiúsculas
    textLabel.TextColor3 = Color3.new(0, 0, 1) -- Azul
    textLabel.TextScaled = true

    -- Anexa o ESP ao objeto
    billboard.Parent = obj

    -- Adiciona uma seta apontando para o botão
    local arrow = Instance.new("BillboardGui")
    arrow.Adornee = obj
    arrow.Size = UDim2.new(2, 0, 2, 0)
    arrow.StudsOffset = Vector3.new(0, 5, 0) -- Posição acima do botão
    arrow.AlwaysOnTop = true

    local arrowLabel = Instance.new("TextLabel", arrow)
    arrowLabel.Size = UDim2.new(1, 0, 1, 0)
    arrowLabel.BackgroundTransparency = 1
    arrowLabel.Text = "↓" -- Seta apontando para baixo
    arrowLabel.TextColor3 = Color3.new(1, 0, 0) -- Vermelho
    arrowLabel.TextScaled = true

    arrow.Parent = obj
end

local function addESPToButtons()
    for _, obj in pairs(workspace:GetDescendants()) do
        if obj:IsA("BasePart") and obj.Name == "Button" then
            createESP(obj)
        end
    end
end

-- Adiciona ESP para objetos chamados "Button" existentes
addESPToButtons()

-- Adiciona ESP para novos objetos chamados "Button" que forem adicionados ao jogo
workspace.DescendantAdded:Connect(function(obj)
    if obj:IsA("BasePart") and obj.Name == "Button" then
        createESP(obj)
    end
end)
