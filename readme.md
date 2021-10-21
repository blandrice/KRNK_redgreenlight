
# Red Light / Green Light in KrunkScript

```cs
# ======================================================
# HOST KNOBS
num VEL_NOTMOVING = 0.01; # how fast can a player move before we start shooting it (pixels/ms)
num MS_FIRERATE = 1000; # how fast to shoot
num GUNDAMAGE = 200; # how much damage per shot



# Stage 1: Red/Green light
num MS_MINREDLIGHT = 2000;     num MS_MAXREDLIGHT = 2000;
num MS_MINGREENLIGHT = 1500;   num MS_MAXGREENLIGHT = 3000;
num MS_CLOCKTIMER = 50000; 
num MS_INTERVAL_CLOCKSYNC = 5000;

# Stage 2: honeycomb
obj[] honeycombstart = obj[ # randomly teleports to one of the positions below
	{x: -173, y: 100, z: 132}, # position 1
	{x: -173, y: 200, z: 132}, # position 2
	{x: -173, y: 300, z: 132} # position 3
];

# ======================================================
# CLIENT KNOBS
num MS_DURATION_SONG = 3000; # change if the soundfile length is changed
num MS_DURATION_BOTSCAN = 1000; # change if the soundfile length is changed
num MSDURATION_DROP = 1000; num MS_DURATIONDEATH = 3000;
# ======================================================
```

# Road Map
1. Red/Green light (additional features)
	- 🤖 robot head will PAUSE AND POINT LASER 😱 if it detects movement, & wait to DETECT MORE MOVEMENT 😣 before shooting
	- bullets will 🗡️PIERCE players and damage others behind them (requires raycasting (WIP) from KS, or my already made custom collision code 😏)
	- players can 😈 HIDE behind other players and continue moving (also requires raycasting (WIP) from KS, or my already made custom collision code 😏)
2. Honeycomb stage
	- parkour stage (randomly dropped into cirle, triangle, umbrella...)
	- timer for death
3. tug-of-war stage
	- clicker / left right key tapper in teams 
4. marbles
	- collect 20 marbles (spawn randomly)
5.  glass stepping stones
	- triggers for stepping (randomized left/right)
	- turn off/flicker environment lighting halfway through
6. Final Round - squid game
	- melee last man standing

## V2.0 - First Release
- Marbles Game
- squid game (teleport to squid zone)
- Winning messages
- fog setting for last game 
- many more sounds, background music
- images for win/red/greenlight
- updated death system to accomodate spectators
tbc.. 

## V1.2 
- doll now plays sound when turning head
- honeycomb random 3 spawn locations
- endgame trigger -> displays winner text & plays sound to everyone

## V1.1.1
- soldier shoot animation
- timer countdown
	- teleport to honeycomb after round end
- death animation

## V1.1  
- 🔫 Gun will take time shooting the NEAREST marked players (start shooting the nearest player, after nearest marked player dies, start shooting next nearest player)
	- ⏱️❎ green light phase will only start when all marked players are dead
- 🎥 Animations done for 🎎 doll
- 🔊 Sounds for 🎵 Song and 💥Gunshot for death
- ▶️ Trigger added for 🏃🏠leaving gameroom
- 🔴 🟢 Simple Overlay indicating light is red/green 




## V1.0 - redlight/greenlight functionality. 

https://streamable.com/dlyfa5

![video](2021-10-13_23-03-07.gif)

If a player moves during redlight phase, they will get fired at until they are dead or the mark is removed.
- Determine firing range by using onenter trigger w/ customParam "inrange", "outrange"
- redlight starts by sending customParam message "redlight"
- redlight ends (greenlight starts) by sending customParam message "greenlight"
- to fine-tune, change values of KNOBS in the host.krnk file.

### Tips:
1. player always spawns out of range of firing
2. customParam messages are caps sensitive ("redlight" works, "ReDlIgHt" does not work)
