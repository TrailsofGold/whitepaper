

<p align="center">
  <img width="128" src="./img/rudder.png">
</p>

Any player can start a hunt. However if a player starts a hunt without a pirate, he/she will not gt any reward when finding treasures.


```blockdiag
blockdiag {
  default_shape = roundedbox
  
  "Hunt start" -> "Hunt end";
  "Hunt end" -> "Crew rest" -> "Hunt start";

  "Hunt start" [color = "#BCD3FB"];
  "Hunt end" [color = "#E0ADFA"];
  "Crew rest" [color = "greenyellow"];

 
}
```

| Stage      	| Description                                                                                           	                              |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Hunt start 	| When the hunt starts, treasures are spawned on based on the current player crew skills.                               |
| Hunt end  	| Hunt ends when all treasures are expired.                                                             	                              |
| Crew rest  	| When a hunt ends, the crew needs rest (time) before starting a new hunt. The duration of the rest varies according to the crew skills.|

## Hunting

Players have to find treasures that only them can see.

When a player wants to play he/she needs to explicitly start a hunt.

A hunt can be started when :
- his/her previous hunt already ended
- the crew had enough rest since the previous hunt. This rest time varies according to the crew skills

A hunt ends when all treasures expire, or are found.

When starting a new hunt, the game system spawns several treasures around the player location, and everytime he/she reaches this physical location he/she is rewarded with PGLD and PRBT.

## Empty crew mode

If the player starts a hunt without a crew (at least one pirate), 4 treasures are spawned, but all of them will be emtpy (no PGLD or PRBT reward).

This mode was designed for trial / test mode.

## Rest time

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

## Ship maintenance

After a hunt, the ship used needs maintenance. When a ship is under maintenance, it cannot be used in a new hunt until its mainteance time is elapsed.

Ship mainteance time depends on its capacity.

?> For more information on ship mainteance, read [Ships](game_concept/ships.md)


## Crew trading during a hunt

When a hunt is in progress, the player is free to trade pirates, ship and items NFTs of his/her crew. However, those cannot be involved into another player's hunt until this one is finsihed.

If the player transfers (or burns) pirates, items or the ship used while hunting, he/she will not be able to dig treasures.

When the player receives a new pirate, item or ship from another player (NFT transfer), he/she will not be able to add it to his/her crew during 4 hours.
