
When the player has setup his/her crew, he/she is able to start a treasure hunt.

```blockdiag
blockdiag {
  default_shape = roundedbox
  
  "Select mode" -> "Hunt start";
  "Hunt start" -> "Hunt end";
  "Hunt end" -> "Crew rest" -> "Select mode";

  "Select mode" [color = "#FEF58F"];
  "Hunt start" [color = "#BCD3FB"];
  "Hunt end" [color = "#E0ADFA"];
  "Crew rest" [color = "greenyellow"];

 
}
```

| Stage      	| Description                                                                                           	|
|------------	|-------------------------------------------------------------------------------------------------------	|
| Select mode      	| Before starting ahunt, the player chooses solo mode or VS mode.                        	|
| Hunt start        	| When the hunt starts, in solo mode: treasures and ship wrecks are spawned on based on the current player crew skills. In VS mode, treasures can spawn at anytime (before, or during the hunt). 	|
| Hunt end 	| In solo mode, hunt ends when all treasures are expired. In VS mode, hunt ends when the player finds a treasure or after 4 hours.      	|
| Crew rest       	| When a hunt ends, the crew needs rest (time) before starting a new hunt. The duration of the rest varies according to the crew skills.                                      	|

## Modes

### Solo hunt

In a solo hunt, players have to find treasures that only them can see.

When a player wants to play he/she needs to explicitly start a solo hunt.

A solo hunt can be started when :
- his/her previous solo hunt already ended
- the crew had enough rest since the previous hunt. This rest time varies according to the crew skills

A solo hunt ends when all treasures expire.

When starting a solo hunt , the game system spawns several treasures around the player location, and everytime he/she reaches this physical location he/she is rewarded with PGLD.

While moving towards treasure locations players may discover ship wrecks containing pirates and / or PGLD tokens.

Players can see treasures on their map, but have to "pole" to see ship wrecks.

### VS hunt

In VS hunt mode, players have to find the same treasures, and the first reaching the location wins all the PGLD (winner takes all). 

The VS hunt treasure value is greater than the solo hunt treasure.

The hunt ends as soon as the player finds a treasure or after 4 hours.

A player cannot start a solo hunt and a VS hunt at the same time.

### Rest time

The rest time between two hunts is deterined by the crew combat skill.

The formula to compute the crew rest time (in minutes) is:

> $((r / ct ) * 10000) + m$

where:
- $ct$ is the combat skill total of each pirate of the crew
- $cs$ is the crew size (number of pirates in the crew)
- $r$ is a random ratio
- $m$ is the minimumn rest duration in minutes (15min)

For a crew with a total of 250 in combat skill, and a random ratio of 0.3:

$ ((0.3 / 250) * 10000) + 15 = 27min$

Other examples:

| Random ratio 	| ct = 50 	| ct = 250 	| ct = 500 	|
|--------------	|---------	|----------	|----------	|
| 0.1          	| 35min   	| 19min    	| 17min    	|
| 0.2          	| 55min   	| 23min    	| 19min    	|
| 0.3          	| 1h15min 	| 27min    	| 21min    	|
| 0.4          	| 1h35min 	| 31min    	| 23min    	|
| 0.5          	| 1h55min 	| 35min    	| 25min    	|
| 0.6          	| 2h15min 	| 39min    	| 27min    	|
| 0.7          	| 2h35min 	| 43min    	| 29min    	|
| 0.8          	| 2h55min 	| 47min    	| 31min    	|
| 0.9          	| 3h15min 	| 51min    	| 33min    	|
| 1            	| 3h35min 	| 55min    	| 35min    	|


### Crew trading during a hunt

When a hunt is in progress, the player is free to trade pirates, ship and items NFTs of his/her crew. However, those cannot be involved into another player's hunt until this one is finsihed.
