---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - V-Handle

toc_footers:

includes:
  - errors

search: true
---

# Introduction

Welcome to the documentation for Avalon!

If anything is outdate or missing, please let us know and we will fix this ASAP.

# User commands

## Spectating
> Start spectating (free roam camera):

```V-Handle
spectate/
```

> Spectating a user named 'Joe':

```V-Handle
spectate/Joe
```

> Stop spectating:

```V-Handle
unspec/
```

> You can press 'spacebar' to switch between free-roam and auto follow mode

You can specate players in the game by using <code>spectate/@player_name</code> or start a free roam camera by using <code>spectate/</code>

## AFK

> Set yourself as AFK

```V-Handle
afk/
```

> Set yourself as back

```V-Handle
back/
```

Using `afk/` will prevent you from being set to either red or blue when a simulation is being loaded. 

<aside class="notice">
Make sure to mark yourself as back using <code>back/</code>.
</aside>

<aside class="notice">
Trainers can still set people who are AFK to a specfic team when using <code>set/player/team</code>. This only prevents you from being teamed when the trainer uses <code>balance/</code>.
</aside>


## Macro

### Run macro
### Starting macro capture
### Saving macro capture
### Discard macro capture


# Trainer Commands

## Maps

### Arena
> Load arena:

```V-Handle
arena
```

An arena can be opened under the temple with <code>arena/</code>


### Loading
> Example of loading 'bricktops':

```V-Handle
load/bricktops
```

> You can also load based on partial names.

```V-Handle
load/brick
```

> A list of maps can be found below.

The <code>load/@map_name</code> command can be used to load maps into the simulation. 

The following things happen, by default, when running the <code>load/</code> command:  

* All previous loaded modifiers are removed/disabled
* MaxLives is set to 11
* All the onfiguration variables are reset to their original state (see 'Configurations')
* The map will be rendered in the simulation

<aside class="notice">
You must use <code>end/</code> to end the simulation of a loaded map manually.
</aside>

<aside class="notice">
While a map is loaded in the simulation, no other map can be loaded in the simulation.
</aside>

### Ending
> Example of ending the current map:

```V-Handle
end/
```
The <code>end/</code> command can be used to end the simulation of a loaded map manually.  
Some map simulations are be ended automatically, eg when a VIP target dies in assasination.  

### Map list
| Map name         | Type    | KOTH | DOM | CTF |
|------------------|---------|------|-----|-----|
| Bastion          | Bricks  | Y    | Y   | N   |
| Bricktops        | Bricks  | Y    | N   | N   |
| Bridges          | Bricks  | Y    | Y   | N   |
| Cache            | Bricks  | Y    | N   | N   |
| Castletops       | Bricks  | Y    | N   | N   |
| Catwalks         | Bricks  | N    | N   | N   |
| City             | Bricks  | Y    | Y   | Y   |
| Colosseum        | Bricks  | N    | N   | N   |
| Cordovan         | Bricks  | Y    | Y   | N   |
| Cornerstone      | Bricks  | Y    | N   | N   |
| Corp             | Bricks  | Y    | Y   | Y   |
| Corporate        | Bricks  | N    | N   | N   |
| Cross            | Bricks  | N    | N   | N   |
| Crown            | Bricks  | Y    | Y   | Y   |
| Crowntops        | Bricks  | N    | N   | N   |
| Darkside         | Bricks  | Y    | N   | N   |
| Division         | Bricks  | N    | N   | N   |
| Dust             | Bricks  | N    | N   | Y   |
| Dust2            | Bricks  | Y    | Y   | N   |
| Factory          | Bricks  | Y    | N   | N   |
| FairCity         | Bricks  | Y    | Y   | Y   |
| Hollows          | Bricks  | N    | N   | N   |
| Island           | Bricks  | Y    | N   | N   |
| JumpPads         | Bricks  | N    | N   | N   |
| Trainyard        | Bricks  | Y    | Y   | Y   |
| Maze             | Bricks  | N    | N   | Y   |
| Meadows          | Bricks  | Y    | N   | N   |
| Narrowgill       | Bricks  | Y    | Y   | N   |
| TwoSides         | Bricks  | Y    | Y   | Y   |
| Overpass         | Bricks  | Y    | N   | N   |
| Ozburn           | Bricks  | Y    | N   | N   |
| Pitgrounds       | Bricks  | Y    | Y   | Y   |
| Prospect         | Bricks  | N    | N   | N   |
| Rural            | Bricks  | Y    | N   | N   |
| Sandtops         | Bricks  | N    | N   | N   |
| Scrapheap        | Bricks  | N    | Y   | N   |
| Sector9          | Bricks  | Y    | N   | N   |
| SkyFactory       | Bricks  | N    | N   | N   |
| View             | Bricks  | N    | N   | N   |
| Spyder           | Bricks  | N    | N   | N   |
| Steeltops        | Bricks  | Y    | N   | N   |
| Stonebrick       | Bricks  | Y    | N   | N   |
| SwordBridge      | Bricks  | Y    | N   | N   |
| SwordFightPlains | Bricks  | N    | N   | N   |
| SwordPlains      | Bricks  | Y    | N   | N   |
| Temple           | Bricks  | Y    | Y   | Y   |
| TinpotOps        | Bricks  | Y    | N   | N   |
| Trains           | Bricks  | Y    | Y   | Y   |
| LargeForrest     | Terrain | N    | N   | N   |
| NordicVolcano    | Terrain | N    | N   | N   |
| SmallForest      | Terrain | N    | N   | N   |
| Tundra           | Terrain | N    | N   | N   |
| Valley           | Terrain | N    | N   | N   |
| WashedLands      | Terrain | N    | N   | N   |
| Wasteland        | Terrain | N    | N   | N   |

