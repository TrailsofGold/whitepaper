<p align="center">
  <img width="128" height="128" src="./img/ship1.png">
  <img width="128" height="128" src="./img/ship2.png">
  <img width="128" height="128" src="./img/ship3.png">
  <img width="128" height="128" src="./img/ship4.png">
</p>

Ships are NFTs that can be bought by players with PGLD and PRBT.

## Seasons

Ships NFTs are gathered into collections (Smart Contracts) named "seasons".

Each season provides a set of ships, and each ship has a variable mint occurence according to its skills (the best the skills are, the rarest the pirate is).


## Skills

Ships skills are:
- Speed
- Armament
- Capacity

Speed and Armament affect the game mechanics as Capacity gives the maximum crew size.

If a player has more pirates that his/her ship capacity he/she can modify his/her crew composition in between each treasure hunt.

He/she can also sell or trade pirates that he/she does not use.

## Types

Ships can be of different types.

The ship type as an incidence on its caracterics. 

Some types are more common than others (gen occurence).

| Type       	| Capacity 	| Speed  	| Armament 	| Gen occurence 	  |
|------------	|----------	|--------	|----------	|-----------------	|
| Sloop      	| 4-6      	| 10-100 	| 10-60    	| 10              	|
| Schooner   	| 5-10     	| 10-90 	| 10-70    	| 7               	|
| Brigantine 	| 10-15    	| 10-80 	| 15-100   	| 3               	|
| Frigate    	| 15-20    	| 10-75  	| 20-100   	| 2               	|

## Rarity level

Like pirates, ship types have rarity levels. The rarest a ship is, the best its skills are.

Ships skill point are speed and armament.

| Level     | Sum of skill points | Mint occurence|
|-----------|---------------------|----------------|
| Common    | 40                  | 60             |
| Rare      | 70                  | 35             |
| Epic      | 95                  | 30             |
| Legendary | 175                 | 25             |


For example if the season has 4 common ships, 3 rare ships, 2 epic ships and 1 legendary ship, the sum of occurences are:

$4 * 60 + 3 * 35 + 2 * 30 + 25 = 430$

Meaning that a player has :
- 25 chances out of 430 to get a legendary ship
- 60 chances out of 430 to get an epic ship
- 105 chances out of 430 to get a rare ship
- 240 chances out of 430 to get a common ship

If mixed with ship type, the sum of occurences are:

$430 * 10 + 430 * 7 + 430 * 3 + 430 * 2 = 9 460$

Meaning that a player has :
- 50 chances ( 25 * 2) out of 9 460 to get a legendary Frigate
- 90 chances (30 * 3) out of 9 460 to get an epic Brigantine
- 600 chances (10 * 60) out of 9 460 to get a common Sloop

## Mainteance

After a hunt a ship needs maintenance. And during mainteance time, it cannot be used in a new hunt.

Ship mainteance time is calculated according to its capacity skill: 3 hours per capacity.

Examples:

| Capacity  | Maintenance duration (hours) |
|-----------|------------------------------|
| 4         | 12                           |
| 8         | 24                           |
| 12        | 36                           |
| 20        | 60                           |

?> Note: if the player owns multiple ships with the same id, maintenance time is divided by the number of copies. Example: if player owns 2 copies of ship #5 (capacity 5): maintenance time will be $5 * 3 / 2 = 7h30$.