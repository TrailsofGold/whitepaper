<p align="center">
  <img width="128" src="./img/chest.png">
</p>

Treasures are geolocated rewards for players.

A treasure is defined by :
- A location (lon, lat)
- An expiration delay
- A value in PGLD (the reward)

Everytime a player finds a treasure he/she gets a fixed amount of PRBT as well.

## Spawning

### Solo mode

In solo mode treasures are spawned all around the player's current location when the hunt starts.

The number of spawned treasures in a hunt depends on the crew size (number of pirates in the crew):

| Crew size    	| Expected treasures |
|--------------	|--------------------|
| 1            	| 2            	     |
| 2      	    | 4            	     |
| 4    	        | 8          	     |
| 20 	        | 40           	     |

The max crew size is capped to 20.

### VS mode

In VS mode treasures are spawned where the most solo mode treasures (not expired) are.

A new VS mode treasure is spawned every 2 hours.

If there is no VS treasure in a 1.5km range arround the player when he/she selects a VS mode hunt: he/she is warned that there is no treasure around, so that he/she does not waste a hunt for nothing.


## Location

### Solo mode

In solo mode, treasures location are set in a 1.5km range around the player when he/she starts the hunt.

The distance to the player is influenced by the ship speed skill: the faster a ship is, the higher the probability is to have treasures closer to the player.

Distance computation formula is:

> $md - ((r * md) * (\sqrt{s * 10} * md / 100))$

where:
- $md$ is the maximum distance (1.5km)
- $r$ is a random ratio
- $s$ is the ship speed

For example, a crew with no ship (speed = 1) and a random ratio of 0.3 gives the distance of:

$1.5 - ((0.3 * 1.5) * (\sqrt{1 * 10} * 1.5 / 100)) = 1.48km$

Other examples (rounded to 2 decimals):

| Random ratio | Ship speed = 1 | Ship speed = 50 | Ship speed = 100 |
|--------------|----------------|-----------------|------------------|
| 0.1          | 1.49 km        | 1.45 km         | 1.43 km          |
| 0.2          | 1.49 km        | 1.40 km         | 1.36 km          |
| 0.3          | 1.48 km        | 1.35 km         | 1.29 km          |
| 0.4          | 1.47 km        | 1.30 km         | 1.22 km          |
| 0.5          | 1.46 km        | 1.25 km         | 1.14 km          |
| 0.6          | 1.46 km        | 1.20 km         | 1.07 km          |
| 0.7          | 1.45 km        | 1.15 km         | 1.00 km          |
| 0.8          | 1.44 km        | 1.10 km         | 0.93 km          |
| 0.9          | 1.44 km        | 1.05 km         | 0.86 km          |
| 1            | 1.43 km        | 1.00 km         | 0.79 km          |

In order to keep the game entraining, half of the treasures spawned for a hunt are closer by 30% to the player initial location.

As an example, in a hunt with a single pirate, 2 treasures are spawned:
- The first one will be located according to the above location formula: $1.48km$
- The second one will located at 30% of the the first one distance, that is $1.48 * 0.3 = 444m$

### VS mode

In VS mode, the game system checks where the most active solo mode treasures are (clusters), and spawns a VS mode treasure in the middle.

If there is already a VS mode treasure in a 10km range, the system moves to the next most "crowded" cluster, and so on.

A new VS mode treasure is spawned 2 hours.


## Expiration delay

Each treasure has an expiration delay.

An expired treasure cannot be found and disappears from the player's map.

### Solo mode

In solo mode, the expiration delay is computed according to the crew combat and navigaton skills, plus a random factor.

The minimum expiration delay is 30 minutes, the maximum is one day.

The expiration delay (in minutes) computation formula is:

> $((ct + nt) * r) + m$

where:
- $ct$ is the combat skill total of each pirate of the crew
- $nt$ is the navigation skill total of each pirate of the crew
- $r$ is a random ratio
- $m$ is the minimumn expiration delay in minutes (30min)

When the result is above 24 hours. It is capped to 24 hours.

For a crew with a total of 250 in combat skill and 320 in navigation skill and a random ratio of 0.4:

$((250 + 320) * 0.4) + 30 = 258min = 4h18min$

