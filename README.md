local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "SlapBattlesSolo",
   LoadingTitle = "Insanitgo",
loadingSubtitle = "by Solo",
 Theme = "Green", -- DarkBlue, Green, Light, Default - more coming soon!  
        
        DisableRayfieldPrompts = false,

        ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "SlapBattlesSolo",
      Subtitle = "Made By Solo",
      Note = "GO To My Yt Channel: ScripterWinner",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"SlapBattlesDaBest"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }


        
})

local MainTab = Window:CreateTab("Main", nil) -- Title, Image
Rayfield:Notify({
   Title = "Enjoy",
   Content = "Insane",
   Duration = 3,
   Image = 4483362458,
   Actions = { -- Notification Buttons

      Ignore = { -- Duplicate this table (or remove it) to add and remove buttons to the notification.
         Name = "Solo",
         Callback = function()
            print("The user tapped Okay!")
         end
      },

},
})

local Button = MainTab:CreateButton({
   Name = "Slap Aura (Hit One Person at A Time Or U will be KICKED (PUBLIC ONLY!!))",
   Callback = function()
       --[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
function isSpawned(player)
   if workspace:FindFirstChild(player.Name) and player.Character:FindFirstChild("HumanoidRootPart") then
       return true
   else
       return false
   end
end

while wait() do
   for i, v in pairs(game.Players:GetPlayers()) do
       if isSpawned(v) and v ~= game.Players.LocalPlayer and not v.Character.Head:FindFirstChild("UnoReverseCard") then
           if (v.Character.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
               game:GetService("ReplicatedStorage").b:FireServer(v.Character["Right Arm"])
               wait(0.1)
           end
       end
   end
end        
   end,
})

local Button = MainTab:CreateButton({
   Name = "Anti-Void (Press U (Mobile Use Universal Keyboard)",
   Callback = function()
       local arenaY = -50  -- Set the Y position of the arena floor (adjust as needed)
local platformSize = Vector3.new(1000, 7, 1000)  -- Slightly taller platform (height changed from 5 to 7)

local platformCreated = false  -- Variable to track if the platform is created
local platform  -- Store reference to the platform

-- Create the large platform at the same height as the arena but slightly raised
local function createArenaPlatform()
    -- Create the part that will act as the platform
    platform = Instance.new("Part")
    platform.Size = platformSize  -- Size of the platform (increased height to 7 for a little more thickness)
    platform.Position = Vector3.new(0, arenaY + 35, 0)  -- Raise platform slightly above the arena by 7
    platform.Anchored = true  -- Anchor the platform so it doesn't move
    platform.CanCollide = true  -- Make the platform collidable so players can walk on it
    platform.BrickColor = BrickColor.new("Bright blue")  -- Color of the platform (change if needed)
    platform.Parent = game.Workspace  -- Add the platform to the game workspace
end

-- Function to prevent players from falling into the void by ensuring they stand on the platform
local function preventFallingIntoVoid()
    local player = game.Players.LocalPlayer  -- Get the local player
    
    -- Wait for the character to load
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    -- Keep the player above the platform and prevent falling into the void
    while platformCreated do
        local position = humanoidRootPart.Position

        -- If the player falls below the platform Y position, make sure they stand on the platform
        if position.Y < arenaY + 35 then  -- Adjusted to prevent falling below the slightly raised platform
            -- Set the player's Y position to the platform level to stop them from falling
            local newPosition = Vector3.new(position.X, arenaY + 7, position.Z)
            humanoidRootPart.CFrame = CFrame.new(newPosition)
        end
        wait(0.1)  -- Check every 0.1 seconds to keep the player from falling
    end
end

-- Toggle function to create/remove the platform and prevent falling
local function togglePlatform()
    if platformCreated then
        -- If the platform is already created, destroy it and stop preventing falling
        if platform then
            platform:Destroy()
        end
        platformCreated = false
    else
        -- Create the platform and start preventing falling
        createArenaPlatform()
        platformCreated = true
        preventFallingIntoVoid()
    end
end

-- Listen for the "U" key press to toggle the platform
game:GetService("UserInputService").InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end  -- Ignore input that the game has already processed (like chat, etc.)

    if input.KeyCode == Enum.KeyCode.U then
        togglePlatform()
    end
end)

   end,
})

local Button = MainTab:CreateButton({
   Name = "Universal Keyboard (Use for teleports Antivoid and Others!)",
   Callback = function()
       loadstring(game:HttpGet("https://gist.githubusercontent.com/RedZenXYZ/4d80bfd70ee27000660e4bfa7509c667/raw/da903c570249ab3c0c1a74f3467260972c3d87e6/KeyBoard%2520From%2520Ohio%2520Fr%2520Fr"))()
   end,
})

local Dropdown = MainTab:CreateDropdown({
   Name = "Farms",
   Options = {"Bob Farm (20-30 mins u should MUST have enough slaps)","Coming Soon"},
   CurrentOption = {"Option 1"},
   MultipleOptions = false,
   Flag = "Dropdown1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Options)
       
   end,
})

local Button = MainTab:CreateButton({
   Name = "Hitbox",
   Callback = function()
        --[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
-- leave a like pls


_G.HeadSize = 20
_G.Disabled = true
 
game:GetService('RunService').RenderStepped:connect(function()
if _G.Disabled then
for i,v in next, game:GetService('Players'):GetPlayers() do
if v.Name ~= game:GetService('Players').LocalPlayer.Name then
pcall(function()
v.Character.HumanoidRootPart.Size = Vector3.new(_G.HeadSize,_G.HeadSize,_G.HeadSize)
v.Character.HumanoidRootPart.Transparency = 0.7
v.Character.HumanoidRootPart.BrickColor = BrickColor.new("Really blue")
v.Character.HumanoidRootPart.Material = "Neon"
v.Character.HumanoidRootPart.CanCollide = false
end)
end
end
end
end)
   end,
        
})

local Button = MainTab:CreateButton({
   Name = "AntiRagdoll",
   Callback = function()
        -- Anti Knockback Script for Roblox (For use with mycomplier.io)

-- Settings for Knockback Prevention
local preventionDuration = 0.5  -- Time to prevent knockback (seconds)
local maxForce = Vector3.new(10000, 10000, 10000)  -- Max force to block any movement
local velocityZero = Vector3.new(0, 0, 0)  -- Counteract any velocity applied to the character

-- Variables
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
local humanoid = character:WaitForChild("Humanoid")
local isFrozen = false  -- Flag to track if the character is already frozen

-- Function to freeze the character mid-air
local function freezeCharacter()
    if isFrozen then return end  -- Do nothing if already frozen

    isFrozen = true  -- Set the flag to indicate character is frozen

    -- Create a BodyVelocity to counter any knockback force
    local bodyVelocity = Instance.new("BodyVelocity")
    bodyVelocity.MaxForce = maxForce  -- Allow enough force to prevent movement
    bodyVelocity.Velocity = velocityZero  -- Set velocity to zero to stop movement
    bodyVelocity.P = 10000  -- Increase power to immediately stop velocity
    bodyVelocity.Parent = humanoidRootPart  -- Attach it to the character's root part

    -- Freeze for the duration
    wait(preventionDuration)

    -- After the freeze duration, remove the BodyVelocity to allow movement again
    bodyVelocity:Destroy()

    -- Reset the frozen flag to allow next freeze
    isFrozen = false
end

-- Listen for hits (e.g., slaps or collisions)
humanoidRootPart.Touched:Connect(function(hitPart)
    -- Check if the hit part is from a valid source (e.g., another player or ability)
    -- This condition will ignore the blue hitbox and other irrelevant collisions

    -- Check if the hit part belongs to a slap or a specific part
    if hitPart and hitPart.Parent and hitPart.Parent:FindFirstChild("Humanoid") then
        -- Only freeze if the hit is from a slap (or other specific part)
        freezeCharacter()
    end

    -- Check if the hitPart is part of the blue hitbox and do not freeze in that case
    if hitPart.Name == "BlueHitbox" then  -- Change "BlueHitbox" to your hitbox part's name
        return  -- Don't freeze the character when entering the blue hitbox
    end

    -- Add other conditions for other unwanted hitboxes if needed
end)
          
   end,
})
local MainTab = Window:CreateTab("Local", 4483362458) -- Title, Image
local Slider = MainTab:CreateSlider({
   Name = "Walkspeed (Max 300)",
   Range = {0, 300},
   Increment = 1,
   Suffix = "Speed",
   CurrentValue = 16,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = (Value)
   end,
})
local Slider = MainTab:CreateSlider({
   Name = "JumpPower (Max 400)",
   Range = {0, 400},
   Increment = 1,
   Suffix = "LOOK HES FLYING",
   CurrentValue = 16,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = (Value)
   end,
})

local MainTab = Window:CreateTab("Scripts", 4483362458) -- Title, Image
local Button = MainTab:CreateButton({
   Name = "Kill All OP (NotMadeByMe",
   Callback = function()
       loadstring(game:HttpGet("https://pastebin.com/raw/73hrme5T"))()
   end,
})

local Button = MainTab:CreateButton({
   Name = "Become Diddy (Key: (iammusic) No Capitals  (FUCK ALL))",
   Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/1price/usercreation/refs/heads/main/UserCreation.lua", true))()
   end,
})

local Button = MainTab:CreateButton({
   Name = "Animation FE (Fucking Insane)",
   Callback = function()
       loadstring(game:HttpGet(('https://pastebin.com/raw/1p6xnBNf'),true))()
   end,
})

local Button = MainTab:CreateButton({
   Name = "Inf Yield (NotMadeByMe)",
   Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
   end,
})

local Button = MainTab:CreateButton({
   Name = "Fly Gui V3 (NotMadeByMe)",
   Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/XNEOFF/FlyGuiV3/main/FlyGuiV3.txt"))()
   end,
})

local MiscTab = Window:CreateTab("Misc", nil) -- Title, Image
local Button = MiscTab:CreateButton({
   Name = "Teleport To Slaply (Press T PC ONLY)",
   Callback = function()
        -- Teleport Script for Slap Battles to Slaply Island

-- Correct coordinates for Slaply Island
local slaplyIslandPosition = Vector3.new(-393.1788330078125, 50.764225006103516, -13.747956275939941)  -- Slaply Island's location (Y = 1100)

-- Optional safety margin to ensure player lands on the island properly
local teleportSafetyMargin = 10  -- A buffer to prevent the player from getting stuck inside the island

-- Get the player and their character
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

-- Function to teleport the player to Slaply Island
local function teleportToSlaplyIsland()
    -- Ensure the character exists
    if character and humanoidRootPart then
        -- Set the character's position to a safe location above Slaply Island
        humanoidRootPart.CFrame = CFrame.new(slaplyIslandPosition + Vector3.new(0, teleportSafetyMargin, 0))
    end
end

-- Connect the teleport function to the `T` key press
game:GetService("UserInputService").InputBegan:Connect(function(input, gameProcessedEvent)
    -- Ignore input if it's processed by other game controls (like chat)
    if gameProcessedEvent then return end
    
    -- Check if the player pressed the "T" key
    if input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.T then
        -- Teleport the player to Slaply Island
        teleportToSlaplyIsland()
    end
end)

   end,
})

local Button = MiscTab:CreateButton({
   Name = "Teleport To Moai (Press R PC ONLY)",
   Callback = function()
        -- Teleport Script for Slap Battles to Moai Location

-- Correct coordinates for Moai location
local moaiPosition = Vector3.new(213.720458984375, -15.716063499450684, -10.204557418823242)  -- Moai statue position (Y = 100, Z = -1000)

-- Optional safety margin to ensure the player lands safely
local teleportSafetyMargin = 10  -- A small buffer to ensure the player doesn't fall through or collide

-- Get the player and their character
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

-- Function to teleport the player to Moai
local function teleportToMoai()
    -- Ensure the character exists
    if character and humanoidRootPart then
        -- Set the character's position to the Moai location
        humanoidRootPart.CFrame = CFrame.new(moaiPosition + Vector3.new(0, teleportSafetyMargin, 0))
    end
end

-- Connect the teleport function to the `R` key press
game:GetService("UserInputService").InputBegan:Connect(function(input, gameProcessedEvent)
    -- Ignore input if it's processed by other game controls (like chat)
    if gameProcessedEvent then return end
    
    -- Check if the player pressed the "R" key
    if input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.R then
        -- Teleport the player to Moai
        teleportToMoai()
    end
end)

   end,
})

local Button = MiscTab:CreateButton({
   Name = "Teleport To Default (Press Y PC ONLY)",
   Callback = function()
        -- Teleport Script for Slap Battles to Moai Location

-- Correct coordinates for Moai location
local moaiPosition = Vector3.new(142.1498565673828, 359.9842224121094, -3.7191057205200195)  -- Moai statue position (Y = 100, Z = -1000)

-- Optional safety margin to ensure the player lands safely
local teleportSafetyMargin = 10  -- A small buffer to ensure the player doesn't fall through or collide

-- Get the player and their character
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

-- Function to teleport the player to Moai
local function teleportToMoai()
    -- Ensure the character exists
    if character and humanoidRootPart then
        -- Set the character's position to the Moai location
        humanoidRootPart.CFrame = CFrame.new(moaiPosition + Vector3.new(0, teleportSafetyMargin, 0))
    end
end

-- Connect the teleport function to the `Y` key press
game:GetService("UserInputService").InputBegan:Connect(function(input, gameProcessedEvent)
    -- Ignore input if it's processed by other game controls (like chat)
    if gameProcessedEvent then return end
    
    -- Check if the player pressed the "Y" key
    if input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.Y then
        -- Teleport the player to Moai
        teleportToMoai()
    end
end)

   end,
})

local Button = MiscTab:CreateButton({
   Name = "Teleport To Slaply (Mobile Tap On It)",
   Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-395.93182373046875, 50.764225006103516, -16.913148880004883)
   end,
})

local Button = MiscTab:CreateButton({
   Name = "Teleport To Moai (Mobile Tap On It)",
   Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(208.78582763671875, -15.716063499450684, -8.843342781066895)
   end,
})

local Button = MiscTab:CreateButton({
   Name = "Teleport To Default (Mobile Tap On It)",
   Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(134.2162322998047, 359.9842224121094, -15.451227188110352)
   end,
})

local MainTab = Window:CreateTab("Badges", nil) -- Title, Image
local Button = MainTab:CreateButton({
   Name = "Get Untitled Glove (X2 Execution)",
   Callback = function()
        if game.PlaceId ~= 115782629143468 then
game:GetService("TeleportService"):Teleport(115782629143468)
else
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(0, 250, 0)
end
--You can execute this script two time, i mean use it in slap battle to teleport to Toh and execute it again to get the glove.
   end,
}) 

local Button = MainTab:CreateButton({
   Name = "Get Frost Bite Glove (X2 Execution)",
   Callback = function()
       if  game.PlaceId ~= 17290438723 then
game:GetService("TeleportService"):Teleport(17290438723)
elseif game.PlaceId == 17290438723 then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-558, 182, 54)
local function fireAllProximityPrompts()
    for _, descendant in ipairs(workspace:GetDescendants()) do
        if descendant:IsA("ProximityPrompt") then
            fireproximityprompt(descendant)
        end
    end
end

-- Trigger all ProximityPrompts
fireAllProximityPrompts()
end
   end,
})


