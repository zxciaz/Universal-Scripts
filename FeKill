repeat wait() until game:IsLoaded() and game:WaitForChild"Players"

local Players, RStorage, RService, TPService, SGui = game:GetService"Players", game:GetService"ReplicatedStorage", game:GetService"RunService", game:GetService"TeleportService", game:GetService"StarterGui";
local Client, Camera, CF, Vec3, UD, UD2, Prefix = Players.LocalPlayer, workspace.CurrentCamera, CFrame.new, Vector3.new, UDim.new, UDim2.new, "/e ";
local Feloop, Spamming, FeloopTarget, WordToSpam = false, false, nil, nil;
local BlacklistedItems, Commands, LoadingTime = {"BoomBox", "Radio", "DualGoldenSuperFlyBoombox"}, {}, tick();
    
coroutine.wrap(function()
    if not getrawmetatable then 
        return Notify("xaxa", "Exploit not supported, function missing: getrawmetatable", "", 3)
    end
end)()

Commands["Fekill"] = {
    ["Aliases"] = {"feloop", "fekill", "fe", "kill"};
    ["Description"] = "Sets your Fekill/loop Target and kills them";
};
Commands["Unfekill"] = {
    ["Aliases"] = {"unfeloop", "unfekill", "unfe", "unkill"};
    ["Description"] = "Stops killing your Fekill Target";
};
Commands["Rejoin"] = {
    ["Aliases"] = {"rejoin", "rj"};
    ["Description"] = "Rejoins your current game";
};

function PrintCommands()
    local CommandFound, TotalCommands = "", 0;
    for _, C in next, Commands do 
        if C.Aliases and C.Description then 
            CommandFound = ""..(CommandFound).."["..table.concat(C.Aliases, ", ").."] - "..(C.Description).."\n";
            TotalCommands = TotalCommands + 1
        end
    end
    
    local ToPrint = [[
    
    
FeKill/Loop/Fling - by xix on v3rm/xaxa/zxciaz/fiviefourteen
=================================================
Commands (Make sure to put /e or your prefix before them):
==========================================================
]]..CommandFound..[[

=====================

Total Commands: ]]..(TotalCommands)..[[
]]
print(ToPrint)
end
PrintCommands()
    
