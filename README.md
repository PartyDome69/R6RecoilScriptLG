# R6RecoilScriptLG
Rainbow Six Siege X Recoil Script for Logitech G Hub 

Create a new profile in Logitech G Hub in R6, copy the code below, and paste in the Luna Script.
*******************************************************************************************************************************


local activateKey = "capslock"   -- Keys: "capslock", "numlock"  "scrolllock"
local requireRightThenLeft = true
local verticalForce = 12        -- Vertical Recoil
local horizontalForce = -1         -- Horizontal recoil: NEUTRO (0 = CENTER), NEGATIVE (-1, -2, -3, ETC = LEFT), POSSIITIVE = (1, 2, 3, ETC = RIGHT)

local delayMS = 9                 

EnablePrimaryMouseButtonEvents(true)

function OnEvent(event, arg)
  if event == "PROFILE_ACTIVATED" then
    EnablePrimaryMouseButtonEvents(true)
    return
  end


  if not IsKeyLockOn(activateKey) then return end

  if requireRightThenLeft then
   
    if event == "MOUSE_BUTTON_PRESSED" and arg == 1 and IsMouseButtonPressed(3) then
      repeat
        MoveMouseRelative(horizontalForce, verticalForce)
        Sleep(delayMS)
      until not (IsMouseButtonPressed(1) and IsMouseButtonPressed(3))
    end
  else
 
    if IsMouseButtonPressed(1) and IsMouseButtonPressed(3) then
      repeat
        MoveMouseRelative(horizontalForce, verticalForce)
        Sleep(delayMS)
      until not (IsMouseButtonPressed(1) and IsMouseButtonPressed(3))
    end
  end
end




------ATTACK----
--ZERO = 23
--ASH = 26, -2
--JACKAL = 20
--TWITCH = 15
--BUCK = 22
--ACE = 22
--NOKK = 22
--IANA = 20
--SLEDGE = 18, 1
--FUZE = 9 
--YING = 20
--LION = 15
--SMG AMARU = 12
--THATCHER = 16
--DOKKAEBI = 15, 2
--KALI = 8

----DEFENSE----

--TACHANKA = 8
--AZAMI = 8
--KAPKAN = 8
--ROOK = 21
--THORN = 7
--SOLIS = 9
--SMG SMOKE = 15
--SMG MUTE = 12
--ARUNI = 8
--ECKO = 22
--BANDIT = 8
--KAID = 7
