Treasures are geolocated rewards for players.

A treasure is defined by :
- A location (lon, lat)
- An expiration date
- A value in PGLD (the reward)


## Spawning

In VS mode treasures are spawned anywhere, at anytime.

In solo mode treasures are spawned all around the player's current location when the hunt starts.

The number of spawned treasures in a hunt depend on the crew size (number of pirates in the crew) plus a random factor:

| Crew size    	| Expected treasures 	|
|--------------	|--------------------	|
| 1            	| 1 to 2             	|
| 2 to 4       	| 4 to 8             	|
| 4 to 8       	| 8 to 14            	|
| 8 to 12      	| 14 to 20           	|
| 12 to 16     	| 20 to 30           	|
| more than 20 	| 40 to 60           	|


## Location

Treasures location are set in a 5km range around the player when he/she starts the hunt.

The distance to the player is influenced by the ship speed skill: the faster a ship is, the higher the probability is to have treasures closer to the player.

Distance computation formula is:

> $md - ((r * md) * (s / 10))$

where:
- $md$ is the maximum distance (5km)
- $r$ is a random ratio
- $s$ is the ship speed

For example, a crew with no ship (speed = 1) and a random ratio of 0.3 gives the distance of:

$5km - ((0.3 * 5km) * (1 / 10)) = 4,85km$

Other examples:

| Random ratio 	| Ship speed = 1 	| Ship speed = 50 	| Ship speed = 100 	|
|--------------	|----------------	|-----------------	|------------------	|
| 0.1          	| 4.95km         	| 4.75km          	| 4.5km            	|
| 0.2          	| 4.9km          	| 4.5km           	| 4km             	|
| 0.3          	| 4.85km        	| 4.25km           	| 3.5km            	|
| 0.4          	| 4.8km            	| 4km             	| 3km              	|
| 0.5          	| 4.75km         	| 3.75km           	| 2.5km            	|
| 0.6          	| 4.7km         	| 3.5km            	| 2km              	|
| 0.7          	| 4.65km           	| 3.25km           	| 1.5km            	|
| 0.8          	| 4.6km            	| 3km              	| 1km             	|
| 0.9          	| 4.55km           	| 2.75km           	| 0.5km            	|
| 1.0          	| 4.5km            	| 2.5km            	| 0km              	|


## Expiration date

Each treasure has an expiration delay.

An expired treasure cannot be found and disappears from the player's map.

In VS mode a treasure has always a one day expiration delay.

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

For a crew with a total of 250 in combat skill and 320 in navigation skill and a random ration of 0.4:

($(250 + 320) * 0.4) + 30 = 258min = 4h18min$

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


## Value

In order to reward all the users the max treasure value is recalculated every day (00:00 CET). 

The max treasure value computation formula is :

> $(x - X) / (2y - z)$

where:
- $x$ is the PGLDs available in reward
- $X$ is the security margin constant, set to 20% of the PGLD in rewards
- $y$ is the number of treasure generated last day
- $z$ is the number of treasure generated day before yesterday

Example :
If yesterday the game generated 300 treasures, the day before yesterday the game generated 280 treasures and there is 10 000 PGLD available in rewards :

$(10 000 - (10 000 * 0.2)) / (2 * 300 - 280) = 25$ PGLD

In this example we saw that the max treasure value is 25 PGLD.
