# FPS-Limiter

local RunService = game:GetService("RunService")
local MaxFPS = 240
local LastFrameTime = tick()
local FrameTime = 0

```lua
while true do
	local t0 = tick()
	RunService.Heartbeat:Wait()
	local dt = t0 - LastFrameTime
	LastFrameTime = t0
	FrameTime = FrameTime + (dt - FrameTime) * 0.1 -- Smooth out frame time for more accurate limiter

	if FrameTime > 0 then
		local TargetFrameTime = 1/MaxFPS

		repeat until (t0 + TargetFrameTime) < tick()
	end
end
```
