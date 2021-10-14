
# Red Light / Green Light in KrunkScript

![video](2021-10-13_23-03-07.gif)
https://streamable.com/dlyfa5

	
## V1.0 - redlight/greenlight functionality. 
If a player moves during redlight phase, they will get fired at until they are dead or the mark is removed.
- Determine firing range by using onenter trigger w/ customParam "inrange", "outrange"
- redlight starts by sending customParam message "redlight"
- redlight ends (greenlight starts) by sending customParam message "greenlight"
- to fine-tune, change values of VEL_NOTMOVING, MS_FIRERATE, GUNDAMAGE in the host.krnk file.
	VEL_NOTMOVING: how fast can a player move before we start shooting it (pixels/ms)
	MS_FIRERATE: how fast to shoot
	GUNDAMAGE: how much damage per shot
	
### Tips:
1. player always spawns out of range of firing
2. customParam messages are caps sensitive ("redlight" works, "ReDlIgHt" does not work)
	
## V1.1 (if you want :D) 
- Shows RED MARK underneath you if you are marked during redlight
	- will DARKEN the sky when u are about to be shot
- Gun will take time shooting the NEAREST marked players (start shooting the nearest player, after nearest marked player dies, start shooting next nearest player)
	- green light phase will only start when all marked players are dead
- robot head will PAUSE AND POINT LASER if it detects movement, & wait to DETECT MORE MOVEMENT  before shooting
	- bullets will PIERCE players and damage others behind them (requires raycasting from KS, or my custom collision code)
	- players can HIDE behind other players and continue moving (also requires raycasting from KS, or my custom collision code)
- CUTSCENE to start round 