function GetPlayer(Name)
    local FoundPlayer = nil
    local GP = Players:GetPlayers()
    for _, FS in next, GP do 
        if string.sub(string.lower(tostring(FS)), 1, #Name) == Name then
            FoundPlayer = FS;return FS
        end
    end
    if FoundPlayer and FoundPlayer ~= nil then 
        return FoundPlayer
    else 
        return Notify("xaxa", "Player not found!", "", 3)
    end
end

function Notify(Title, Text, Icon, Time)
    if SGui then 
        SGui:SetCore("SendNotification", {
            Title = Title;
            Text = Text;
            Icon = "";
            Duration = Time;
        }) 
    end
end

function ChatSpy()
    local ChatSpyFrame = Client.PlayerGui:FindFirstChild("Chat").Frame
    if ChatSpyFrame.ChatChannelParentFrame.Visible == false then 
        ChatSpyFrame.ChatChannelParentFrame.Visible = true
        ChatSpyFrame.ChatBarParentFrame.Position = ChatSpyFrame.ChatChannelParentFrame.Position + UD2(UD(), ChatSpyFrame.ChatChannelParentFrame.Size.Y)
    end
end
ChatSpy()

function ResetCharacter()
    if Client and Client.Character and Client.Character:FindFirstChildOfClass"Humanoid" then 
        Client.Character.Humanoid:ChangeState(15)
    end
end

function Chat(Word)
    if RStorage and RStorage:FindFirstChild"DefaultChatSystemChatEvents" then 
        RStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(tostring(Word), "All")
    end
end
    
function ChattedEvent(Msg)
    if string.sub(string.lower(Msg), 1, #Prefix) == Prefix then
        args = string.split(string.sub(string.lower(Msg), #Prefix + 1), " ")
        if args[1] == "feloop" or args[1] == "fekill" or args[1] == "fe" or args[1] == "kill" then
            if args[2] then 
                FeloopTarget = GetPlayer(args[2])
                if FeloopTarget and FeloopTarget ~= nil and FeloopTarget ~= tostring(Client) then 
                    Feloop = true;ResetCharacter();Notify("xaxa", "Feloop Target: "..tostring(FeloopTarget), "", 3)
                end
            elseif not args[2] then 
                Feloop = true;Notify("xaxa", "Feloop: "..tostring(Feloop), "", 3)
            end
        elseif args[1] == "unfeloop" or args[1] == "unfekill" or args[1] == "unfe" or args[1] == "unkill"  then 
            Feloop = false;ResetCharacter();Notify("xaxa", "Feloop: "..tostring(Feloop), "", 3)
        elseif args[1] == "rejoin" or args[1] == "rj" then 
            TPService:Teleport(game.PlaceId, Client)
        end
    end
end
Client.Chatted:Connect(ChattedEvent)

local rm = getrawmetatable(game) or debug.getrawmetatable(game) or getmetatable(game) or debug.getmetatable(game)
if setreadonly then setreadonly(rm, false) else make_writeable(rm, true) end 
local closure, caller = newcclosure or read_me or function(f) return f end, checkcaller or is_protosmasher_caller;
local ncall = rm.__namecall

rm.__namecall = closure(function(self, ...)
    local Args, Method = {...}, getnamecallmethod() or get_namecall_method();
    if Method == "LoadAnimation" and Feloop == true then 
        return wait(9e9)
    end
    if Method == "Kick" then 
        return wait(9e9)
    end
    if game.PlaceId == 455366377 then 
        if Method == "FireServer" and self.Name == "Input" then
            if Args[1] == "bv" or Args[1] == "hb" or Args[1] == "ws" then 
                return wait(9e9)
            end
        end
    end
    if Method == "FireServer" and not self.Name == "SayMessageRequest" then 
        if self.Name == "ReplicatedStorage" or self.Name == "lIII" or Args[1] == "hey" then 
            return wait(9e9)
        end
    end
    return ncall(self, unpack(Args))
end)
if setreadonly then setreadonly(rm, true) else make_writeable(rm, false) end 

RService.Stepped:Connect(function()
    if Feloop == true then 
        if Client and Client.Character and Client.Character:FindFirstChild"Right Leg" and Client.Character:FindFirstChildOfClass"Humanoid" then
            Client.Character:WaitForChild"Right Leg":Destroy()
            local NewHum = Client.Character.Humanoid:Clone()
            Client.Character.Humanoid:Destroy()
            NewHum.Parent = Client.Character;Camera.CameraSubject = Client.Character
        end
        for _, v in next, Client.Backpack:GetChildren() do 
            if game.PlaceId == 455366377 or game.PlaceId == 4669040 then 
                if v and v:IsA"Tool" and not table.find(BlacklistedItems, v.Name) then 
                    v.Parent = Client.Character
                    v.Handle.CanCollide = true 
                    v.Handle.Massless = true
                    wait()
                    v.Grip = CF(0, 9000, 0)
                end
            elseif game.PlaceId ~= 455366377 or game.PlaceId ~= 4669040 then 
                if v and v:IsA"Tool" then 
                    v.Parent = Client.Character
                    v.Handle.CanCollide = true 
                    v.Handle.Massless = true
                    wait()
                    v.Grip = CF(0, 9000, 0)
                end
            end
        end
        if FeloopTarget and FeloopTarget.Character then
            local ClientPF = Client.Character:FindFirstChild"HumanoidRootPart" or Client.Character:FindFirstChild"Torso";
            local TargetPF;
            if FeloopTarget.Character.Humanoid.RigType == Enum.HumanoidRigType.R15 then 
                TargetPF = FeloopTarget.Character:FindFirstChild"Head"
            elseif FeloopTarget.Character.Humanoid.RigType == Enum.HumanoidRigType.R6 then 
                TargetPF = FeloopTarget.Character:FindFirstChild"Torso" 
            end
            local FlingPF = FeloopTarget.Character:FindFirstChild"Right Arm" or TargetPF;
            if ClientPF and FlingPF then 
                workspace.FallenPartsDestroyHeight = -9000
                pcall(function() 
                    ClientPF.CFrame = TargetPF.CFrame
                    wait()
                    ClientPF.CFrame = FlingPF.CFrame * CF(0, 9000, 0)
                end)
            end
        end
    end
end)

Players.PlayerAdded:Connect(function(Player)
    if tostring(FeloopTarget) == tostring(Player) then 
        FeloopTarget = Player
        Feloop = true 
    end
end)
Players.PlayerRemoving:Connect(function(Player)
    if tostring(FeloopTarget) == tostring(Player) then 
        FeloopTarget = nil
        Feloop = false 
    end
end)
 
Notify("xaxa", "PRESS F9 FOR THE FUCKING COMMANDS", "", 3)
Notify("xaxa", "Script loaded in: "..string.sub(tostring(tick() - LoadingTime), 1, 6), "", 3)