## Weapons

> Toggle a sword red & blue:

```V-Handle
toggle/sword/red,blue
```

> Toggle a saw for red, spider for blue:

```V-Handle
toggle/saw/red
toggle/spider/blue
```

> Toggle a gun progression for gungame saw for 0 kills, spider for 5 kills, cypher for 10 kills:

```V-Handle
toggle/saw/red,blue/0
toggle/spider/red,blue/4
toggle/cypher/red,blue/10
```

### Toggle
<code>toggle/@weapon_name/@team/@kill_amount</code> can be used to toggle weapons that can be used during a simulation.

### Untoggle
<code>untoggle/@weapon_name/@team</code> to untoggle certain weapons.

### Weapon list

| Weapon name |
|-------------|
| Dragonshout |
| Sword       |
| Saw         |
| Service     |
| Spider      |
| Silenced    |
| Sub4S       |
| M3-D        |
| Cypher      |
| Designation |
| Replication |
| AT96        |
| Type_15     |
| Firefly     |
| RSE         |
| Zero        |
| Stumpy      |
| Rotational  |
| Minigun     |
| Medpack     |

## Modifiers

> Loading assasinate and setting 2 VIPs

```V-Handle
modifier/assasinate
vip/redplayer
vip/blueplayer
```

> Loading gungame

```V-Handle
modifier/gungame
toggle/saw/red,blue/0
toggle/spider/red,blue/4
toggle/cypher/red,blue/10
```

> Loading a battle royale game with crates

```V-Handle
modifier/br
modifier/crates
modifier/ffa
toggle/spider/red,blue
ac/regencrates/true
ac/maxlives/1
```

> Load a funny game mode

```V-Handle
modifier/penguin
modifier/icemap
modifier/gravityswitch
toggle/firefly/red,blue
ac/walkspeed/64
ac/health/200
```


### Loading modifiers
Modifiers can be loaded using <code>modifier/@modifier_name</code>. Some modifiers such as CTF, DOM, KOTH only work on certain maps (see map list). BR only works on terrain based maps.

### Unloading modifiers
Modifiers can be unloaded/removed using <code>removemodifier/@modifier_name</code>.

<aside class="notice">
All modifiers are unset after a map is ended.
</aside>