local MainTab = Window:CreateTab("Extra", 4483362458) -- Title, Image
local Button = MainTab:CreateButton({
   Name = "ServerHop",
   Callback = function()
       local teleportService = game:GetService("TeleportService")
local players = game:GetService("Players")
local placeId = game.PlaceId  -- Get the current place ID

-- Function to hop to another server
local function serverHop()
    -- Use TeleportService to find a different server in the current place
    local success, result = pcall(function()
        teleportService:TeleportToPlaceInstance(placeId, game.JobId)
    end)

    if success then
        print("Successfully hopped to another server!")
    else
        warn("Failed to hop to another server: " .. tostring(result))
    end
end

-- Call the function to perform the server hop
serverHop()

   end,
})

local Button = MainTab:CreateButton({
   Name = "Rejoin",
   Callback = function(Value)
        local teleportService = game:GetService("TeleportService")
local players = game:GetService("Players")
local placeId = game.PlaceId  -- Get the current game place ID
local jobId = game.JobId      -- Get the current server (job) ID

-- Function to rejoin the same server
local function rejoinGame()
    -- Teleport the player back to the same game server they are currently in
    teleportService:TeleportToPlaceInstance(placeId, jobId, players.LocalPlayer)
end

-- Execute the function to rejoin the game
rejoinGame()

   end,
})

