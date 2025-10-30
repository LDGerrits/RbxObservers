# Players

The `observePlayer` observer can be used to observe when players enter and leave a game. The exit reason is passed to the returned callback. This will be `Enum.PlayerExitReason.Unknown` if the observer is cleaned up before an observed player leaves.

```lua
Observers.observePlayer(function(player)
	print(player.Name .. " entered game")
	
	return function(reason)
		print(player.Name .. " left game")
		print(`{player.Name} left game (or observer stopped) | reason: {reason.Name}`)
	end
end)
```
