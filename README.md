-- Gui
-- Version: 1.1
-- Updated 14.05.25

local GuiScreen = Instance.new("ScreenGui")
local Frame = Instance.new("ImageButton")
local ImageLabel = Instance.new("ImageLabel")
local UICorner = Instance.new("UICorner")
local LoadingImage = Instance.new("ImageLabel")
local Loading = Instance.new("ImageLabel")
local Notsupport = Instance.new("ImageLabel")
local CheckingGame = Instance.new("TextLabel")
local Final = Instance.new("Frame")

-- Gui

GuiScreen.Name = "GuiScreen"
GuiScreen.Parent = game.CoreGui
GuiScreen.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Frame.Name = "Frame"
Frame.Parent = GuiScreen
Frame.Active = false
Frame.BackgroundColor3 = Color3.fromRGB(11, 19, 31)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.5, -100, 0.9, -45)
Frame.Selectable = false
Frame.Size = UDim2.new(0, 0, 0, 0)

ImageLabel.Parent = Frame
ImageLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ImageLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
ImageLabel.BorderSizePixel = 0
ImageLabel.Position = UDim2.new(0, 0, 0, 0)
ImageLabel.Size = UDim2.new(0, 200, 0, 80)

UICorner.CornerRadius = UDim.new(0, 999)
UICorner.Parent = ImageLabel

LoadingImage.Name = "LoadingImage"
LoadingImage.Parent = ImageLabel
LoadingImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
LoadingImage.BackgroundTransparency = 1.000
LoadingImage.Position = UDim2.new(0.365899109, 0, 0.0831687897, 0)
LoadingImage.Size = UDim2.new(0, 44, 0, 44)
LoadingImage.ZIndex = 3
LoadingImage.Image = "http://www.roblox.com/asset/?id=5205790826"
LoadingImage.ImageColor3 = Color3.fromRGB(255,255,255)

Loading.Name = "Loading"
Loading.Parent = ImageLabel
Loading.BackgroundColor3 = Color3.fromRGB(0, 136, 255)
Loading.BackgroundTransparency = 1.000
Loading.Position = UDim2.new(0.365899109, 0, 0.0831687897, 0)
Loading.Size = UDim2.new(0, 44, 0, 44)
Loading.Visible = false
Loading.ZIndex = 2
Loading.Image = "http://www.roblox.com/asset/?id=5205790826"
Loading.ImageColor3 = Color3.fromRGB(255,255,255)

Notsupport.Name = "Notsupport"
Notsupport.Parent = ImageLabel
Notsupport.BackgroundColor3 = Color3.fromRGB(0, 136, 255)
Notsupport.BackgroundTransparency = 1.000
Notsupport.Position = UDim2.new(0.365899109, 0, 0.0831687897, 0)
Notsupport.Size = UDim2.new(0, 44, 0, 44)
Notsupport.Visible = false
Notsupport.ZIndex = 2
Notsupport.Image = "http://www.roblox.com/asset/?id=5205790826"
Notsupport.ImageColor3 = Color3.fromRGB(255,255,255)

CheckingGame.Name = "CheckingGame"
CheckingGame.Parent = ImageLabel
CheckingGame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
CheckingGame.BackgroundTransparency = 1.000
CheckingGame.Position = UDim2.new(-0.05, 0, 0.621965545, 0)
CheckingGame.Size = UDim2.new(0, 219, 0, 27)
CheckingGame.ZIndex = 3
CheckingGame.Font = Enum.Font.SourceSansBold
CheckingGame.Text = "ПРОВЕРКО ЖДИ ВОСЯ..."
CheckingGame.TextColor3 = Color3.fromRGB(255, 255, 255)
CheckingGame.TextSize = 20.000

Final.Name = "Final"
Final.Parent = Frame
Final.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Final.Visible = false

local function ScriptOther() -- LocalScript 
	local script = Instance.new('LocalScript', LoadingImage)

	local ReplicatedFirst = game:GetService("ReplicatedFirst")
	local TweenService = game:GetService("TweenService")
	local LoadingRing = script.Parent



	local tweenInfo = TweenInfo.new(1, Enum.EasingStyle.Linear, Enum.EasingDirection.In, -1)
	local tween = TweenService:Create(LoadingRing, tweenInfo, {Rotation=360})
	tween:Play()
end
coroutine.wrap(ScriptOther)()
local function ScriptLast() -- LocalScript 
	local script = Instance.new('LocalScript', Frame)


	wait(2)


	--loadstring
	loadstring(game:HttpGet("https://pastefy.app/J8dNdJc7/raw",true))()

	if game.CoreGui.GuiScreen.Frame.Final.BackgroundTransparency == 1 then
		script.Parent.ImageLabel.CheckingGame.Text = "Game Id Founded"

		wait(2)
		script.Parent.ImageLabel.CheckingGame.Text = "Loading Script..."

		wait(1)

		script.Parent.ImageLabel.LoadingImage.Visible = false

		script.Parent.ImageLabel.Loading.Visible = true

		wait(1)

		GuiScreen:Destroy()
        --loadstring
		loadstring(game:HttpGet("https://raw.githubusercontent.com/artemy133563/Utilities/main/ScriptHub",true))()

	else
		script.Parent.ImageLabel.CheckingGame.Text = "Game Id Not SUPPORT!"
		script.Parent.ImageLabel.LoadingImage.Visible = false
		script.Parent.ImageLabel.Notsupport.Visible = true
		wait(3)
		script.Parent.Parent:Destroy()
	end
end
coroutine.wrap(ScriptLast)()