More examples:

| Random ratio 	| ct + nt = 100 	| ct + nt = 500 	| ct + nt = 1000 	|
|--------------	|---------------	|---------------	|----------------	|
| 0.1          	| 40min         	| 1h20min       	| 2h10min        	|
| 0.2          	| 50min         	| 2h10min       	| 3h50min        	|
| 0.3          	| 1h            	| 3h            	| 5h30min        	|
| 0.4          	| 1h10min       	| 3h50min       	| 7h10min        	|
| 0.5          	| 1h20min       	| 4h40min       	| 8h50min        	|
| 0.6          	| 1h30min       	| 5h30min       	| 10h30min       	|
| 0.7          	| 1h40min       	| 6h20min       	| 12h10min       	|
| 0.8          	| 1h50min       	| 7h10min       	| 13h50min       	|
| 0.9          	| 2h            	| 8h            	| 15h30min       	|
| 1.0          	| 2h10min       	| 8h50min       	| 17h10min       	|

### VS mode

In VS mode a treasure has always a 4h expiration delay.


## Value

In order to be able to reward all the players. A max treasure value is used for every treasure value computation.

A treasure can never have a value greater than the max treasure value.

The max treasure value computation formula is :

> $(x - X) / (abs(2y - z) + 1)$

where:
- $x$ is the amount PGLD available in rewards
- $X$ is the security margin constant, set to 20% of the PGLD in rewards
- $y$ is the number of treasures generated the previous day
- $z$ is the number of treasures generated day before yesterday

Example :
If yesterday the game generated 300 treasures, the day before yesterday the game generated 280 treasures and there is an amount of 10000 PGLD available in rewards :

$(10000 - (10000 * 0.2)) / (abs(2 * 300 - 280) + 1) = 24.92$ PGLD

?> For more information about PGLD rewards amount, see [PGLD token](tokenomics/pgld_token.md)

### Solo mode

Once the max treasure value is known it is used to calculate treasure value for each treasure of the game in solo mode.

The crew strategy and navigation skills are used to 

The treasure value computation formula is:

> $((st + nt)* (mtv / 2000)) * r$

where:
- $st$ is the strategy skill total of each pirate of the crew
- $nt$ is the navigation skill total of each pirate of the crew
- $mtv$ is the maximum treasure value
- $r$ is a random ratio

When result is greater than max treasure value, it is capped to max treasure value.

If a crew strategy skill is 500, navigation skill is 350, max treasure value is 25 PGLD, and random ratio is 0.4, then the treasure value is:

$((500 + 350) * (25 / 2000)) * 0.4 = 4.25$ PGLD

More examples:

| Random ratio 	| st + nt = 100 	| st + nt = 500 	| st + nt = 1000 	|
|--------------	|---------------	|---------------	|----------------	|
| 0.1          	| 0.13 PGLD     	| 0.63 PGLD     	| 1.25 PGLD      	|
| 0.2          	| 0.25 PGLD     	| 1.25 PGLD     	| 2.50 PGLD      	|
| 0.3          	| 0.38 PGLD     	| 1.88 PGLD     	| 3.75 PGLD      	|
| 0.4          	| 0.50 PGLD     	| 2.50 PGLD     	| 5.00 PGLD      	|
| 0.5          	| 0.63 PGLD     	| 3.13 PGLD     	| 6.25 PGLD      	|
| 0.6          	| 0.75 PGLD     	| 3.75 PGLD     	| 7.50 PGLD      	|
| 0.7          	| 0.88 PGLD     	| 4.38 PGLD     	| 8.75 PGLD      	|
| 0.8          	| 1.00 PGLD     	| 5.00 PGLD     	| 10.00 PGLD     	|
| 0.9          	| 1.13 PGLD     	| 5.63 PGLD     	| 11.25 PGLD     	|
| 1.0           | 1.25 PGLD     	| 6.25 PGLD     	| 12.50 PGLD     	|

Like location, treasure value is then assigned by pair:
- the first treasure (the furthest) get 90% of the calculated treasure value
- the seconde one (the closest) get 10% of the calculated treasure value

### VS mode

In VS mode, the treasure value is always 10% of the max treasure value.
