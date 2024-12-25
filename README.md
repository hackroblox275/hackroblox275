-- Define the initial speed and the toggled speed
local normalSpeed = 16
local fastSpeed = 50
local isFast = false  -- Toggle state

-- Reference to the character and its humanoid (adjust if your setup is different)
local character = game.Players.LocalPlayer.Character
local humanoid = character:WaitForChild("Humanoid")

-- Function to toggle the speed
local function toggleSpeed()
    if isFast then
        humanoid.WalkSpeed = normalSpeed
    else
        humanoid.WalkSpeed = fastSpeed
    end
    isFast = not isFast
end

-- Event to trigger the toggle, you can replace this with your own input method
local userInputService = game:GetService("UserInputService")

-- Detect tap or click on mobile (you can replace this with button input)
userInputService.TouchTap:Connect(function()
    toggleSpeed()
end)

-- Or, if you're using a button in your game UI, you can use something like:
-- local button = script.Parent -- Assuming the script is inside the button
-- button.MouseButton1Click:Connect(function()
--     toggleSpeed()
-- end)
