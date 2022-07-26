

        local ScreenGui = Instance.new("ScreenGui")
        local ImageButton = Instance.new("ImageButton")
        local UICorner = Instance.new("UICorner")
        
        
        ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
        ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
        
        ImageButton.Parent = ScreenGui
        ImageButton.BackgroundColor3 = Color3.fromRGB(236,45,0)
        ImageButton.BorderSizePixel = 0
        ImageButton.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
        ImageButton.Size = UDim2.new(0, 50, 0, 50)
        ImageButton.Image = "http://www.roblox.com/asset/?id"
        ImageButton.MouseButton1Down:connect(function()
            game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
            game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
        end)
        
        do local GUI = game.CoreGui:FindFirstChild("SOMEXHUB");if GUI then GUI:Destroy();end;if _G.Color == nil then
            _G.Color = Color3.fromRGB(255,0,247)
        end 
        end
        
        local UserInputService = game:GetService("UserInputService")
        local TweenService = game:GetService("TweenService")
        
        local function MakeDraggable(topbarobject, object)
         local Dragging = nil
         local DragInput = nil
         local DragStart = nil
         local StartPosition = nil
        
         local function Update(input)
             local Delta = input.Position - DragStart
             local pos = UDim2.new(StartPosition.X.Scale, StartPosition.X.Offset + Delta.X, StartPosition.Y.Scale, StartPosition.Y.Offset + Delta.Y)
             local Tween = TweenService:Create(object, TweenInfo.new(0.15), {Position = pos})
             Tween:Play()
         end
        
         topbarobject.InputBegan:Connect(
             function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                     Dragging = true
                     DragStart = input.Position
                     StartPosition = object.Position
        
                     input.Changed:Connect(
                         function()
                             if input.UserInputState == Enum.UserInputState.End then
                                 Dragging = false
                             end
                         end
                     )
                 end
             end
         )
        
         topbarobject.InputChanged:Connect(
             function(input)
                 if
                     input.UserInputType == Enum.UserInputType.MouseMovement or
                     input.UserInputType == Enum.UserInputType.Touch
                 then
                     DragInput = input
                 end
             end
         )
        
         UserInputService.InputChanged:Connect(
             function(input)
                 if input == DragInput and Dragging then
                     Update(input)
                 end
             end
         )
        end
        
        local Update = {}
        
        function Update:Window(text,logo,keybind)
         local uihide = false
         local abc = false
         local logo = logo or 0
         local currentpage = ""
         local keybind = keybind or Enum.KeyCode.RightControl
         local yoo = string.gsub(tostring(keybind),"Enum.KeyCode.","")
         
         local SOMEXHUB = Instance.new("ScreenGui")
         SOMEXHUB.Name = "SOMEXHUB"
         SOMEXHUB.Parent = game.CoreGui
         SOMEXHUB.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
        
         local Main = Instance.new("Frame")
         Main.Name = "Main"
         Main.Parent = SOMEXHUB
         Main.ClipsDescendants = true
         Main.AnchorPoint = Vector2.new(0.5,0.5)
         Main.BackgroundColor3 = Color3.fromRGB(45, 255, 45)
         Main.Position = UDim2.new(0.5, 0, 0.5, 0)
         Main.Size = UDim2.new(0, 0, 0, 0)
         
         Main:TweenSize(UDim2.new(0, 656, 0, 400),"Out","Quad",0.4,true)
        
         local MCNR = Instance.new("UICorner")
         MCNR.Name = "MCNR"
         MCNR.Parent = Main
        
         local Top = Instance.new("Frame")
         Top.Name = "Top"
         Top.Parent = Main
         Top.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
         Top.Size = UDim2.new(0, 656, 0, 27)
        
         local TCNR = Instance.new("UICorner")
         TCNR.Name = "TCNR"
         TCNR.Parent = Top
        
         local Logo = Instance.new("ImageLabel")
         Logo.Name = "Logo"
         Logo.Parent = Top
         Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 45)
         Logo.BackgroundTransparency = 1.000
         Logo.Position = UDim2.new(0, 10, 0, 1)
         Logo.Size = UDim2.new(0, 25, 0, 25)
         Logo.Image = "rbxassetid://"..tostring(logo)
        
         local Name = Instance.new("TextLabel")
         Name.Name = "Name"
         Name.Parent = Top
         Name.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
         Name.BackgroundTransparency = 1.000
         Name.Position = UDim2.new(0.0609756112, 0, 0, 0)
         Name.Size = UDim2.new(0, 61, 0, 27)
         Name.Font = Enum.Font.GothamSemibold
         Name.Text = text
         Name.TextColor3 = Color3.fromRGB(225, 225, 225)
         Name.TextSize = 17.000
        
         local Hub = Instance.new("TextLabel")
         Hub.Name = "Hub"
         Hub.Parent = Top
         Hub.BackgroundColor3 = Color3.fromRGB(255, 255, 45)
         Hub.BackgroundTransparency = 1.000
         Hub.Position = UDim2.new(0, 110, 0, 0)
         Hub.Size = UDim2.new(0, 81, 0, 27)
         Hub.Font = Enum.Font.GothamSemibold
         Hub.Text = ""
         Hub.TextColor3 = _G.Color
         Hub.TextSize = 17.000
         Hub.TextXAlignment = Enum.TextXAlignment.Left
        
         local BindButton = Instance.new("TextButton")
         BindButton.Name = "BindButton"
         BindButton.Parent = Top
         BindButton.BackgroundColor3 = Color3.fromRGB(247, 255, 45)
         BindButton.BackgroundTransparency = 1.000
         BindButton.Position = UDim2.new(0.847561002, 0, 0, 0)
         BindButton.Size = UDim2.new(0, 100, 0, 27)
         BindButton.Font = Enum.Font.GothamSemibold
         BindButton.Text = "[ "..string.gsub(tostring(keybind),"Enum.KeyCode.","").." ]"
         BindButton.TextColor3 = Color3.fromRGB(100, 100, 100)
         BindButton.TextSize = 11.000
         
         BindButton.MouseButton1Click:Connect(function ()
             BindButton.Text = "[ ... ]"
             local inputwait = game:GetService("UserInputService").InputBegan:wait()
             local shiba = inputwait.KeyCode == Enum.KeyCode.Unknown and inputwait.UserInputType or inputwait.KeyCode
        
             if shiba.Name ~= "Focus" and shiba.Name ~= "MouseMovement" then
                 BindButton.Text = "[ "..shiba.Name.." ]"
                 yoo = shiba.Name
             end
         end)
        
         local Tab = Instance.new("Frame")
         Tab.Name = "Tab"
         Tab.Parent = Main
         Tab.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
         Tab.Position = UDim2.new(0, 5, 0, 30)
         Tab.Size = UDim2.new(0, 150, 0, 365)
        
         local TCNR = Instance.new("UICorner")
         TCNR.Name = "TCNR"
         TCNR.Parent = Tab
        
         local ScrollTab = Instance.new("ScrollingFrame")
         ScrollTab.Name = "ScrollTab"
         ScrollTab.Parent = Tab
         ScrollTab.Active = true
         ScrollTab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
         ScrollTab.BackgroundTransparency = 1.000
         ScrollTab.Size = UDim2.new(0, 150, 0, 365)
         ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
         ScrollTab.ScrollBarThickness = 0
        
         local PLL = Instance.new("UIListLayout")
         PLL.Name = "PLL"
         PLL.Parent = ScrollTab
         PLL.SortOrder = Enum.SortOrder.LayoutOrder
         PLL.Padding = UDim.new(0, 15)
        
         local PPD = Instance.new("UIPadding")
         PPD.Name = "PPD"
         PPD.Parent = ScrollTab
         PPD.PaddingLeft = UDim.new(0, 10)
         PPD.PaddingTop = UDim.new(0, 10)
        
         local Page = Instance.new("Frame")
         Page.Name = "Page"
         Page.Parent = Main
         Page.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
         Page.Position = UDim2.new(0.245426834, 0, 0.075000003, 0)
         Page.Size = UDim2.new(0, 490, 0, 365)
        
         local PCNR = Instance.new("UICorner")
         PCNR.Name = "PCNR"
         PCNR.Parent = Page
        
         local MainPage = Instance.new("Frame")
         MainPage.Name = "MainPage"
         MainPage.Parent = Page
         MainPage.ClipsDescendants = true
         MainPage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
         MainPage.BackgroundTransparency = 1.000
         MainPage.Size = UDim2.new(0, 490, 0, 365)
        
         local PageList = Instance.new("Folder")
         PageList.Name = "PageList"
         PageList.Parent = MainPage
        
         local UIPageLayout = Instance.new("UIPageLayout")
        
         UIPageLayout.Parent = PageList
         UIPageLayout.SortOrder = Enum.SortOrder.LayoutOrder
         UIPageLayout.EasingDirection = Enum.EasingDirection.InOut
         UIPageLayout.EasingStyle = Enum.EasingStyle.Quad
         UIPageLayout.FillDirection = Enum.FillDirection.Vertical
         UIPageLayout.Padding = UDim.new(0, 15)
         UIPageLayout.TweenTime = 0.400
         UIPageLayout.GamepadInputEnabled = false
         UIPageLayout.ScrollWheelInputEnabled = false
         UIPageLayout.TouchInputEnabled = false
         
         MakeDraggable(Top,Main)
        
         UserInputService.InputBegan:Connect(function(input)
             if input.KeyCode == Enum.KeyCode[yoo] then
                 if uihide == false then
                     uihide = true
                     Main:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
                 else
                     uihide = false
                     Main:TweenSize(UDim2.new(0, 656, 0, 400),"Out","Quad",0.4,true)
                 end
             end
         end)
         
         local uitab = {}
         
         function uitab:Tab(text)
             local TabButton = Instance.new("TextButton")
             TabButton.Parent = ScrollTab
             TabButton.Name = text.."Server"
             TabButton.Text = text
             TabButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
             TabButton.BackgroundTransparency = 1.000
             TabButton.Size = UDim2.new(0, 130, 0, 23)
             TabButton.Font = Enum.Font.GothamSemibold
             TabButton.TextColor3 = Color3.fromRGB(225, 225, 225)
             TabButton.TextSize = 15.000
             TabButton.TextTransparency = 0.500
        
             local MainFramePage = Instance.new("ScrollingFrame")
             MainFramePage.Name = text.."_Page"
             MainFramePage.Parent = PageList
             MainFramePage.Active = true
             MainFramePage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
             MainFramePage.BackgroundTransparency = 1.000
             MainFramePage.BorderSizePixel = 0
             MainFramePage.Size = UDim2.new(0, 490, 0, 365)
             MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
             MainFramePage.ScrollBarThickness = 0
             
             local UIPadding = Instance.new("UIPadding")
             local UIListLayout = Instance.new("UIListLayout")
             
             UIPadding.Parent = MainFramePage
             UIPadding.PaddingLeft = UDim.new(0, 10)
             UIPadding.PaddingTop = UDim.new(0, 10)
        
             UIListLayout.Padding = UDim.new(0,15)
             UIListLayout.Parent = MainFramePage
             UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
             
             TabButton.MouseButton1Click:Connect(function()
                 for i,v in next, ScrollTab:GetChildren() do
                     if v:IsA("TextButton") then
                         TweenService:Create(
                             v,
                             TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
                         
