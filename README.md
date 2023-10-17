task.wait(0.4)
local UserInputService = game:GetService("UserInputService")
local GuiService = game:GetService("GuiService")

local __namecall;
local __index;

__index = hookmetamethod(game, "__index", function(tbl, idx)
   if tostring(getcallingscript()) ~= "ControlModule" and tbl == UserInputService then
       if idx == "TouchEnabled" then
           return true;
       elseif idx == "MouseEnabled" then
           return false;
       elseif idx == "KeyboardEnabled" then
           return false;
       end
   end
   return __index(tbl, idx);
end);