local Button = MainTab:CreateButton({
   Name = "Teleport Back To (Slap Battles)",
   Callback = function()
       -- Get the TeleportService
local teleportService = game:GetService("TeleportService")

-- The Game ID of the target game you want to teleport to
local targetGameID = 6403373529 -- Replace with the target Game ID you want to teleport to

-- Function to teleport the player to the target game
local function teleportToGame()
    local player = game.Players.LocalPlayer -- Get the local player
    teleportService:Teleport(targetGameID, player) -- Teleport the player
end

-- Execute the teleportation function
teleportToGame()

   end,
})

local MainTab = Window:CreateTab("Games Teleport", 4483362458) -- Title, Image
local Button = MainTab:CreateButton({
   Name = "Adopt Me",
   Callback = function()
       -- Get the TeleportService
local teleportService = game:GetService("TeleportService")

-- The Game ID of the target game you want to teleport to
local targetGameID = 920587237 -- Replace with the target Game ID you want to teleport to

-- Function to teleport the player to the target game
local function teleportToGame()
    local player = game.Players.LocalPlayer -- Get the local player
    teleportService:Teleport(targetGameID, player) -- Teleport the player
end

-- Execute the teleportation function
teleportToGame()

   end,
})

local Button = MainTab:CreateButton({
   Name = "MM2",
   Callback = function()
       -- Get the TeleportService
local teleportService = game:GetService("TeleportService")

-- The Game ID of the target game you want to teleport to
local targetGameID = 142823291 -- Replace with the target Game ID you want to teleport to

-- Function to teleport the player to the target game
local function teleportToGame()
    local player = game.Players.LocalPlayer -- Get the local player
    teleportService:Teleport(targetGameID, player) -- Teleport the player
end

-- Execute the teleportation function
teleportToGame()

   end,
})

local Button = MainTab:CreateButton({
   Name = "More Coming Soon",
   Callback = function()
   -- The function that takes place when the button is pressed
   end,
})
