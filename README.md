# pcall(function()
    repeat wait() until game:IsLoaded()
    repeat wait() until game:GetService("Players")
    repeat wait() until game:GetService("Players").LocalPlayer
    repeat wait() until game:GetService("Players").LocalPlayer.PlayerGui
    repeat wait() until game:GetService("ReplicatedStorage").Effect.Container

    if not game:IsLoaded() then
        local Loaded = Instance.new("Message",workspace)
        Loaded.Text = 'Wait Game Loading'
        game.Loaded:Wait()
        Loaded:Destroy()
        task.wait(10)
    end

    repeat wait()
        if game.Players.LocalPlayer.Team == nil and game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Visible == true then
            
                game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
                game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
                game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
                wait(.5)
                game:service'VirtualInputManager':SendMouseButtonEvent(500,500, 0, true, game, 1)
                game:service'VirtualInputManager':SendMouseButtonEvent(500,500, 0, false, game, 1)
        end    
        
    until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded()
    if game.PlaceId == 2753915549 then
        W = true
    elseif game.PlaceId == 4442272183 then
        W2 = true
    elseif game.PlaceId == 7449423635 then
        W3 = true
    end
    function topos(Pos)
        Distance = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
        if game.Players.LocalPlayer.Character.Humanoid.Sit == true then game.Players.LocalPlayer.Character.Humanoid.Sit = false end
        pcall(function() tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(Distance/210, Enum.EasingStyle.Linear),{CFrame = Pos}) end)
        tween:Play()
        if Distance <= 250 then
            tween:Cancel()
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Pos
        end
       
    end
    function ByPass(Position)
        game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Position
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")

    end
    --------------------
    getgenv().farm = true
    _G.kill = true
    _G.equip = false
    _G.saber = false
    farm = false
    equip = false
    function CheckQuest() 
        Level = game:GetService("Players").LocalPlayer.Data.Level.Value
        if W then
            if Level == 1 or Level <= 9 then
                Mon = "Bandit [Lv. 5]"
                LQuest = 1
                NQuest = "BanditQuest1"
                NameMon = "Bandit"
                CFrameQuest = CFrame.new(1059.75586, 16.3627472, 1548.59851, -0.987375617, 1.39881342e-08, 0.158396393, 2.30001458e-08, 1, 5.50621735e-08, -0.158396393, 5.80101869e-08, -0.987375617)
                CFramemon = CFrame.new(1037.43994140625, 80.64015197753906, 1594.4931640625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 10 or Level <= 14 then
                Mon = "Monkey [Lv. 14]"
                LQuest = 1
                NQuest = "JungleQuest"
                NameMon = "Monkey"
                CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
                CFramemon = CFrame.new(-1631.551513671875, 37.97154235839844, 131.1148223876953)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 15 or Level <= 19 then
                Mon = "Gorilla [Lv. 20]"
                LQuest = 2
                NQuest = "JungleQuest"
                NameMon = "Gorilla"
                CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
                CFramemon = CFrame.new(-1201.2413330078125, 7.6906514167785645, -447.7992248535156)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 20 or Level <= 59 then
                Mon = "God's Guard [Lv. 450]"
                LQuest = 1
                NQuest = "SkyExp1Quest"
                NameMon = "God's Guard"
                CFrameQuest = CFrame.new(-4721.88867, 843.874695, -1949.96643, 0.996191859, -0, -0.0871884301, 0, 1, -0, 0.0871884301, 0, 0.996191859)
                CFramemon = CFrame.new(-4624.54150390625, 866.9027709960938, -1940.4219970703125)
                for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main:GetChildren()) do
                    if v.Name == "Quest" then
                    v.Visible = true
                    end
                    
                
                end
                for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle:GetChildren()) do
                    if v.Name == "Title" then
                        v.Text = "God's Guard"
                    end
                
                
                
                end
                if getgenv().farm and (CFramemon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFramemon)
                end
            elseif Level == 60 or Level <= 149 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                while wait() do
                    if _G.start and _G.kill then
                        farm = false
                        if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
                        elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then  
                            for i,v in pairs(game:GetService("Players"):GetChildren()) do
                                if  string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,v.Name) then
                                    repeat wait(.1)
                                        topos(game.Players[v.Name].Character.HumanoidRootPart.CFrame * CFrame.new(0,0,10))
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
                                        game:GetService("VirtualInputManager"):SendKeyEvent(true,120,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
                                        game:GetService("VirtualInputManager"):SendKeyEvent(false,120,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
                                    until game.Players[v.Name].Character.Humanoid.Health >= 0 or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                end
                            end 
                        end    
                    end
                end    
            elseif Level == 150 or Level <= 174 then
                Mon = "Sky Bandit [Lv. 150]"
                LQuest = 1
                NQuest = "SkyQuest"
                NameMon = "Sky Bandit"
                CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
                CFramemon = CFrame.new(-4955.0029296875, 358.6697998046875, -2906.887451171875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 175 or Level <= 189 then
                Mon = "Dark Master [Lv. 175]"
                LQuest = 2
                NQuest = "SkyQuest"
                NameMon = "Dark Master"
                CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
                CFramemon = CFrame.new(-5226.1923828125, 429.4580078125, -2280.237548828125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 190 or Level <= 209 then
                Mon = "Prisoner [Lv. 190]"
                LQuest = 1
                NQuest = "PrisonerQuest"
                NameMon = "Prisoner"
                CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
                CFramemon = CFrame.new(5297.5810546875, 72.65214538574219, 360.3554382324219)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 210 or Level <= 249 then
                Mon = "Prisoner [Lv. 190]"
                LQuest = 1
                NQuest = "PrisonerQuest"
                NameMon = "Prisoner"
                CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
                CFramemon = CFrame.new(5297.5810546875, 72.65214538574219, 360.3554382324219)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 250 or Level <= 274 then
                Mon = "Toga Warrior [Lv. 250]"
                LQuest = 1
                NQuest = "ColosseumQuest"
                NameMon = "Toga Warrior"
                CFrameQuest = CFrame.new(-1580.04663, 6.35000277, -2986.47534, -0.515037298, 0, -0.857167721, 0, 1, 0, 0.857167721, 0, -0.515037298)
                CFramemon = CFrame.new(-1776.0101318359375, 43.565528869628906, -2735.54931640625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 275 or Level <= 299 then
                Mon = "Gladiator [Lv. 275]"
                LQuest = 2
                NQuest = "ColosseumQuest"
                NameMon = "Gladiator"
                CFrameQuest = CFrame.new(-1580.04663, 6.35000277, -2986.47534, -0.515037298, 0, -0.857167721, 0, 1, 0, 0.857167721, 0, -0.515037298)
                CFramemon = CFrame.new(-1330.1435546875, 58.61536407470703, -3229.501708984375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 300 or Level <= 324 then
                Mon = "Military Soldier [Lv. 300]"
                LQuest = 1
                NQuest = "MagmaQuest"
                NameMon = "Military Soldier"
                CFrameQuest = CFrame.new(-5313.37012, 10.9500084, 8515.29395, -0.499959469, 0, 0.866048813, 0, 1, 0, -0.866048813, 0, -0.499959469)
                CFramemon = CFrame.new(-5423.5283203125, 10.413415908813477, 8440.9404296875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 325 or Level <= 374 then
                Mon = "Military Spy [Lv. 325]"
                LQuest = 2
                NQuest = "MagmaQuest"
                NameMon = "Military Spy"
                CFrameQuest = CFrame.new(-5313.37012, 10.9500084, 8515.29395, -0.499959469, 0, 0.866048813, 0, 1, 0, -0.866048813, 0, -0.499959469)
                CFramemon = CFrame.new(-5775.0439453125, 119.1070327758789, 8813.14453125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 375 or Level <= 399 then
                Mon = "Fishman Warrior [Lv. 375]"
                LQuest = 1
                NQuest = "FishmanQuest"
                NameMon = "Fishman Warrior"
                CFrameQuest = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                CFramemon = CFrame.new(60947.69140625, 48.673519134521484, 1551.0787353515625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                end
            elseif Level == 400 or Level <= 449 then
                Mon = "Fishman Commando [Lv. 400]"
                LQuest = 2
                NQuest = "FishmanQuest"
                NameMon = "Fishman Commando"
                CFrameQuest = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                CFramemon = CFrame.new(61890.03515625, 75.47235107421875, 1397.786865234375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                end
            elseif Level == 450 or Level <= 474 then
                Mon = "God's Guard [Lv. 450]"
                LQuest = 1
                NQuest = "SkyExp1Quest"
                NameMon = "God's Guard"
                CFrameQuest = CFrame.new(-4721.88867, 843.874695, -1949.96643, 0.996191859, -0, -0.0871884301, 0, 1, -0, 0.0871884301, 0, 0.996191859)
                CFramemon = CFrame.new(-4624.54150390625, 866.9027709960938, -1940.4219970703125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 475 or Level <= 524 then
                Mon = "Shanda [Lv. 475]"
                LQuest = 2
                NQuest = "SkyExp1Quest"
                NameMon = "Shanda"
                CFrameQuest = CFrame.new(-7859.09814, 5544.19043, -381.476196, -0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, -0.422592998)
                CFramemon = CFrame.new(-7687.546875, 5600.83740234375, -440.55242919921875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 525 or Level <= 549 then
                Mon = "Royal Squad [Lv. 525]"
                LQuest = 1
                NQuest = "SkyExp2Quest"
                NameMon = "Royal Squad"
                CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-7632.59716796875, 5637.08056640625, -1404.517822265625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 550 or Level <= 624 then
                Mon = "Royal Soldier [Lv. 550]"
                LQuest = 2
                NQuest = "SkyExp2Quest"
                NameMon = "Royal Soldier"
                CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-7834.904296875, 5680.8173828125, -1791.9239501953125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 625 or Level <= 649 then
                Mon = "Galley Pirate [Lv. 625]"
                LQuest = 1
                NQuest = "FountainQuest"
                NameMon = "Galley Pirate"
                CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
                CFramemon = CFrame.new(5550.33837890625, 78.90135192871094, 3923.0048828125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level >= 650 then
                Mon = "Galley Captain [Lv. 650]"
                LQuest = 2
                NQuest = "FountainQuest"
                NameMon = "Galley Captain"
                CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
                CFramemon = CFrame.new(5780.630859375, 115.52667999267578, 4800.859375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            end
        elseif W2 then
            if Level == 700 or Level <= 724 then
                Mon = "Raider [Lv. 700]"
                LQuest = 1
                NQuest = "Area1Quest"
                NameMon = "Raider"
                CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
                CFramemon = CFrame.new(-653.7174072265625, 39.135799407958984, 2387.494384765625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 725 or Level <= 774 then
                Mon = "Mercenary [Lv. 725]"
                LQuest = 2
                NQuest = "Area1Quest"
                NameMon = "Mercenary"
                CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
                CFramemon = CFrame.new(-959.2958984375, 80.63091278076172, 1690.692626953125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 775 or Level <= 799 then
                Mon = "Swan Pirate [Lv. 775]"
                LQuest = 1
                NQuest = "Area2Quest"
                NameMon = "Swan Pirate"
                CFrameQuest = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
                CFramemon = CFrame.new(965.701904296875, 141.96263122558594, 1216.7733154296875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 800 or Level <= 874 then
                Mon = "Factory Staff [Lv. 800]"
                NQuest = "Area2Quest"
                LQuest = 2
                NameMon = "Factory Staff"
                CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
                CFramemon = CFrame.new(729.8469848632812, 118.41995239257812, -30.045679092407227)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 875 or Level <= 899 then
                Mon = "Marine Lieutenant [Lv. 875]"
                LQuest = 1
                NQuest = "MarineQuest3"
                NameMon = "Marine Lieutenant"
                CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
                CFramemon = CFrame.new(-3181.96728515625, 161.1638641357422, -2923.768310546875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 900 or Level <= 949 then
                Mon = "Marine Captain [Lv. 900]"
                LQuest = 2
                NQuest = "MarineQuest3"
                NameMon = "Marine Captain"
                CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
                CFramemon = CFrame.new(-1767.8397216796875, 99.89533233642578, -3166.265380859375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 950 or Level <= 974 then
                Mon = "Zombie [Lv. 950]"
                LQuest = 1
                NQuest = "ZombieQuest"
                NameMon = "Zombie"
                CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
                CFramemon = CFrame.new(-5541.1748046875, 98.90672302246094, -785.064697265625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 975 or Level <= 999 then
                Mon = "Vampire [Lv. 975]"
                LQuest = 2
                NQuest = "ZombieQuest"
                NameMon = "Vampire"
                CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
                CFramemon = CFrame.new(-6041.71533203125, 6.3987135887146, -1328.632568359375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1000 or Level <= 1049 then
                Mon = "Snow Trooper [Lv. 1000]"
                LQuest = 1
                NQuest = "SnowMountainQuest"
                NameMon = "Snow Trooper"
                CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
                CFramemon = CFrame.new(545.2506103515625, 428.0561218261719, -5561.25830078125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1050 or Level <= 1099 then
                Mon = "Winter Warrior [Lv. 1050]"
                LQuest = 2
                NQuest = "SnowMountainQuest"
                NameMon = "Winter Warrior"
                CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
                CFramemon = CFrame.new(1320.4791259765625, 429.4178771972656, -5298.9267578125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1100 or Level <= 1124 then
                Mon = "Lab Subordinate [Lv. 1100]"
                LQuest = 1
                NQuest = "IceSideQuest"
                NameMon = "Lab Subordinate"
                CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
                CFramemon = CFrame.new(-5777.20703125, 42.40324020385742, -4481.55126953125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1125 or Level <= 1174 then
                Mon = "Horned Warrior [Lv. 1125]"
                LQuest = 2
                NQuest = "IceSideQuest"
                NameMon = "Horned Warrior"
                CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
                CFramemon = CFrame.new(-6314.92724609375, 32.51631546020508, -6002.9716796875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1175 or Level <= 1199 then
                Mon = "Magma Ninja [Lv. 1175]"
                LQuest = 1
                NQuest = "FireSideQuest"
                NameMon = "Magma Ninja"
                CFrameQuest = CFrame.new(-5428.03174, 15.0622921, -5299.43457, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
                CFramemon = CFrame.new(-5465.013671875, 130.1513214111328, -5838.06884765625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1200 or Level <= 1249 then
                Mon = "Lava Pirate [Lv. 1200]"
                LQuest = 2
                NQuest = "FireSideQuest"
                NameMon = "Lava Pirate"
                CFrameQuest = CFrame.new(-5428.03174, 15.0622921, -5299.43457, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
                CFramemon = CFrame.new(-5251.08544921875, 50.5064811706543, -4719.296875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1250 or Level <= 1274 then
                Mon = "Ship Deckhand [Lv. 1250]"
                LQuest = 1
                NQuest = "ShipQuest1"
                NameMon = "Ship Deckhand"
                CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016)
                CFramemon = CFrame.new(640.0233764648438, 125.72512817382812, 32981.76171875)         
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1275 or Level <= 1299 then
                Mon = "Ship Engineer [Lv. 1275]"
                LQuest = 2
                NQuest = "ShipQuest1"
                NameMon = "Ship Engineer"
                CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016) 
                CFramemon = CFrame.new(916.8641357421875, 43.5400276184082, 32781.0234375)  
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end             
            elseif Level == 1300 or Level <= 1324 then
                Mon = "Ship Steward [Lv. 1300]"
                LQuest = 1
                NQuest = "ShipQuest2"
                NameMon = "Ship Steward"
                CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125)
                CFramemon = CFrame.new(920.375732421875, 129.552001953125, 33441.21875)         
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1325 or Level <= 1349 then
                Mon = "Ship Officer [Lv. 1325]"
                LQuest = 2
                NQuest = "ShipQuest2"
                NameMon = "Ship Officer"
                CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125)
                CFramemon = CFrame.new(639.2978515625, 181.14512634277344, 33306.28515625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1350 or Level <= 1374 then
                Mon = "Arctic Warrior [Lv. 1350]"
                LQuest = 1
                NQuest = "FrostQuest"
                NameMon = "Arctic Warrior"
                CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
                CFramemon = CFrame.new(6095.54296875, 28.36317253112793, -6239.02685546875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1375 or Level <= 1424 then
                Mon = "Snow Lurker [Lv. 1375]"
                LQuest = 2
                NQuest = "FrostQuest"
                NameMon = "Snow Lurker"
                CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
                CFramemon = CFrame.new(5519.1904296875, 60.51692199707031, -6829.9326171875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1425 or Level <= 1449 then
                Mon = "Sea Soldier [Lv. 1425]"
                LQuest = 1
                NQuest = "ForgottenQuest"
                NameMon = "Sea Soldier"
                CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
                CFramemon = CFrame.new(-3236.376708984375, 64.34226989746094, -9733.05078125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level >= 1450 then
                Mon = "Water Fighter [Lv. 1450]"
                LQuest = 2
                NQuest = "ForgottenQuest"
                NameMon = "Water Fighter"
                CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
                CFramemon = CFrame.new(-3268.175537109375, 298.6604919433594, -10550.9599609375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            end
        elseif W3 then
            if Level == 1500 or Level <= 1524 then
                Mon = "Pirate Millionaire [Lv. 1500]"
                LQuest = 1
                NQuest = "PiratePortQuest"
                NameMon = "Pirate Millionaire"
                CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
                CFramemon = CFrame.new(-521.0215454101562, 61.0096549987793, 5546.3740234375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1525 or Level <= 1574 then
                Mon = "Pistol Billionaire [Lv. 1525]"
                LQuest = 2
                NQuest = "PiratePortQuest"
                NameMon = "Pistol Billionaire"
                CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
                CFramemon = CFrame.new(-283.1584167480469, 129.15762329101562, 5987.52294921875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1575 or Level <= 1599 then
                Mon = "Dragon Crew Warrior [Lv. 1575]"
                LQuest = 1
                NQuest = "AmazonQuest"
                NameMon = "Dragon Crew Warrior"
                CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
                CFramemon = CFrame.new(6517.7001953125, 51.49229431152344, -959.3108520507812)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1600 or Level <= 1624 then 
                Mon = "Dragon Crew Archer [Lv. 1600]"
                NQuest = "AmazonQuest"
                LQuest = 2
                NameMon = "Dragon Crew Archer"
                CFrameQuest = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
                CFramemon = CFrame.new(6684.0859375, 378.3859558105469, 323.9324645996094)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1625 or Level <= 1649 then
                Mon = "Female Islander [Lv. 1625]"
                NQuest = "AmazonQuest2"
                LQuest = 1
                NameMon = "Female Islander"
                CFrameQuest = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
                CFramemon = CFrame.new(5558.93310546875, 764.2176513671875, 760.17578125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1650 or Level <= 1699 then 
                Mon = "Giant Islander [Lv. 1650]"
                NQuest = "AmazonQuest2"
                LQuest = 2
                NameMon = "Giant Islander"
                CFrameQuest = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
                CFramemon = CFrame.new(4842.30078125, 632.253662109375, -271.97900390625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1700 or Level <= 1724 then
                Mon = "Marine Commodore [Lv. 1700]"
                LQuest = 1
                NQuest = "MarineTreeIsland"
                NameMon = "Marine Commodore"
                CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
                CFramemon = CFrame.new(2301.28076171875, 73.13015747070312, -7177.0107421875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1725 or Level <= 1774 then
                Mon = "Marine Rear Admiral [Lv. 1725]"
                NameMon = "Marine Rear Admiral"
                NQuest = "MarineTreeIsland"
                LQuest = 2
                CFrameQuest = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
                CFramemon = CFrame.new(3669.8388671875, 160.5200653076172, -7035.29052734375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1775 or Level <= 1799 then
                Mon = "Fishman Raider [Lv. 1775]"
                LQuest = 1
                NQuest = "DeepForestIsland3"
                NameMon = "Fishman Raider"
                CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
                CFramemon = CFrame.new(-10424.107421875, 331.7586364746094, -8374.6435546875)   
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1800 or Level <= 1824 then
                Mon = "Fishman Captain [Lv. 1800]"
                LQuest = 2
                NQuest = "DeepForestIsland3"
                NameMon = "Fishman Captain"
                CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213) 
                CFramemon = CFrame.new(-10974.2626953125, 331.7586364746094, -8972.0419921875)  
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1825 or Level <= 1849 then
                Mon = "Forest Pirate [Lv. 1825]"
                LQuest = 1
                NQuest = "DeepForestIsland"
                NameMon = "Forest Pirate"
                CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
                CFramemon = CFrame.new(-13512.380859375, 375.72705078125, -7887.423828125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1850 or Level <= 1899 then
                Mon = "Mythological Pirate [Lv. 1850]"
                LQuest = 2
                NQuest = "DeepForestIsland"
                NameMon = "Mythological Pirate"
                CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
                CFramemon = CFrame.new(-13450.3603515625, 543.2171630859375, -6961.95166015625)  
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end 
            elseif Level == 1900 or Level <= 1924 then
                Mon = "Jungle Pirate [Lv. 1900]"
                LQuest = 1
                NQuest = "DeepForestIsland2"
                NameMon = "Jungle Pirate"
                CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
                CFramemon = CFrame.new(-11957.904296875, 331.7342834472656, -10605.0068359375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1925 or Level <= 1974 then
                Mon = "Musketeer Pirate [Lv. 1925]"
                LQuest = 2
                NQuest = "DeepForestIsland2"
                NameMon = "Musketeer Pirate"
                CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
                CFramemon = CFrame.new(-13481.48828125, 429.4248046875, -9853.1953125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 1975 or Level <= 1999 then
                Mon = "Reborn Skeleton [Lv. 1975]"
                LQuest = 1
                NQuest = "HauntedQuest1"
                NameMon = "Reborn Skeleton"
                CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
                CFramemon = CFrame.new(-8761.7177734375, 179.4827880859375, 6167.3916015625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2000 or Level <= 2024 then
                Mon = "Living Zombie [Lv. 2000]"
                LQuest = 2
                NQuest = "HauntedQuest1"
                NameMon = "Living Zombie"
                CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
                CFramemon = CFrame.new(-10079.0703125, 237.11517333984375, 5912.5537109375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2025 or Level <= 2049 then
                Mon = "Demonic Soul [Lv. 2025]"
                LQuest = 1
                NQuest = "HauntedQuest2"
                NameMon = "Demonic Soul"
                CFrameQuest = CFrame.new(-9516.99316, 172.017181, 6078.46533, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-9274.3349609375, 204.66604614257812, 6040.24072265625) 
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2050 or Level <= 2074 then
                Mon = "Posessed Mummy [Lv. 2050]"
                LQuest = 2
                NQuest = "HauntedQuest2"
                NameMon = "Posessed Mummy"
                CFrameQuest = CFrame.new(-9516.99316, 172.017181, 6078.46533, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-9515.0849609375, 60.25532150268555, 6322.96923828125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2075 or Level <= 2099 then
                Mon = "Peanut Scout [Lv. 2075]"
                LQuest = 1
                NQuest = "NutsIslandQuest"
                NameMon = "Peanut Scout"
                CFrameQuest = CFrame.new(-2104.3908691406, 38.104167938232, -10194.21875, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-2009.8851318359375, 51.037567138671875, -9976.7490234375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2100 or Level <= 2124 then
                Mon = "Peanut President [Lv. 2100]"
                LQuest = 2
                NQuest = "NutsIslandQuest"
                NameMon = "Peanut President"
                CFrameQuest = CFrame.new(-2104.3908691406, 38.104167938232, -10194.21875, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-1952.3201904296875, 99.6769790649414, -10648.90234375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2125 or Level <= 2149 then
                Mon = "Ice Cream Chef [Lv. 2125]"
                LQuest = 1
                NQuest = "IceCreamIslandQuest"
                NameMon = "Ice Cream Chef"
                CFrameQuest = CFrame.new(-820.64825439453, 65.819526672363, -10965.795898438, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-705.68212890625, 145.35694885253906, -10850.75)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2150 or Level <= 2199 then
                Mon = "Ice Cream Commander [Lv. 2150]"
                LQuest = 2
                NQuest = "IceCreamIslandQuest"
                NameMon = "Ice Cream Commander"
                CFrameQuest = CFrame.new(-820.64825439453, 65.819526672363, -10965.795898438, 0, 0, -1, 0, 1, 0, 1, 0, 0)
                CFramemon = CFrame.new(-654.2710571289062, 144.19610595703125, -11350.1357421875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2200 or Level <= 2224 then
                Mon = "Cookie Crafter [Lv. 2200]"
                LQuest = 1
                NQuest = "CakeQuest1"
                NameMon = "Cookie Crafter"
                CFrameQuest = CFrame.new(-2021.32007, 37.7982254, -12028.7295, 0.957576931, -8.80302053e-08, 0.288177818, 6.9301187e-08, 1, 7.51931211e-08, -0.288177818, -5.2032135e-08, 0.957576931)
                CFramemon = CFrame.new(-2379.423828125, 37.79426193237305, -12123.7265625)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2225 or Level <= 2249 then
                Mon = "Cake Guard [Lv. 2225]"
                LQuest = 2
                NQuest = "CakeQuest1"
                NameMon = "Cake Guard"
                CFrameQuest = CFrame.new(-2021.32007, 37.7982254, -12028.7295, 0.957576931, -8.80302053e-08, 0.288177818, 6.9301187e-08, 1, 7.51931211e-08, -0.288177818, -5.2032135e-08, 0.957576931)
                CFramemon = CFrame.new(-1569.7547607421875, 195.65078735351562, -12238.2392578125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2250 or Level <= 2274 then
                Mon = "Baking Staff [Lv. 2250]"
                LQuest = 1
                NQuest = "CakeQuest2"
                NameMon = "Baking Staff"
                CFrameQuest = CFrame.new(-1927.91602, 37.7981339, -12842.5391, -0.96804446, 4.22142143e-08, 0.250778586, 4.74911062e-08, 1, 1.49904711e-08, -0.250778586, 2.64211941e-08, -0.96804446)
                CFramemon =  CFrame.new(-1923.2867431640625, 157.9374237060547, -12860.9482421875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2275 or Level <=2299 then
                Mon = "Head Baker [Lv. 2275]"
                LQuest = 2
                NQuest = "CakeQuest2"
                NameMon = "Head Baker"
                CFrameQuest = CFrame.new(-1927.91602, 37.7981339, -12842.5391, -0.96804446, 4.22142143e-08, 0.250778586, 4.74911062e-08, 1, 1.49904711e-08, -0.250778586, 2.64211941e-08, -0.96804446)
                CFramemon = CFrame.new(-1923.2867431640625, 157.9374237060547, -12860.9482421875)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2300 or Level <= 2324 then
                Mon = "Cocoa Warrior [Lv. 2300]"
                LQuest = 1
                NQuest = "ChocQuest1"
                NameMon = "Cocoa Warrior"
                CFrameQuest = CFrame.new(231.742981, 25.3354111, -12199.0537, 0.998278677, -5.16006757e-08, 0.0586484075, 4.79685092e-08, 1, 6.33390442e-08, -0.0586484075, -6.04167383e-08, 0.998278677)
                CFramemon = CFrame.new(-92.33313751220703, 141.1387939453125, -12267.251953125)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2325 or Level <= 2349 then
                Mon = "Chocolate Bar Battler [Lv. 2325]"
                LQuest = 2
                NQuest = "ChocQuest1"
                NameMon = "Chocolate Bar Battler"
                CFrameQuest = CFrame.new(231.742981, 25.3354111, -12199.0537, 0.998278677, -5.16006757e-08, 0.0586484075, 4.79685092e-08, 1, 6.33390442e-08, -0.0586484075, -6.04167383e-08, 0.998278677)
                CFramemon = CFrame.new(722.2906494140625, 68.47393035888672, -12595.6005859375)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level == 2350 or Level <= 2374 then
                Mon = "Sweet Thief [Lv. 2350]"
                LQuest = 1
                NQuest = "ChocQuest2"
                NameMon = "Sweet Thief"
                CFrameQuest = CFrame.new(149.867218, 24.8196201, -12775.5283, -0.0371122323, -7.14229245e-08, -0.99931109, -6.93553162e-08, 1, -6.88964548e-08, 0.99931109, 6.6750637e-08, -0.0371122323)
                CFramemon = CFrame.new(-22.124303817749023, 70.68841552734375, -12700.6357421875)   
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            elseif Level >= 2375 then
                Mon = "Candy Rebel [Lv. 2375]"
                LQuest = 2
                NQuest = "ChocQuest2"
                NameMon = "Candy Rebel"
                CFrameQuest = CFrame.new(149.867218, 24.8196201, -12775.5283, -0.0371122323, -7.14229245e-08, -0.99931109, -6.93553162e-08, 1, -6.88964548e-08, 0.99931109, 6.6750637e-08, -0.0371122323)
                CFramemon = CFrame.new(36.56766891479492, 97.00366973876953, -12934.25)
                if getgenv().farm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1200 then
                    ByPass(CFrameQuest)
                end
            end
        end
    end
    local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/WetCheezit/Bracket-V2/main/src.lua"))()

    -- Window
    local Window, MainGUI = Library:CreateWindow("OXEGEN Hub NEXT Genaration Series Y")

    -- Tabs
    local Tab1 = Window:CreateTab("Main")
    local Tab2 = Window:CreateTab("Player")

    local Groupbox1 = Tab1:CreateGroupbox("AUtoFarm", "Left")
    local Groupbox2 = Tab1:CreateGroupbox("", "Right")

    local Groupbox3 = Tab2:CreateGroupbox("stats", "Left")
    local Groupbox4 = Tab2:CreateGroupbox("Groupbox 2", "Right")

    -- Groupbox 1
    local ExampleToggle = Groupbox1:CreateToggle("AutoFarmLv", function(state)
        _G.start = state
    end)
    
  

    
    spawn(function()
        pcall(function()
            while wait() do  
                if _G.start and getgenv().farm then
                    farm = true
                    if farm then
                        if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                            CheckQuest() 
                            topos(CFrameQuest)
                            if (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
                            
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NQuest,LQuest)
                                    
                            end
                            
                        elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                                
                            if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,NameMon) then
                                topos(CFramemon)
                                AutoHaki()
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do 
                                    
                                    pcall(function()    
                                        if v.Name == Mon then
                                            
                                            repeat wait(0.1) 
                                                topos(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
                                            until game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false or getgenv().farm  == false
                                        
                                        end
                                                            
                                    
                                
                                    end)
                                end
            
                            else 
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                            end
                                    
                            
                    
                        
                            
                        end   
                    end   
                end        
            end
        end)
    end)
                                 
    local plr = game.Players.LocalPlayer
    local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
    local CbFw2 = CbFw[2]
    function GetCurrentBlade()
        local p13 = CbFw2.activeController
        local ret = p13.blades[1]
        if not ret then
            return
        end
        while ret.Parent ~= game.Players.LocalPlayer.Character do
            ret = ret.Parent
        end
        return ret
    end
    function AttackNoCD()
        local AC = CbFw2.activeController
        for i = 1, 1 do
            local bladehit =
                require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
                plr.Character,
                {plr.Character.HumanoidRootPart},
                60
            )
            local cac = {}
            local hash = {}
            for k, v in pairs(bladehit) do
                if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                    table.insert(cac, v.Parent.HumanoidRootPart)
                    hash[v.Parent] = true
                end
            end
            bladehit = cac
            if #bladehit > 0 then
                local u8 = debug.getupvalue(AC.attack, 5)
                local u9 = debug.getupvalue(AC.attack, 6)
                local u7 = debug.getupvalue(AC.attack, 4)
                local u10 = debug.getupvalue(AC.attack, 7)
                local u12 = (u8 * 798405 + u7 * 727595) % u9
                local u13 = u7 * 798405
                (function()
                    u12 = (u12 * u9 + u13) % 1099511627776
                    u8 = math.floor(u12 / u9)
                    u7 = u12 - u8 * u9
                end)()
                u10 = u10 + 1
                debug.setupvalue(AC.attack, 5, u8)
                debug.setupvalue(AC.attack, 6, u9)
                debug.setupvalue(AC.attack, 4, u7)
                debug.setupvalue(AC.attack, 7, u10)
                pcall(
                    function()
                        for k, v in pairs(AC.animator.anims.basic) do
                            v:Play()
                        end
                    end
                )
                if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer(
                        "weaponChange",
                        tostring(GetCurrentBlade())
                    )
                    game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "")
                    y.activeController.timeToNextAttack = -10
                    y.activeController.hitboxMagnitude = 100
                    y.activeController.active = false
                    y.activeController.timeToNextBlock = 0
                    y.activeController.focusStart = 0
                    y.activeController.increment = 0
                    y.activeController.blocking = false
                    y.activeController.attacking = false
                    y.activeController.humanoid.AutoRotate = true
                end
            end
        end
    end
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    task.spawn(
        function()
            while wait(.8) do
                pcall(
                    function()
                        if _G.start then
                            repeat wait(.2)
                                AttackNoCD()
                            until _G.start == false
                            
                        end
                    end
                )
            end
        end
    )
    local CameraShaker = require(game.ReplicatedStorage.Util.CameraShaker)
    CombatFrameworkR = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    y = debug.getupvalues(CombatFrameworkR)[2]
    spawn(
        function()
            game:GetService("RunService").RenderStepped:Connect(
                function()
                    if _G.start then
                        if _G.start then
                            pcall(
                                function()
                                    CameraShaker:Stop()
                                    y.activeController.timeToNextAttack = 0
                                    y.activeController.hitboxMagnitude = 100
                                    y.activeController.active = false
                                    y.activeController.timeToNextBlock = 0
                                    y.activeController.focusStart = 0
                                    y.activeController.increment = 0
                                    y.activeController.blocking = false
                                    y.activeController.attacking = false
                                    y.activeController.humanoid.AutoRotate = true
                                end
                            )
                        end
                    end
                end
            )
        end
    )
    spawn(
    function()
        game:GetService("RunService").RenderStepped:Connect(
            function()
                if _G.start == true then
                    game.Players.LocalPlayer.Character.Stun.Value = 0
                    game.Players.LocalPlayer.Character.Humanoid.Sit = false
                    game.Players.LocalPlayer.Character.Busy.Value = false
                end
            end
        )
    end
    )
    task.spawn(function()
        if game.Players.LocalPlayer.Character:FindFirstChild("Stun") then
            game.Players.LocalPlayer.Character.Stun.Changed:connect(function()
                pcall(function()
                    if game.Players.LocalPlayer.Character:FindFirstChild("Stun") then
                        game.Players.LocalPlayer.Character.Stun.Value = 0
                    end
                end)
            end)
        end
    end)

  
    task.spawn(function()
        if _G.start then
            while wait() do
                for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"]:GetChildren()) do
                    pcall(function()
                        if v.Name == ("CurvedRing") or v.Name == ("SlashHit") or v.Name == ("SwordSlash") or v.Name == ("SlashTail") or v.Name == ("Sounds") then
                            v:Destroy()
                        end
                    end)
                end
            end    
        end    
    end)
    spawn(function()
        pcall(function()
            while wait() do
                if _G.start then
                    if game.Players.Localplayer.Character.Humanoid.Health >= 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                    end    
                end
            end
        end)
    end)    
    spawn(function()
        pcall(function()
            while wait() do
                if _G.start then
                    
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                     
                end
            end
        end)
    end)        
    
            

   
   
    
         
   



    
    
         
        
       
    spawn(function()
        pcall(function()
            while wait() do
                if _G.start == true then
                    if not game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                        local Noclip = Instance.new("BodyVelocity")
                        Noclip.Name = "BodyClip"
                        Noclip.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
                        Noclip.MaxForce = Vector3.new(100000,100000,100000)
                        Noclip.Velocity = Vector3.new(0,0,0)
                        
                    end
                end
            end
        end)
    end)    
    function AutoHaki()
        if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HasBuso") then
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
        end
    end
    spawn(function()
        while wait() do
            pcall(function()
                if _G.start then
                    if game.Players.LocalPlayer.Data.Level.Value == 100 then
                        _G.kill = false
                        farm = true
                    end
                end
            end)
        end
    end)   
    spawn(function()
        while wait() do
            pcall(function()
                if _G.start then
                    equip = true
                    if equip then
                        for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                            if v.ToolTip == "Melee" then
                                if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
                                    game.Players.LocalPlayer.Character.Humanoid:EquipTool(game.Players.LocalPlayer.Backpack:FindFirstChild(v.Name))
                                end   
                            end
                        end
                    end
                end
            end)
        end
    end)   
    spawn(function()
        game:GetService("RunService").RenderStepped:Connect(function()
            if _G.start == true then
                game.Players.LocalPlayer.Character.Stun.Value = 0
                game.Players.LocalPlayer.Character.Humanoid.Sit = false
                game.Players.LocalPlayer.Character.Busy.Value = false   
            end
        end)
    end)

    function Click()
        game:GetService("RunService").Heartbeat:Connect(function()  
            

            game:GetService'VirtualUser':CaptureController()
            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))

            
        end)
    end 

    
    spawn(function()
        while wait() do
            pcall(function()
                if _G.start then
                            CheckQuest() 
                    
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == Mon then
                                
                                    v.HumanoidRootPart.CFrame = CFramemon
                                    v.HumanoidRootPart.CanCollide = false
                                    v.HumanoidRootPart.Transparency = 1
                                    v.Humanoid.WalkSpeed = 0
                                    v.Humanoid.JumpPower = 0
                                    v.HumanoidRootPart.Locked = true
                                    v.Humanoid:ChangeState(14)
                                    v.Humanoid:ChangeState(11)
                                    if sethiddenproperty then
                                        sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                                    end
                                    
                                    
                                    if v.Humanoid:FindFirstChild("Animator") then
                                        v.Humanoid.Animator:Destroy()
                                    end
                                
                                end
                            
                            
                            
                            
                                
                            end

                end
            end)
        end
    end)
    spawn(function()
        pcall(function()
            while wait() do
                if _G.start then
                    local args = {
                        [1] = "AddPoint",
                        [2] = "Melee",
                        [3] = 1
                    }

                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    if game:GetService("Players").LocalPlayer.Data.Stats.Melee.Level.Value == 2400 then 
                               
                        local args = {
                            [1] = "AddPoint",
                            [2] = "Defense",
                            [3] = 1
                        }

                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

                    end
                end
            end
        end)
    end)    
    spawn(function()
        pcall(function()
            while wait() do
                if _G.start then
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Sub2Fer999")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Enyu_is_Pro")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Magicbus")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("JCWK")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Starcodeheo")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Bluxxy")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("THEGREATACE")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("SUB2GAMERROBOT_EXP1")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("StrawHatMaine")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Sub2OfficialNoobie")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("SUB2NOOBMASTER123")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Sub2Daigrock")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("Axiore")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("TantaiGaming")
                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer("STRAWHATMAINE")
                end
            end
        end)
    end)
        spawn(function()
            game:GetService("RunService").Heartbeat:Connect(function()
                if _G.start then
                if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
                    setfflag("HumanoidParallelRemoveNoPhysics", "False")
                    setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
                    game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                    end
                end
            end)
        end)
        spawn(function()
            while wait() do
            if _G.start then
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
                    local args = {
                    [1] = "BuyBlackLeg"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end   
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 then
                    local args = {
                    [1] = "BuyElectro"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end
                if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 then
                    local args = {
                    [1] = "BuyElectro"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 then
                    local args = {
                    [1] = "BuyFishmanKarate"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end
                if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 then
                    local args = {
                    [1] = "BuyFishmanKarate"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 then
                    local args = {
                    [1] = "BlackbeardReward",
                    [2] = "DragonClaw",
                    [3] = "1"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    local args = {
                    [1] = "BlackbeardReward",
                    [2] = "DragonClaw",
                    [3] = "2"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args)) 
                end
                if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300 then
                    local args = {
                    [1] = "BlackbeardReward",
                    [2] = "DragonClaw",
                    [3] = "1"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    local args = {
                    [1] = "BlackbeardReward",
                    [2] = "DragonClaw",
                    [3] = "2"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args)) 
                end
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 then
                    local args = {
                    [1] = "BuySuperhuman"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end
                if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 then
                    local args = {
                    [1] = "BuySuperhuman"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end    
            end
            end
        end)
        spawn(function()
            while wait() do
                if _G.start then
                    pcall(function()
                       
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bomb-Bomb")
                        
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spike-Spike")
                        
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Chop-Chop")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spring-Spring")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Kilo-Kilo")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Smoke-Smoke")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spin-Spin")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Flame-Flame")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Falcon")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Ice-Ice")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Sand-Sand")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dark-Dark")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Revive-Revive")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Diamond-Diamond")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Light-Light")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Love-Love")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rubber-Rubber")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Barrier-Barrier")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Magma-Magma")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Door-Door")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Quake-Quake")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Human-Human: Buddha")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","String-String")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Phoenix")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rumble-Rumble")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Paw-Paw")

                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Gravity-Gravity")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dough-Dough")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Shadow-Shadow")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Venom-Venom")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Control-Control")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Soul-Soul")
                        
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dragon-Dragon")
                        
                       
                    end)
                end
            end
        end)
       
        spawn(function()
            while wait() do
                if _G.start then
                    pcall(function()
                        game:GetService("Players").LocalPlayer.Idled:connect(function()
                            game:GetService("VirtualUser"):Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                            wait(1)
                            game:GetService("VirtualUser"):Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                        end)
                    end)
                end
            end
        end)
        spawn(function()
            while wait() do
                if _G.start then
                    pcall(function()
                        AutoHaki()
                    end)
                end
            end
        end)
        function HopServer()
            local PlaceID = game.PlaceId
            local AllIDs = {}
            local foundAnything = ""
            local actualHour = os.date("!*t").hour
            local Deleted = false
             --[[
             local File = pcall(function()
                AllIDs = game:GetService('HttpService'):JSONDecode(readfile("NotSameServers.json"))
             end)
             if not File then
                table.insert(AllIDs, actualHour)
                writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
             end
             ]]
            function TPReturner()
                local Site;
                if foundAnything == "" then
                    Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
                else
                    Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
                end
                local ID = ""
                if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
                    foundAnything = Site.nextPageCursor
                end
                local num = 0;
                for i,v in pairs(Site.data) do
                    local Possible = true
                    ID = tostring(v.id)
                    if tonumber(v.maxPlayers) > tonumber(v.playing) then
                        for _,Existing in pairs(AllIDs) do
                            if num ~= 0 then
                                if ID == tostring(Existing) then
                                    Possible = false
                                end
                            else
                                if tonumber(actualHour) ~= tonumber(Existing) then
                                    local delFile = pcall(function()
                                        -- delfile("NotSameServers.json")
                                        AllIDs = {}
                                        table.insert(AllIDs, actualHour)
                                    end)
                                end
                            end
                            num = num + 1
                        end
                        if Possible == true then
                            table.insert(AllIDs, ID)
                            wait()
                            pcall(function()
                                -- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                                wait()
                                game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
                            end)
                            wait(4)
                        end
                    end
                end
            end
        
            function Teleport()
                while wait() do
                    pcall(function()
                        TPReturner()
                        if foundAnything ~= "" then
                            TPReturner()
                        end
                    end)
                end
            end
        
            Teleport()
            wait(1)
        end
        spawn(function()
            while wait() do
                if _G.start then
                    pcall(function()
                        if game.Players.Localplayer.Character.Humanoid.Health <= 0 then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")

                        end
                    end)
                end
            end
        end)
        for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")) do
            if Level == 200 or Level <= 200 then 
                _G.saber = true
                while wait() do
                    pcall(function()
                        local Level = game.Players.LocalPlayer.Data.Level.Value
                        if equip and not v.Name == "Saber" then 
                            
                            farm = false
                            _G.kill = false    
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","Plate",1)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","Plate",2)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","Plate",3)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","Plate",4)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","Plate",5)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetTorch")
                            equip = false
                            for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
                                game.Players.LocalPlayer.Character.Humanoid:EquipTool(game.Players.LocalPlayer.Backpack:FindFirstChild("Torch"))
                            end
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetCup")
                            for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
                                game.Players.LocalPlayer.Character.Humanoid:EquipTool(game.Players.LocalPlayer.Backpack:FindFirstChild("Cup"))
                            end        
                            local args = {
                                [1] = "ProQuestProgress",
                                [2] = "FillCup",
                                [3] = game:GetService("Players").LocalPlayer.Character.Cup
                            }

                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
                            if game:GetService("Workspace").Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                                for i,v in pairs( game:GetService("ReplicatedStorage"):GetChildren()) do
                                        if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                                            v.Humanoid.JumpPower = 0
                                            v.Humanoid.WalkSpeed = 0
                                            v.HumanoidRootPart.CanCollide = false
                                            v.Humanoid:ChangeState(11)
                                            repeat
                                                topos(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
                                            until v.Humanoid.Health == 0
                                        end
                                end
                        
                            end
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
                            wait(0.5)
                            for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
                                game.Players.LocalPlayer.Character.Humanoid:EquipTool(game.Players.LocalPlayer.Backpack:FindFirstChild("Relic"))
                            end
                            wait(20)
                            topos(CFrame.new(-1404.91504, 29.9773273, 3.80598116, 0.876514494, 5.66906877e-09, 0.481375456, 2.53851997e-08, 1, -5.79995607e-08, -0.481375456, 6.30572643e-08, 0.876514494))
                            if game:GetService("Workspace").Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                                for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
                                    if v.Name == "Saber Expert [Lv. 200] [Boss]" then
                                        v.Humanoid.JumpPower = 0
                                        v.Humanoid.WalkSpeed = 0
                                        v.HumanoidRootPart.CanCollide = false
                                        v.Humanoid:ChangeState(11)
                                        repeat
                                            topos(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
                                        until v.Humanoid.Health == 0
                                    end
                                end
                            else
                                HopServer()
                            end
                            for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")) do
                                if v.Name == "Saber" then
                                    farm = true
                                    equip = true
                                    _G.saber = false
                                end
                            end
                        end    
                    end)
                end
            end
        end    
            task.spawn(
                function()
                    while true do
                        wait()
                        _G.rejoin =
                            game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(
                            function(Kick)
                                if not _G.Rejoin then
                                    if
                                        Kick.Name == "ErrorPrompt" and Kick:FindFirstChild("MessageArea") and
                                            Kick.MessageArea:FindFirstChild("ErrorFrame")
                                    then
                                        game:GetService("TeleportService"):Teleport(game.PlaceId)
                                        wait()
                                    end
                                end
                            end
                        )
                    end
                end
            )
            local CombatFramework = require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework"))
            local CombatFrameworkR = getupvalues(CombatFramework)[2]
            local RigController = require(game:GetService("Players")["LocalPlayer"].PlayerScripts.CombatFramework.RigController)
            local RigControllerR = getupvalues(RigController)[2]
            local realbhit = require(game.ReplicatedStorage.CombatFramework.RigLib)
            local cooldownfastattack = tick()

            function CurrentWeapon()
                local ac = CombatFrameworkR.activeController
                local ret = ac.blades[1]
                if not ret then return game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name end
                pcall(function()
                    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
                end)
                if not ret then return game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name end
                return ret
            end

            function getAllBladeHitsPlayers(Sizes)
                local Hits = {}
                local Client = game.Players.LocalPlayer
                local Characters = game:GetService("Workspace").Characters:GetChildren()
                for i=1,#Characters do local v = Characters[i]
                    local Human = v:FindFirstChildOfClass("Humanoid")
                    if v.Name ~= game.Players.LocalPlayer.Name and Human and Human.RootPart and Human.Health > 0 and Client:DistanceFromCharacter(Human.RootPart.Position) < Sizes+5 then
                        table.insert(Hits,Human.RootPart)
                    end
                end
                return Hits
            end

            function getAllBladeHits(Sizes)
                local Hits = {}
                local Client = game.Players.LocalPlayer
                local Enemies = game:GetService("Workspace").Enemies:GetChildren()
                for i=1,#Enemies do local v = Enemies[i]
                    local Human = v:FindFirstChildOfClass("Humanoid")
                    if Human and Human.RootPart and Human.Health > 0 and Client:DistanceFromCharacter(Human.RootPart.Position) < Sizes+5 then
                        table.insert(Hits,Human.RootPart)
                    end
                end
                return Hits
            end

            function AttackFunction()
                local ac = CombatFrameworkR.activeController
                if ac and ac.equipped then
                    for indexincrement = 1, 1 do
                        local bladehit = getAllBladeHits(30)
                        if #bladehit > 0 then
                            local AcAttack8 = debug.getupvalue(ac.attack, 5)
                            local AcAttack9 = debug.getupvalue(ac.attack, 6)
                            local AcAttack7 = debug.getupvalue(ac.attack, 4)
                            local AcAttack10 = debug.getupvalue(ac.attack, 7)
                            local NumberAc12 = (AcAttack8 * 798405 + AcAttack7 * 727595) % AcAttack9
                            local NumberAc13 = AcAttack7 * 798405
                            (function()
                                NumberAc12 = (NumberAc12 * AcAttack9 + NumberAc13) % 1099511627776
                                AcAttack8 = math.floor(NumberAc12 / AcAttack9)
                                AcAttack7 = NumberAc12 - AcAttack8 * AcAttack9
                            end)()
                            AcAttack10 = AcAttack10 + 1
                            debug.setupvalue(ac.attack, 5, AcAttack8)
                            debug.setupvalue(ac.attack, 6, AcAttack9)
                            debug.setupvalue(ac.attack, 4, AcAttack7)
                            debug.setupvalue(ac.attack, 7, AcAttack10)
                            for k, v in pairs(ac.animator.anims.basic) do
                                v:Play(0.1,0.5,0.2,0.8)
                            end                 
                            if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") and ac.blades and ac.blades[1] then 
                                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(CurrentWeapon()))
                                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(NumberAc12 / 1099511627776 * 16777215), AcAttack10)
                                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, 2, "") 
                            end
                        end
                    end
                end
            end

            coroutine.wrap(function()
            while task.wait(.1) do
                local ac = CombatFrameworkR.activeController
                    if ac and ac.equipped then
                        if _G.start then
                            AttackFunction()
                            if _G.start then
                                if tick() - cooldownfastattack > 5 then wait(.9) cooldownfastattack = tick() end
                            end
                        elseif _G.start == true then
                            if ac.hitboxMagnitude ~= 55 then
                                ac.hitboxMagnitude = 55
                            end
                            ac:attack()
                        end
                    end
                end
            end)()
            _G.FastAttackNormalSpeed = true
            
            local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
            local VirtualUser = game:GetService('VirtualUser')
            local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
            local Client = game:GetService("Players").LocalPlayer
            local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
            
            function SeraphFuckWeapon() 
                local p13 = SeraphFrame.activeController
                local wea = p13.blades[1]
                if not wea then return end
                while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
                return wea
            end
            
            function getHits(Size)
                local Hits = {}
                local Enemies = workspace.Enemies:GetChildren()
                local Characters = workspace.Characters:GetChildren()
                for i=1,#Enemies do local v = Enemies[i]
                    local Human = v:FindFirstChildOfClass("Humanoid")
                    if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+5 then
                        table.insert(Hits,Human.RootPart)
                    end
                end
                for i=1,#Characters do local v = Characters[i]
                    if v ~= game.Players.LocalPlayer.Character then
                        local Human = v:FindFirstChildOfClass("Humanoid")
                        if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+5 then
                            table.insert(Hits,Human.RootPart)
                        end
                    end
                end
                return Hits
            end
            
            task.spawn(
                function()
                while wait(0) do
                    if  _G.FastAttackNormalSpeed then
                        if SeraphFrame.activeController then
                            -- if v.Humanoid.Health > 0 then
                                SeraphFrame.activeController.timeToNextAttack = 0
                                SeraphFrame.activeController.focusStart = 0
                                SeraphFrame.activeController.hitboxMagnitude = 40
                                SeraphFrame.activeController.humanoid.AutoRotate = true
                                SeraphFrame.activeController.increment = 1 + 1 / 1
                            -- end
                        end
                    end
                end
            end)
            
            function Boost()
                spawn(function()
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
                end)
            end
            
            function Unboost()
                spawn(function()
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
                end)
            end
            
            local cdnormal = 0
            local Animation = Instance.new("Animation")
            local CooldownFastAttack = 0
            Attack = function()
                local ac = SeraphFrame.activeController
                if ac and ac.equipped then
                    task.spawn(
                        function()
                        if tick() - cdnormal > 0.5 then
                            ac:attack()
                            cdnormal = tick()
                        else
                            -- Animation.AnimationId = ac.anims.basic[2]
                            -- ac.humanoid:LoadAnimation(Animation):Play(1, 1)
                            game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(120), 2, "")
                        end
                    end)
                end
            end
            
            b = tick()
            spawn(function()
                while wait(.2) do
                    if  _G.FastAttackNormalSpeed then
                        if b - tick() > 0.99 then
                            wait(.2)
                            b = tick()
                        end
                        pcall(function()
                            for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                                if v.Humanoid.Health > 0 then
                                    if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 60.9 then
                                        Attack()
                                        wait(.5)
                                        Boost()
                                    end
                                end
                            end
                        end)
                    end
                end
            end)
            
            k = tick()
            spawn(function()
                while wait(0.059) do
                    if  _G.FastAttackNormalSpeed then
                        if k - tick() > 0.99 then
                            wait(0)
                            k = tick()
                        end
                        pcall(function()
                            for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                                if v.Humanoid.Health > 0 then
                                    if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 60.9 then
                                    wait(.2)
                                    Unboost()
                                    end
                                end
                            end
                        end)
                    end
                end
            end)
            
            tjw1 = true
            task.spawn(
                function()
                    local a = game.Players.LocalPlayer
                    local b = require(a.PlayerScripts.CombatFramework.Particle)
                    local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
                    if not shared.orl then
                        shared.orl = c.wrapAttackAnimationAsync
                    end
                    if not shared.cpc then
                        shared.cpc = b.play
                    end
                    if tjw1 then
                        pcall(
                            function()
                                c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                                    local i = c.getBladeHits(e, f, g)
                                    if i then
                                        b.play = function()
                                        end
                                        d:Play(1.25, 1.25, 1.25)
                                        h(i)
                                        b.play = shared.cpc
                                        wait(.5)
                                        d:Stop()
                                    end
                                end
                            end
                        )
                    end
                end
            )
            
            
   

        




end)
