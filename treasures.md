# Treasure Sites

<div align="center"><img src="docs/game_concept/img/chest.png" alt="" width="128"></div>

Treasures are geolocated rewards for players.

A treasure is defined by :

* A location (lon, lat)
* An amount of GOLD (the reward)

Every time a player finds a treasure he/she gets a fixed amount of Gold as well.

### The Navigator's Utility

Treasures are unlocked all around the player's current location when the hunt starts.

The number of spawned treasures in a hunt depends on the level of The Navigator:

<table><thead><tr><th width="344">The Navigators Level</th><th>Expected treasures</th></tr></thead><tbody><tr><td>Common</td><td>2</td></tr><tr><td>Uncommon</td><td>4</td></tr><tr><td>Rare</td><td>6</td></tr><tr><td>Epic</td><td>8</td></tr><tr><td>Legendary</td><td>10</td></tr></tbody></table>

### Location

Treasures location are set in a 1.5km range around the player when he/she starts the hunt.

The distance to the player is influenced by the ships speed: the faster a ship is, the higher the probability is to have treasures closer to the player.

Distance computation formula is:

> $md - ((r \* md) \* (\sqrt{s \* 10} \* md / 100))$

where:

* $md$ is the maximum distance (1.5km)
* $r$ is a random ratio
* $s$ is the ship speed

For example, a crew with no ship (speed = 1) and a random ratio of 0.3 gives the distance of:

$1.5 - ((0.3 \* 1.5) \* (\sqrt{1 \* 10} \* 1.5 / 100)) = 1.48km$

Other examples (rounded to 2 decimals):

| Random ratio | Ship speed = 1 | Ship speed = 100 | Ship speed = 200 |
| ------------ | -------------- | ---------------- | ---------------- |
| 0.1          | 1.49 km        | 1.45 km          | 1.43 km          |
| 0.2          | 1.49 km        | 1.40 km          | 1.36 km          |
| 0.3          | 1.48 km        | 1.35 km          | 1.29 km          |
| 0.4          | 1.47 km        | 1.30 km          | 1.22 km          |
| 0.5          | 1.46 km        | 1.25 km          | 1.14 km          |
| 0.6          | 1.46 km        | 1.20 km          | 1.07 km          |
| 0.7          | 1.45 km        | 1.15 km          | 1.00 km          |
| 0.8          | 1.44 km        | 1.10 km          | 0.93 km          |
| 0.9          | 1.44 km        | 1.05 km          | 0.86 km          |
| 1            | 1.43 km        | 1.00 km          | 0.79 km          |

In order to keep the game entraining, half of the treasures spawned for a hunt are closer by 30% to the player initial location.

As an example, in a hunt with a single pirate, 2 treasures are spawned:

* The first one will be located according to the above location formula: $1.48km$
* The second one will located at 30% of the the first one distance, that is $1.48 \* 0.3 = 444m$



### Skipping

During a hunt a player can skip a treasure (because it is not reachable or he/she does not want to get it).

The ability to skip a treasure relies on the crew mercy skill: each mercy skill point give the player a skip point.

Skip points required to skip a given treasure depend on the distance between the player and the treasure he/she wants to skip: one skip point gives one meter skip distance.

For example: if the player wants to skip a treasure located 89 meters away from his/her location, the skip point amount required is 89.

### Value

In order to be able to reward all the players. A max treasure value is used for every treasure value computation.\
\
At 00:00 UTC, a snapshot of Captain Experience is Taken and the following calculation is processed.\
\
`Users Captain Experience/Total Captain Experience = % of Daily Treasure Pool Allocated to The User Captain.`\
\
The % of Daily Treasure Pool Allocated to The User Captain is then divided by the Maximum number of Chests Available in a Day.\
\
`% of Daily Treasure Allocated to The User Captain/10 = Treasure Value per Treasure site`



The User now has their Daily Treasure Site Value Allocation set.\
\
A user is only limited by the Rarity of Their Navigator as far as how many Treasure Sites can be collected each day.\
\
Any Treasure Site left unexplored by 00:00 UTC will be marked as Unclaimed and burned from the GOLD Supply

