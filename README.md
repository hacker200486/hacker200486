- š Hi, Iām @hacker200486
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
hacker200486/hacker200486 is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
spawn(function()
    if AutoKillEnemies == true then
        for i,v in pairs(workspace.Pets:GetDescendants()) do
            if v.Name == "Owner" then
                if v.Value == game.Players.LocalPlayer then
                    if v.Parent.Attacking.Value == nil then
                        game:GetService("Players").LocalPlayer.CameraMaxZoomDistance = 0
                        local tweenInfo = TweenInfo.new(
                        0
                        )
                        local t = game.TweenService:Create(game.Players.LocalPlayer.Character.PrimaryPart, tweenInfo, {CFrame = CFrame.new(
                        ClosestPart().CFrame.Position + Vector3.new(0,0,0)
                        )})
                        game.Players.LocalPlayer.Character.PrimaryPart.Anchored = true 
                        t:Play()
                        wait(0)
                        mouse1press() wait() mouse1release()
                    else
                        game.Players.LocalPlayer.Character.PrimaryPart.Anchored = false
                        game:GetService("Players").LocalPlayer.CameraMaxZoomDistance = 128
                    end
                end
            end
        end
    end
end)

spawn(function()
    if AutoClickDamage == true then
        game:GetService("ReplicatedStorage").Remote.ClickerDamage:FireServer()
    end
end)

spawn(function()
    if AntiAfk == true then
        local bb=game:service'VirtualUser'
        bb:CaptureController()
        bb:ClickButton2(Vector2.new())
    end
end)
