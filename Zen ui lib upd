-- Zen UI Library
-- For all you skids, best UI lib out there

local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")

local Player = Players.LocalPlayer
local PlayerGui = Player:WaitForChild("PlayerGui")

local ZenUI = {}

local Colors = {
    Accent      = Color3.fromRGB(255, 255, 255),
    Background  = Color3.fromRGB(9, 9, 10),
    Panel       = Color3.fromRGB(14, 14, 15),
    Panel2      = Color3.fromRGB(18, 18, 19),
    Border      = Color3.fromRGB(42, 42, 44),
    Text        = Color3.fromRGB(242, 242, 242),
    SubText     = Color3.fromRGB(148, 148, 152),
    Green       = Color3.fromRGB(98, 214, 72),
    Red         = Color3.fromRGB(255, 70, 70),
    Yellow      = Color3.fromRGB(255, 200, 50),
    Hover       = Color3.fromRGB(24, 24, 26),
}

-- Executor Detection
local function DetectExecutor()
    local executors = {
        {name = "Synapse X", check = function() return pcall(function() return syn and syn.crypt end) end},
        {name = "Krnl", check = function() return pcall(function() return krnl and krnl.loadfile end) end},
        {name = "ScriptWare", check = function() return pcall(function() return scriptware and scriptware.loadfile end) end},
        {name = "Oxygen U", check = function() return pcall(function() return oxygen and oxygen.loadfile end) end},
        {name = "Fluxus", check = function() return pcall(function() return fluxus and fluxus.loadfile end) end},
        {name = "Electron", check = function() return pcall(function() return electron and electron.loadfile end) end},
        {name = "Sirius", check = function() return pcall(function() return sirius and sirius.loadfile end) end},
        {name = "Vega X", check = function() return pcall(function() return vega and vega.loadfile end) end},
        {name = "Celestial", check = function() return pcall(function() return celestial and celestial.loadfile end) end},
        {name = "Seliware", check = function() return pcall(function() return seliware and seliware.loadfile end) end},
        {name = "Velocity", check = function() return pcall(function() return velocity and velocity.loadfile end) end},
        {name = "AWP", check = function() return pcall(function() return awp and awp.loadfile end) end},
        {name = "Elysian", check = function() return pcall(function() return elysian and elysian.loadfile end) end},
        {name = "Calamari", check = function() return pcall(function() return calamari and calamari.loadfile end) end},
        {name = "Valyse", check = function() return pcall(function() return valyse and valyse.loadfile end) end},
        {name = "Unknown", check = function() return true end},
    }
    
    for _, executor in ipairs(executors) do
        if executor.check() then
            return executor.name
        end
    end
    return "Unknown"
end

local ExecutorName = DetectExecutor()

