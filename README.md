if game.CoreGui:FindFirstChild("LibraryGui") then
	game.CoreGui.LibraryGui:Destroy()
end

local Library = {}

function Library:Window(Name)
	
	local LibraryGui = Instance.new("ScreenGui")
	local Window = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local TopBar = Instance.new("Frame")
	local UICorner_2 = Instance.new("UICorner")
	local Close = Instance.new("ImageLabel")
	local HubName = Instance.new("TextLabel")

	local UIS = game:GetService("UserInputService")

	UIS.InputBegan:Connect(function(keyCode)
		if keyCode.KeyCode == Enum.KeyCode.Delete then
            Window.Visible = not Window.Visible
		end
	end)

	LibraryGui.Name = "LibraryGui"
	LibraryGui.Parent = game.CoreGui
	LibraryGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	Window.Name = "Window"
	Window.Parent = LibraryGui
	Window.BackgroundColor3 = Color3.fromRGB(29, 29, 29)
	Window.BorderSizePixel = 0
	Window.Position = UDim2.new(0.19329609, 0, 0.236162364, 0)
	Window.Size = UDim2.new(0, 548, 0, 285)

	UICorner.CornerRadius = UDim.new(0, 6)
	UICorner.Parent = Window

	TopBar.Name = "TopBar"
	TopBar.Parent = Window
	TopBar.BackgroundColor3 = Color3.fromRGB(93, 93, 93)
	TopBar.Position = UDim2.new(0.0109489048, 0, 0.0210526325, 0)
	TopBar.Size = UDim2.new(0, 536, 0, 36)

	UICorner_2.CornerRadius = UDim.new(0, 3)
	UICorner_2.Parent = TopBar

	Close.Name = "Close"
	Close.Parent = TopBar
	Close.BackgroundTransparency = 1.000
	Close.Position = UDim2.new(0.958955228, 0, 0.305555552, 0)
	Close.Size = UDim2.new(0, 13, 0, 13)
	Close.Image = "rbxassetid://6236220207"
	
	Close.MouseButton1Click:Connect(function()
      LibraryGui:Destroy()
	end)
	
	HubName.Name = "HubName"
	HubName.Parent = TopBar
	HubName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	HubName.BackgroundTransparency = 1.000
	HubName.Position = UDim2.new(0.0111940298, 0, 0, 0)
	HubName.Size = UDim2.new(0, 500, 0, 36)
	HubName.Font = Enum.Font.Unknown
	HubName.Text = Name or "Where The Name Of The Hub Bro???"
	HubName.TextColor3 = Color3.fromRGB(255, 255, 255)
	HubName.TextScaled = true
	HubName.TextSize = 14.000
	HubName.TextWrapped = true
	
	Close.MouseEnter:Connect(function()
		Close.ImageColor3 = Color3.fromRGB(255, 28, 28)
	end)
	
	Close.MouseLeave:Connect(function()
		Close.ImageColor3 = Color3.fromRGB(255, 255, 255)
	end)
end
return Library


