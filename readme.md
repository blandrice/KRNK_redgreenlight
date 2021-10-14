
# Red Light / Green Light in KrunkScript
https://streamable.com/dlyfa5

![video](2021-10-13_23-03-07.gif)


	
## V1.0 - redlight/greenlight functionality. 
If a player moves during redlight phase, they will get fired at until they are dead or the mark is removed.
- Determine firing range by using onenter trigger w/ customParam "inrange", "outrange"
- redlight starts by sending customParam message "redlight"
- redlight ends (greenlight starts) by sending customParam message "greenlight"
- to fine-tune, change values of KNOBS in the host.krnk file.

	```cs
	# ======================================================
	# KNOBS
	num VEL_NOTMOVING = 0.01; # how fast can a player move before we start shooting it (pixels/ms)
	num MS_FIRERATE = 1000; # how fast to shoot
	num GUNDAMAGE = 200; # how much damage per shot

	# wait periods
	num MS_MINREDLIGHT = 2000;     num MS_MAXREDLIGHT = 2000;
	num MS_MINGREENLIGHT = 1500;   num MS_MAXGREENLIGHT = 3000;
	num DURATION_SOUNDFILE = 3000; # change if the soundfile length is changed
	# ======================================================
	```
	
### Tips:
1. player always spawns out of range of firing
2. customParam messages are caps sensitive ("redlight" works, "ReDlIgHt" does not work)

## V1.1  
- 🔫 Gun will take time shooting the NEAREST marked players (start shooting the nearest player, after nearest marked player dies, start shooting next nearest player)
	- ⏱️❎ green light phase will only start when all marked players are dead
- 🎥 Animations done for 🎎 doll
- 🔊 Sounds for 🎵 Song and 💥Gunshot for death
- ▶️ Trigger added for 🏃🏠leaving gameroom
- 🔴 🟢 Simple Overlay indicating light is red/green 

## V1.2 (if you want :D then I will work on this)  

- Shows ❌ RED MARK underneath you if you are marked during redlight
	- will 🌘DARKEN the sky when u are about to be shot

- 🤖 robot head will PAUSE AND POINT LASER 😱 if it detects movement, & wait to DETECT MORE MOVEMENT 😣 before shooting
	- bullets will 🗡️PIERCE players and damage others behind them (requires raycasting (WIP) from KS, or my already made custom collision code 😏)
	- players can 😈 HIDE behind other players and continue moving (also requires raycasting (WIP) from KS, or my already made custom collision code 😏)
- optionally, players will NOT be allowed to 🛑↪️ ROTATE or even 🛑⬇️ CROUCH
- 🎬 CUTSCENE to start round 