function ZenUI.Create()
    local ScreenGui = Instance.new("ScreenGui")
    ScreenGui.Name = "ZenUI"
    ScreenGui.ResetOnSpawn = false
    ScreenGui.IgnoreGuiInset = true
    ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
    ScreenGui.Parent = PlayerGui

    local Main = Instance.new("Frame")
    Main.Name = "Main"
    Main.AnchorPoint = Vector2.new(0.5, 0.5)
    Main.Position = UDim2.fromScale(0.5, 0.5)
    Main.Size = UDim2.fromOffset(1120, 680)
    Main.BackgroundColor3 = Colors.Background
    Main.BorderSizePixel = 0
    Main.ClipsDescendants = true
    Main.Parent = ScreenGui

    local MainCorner = Instance.new("UICorner")
    MainCorner.CornerRadius = UDim.new(0, 16)
    MainCorner.Parent = Main

    local MainStroke = Instance.new("UIStroke")
    MainStroke.Color = Color3.fromRGB(58, 58, 60)
    MainStroke.Thickness = 1
    MainStroke.Parent = Main

    local Camera = workspace.CurrentCamera
    local function Resize()
        local viewport = Camera.ViewportSize
        if viewport.X < 960 then
            Main.Size = UDim2.new(0.94, 0, 0.88, 0)
        else
            Main.Size = UDim2.fromOffset(1120, 680)
        end
    end
    Resize()
    Camera:GetPropertyChangedSignal("ViewportSize"):Connect(Resize)

    local Sidebar = Instance.new("Frame")
    Sidebar.Size = UDim2.new(0, 228, 1, 0)
    Sidebar.BackgroundColor3 = Color3.fromRGB(8, 8, 9)
    Sidebar.BorderSizePixel = 0
    Sidebar.Parent = Main

    local Divider = Instance.new("Frame")
    Divider.Position = UDim2.new(1, -1, 0, 0)
    Divider.Size = UDim2.new(0, 1, 1, 0)
    Divider.BackgroundColor3 = Color3.fromRGB(32, 32, 34)
    Divider.BorderSizePixel = 0
    Divider.Parent = Sidebar

    local Logo = Instance.new("Frame")
    Logo.Position = UDim2.new(0, 20, 0, 22)
    Logo.Size = UDim2.new(1, -40, 0, 58)
    Logo.BackgroundTransparency = 1
    Logo.Parent = Sidebar

    local LogoIcon = Instance.new("TextLabel")
    LogoIcon.BackgroundTransparency = 1
    LogoIcon.Text = ""
    LogoIcon.TextColor3 = Colors.Text
    LogoIcon.TextSize = 36
    LogoIcon.Font = Enum.Font.GothamBold
    LogoIcon.TextXAlignment = Enum.TextXAlignment.Center
    LogoIcon.TextYAlignment = Enum.TextYAlignment.Center
    LogoIcon.Size = UDim2.fromOffset(40, 58)
    LogoIcon.Parent = Logo

    local LogoText = Instance.new("TextLabel")
    LogoText.BackgroundTransparency = 1
    LogoText.Text = "ZEN UI"
    LogoText.TextColor3 = Colors.Text
    LogoText.TextSize = 22
    LogoText.Font = Enum.Font.GothamBold
    LogoText.TextXAlignment = Enum.TextXAlignment.Left
    LogoText.TextYAlignment = Enum.TextYAlignment.Center
    LogoText.Position = UDim2.new(0, 44, 0, 6)
    LogoText.Size = UDim2.new(1, -44, 0, 28)
    LogoText.Parent = Logo

    local LogoSub = Instance.new("TextLabel")
    LogoSub.BackgroundTransparency = 1
    LogoSub.Text = "PREMIUM SCRIPT"
    LogoSub.TextColor3 = Colors.SubText
    LogoSub.TextSize = 9
    LogoSub.Font = Enum.Font.GothamMedium
    LogoSub.TextXAlignment = Enum.TextXAlignment.Left
    LogoSub.TextYAlignment = Enum.TextYAlignment.Center
    LogoSub.Position = UDim2.new(0, 45, 0, 34)
    LogoSub.Size = UDim2.new(1, -45, 0, 16)
    LogoSub.Parent = Logo

    local NavItems = {
        {"HOME"},
        {"PLAYER"},
        {"VISUALS"},
        {"COMBAT"},
        {"MOVEMENT"},
        {"WORLD"},
        {"TELEPORT"},
        {"MISC"},
        {"SETTINGS"},
        {"SCRIPTS"},
        {"CREDITS"},
    }

    local SelectedButton = nil

    for i, item in ipairs(NavItems) do
        local btn = Instance.new("TextButton")
        btn.Name = item[1]
        btn.AutoButtonColor = false
        btn.Text = ""
        btn.Position = UDim2.new(0, 14, 0, 108 + (i-1)*46)
        btn.Size = UDim2.new(1, -28, 0, 40)
        if i == 1 then
            btn.BackgroundColor3 = Colors.Text
        else
            btn.BackgroundColor3 = Color3.fromRGB(8, 8, 9)
        end
        btn.BorderSizePixel = 0
        btn.Parent = Sidebar

        local btnCorner = Instance.new("UICorner")
        btnCorner.CornerRadius = UDim.new(0, 10)
        btnCorner.Parent = btn

        local label = Instance.new("TextLabel")
        label.BackgroundTransparency = 1
        label.Text = item[1]
        if i == 1 then
            label.TextColor3 = Color3.fromRGB(12, 12, 13)
        else
            label.TextColor3 = Colors.Text
        end
        label.TextSize = 13
        label.Font = Enum.Font.GothamMedium
        label.TextXAlignment = Enum.TextXAlignment.Center
        label.TextYAlignment = Enum.TextYAlignment.Center
        label.Position = UDim2.new(0, 12, 0, 0)
        label.Size = UDim2.new(1, -24, 1, 0)
        label.Parent = btn

        btn.MouseEnter:Connect(function()
            if SelectedButton ~= btn then
                TweenService:Create(btn, TweenInfo.new(0.18, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
                    BackgroundColor3 = Colors.Hover
                }):Play()
            end
        end)

        btn.MouseLeave:Connect(function()
            if SelectedButton ~= btn then
                TweenService:Create(btn, TweenInfo.new(0.18, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
                    BackgroundColor3 = Color3.fromRGB(8, 8, 9)
                }):Play()
            end
        end)

        btn.MouseButton1Click:Connect(function()
            if SelectedButton then
                SelectedButton.BackgroundColor3 = Color3.fromRGB(8, 8, 9)
                for _, child in ipairs(SelectedButton:GetChildren()) do
                    if child:IsA("TextLabel") then
                        child.TextColor3 = Colors.Text
                    end
                end
            end

            SelectedButton = btn
            TweenService:Create(btn, TweenInfo.new(0.18, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
                BackgroundColor3 = Colors.Text
            }):Play()

            for _, child in ipairs(btn:GetChildren()) do
                if child:IsA("TextLabel") then
                    child.TextColor3 = Color3.fromRGB(12, 12, 13)
                end
            end
        end)

        if i == 1 then
            SelectedButton = btn
        end
    end

    local Profile = Instance.new("Frame")
    Profile.Position = UDim2.new(0, 14, 1, -82)
    Profile.Size = UDim2.new(1, -28, 0, 66)
    Profile.BackgroundColor3 = Color3.fromRGB(12, 12, 13)
    Profile.BorderSizePixel = 0
    Profile.Parent = Sidebar

    local ProfileCorner = Instance.new("UICorner")
    ProfileCorner.CornerRadius = UDim.new(0, 11)
    ProfileCorner.Parent = Profile

    local ProfileStroke = Instance.new("UIStroke")
    ProfileStroke.Color = Colors.Border
    ProfileStroke.Thickness = 1
    ProfileStroke.Parent = Profile

    local Avatar = Instance.new("ImageLabel")
    Avatar.Position = UDim2.new(0, 11, 0.5, -20)
    Avatar.Size = UDim2.fromOffset(40, 40)
    Avatar.BackgroundColor3 = Color3.fromRGB(32, 32, 34)
    Avatar.Image = "rbxthumb://type=AvatarHeadShot&id=" .. Player.UserId .. "&w=150&h=150"
    Avatar.BorderSizePixel = 0
    Avatar.Parent = Profile

    local AvatarCorner = Instance.new("UICorner")
    AvatarCorner.CornerRadius = UDim.new(0, 50)
    AvatarCorner.Parent = Avatar

    local PlayerName = Instance.new("TextLabel")
    PlayerName.BackgroundTransparency = 1
    if Player.DisplayName ~= "" then
        PlayerName.Text = Player.DisplayName
    else
        PlayerName.Text = "Developer"
    end
    PlayerName.TextColor3 = Colors.Text
    PlayerName.TextSize = 13
    PlayerName.Font = Enum.Font.GothamBold
    PlayerName.TextXAlignment = Enum.TextXAlignment.Left
    PlayerName.TextYAlignment = Enum.TextYAlignment.Center
    PlayerName.Position = UDim2.new(0, 60, 0, 14)
    PlayerName.Size = UDim2.new(1, -70, 0, 20)
    PlayerName.Parent = Profile

    local PlayerRole = Instance.new("TextLabel")
    PlayerRole.BackgroundTransparency = 1
    PlayerRole.Text = "Owner"
    PlayerRole.TextColor3 = Colors.SubText
    PlayerRole.TextSize = 11
    PlayerRole.Font = Enum.Font.GothamMedium
    PlayerRole.TextXAlignment = Enum.TextXAlignment.Left
    PlayerRole.TextYAlignment = Enum.TextYAlignment.Center
    PlayerRole.Position = UDim2.new(0, 60, 0, 35)
    PlayerRole.Size = UDim2.new(1, -70, 0, 16)
    PlayerRole.Parent = Profile

    local Content = Instance.new("Frame")
    Content.Position = UDim2.new(0, 228, 0, 0)
    Content.Size = UDim2.new(1, -228, 1, 0)
    Content.BackgroundTransparency = 1
    Content.Parent = Main

    local Header = Instance.new("Frame")
    Header.Position = UDim2.new(0, 22, 0, 16)
    Header.Size = UDim2.new(1, -44, 0, 58)
    Header.BackgroundTransparency = 1
    Header.Parent = Content

    local Welcome = Instance.new("TextLabel")
    Welcome.BackgroundTransparency = 1
    Welcome.Text = "Welcome back, " .. (Player.DisplayName ~= "" and Player.DisplayName or "Developer")
    Welcome.TextColor3 = Colors.Text
    Welcome.TextSize = 16
    Welcome.Font = Enum.Font.Gotham
    Welcome.TextXAlignment = Enum.TextXAlignment.Left
    Welcome.TextYAlignment = Enum.TextYAlignment.Center
    Welcome.Size = UDim2.new(1, -140, 0, 26)
    Welcome.Parent = Header

    local WelcomeSub = Instance.new("TextLabel")
    WelcomeSub.BackgroundTransparency = 1
    WelcomeSub.Text = "Enjoy the best script experience."
    WelcomeSub.TextColor3 = Colors.SubText
    WelcomeSub.TextSize = 12
    WelcomeSub.Font = Enum.Font.Gotham
    WelcomeSub.TextXAlignment = Enum.TextXAlignment.Left
    WelcomeSub.TextYAlignment = Enum.TextYAlignment.Center
    WelcomeSub.Position = UDim2.new(0, 0, 0, 28)
    WelcomeSub.Size = UDim2.new(1, -140, 0, 20)
    WelcomeSub.Parent = Header

    local function CreateHeaderButton(pos, icon)
        local btn = Instance.new("TextButton")
        btn.Position = pos
        btn.Size = UDim2.fromOffset(42, 42)
        btn.Text = icon
        btn.TextSize = 18
        btn.TextColor3 = Colors.Text
        btn.Font = Enum.Font.Gotham
        btn.BackgroundColor3 = Colors.Panel
        btn.AutoButtonColor = false
        btn.Parent = Header

        local btnCorner = Instance.new("UICorner")
        btnCorner.CornerRadius = UDim.new(0, 9)
        btnCorner.Parent = btn

        local btnStroke = Instance.new("UIStroke")
        btnStroke.Color = Colors.Border
        btnStroke.Thickness = 1
        btnStroke.Parent = btn

        return btn
    end

    CreateHeaderButton(UDim2.new(1, -98, 0, 4), "")
    CreateHeaderButton(UDim2.new(1, -48, 0, 4), "")

    local Hero = Instance.new("Frame")
    Hero.Position = UDim2.new(0, 22, 0, 84)
    Hero.Size = UDim2.new(0.68, -12, 0, 178)
    Hero.BackgroundColor3 = Color3.fromRGB(12, 12, 13)
    Hero.BorderSizePixel = 0
    Hero.ClipsDescendants = true
    Hero.Parent = Content

    local HeroCorner = Instance.new("UICorner")
    HeroCorner.CornerRadius = UDim.new(0, 12)
    HeroCorner.Parent = Hero

    local HeroStroke = Instance.new("UIStroke")
    HeroStroke.Color = Colors.Border
    HeroStroke.Thickness = 1
    HeroStroke.Parent = Hero

    local HeroTitle = Instance.new("TextLabel")
    HeroTitle.BackgroundTransparency = 1
    HeroTitle.Text = "ZEN UI"
    HeroTitle.TextColor3 = Colors.Text
    HeroTitle.TextSize = 34
    HeroTitle.Font = Enum.Font.GothamBlack
    HeroTitle.TextXAlignment = Enum.TextXAlignment.Left
    HeroTitle.TextYAlignment = Enum.TextYAlignment.Center
    HeroTitle.Position = UDim2.new(0, 34, 0, 38)
    HeroTitle.Size = UDim2.new(0.5, 0, 0, 42)
    HeroTitle.Parent = Hero

    local HeroSub = Instance.new("TextLabel")
    HeroSub.BackgroundTransparency = 1
    HeroSub.Text = "BUILT DIFFERENT."
    HeroSub.TextColor3 = Colors.SubText
    HeroSub.TextSize = 15
    HeroSub.Font = Enum.Font.GothamMedium
    HeroSub.TextXAlignment = Enum.TextXAlignment.Left
    HeroSub.TextYAlignment = Enum.TextYAlignment.Center
    HeroSub.Position = UDim2.new(0, 36, 0, 84)
    HeroSub.Size = UDim2.new(0.5, 0, 0, 22)
    HeroSub.Parent = Hero

    local ExecHero = Instance.new("TextButton")
    ExecHero.Position = UDim2.new(0, 36, 1, -48)
    ExecHero.Size = UDim2.fromOffset(132, 36)
    ExecHero.Text = "EXECUTE"
    ExecHero.TextSize = 12
    ExecHero.Font = Enum.Font.GothamBold
    ExecHero.TextColor3 = Colors.Text
    ExecHero.BackgroundColor3 = Color3.fromRGB(11, 11, 12)
    ExecHero.AutoButtonColor = false
    ExecHero.Parent = Hero

    local ExecHeroCorner = Instance.new("UICorner")
    ExecHeroCorner.CornerRadius = UDim.new(0, 8)
    ExecHeroCorner.Parent = ExecHero

    local ExecHeroStroke = Instance.new("UIStroke")
    ExecHeroStroke.Color = Colors.Text
    ExecHeroStroke.Thickness = 1
    ExecHeroStroke.Parent = ExecHero

    for i = 1, 3 do
        local card = Instance.new("Frame")
        card.Position = UDim2.new(1, -238 + (i-1)*30, 0, 28 + (i-1)*-7)
        card.Size = UDim2.fromOffset(122, 158)
        card.Rotation = -11 + (i-1)*9
        card.BackgroundColor3 = Color3.fromRGB(26, 26, 28)
        card.BorderSizePixel = 0
        card.ZIndex = i
        card.Parent = Hero

        local cardCorner = Instance.new("UICorner")
        cardCorner.CornerRadius = UDim.new(0, 7)
        cardCorner.Parent = card

        local cardStroke = Instance.new("UIStroke")
        cardStroke.Color = Color3.fromRGB(90, 90, 92)
        cardStroke.Thickness = 1
        cardStroke.Parent = card

        local cardText = Instance.new("TextLabel")
        cardText.BackgroundTransparency = 1
        cardText.Text = "A"
        cardText.TextColor3 = Colors.Text
        cardText.TextSize = 32
        cardText.Font = Enum.Font.GothamBold
        cardText.TextXAlignment = Enum.TextXAlignment.Center
        cardText.TextYAlignment = Enum.TextYAlignment.Center
        cardText.Size = UDim2.fromScale(1, 1)
        cardText.Parent = card
    end

    local Status = Instance.new("Frame")
    Status.Position = UDim2.new(0.68, 4, 0, 84)
    Status.Size = UDim2.new(0.32, -26, 0, 178)
    Status.BackgroundColor3 = Colors.Panel
    Status.BorderSizePixel = 0
    Status.Parent = Content

    local StatusCorner = Instance.new("UICorner")
    StatusCorner.CornerRadius = UDim.new(0, 12)
    StatusCorner.Parent = Status

    local StatusStroke = Instance.new("UIStroke")
    StatusStroke.Color = Colors.Border
    StatusStroke.Thickness = 1
    StatusStroke.Parent = Status

    local StatusTitle = Instance.new("TextLabel")
    StatusTitle.BackgroundTransparency = 1
    StatusTitle.Text = "SYSTEM STATUS"
    StatusTitle.TextColor3 = Colors.Text
    StatusTitle.TextSize = 13
    StatusTitle.Font = Enum.Font.GothamBold
    StatusTitle.TextXAlignment = Enum.TextXAlignment.Left
    StatusTitle.TextYAlignment = Enum.TextYAlignment.Center
    StatusTitle.Position = UDim2.new(0, 18, 0, 14)
    StatusTitle.Size = UDim2.new(1, -36, 0, 22)
    StatusTitle.Parent = Status

    local StatusItems = {
        {"Status", "Undetected", Colors.Green},
        {"Executor", ExecutorName, Colors.Text},
        {"Uptime", "01:24:37", Colors.Text},
        {"Players", "12/30", Colors.Text},
        {"Server", "United States", Colors.Text},
    }

    for i, data in ipairs(StatusItems) do
        local y = 44 + (i-1)*25

        local divider = Instance.new("Frame")
        divider.Position = UDim2.new(0, 18, 0, y)
        divider.Size = UDim2.new(1, -36, 0, 1)
        divider.BackgroundColor3 = Color3.fromRGB(34, 34, 36)
        divider.BorderSizePixel = 0
        divider.Parent = Status

        local label = Instance.new("TextLabel")
        label.BackgroundTransparency = 1
        label.Text = data[1]
        label.TextColor3 = Colors.Text
        label.TextSize = 12
        label.Font = Enum.Font.Gotham
        label.TextXAlignment = Enum.TextXAlignment.Left
        label.TextYAlignment = Enum.TextYAlignment.Center
        label.Position = UDim2.new(0, 18, 0, y+3)
        label.Size = UDim2.new(0.38, 0, 0, 18)
        label.Parent = Status

        local value = Instance.new("TextLabel")
        value.BackgroundTransparency = 1
        value.Text = data[2]
        value.TextColor3 = data[3]
        value.TextSize = 12
        value.Font = Enum.Font.GothamMedium
        value.TextXAlignment = Enum.TextXAlignment.Right
        value.TextYAlignment = Enum.TextYAlignment.Center
        value.Position = UDim2.new(0.42, 0, 0, y+3)
        value.Size = UDim2.new(0.58, -18, 0, 18)
        value.Parent = Status
    end

    local Features = Instance.new("Frame")
    Features.Position = UDim2.new(0, 22, 0, 278)
    Features.Size = UDim2.new(0.68, -12, 1, -322)
    Features.BackgroundColor3 = Colors.Panel
    Features.BorderSizePixel = 0
    Features.Parent = Content

    local FeaturesCorner = Instance.new("UICorner")
    FeaturesCorner.CornerRadius = UDim.new(0, 12)
    FeaturesCorner.Parent = Features

    local FeaturesStroke = Instance.new("UIStroke")
    FeaturesStroke.Color = Colors.Border
    FeaturesStroke.Thickness = 1
    FeaturesStroke.Parent = Features

    local FeaturesTitle = Instance.new("TextLabel")
    FeaturesTitle.BackgroundTransparency = 1
    FeaturesTitle.Text = "FEATURES"
    FeaturesTitle.TextColor3 = Colors.Text
    FeaturesTitle.TextSize = 13
    FeaturesTitle.Font = Enum.Font.GothamBold
    FeaturesTitle.TextXAlignment = Enum.TextXAlignment.Left
    FeaturesTitle.TextYAlignment = Enum.TextYAlignment.Center
    FeaturesTitle.Position = UDim2.new(0, 18, 0, 14)
    FeaturesTitle.Size = UDim2.new(1, -36, 0, 22)
    FeaturesTitle.Parent = Features

    local FeatureList = {
        {"Infinite Jump", "Allows you to jump infinitely."},
        {"Noclip", "Move through walls and objects."},
        {"WalkSpeed", "Adjust your walk speed value."},
        {"Jump Power", "Adjust your jump power value."},
        {"God Mode", "You can't take any damage."},
        {"Anti Knockback", "Prevents you from being knocked back."},
    }

    local function CreateToggle(parent, y, defaultState)
        local holder = Instance.new("TextButton")
        holder.Position = UDim2.new(1, -92, 0, y)
        holder.Size = UDim2.fromOffset(68, 30)
        if defaultState then
            holder.BackgroundColor3 = Colors.Text
        else
            holder.BackgroundColor3 = Color3.fromRGB(30, 30, 32)
        end
        holder.Text = ""
        holder.AutoButtonColor = false
        holder.Parent = parent

        local holderCorner = Instance.new("UICorner")
        holderCorner.CornerRadius = UDim.new(0, 18)
        holderCorner.Parent = holder

        local knob = Instance.new("Frame")
        knob.AnchorPoint = Vector2.new(0, 0.5)
        if defaultState then
            knob.Position = UDim2.new(1, -26, 0.5, 0)
            knob.BackgroundColor3 = Color3.fromRGB(18, 18, 19)
        else
            knob.Position = UDim2.new(0, 6, 0.5, 0)
            knob.BackgroundColor3 = Color3.fromRGB(200, 200, 202)
        end
        knob.Size = UDim2.fromOffset(20, 20)
        knob.BorderSizePixel = 0
        knob.Parent = holder

        local knobCorner = Instance.new("UICorner")
        knobCorner.CornerRadius = UDim.new(0, 50)
        knobCorner.Parent = knob

        local state = defaultState

        holder.MouseButton1Click:Connect(function()
            state = not state

            if state then
                TweenService:Create(holder, TweenInfo.new(0.18, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
                    BackgroundColor3 = Colors.Text
                }):Play()
                TweenService:Create(knob, TweenInfo.new(0.18, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
                    Position = UDim2.new(1, -26, 0.5, 0),
                    BackgroundColor3 = Color3.fromRGB(18, 18, 19)
                }):Play()
            else
                TweenService:Create(holder, TweenInfo.new(0.18, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
                    BackgroundColor3 = Color3.fromRGB(30, 30, 32)
                }):Play()
                TweenService:Create(knob, TweenInfo.new(0.18, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
                    Position = UDim2.new(0, 6, 0.5, 0),
                    BackgroundColor3 = Color3.fromRGB(200, 200, 202)
                }):Play()
            end
        end)

        return function()
            return state
        end
    end

    local function CreateSlider(parent, y, defaultValue, minVal, maxVal)
        local slider = Instance.new("Frame")
        slider.Position = UDim2.new(1, -280, 0, y + 10)
        slider.Size = UDim2.fromOffset(210, 4)
        slider.BackgroundColor3 = Color3.fromRGB(48, 48, 50)
        slider.BorderSizePixel = 0
        slider.Parent = parent

        local sliderCorner = Instance.new("UICorner")
        sliderCorner.CornerRadius = UDim.new(0, 4)
        sliderCorner.Parent = slider

        local fill = Instance.new("Frame")
        fill.Size = UDim2.new((defaultValue-minVal)/(maxVal-minVal), 0, 1, 0)
        fill.BackgroundColor3 = Colors.Text
        fill.BorderSizePixel = 0
        fill.Parent = slider

        local fillCorner = Instance.new("UICorner")
        fillCorner.CornerRadius = UDim.new(0, 4)
        fillCorner.Parent = fill

        local knob = Instance.new("TextButton")
        knob.AnchorPoint = Vector2.new(0.5, 0.5)
        knob.Position = UDim2.new((defaultValue-minVal)/(maxVal-minVal), 0, 0.5, 0)
        knob.Size = UDim2.fromOffset(15, 15)
        knob.BackgroundColor3 = Colors.Text
        knob.Text = ""
        knob.AutoButtonColor = false
        knob.Parent = slider

        local knobCorner = Instance.new("UICorner")
        knobCorner.CornerRadius = UDim.new(0, 50)
        knobCorner.Parent = knob

        local valueLabel = Instance.new("TextLabel")
        valueLabel.Position = UDim2.new(1, 16, 0.5, -15)
        valueLabel.Size = UDim2.fromOffset(48, 30)
        valueLabel.BackgroundColor3 = Color3.fromRGB(12, 12, 13)
        valueLabel.Text = tostring(defaultValue)
        valueLabel.TextColor3 = Colors.Text
        valueLabel.TextSize = 11
        valueLabel.Font = Enum.Font.GothamMedium
        valueLabel.TextXAlignment = Enum.TextXAlignment.Center
        valueLabel.TextYAlignment = Enum.TextYAlignment.Center
        valueLabel.Parent = slider

        local valueCorner = Instance.new("UICorner")
        valueCorner.CornerRadius = UDim.new(0, 6)
        valueCorner.Parent = valueLabel

        local valueStroke = Instance.new("UIStroke")
        valueStroke.Color = Colors.Border
        valueStroke.Thickness = 1
        valueStroke.Parent = valueLabel

        local isDragging = false

        knob.MouseButton1Down:Connect(function()
            isDragging = true
        end)

        UserInputService.InputEnded:Connect(function(input)
            if input.UserInputType == Enum.UserInputType.MouseButton1 then
                isDragging = false
            end
        end)

        UserInputService.InputChanged:Connect(function(input)
            if isDragging and input.UserInputType == Enum.UserInputType.MouseMovement then
                local percent = math.clamp((input.Position.X - slider.AbsolutePosition.X) / slider.AbsoluteSize.X, 0, 1)
                local value = math.floor(minVal + (maxVal-minVal)*percent)

                fill.Size = UDim2.new(percent, 0, 1, 0)
                knob.Position = UDim2.new(percent, 0, 0.5, 0)
                valueLabel.Text = tostring(value)
            end
        end)
    end

    for i, data in ipairs(FeatureList) do
        local y = 48 + (i-1)*52

        local divider = Instance.new("Frame")
        divider.Position = UDim2.new(0, 18, 0, y + 48)
        divider.Size = UDim2.new(1, -36, 0, 1)
        divider.BackgroundColor3 = Color3.fromRGB(34, 34, 36)
        divider.BorderSizePixel = 0
        divider.Parent = Features

        local name = Instance.new("TextLabel")
        name.BackgroundTransparency = 1
        name.Text = data[1]
        name.TextColor3 = Colors.Text
        name.TextSize = 13
        name.Font = Enum.Font.GothamMedium
        name.TextXAlignment = Enum.TextXAlignment.Left
        name.TextYAlignment = Enum.TextYAlignment.Center
        name.Position = UDim2.new(0, 22, 0, y + 2)
        name.Size = UDim2.new(0.42, 0, 0, 20)
        name.Parent = Features

        local desc = Instance.new("TextLabel")
        desc.BackgroundTransparency = 1
        desc.Text = data[2]
        desc.TextColor3 = Colors.SubText
        desc.TextSize = 10
        desc.Font = Enum.Font.Gotham
        desc.TextXAlignment = Enum.TextXAlignment.Left
        desc.TextYAlignment = Enum.TextYAlignment.Center
        desc.Position = UDim2.new(0, 22, 0, y + 22)
        desc.Size = UDim2.new(0.48, 0, 0, 16)
        desc.Parent = Features

        if data[1] == "WalkSpeed" then
            CreateSlider(Features, y, 150, 16, 300)
        elseif data[1] == "Jump Power" then
            CreateSlider(Features, y, 100, 20, 200)
        else
            CreateToggle(Features, y + 6, true)
        end
    end

    local Theme = Instance.new("Frame")
    Theme.Position = UDim2.new(0.68, 4, 0, 526)
    Theme.Size = UDim2.new(0.15, -12, 1, -568)
    Theme.BackgroundColor3 = Colors.Panel
    Theme.BorderSizePixel = 0
    Theme.Parent = Content

    local ThemeCorner = Instance.new("UICorner")
    ThemeCorner.CornerRadius = UDim.new(0, 12)
    ThemeCorner.Parent = Theme

    local ThemeStroke = Instance.new("UIStroke")
    ThemeStroke.Color = Colors.Border
    ThemeStroke.Thickness = 1
    ThemeStroke.Parent = Theme

    local ThemeTitle = Instance.new("TextLabel")
    ThemeTitle.BackgroundTransparency = 1
    ThemeTitle.Text = "THEME"
    ThemeTitle.TextColor3 = Colors.Text
    ThemeTitle.TextSize = 12
    ThemeTitle.Font = Enum.Font.GothamBold
    ThemeTitle.TextXAlignment = Enum.TextXAlignment.Left
    ThemeTitle.TextYAlignment = Enum.TextYAlignment.Center
    ThemeTitle.Position = UDim2.new(0, 16, 0, 12)
    ThemeTitle.Size = UDim2.new(1, -32, 0, 20)
    ThemeTitle.Parent = Theme

    local Themes = {"Dark", "Light", "Midnight"}
    for i, name in ipairs(Themes) do
        local radio = Instance.new("TextButton")
        radio.Position = UDim2.new(0, 16, 0, 42 + (i-1)*28)
        radio.Size = UDim2.new(1, -32, 0, 24)
        radio.BackgroundTransparency = 1
        if i == 1 then
            radio.Text = "● " .. name
        else
            radio.Text = "○ " .. name
        end
        radio.TextColor3 = Colors.Text
        radio.TextSize = 11
        radio.Font = Enum.Font.Gotham
        radio.TextXAlignment = Enum.TextXAlignment.Left
        radio.AutoButtonColor = false
        radio.Parent = Theme

        radio.MouseButton1Click:Connect(function()
            for _, child in ipairs(Theme:GetChildren()) do
                if child:IsA("TextButton") then
                    child.Text = "○ " .. child.Text:gsub("^[○●]%s*", "")
                end
            end
            radio.Text = "● " .. name
        end)
    end

    local FPS = Instance.new("Frame")
    FPS.Position = UDim2.new(0.83, 0, 0, 526)
    FPS.Size = UDim2.new(0.17, -22, 1, -568)
    FPS.BackgroundColor3 = Colors.Panel
    FPS.BorderSizePixel = 0
    FPS.Parent = Content

    local FPSCorner = Instance.new("UICorner")
    FPSCorner.CornerRadius = UDim.new(0, 12)
    FPSCorner.Parent = FPS

    local FPSStroke = Instance.new("UIStroke")
    FPSStroke.Color = Colors.Border
    FPSStroke.Thickness = 1
    FPSStroke.Parent = FPS

    local FPSTitle = Instance.new("TextLabel")
    FPSTitle.BackgroundTransparency = 1
    FPSTitle.Text = "FPS BOOST"
    FPSTitle.TextColor3 = Colors.Text
    FPSTitle.TextSize = 12
    FPSTitle.Font = Enum.Font.GothamBold
    FPSTitle.TextXAlignment = Enum.TextXAlignment.Left
    FPSTitle.TextYAlignment = Enum.TextYAlignment.Center
    FPSTitle.Position = UDim2.new(0, 16, 0, 12)
    FPSTitle.Size = UDim2.new(1, -32, 0, 20)
    FPSTitle.Parent = FPS

    local circle = Instance.new("Frame")
    circle.AnchorPoint = Vector2.new(0.5, 0)
    circle.Position = UDim2.new(0.5, 0, 0, 44)
    circle.Size = UDim2.fromOffset(88, 88)
    circle.BackgroundColor3 = Color3.fromRGB(9, 9, 10)
    circle.Parent = FPS

    local circleCorner = Instance.new("UICorner")
    circleCorner.CornerRadius = UDim.new(0, 50)
    circleCorner.Parent = circle

    local circleStroke = Instance.new("UIStroke")
    circleStroke.Color = Colors.Text
    circleStroke.Thickness = 4
    circleStroke.Parent = circle

    local fpsVal = Instance.new("TextLabel")
    fpsVal.BackgroundTransparency = 1
    fpsVal.Text = "95%"
    fpsVal.TextColor3 = Colors.Text
    fpsVal.TextSize = 20
    fpsVal.Font = Enum.Font.GothamBold
    fpsVal.TextXAlignment = Enum.TextXAlignment.Center
    fpsVal.TextYAlignment = Enum.TextYAlignment.Center
    fpsVal.Size = UDim2.new(1, 0, 0, 30)
    fpsVal.Position = UDim2.new(0, 0, 0.28, 0)
    fpsVal.Parent = circle

    local fpsSub = Instance.new("TextLabel")
    fpsSub.BackgroundTransparency = 1
    fpsSub.Text = "PERFORMANCE"
    fpsSub.TextColor3 = Colors.SubText
    fpsSub.TextSize = 7
    fpsSub.Font = Enum.Font.GothamMedium
    fpsSub.TextXAlignment = Enum.TextXAlignment.Center
    fpsSub.TextYAlignment = Enum.TextYAlignment.Center
    fpsSub.Size = UDim2.new(1, 0, 0, 16)
    fpsSub.Position = UDim2.new(0, 0, 0.62, 0)
    fpsSub.Parent = circle

    local opt = Instance.new("TextButton")
    opt.Position = UDim2.new(0, 14, 1, -40)
    opt.Size = UDim2.new(1, -28, 0, 28)
    opt.BackgroundColor3 = Colors.Panel2
    opt.Text = "OPTIMIZE"
    opt.TextColor3 = Colors.Text
    opt.TextSize = 10
    opt.Font = Enum.Font.GothamBold
    opt.AutoButtonColor = false
    opt.Parent = FPS

    local optCorner = Instance.new("UICorner")
    optCorner.CornerRadius = UDim.new(0, 7)
    optCorner.Parent = opt

    local optStroke = Instance.new("UIStroke")
    optStroke.Color = Colors.Border
    optStroke.Thickness = 1
    optStroke.Parent = opt

    opt.MouseButton1Click:Connect(function()
        print("Optimize")
    end)

    local Footer = Instance.new("Frame")
    Footer.Position = UDim2.new(0, 22, 1, -32)
    Footer.Size = UDim2.new(1, -44, 0, 22)
    Footer.BackgroundTransparency = 1
    Footer.Parent = Content

    local fs = Instance.new("TextLabel")
    fs.BackgroundTransparency = 1
    fs.Text = "Script status: "
    fs.TextColor3 = Colors.Text
    fs.TextSize = 11
    fs.Font = Enum.Font.Gotham
    fs.TextXAlignment = Enum.TextXAlignment.Left
    fs.TextYAlignment = Enum.TextYAlignment.Center
    fs.Size = UDim2.fromOffset(86, 22)
    fs.Parent = Footer

    local loaded = Instance.new("TextLabel")
    loaded.BackgroundTransparency = 1
    loaded.Text = "Fully Loaded"
    loaded.TextColor3 = Colors.Green
    loaded.TextSize = 11
    loaded.Font = Enum.Font.GothamMedium
    loaded.TextXAlignment = Enum.TextXAlignment.Left
    loaded.TextYAlignment = Enum.TextYAlignment.Center
    loaded.Position = UDim2.new(0, 80, 0, 0)
    loaded.Size = UDim2.fromOffset(90, 22)
    loaded.Parent = Footer

    local ver = Instance.new("TextLabel")
    ver.BackgroundTransparency = 1
    ver.Text = "v2.5.0 | Always Undetected"
    ver.TextColor3 = Colors.SubText
    ver.TextSize = 10
    ver.Font = Enum.Font.Gotham
    ver.TextXAlignment = Enum.TextXAlignment.Right
    ver.TextYAlignment = Enum.TextYAlignment.Center
    ver.Position = UDim2.new(1, -230, 0, 0)
    ver.Size = UDim2.fromOffset(230, 22)
    ver.Parent = Footer

    local dragging = false
    local dragStart = nil
    local startPos = nil

    Header.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
            dragging = true
            dragStart = input.Position
            startPos = Main.Position
            input.Changed:Connect(function()
                if input.UserInputState == Enum.UserInputState.End then
                    dragging = false
                end
            end)
        end
    end)

    UserInputService.InputChanged:Connect(function(input)
        if not dragging then
            return
        end
        if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
            local delta = input.Position - dragStart
            Main.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
        end
    end)

    local Minimize = Instance.new("TextButton")
    Minimize.Position = UDim2.new(1, -86, 0, 22)
    Minimize.Size = UDim2.fromOffset(24, 24)
    Minimize.BackgroundTransparency = 1
    Minimize.Text = "—"
    Minimize.TextColor3 = Colors.Text
    Minimize.TextSize = 18
    Minimize.Font = Enum.Font.GothamBold
    Minimize.AutoButtonColor = false
    Minimize.Parent = Main

    local Restore = Instance.new("TextButton")
    Restore.AnchorPoint = Vector2.new(0, 1)
    Restore.Position = UDim2.new(0, 18, 1, -18)
    Restore.Size = UDim2.fromOffset(52, 52)
    Restore.BackgroundColor3 = Colors.Panel
    Restore.Text = "ZEN"
    Restore.TextColor3 = Colors.Text
    Restore.TextSize = 11
    Restore.Font = Enum.Font.GothamBold
    Restore.Visible = false
    Restore.AutoButtonColor = false
    Restore.Parent = ScreenGui

    local RestoreCorner = Instance.new("UICorner")
    RestoreCorner.CornerRadius = UDim.new(0, 50)
    RestoreCorner.Parent = Restore

    local RestoreStroke = Instance.new("UIStroke")
    RestoreStroke.Color = Colors.Border
    RestoreStroke.Thickness = 1
    RestoreStroke.Parent = Restore

    local normalSize = Main.Size

    Minimize.MouseButton1Click:Connect(function()
        TweenService:Create(Main, TweenInfo.new(0.28, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
            Size = UDim2.fromOffset(0, 0)
        }):Play()
        task.wait(0.28)
        Main.Visible = false
        Restore.Visible = true
    end)

    Restore.MouseButton1Click:Connect(function()
        Restore.Visible = false
        Main.Visible = true
        Main.Size = UDim2.fromOffset(0, 0)
        TweenService:Create(Main, TweenInfo.new(0.28, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
            Size = normalSize
        }):Play()
    end)

    local Close = Instance.new("TextButton")
    Close.Position = UDim2.new(1, -46, 0, 22)
    Close.Size = UDim2.fromOffset(24, 24)
    Close.BackgroundTransparency = 1
    Close.Text = "×"
    Close.TextColor3 = Colors.Text
    Close.TextSize = 22
    Close.Font = Enum.Font.Gotham
    Close.AutoButtonColor = false
    Close.Parent = Main

    Close.MouseButton1Click:Connect(function()
        TweenService:Create(Main, TweenInfo.new(0.22, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
            Size = UDim2.fromOffset(0, 0)
        }):Play()
        task.wait(0.25)
        ScreenGui:Destroy()
    end)

    Main.Size = UDim2.fromOffset(0, 0)
    task.wait()
    TweenService:Create(Main, TweenInfo.new(0.4, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {
        Size = normalSize
    }):Play()

    print("Zen UI loaded - Executor: " .. ExecutorName)
    return ScreenGui
end

return ZenUI