### Modifier list
| Modifier name | Modifier description                                                                                                                |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assasinate    | Players are tasked to protect their VIP, if the VIP dies then the team looses                                                       |
| AutoDuels     | This gamemode automatically puts in x amount of players in red and blue. When someone dies/leaves the player will be replaced       |
| Crates        | This makes supply crates visible on certain maps                                                                                    |
| DoppleGanger  | Everyone looks alike                                                                                                                |
| FallDamage    | Enable fall damage                                                                                                                  |
| Gungame       | This gamemode grants new weapons to players as they get kills. You can configure the gun progression with the weapon toggle command |
| NoJump        | Disables any jump mechanics                                                                                                         |
| NoRegen       | Disables health regeneration                                                                                                        |
| RegenCrates   | This makes supply crates regenerate over time                                                                                       |
| FFA           | Enables FFA (Free For All), this enables team killing                                                                               |
| OneHitKill    | Makes any weapon a one hit kill weapon                                                                                              |
| WeaponDrop    | Players drop a crate on dead with the contents of their backup in it                                                                |
| CTF           | Enables Capture The Flag                                                                                                            |
| DOM           | Enables Domination points                                                                                                           |
| KOTH          | Enables King Of The Hill                                                                                                            |
| TDM           | Enables Team Death Match                                                                                                            |
| ResetKills    | Reset a player's kills on death, useful to change gungame's behaviour                                                               |
| NoSwim        | Respawn players automatically if they start swimming                                                                                |
| BR            | This loads some Battle Royale settings into the game                                                                                |
| BigHead       | Big heads! THIS IS A FUN/EXPERIMENTAL MODIFIER, HAVE NO EXPECTATIONS :)                                                             |
| CatGame       | Meow! THIS IS A FUN/EXPERIMENTAL MODIFIER, HAVE NO EXPECTATIONS :)                                                                  |
| GravitySwitch | Switches gravity after set intervals. See ac/gravityon ac/gravityoff ac/gravityondelay ac/gravityoffdelay                           |
| IceMap        | Makes the map very slippery... (only works for brick maps)                                                                          |
| Penguin       | Slide slide penguins! THIS IS A FUN/EXPERIMENTAL MODIFIER, HAVE NO EXPECTATIONS :)                                                  |


## VIP
Use <code>vip/</code> to mark or unmark a VIP target

## Balance
Use <code>balance/</code> to balance teams

## Point Of Interest (POI)

> Set current POI to obby

```V-Handle
poi/obby
```

> Set current POI to lobby

```V-Handle
poi/lobby
```

Use <code>poi/@poi_name</code> to set a POI. This will set the default spawn locations within the lobby to a particular area. When you enter a wrong poi name it will default to 'lobby'

| POI Name |
|----------|
| Lobby    |
| Obby     |
| Hill     |
| River    |
| Forest   |
| Beach    |


## Obby
Use <code>obby/</code> to regenerate the obbies on the island

## Beacon
Use <code>beacon/@player_name</code> to add a beacon to a player
Use <code>removebeacon/@player_name</code> to add a beacon to a player

## Temple lockdown/forcefield
Use <code>templelockdown/true</code> to lockdown the temple  
Use <code>templelockdown/false</code> to remove the lockdown from the temple

## Configurations
> Setting maxlives to 30:

```V-Handle
ac/maxlives/30
```

> Setting maxkills to 7: 

```V-Handle
ac/maxkills/7
```

> Setting winpoints to 160: 

```V-Handle
ac/winpoints/160
```

> Setting pointsperflag to 40: 

```V-Handle
ac/pointsperflag/40
```

> Setting pointsperpoint to 2: 

```V-Handle
ac/pointsperpoint/2
```

> Setting pointsperkill to 10: 

```V-Handle
ac/pointsperkill/10
```

> Setting leftscreen to "Hello!": 

```V-Handle
ac/leftscreen/"Hello!"
```

> Setting rightscreen to "I like trains!": 

```V-Handle
ac/rightscreen/"I like trains!"
```

> Setting obbydifficulty to 0: 

```V-Handle
ac/obbydifficulty/0
```

> Setting autobalance to true: 

```V-Handle
ac/autobalance/true
```

> Setting regencrates to true: 

```V-Handle
ac/regencrates/true
```

> Setting regencratesmin to 5: 

```V-Handle
ac/regencratesmin/5
```

> Setting regencratesmax to 10: 

```V-Handle
ac/regencratesmax/10
```

> Setting health to 200: 

```V-Handle
ac/health/200
```

> Setting walkspeed to 64: 

```V-Handle
ac/walkspeed/64
```

> Setting gravityon to 200: 

```V-Handle
ac/gravityon/200
```

> Setting gravityoff to 50: 

```V-Handle
ac/gravityoff/50
```

> Setting gravityondelay to 20: 

```V-Handle
ac/gravityondelay/20
```

> Setting gravityoffdelay to 5: 

```V-Handle
ac/gravityoffdelay/5
```


Use <code>ac/@config/@value</code> to set certain config values  

| Config name     | Config description                                                                                                                                           | Config options          | Default | Example                         |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|---------|---------------------------------|
| maxlives lives  | Max amount of lives a player has. When a player reaches this amount of WOs, this player will become a spectator.   Set this value to -1 for unlimited lives. | Any number              | 11      | ac/maxlives/30                  |
| maxkills kills  | When a player reaches this amount of KOs/kills, this player will cause it's team to win.  Set this value to -1 to disable this.                              | Any number              | -1      | ac/maxkills/7                   |
| winpoints       | Amount of points a team needs to win a round.  This value is increased by certain objectives such as TDM, CTF, DOM, KOTH, ...                                | Positive number         | 240     | ac/winpoints/160                |
| pointsperflag   | The amount of points a team gets per flag capture. (Only works when CTF is active)                                                                           | Positive number         | 80      | ac/pointsperflag/40             |
| pointsperpoint  | The amount of points a team gets per point per second they own. (Only works when DOM or KOTH is active)                                                      | Positive number         | 1       | ac/pointsperpoint/2            |
| pointsperkill   | The amount of points a team gets per KO/kill they make. (Only works when TDM is active)                                                                      | Positive number         | 1       | ac/pointsperkill/10             |
| leftscreen      | Set the text of the left hand screen in the lobby.                                                                                                           | String/text             |         | ac/leftscreen/"Hello!"          |
| rightscreen     | Set the text of the right hand screen in the lobby.                                                                                                          | String/text             |         | ac/rightscreen/"I like trains!" |
| obbydifficulty  | Sets the obby difficulty. 1 = Easy mode 0 = Hard mode                                                                                                        | 0 or 1                  | 1       | ac/obbydifficulty/0             |
| autobalance     | Enables auto balancing of teams. When a new player joins, this player will be put in a team automatically.                                                   | Boolean (true or false) | false   | ac/autobalance/true             |
| regencrates     | Disable or enable regenerative crates during eg Battle Royale maps.                                                                                          | Boolean (true or false) | false   | ac/regencrates/true             |
| regencratesmin  | Sets the min time before a crate regenerates.                                                                                                                | Positive number         | 20      | ac/regencratesmin/5             |
| regencratesmax  | Sets the max time before a crate regenerates.                                                                                                                | Positive number         | 60      | ac/regencratesmax/10            |
| health          | Sets the default health of all players.                                                                                                                      | Positive number         | 100     | ac/health/200                   |
| walkspeed       | Sets the default walkspeed of all players.                                                                                                                   | Positive number         | 16      | ac/walkspeed/64                 |
| gravityon       | The gravity when the gravity is 'on' in the gravityswitch modifier.                                                                                          | Positive number         | 196.2   | ac/gravityon/200                |
| gravityoff      | The gravity when the gravity is 'off' in the gravityswitch modifier.                                                                                         | Positive number         | 16      | ac/gravityoff/50                |
| gravityondelay  | The amount of time that the gravity is 'on' in the gravityswitch modifier.                                                                                   | Positive number         | 60      | ac/gravityondelay/20            |
| gravityoffdelay | The amount of time that the gravity is 'off' in the gravityswitch modifier. 



