---
hidden: true
---

# ship\_wrecks

Like treasures, ship wrecks are geolocated rewards, however they do not appear on the player's map until he/she finds them.

A ship wreck is defined by :

* A location (lon, lat)
* An expiration delay
* Rewards:
  * A value in PGLD ranging from 0 to half of the max treasure value
  * 0 to 3 wrecked pirates

?> for more information about the max treasure value, see [Treasures](game_concepts/treasures.md)

Everytime a player finds a ship wreck he/she gets a fixed amount of PRBT as well.

### Wreck polling

In order to reveal a ship wreck on the map, the player needs to "poll" (by explicitly clicking a button on the map).

When a wreck is located at under a given distance, polling reveals the wreck on the map.

This polling distance depends on the crew navigation and mercy skills. The better they are, the further the crew will be able to localise a wreck.

The polling distance (in meters) formula is :

> $nt + mt$

where:

* $nt$ is the navigation skill total of each pirate of the crew
* $mt$ is the mercy skill total of each pirate of the crew

For example a crew with a navigation skill of 300 and a mercy skill of 200 has a polling distance of 500m.

### Spawning

The number of spawned ship wrecks in a hunt depends on 2 factors:

* the crew size (number of pirates in the crew)
* the rate of expired treasures by every player on the previous day

The formula is then:

> $re \* cs$

Rounded to upper integer.

where:

* $re$ is the expirated treasures rate on the pevious day
* $cs$ is the crew size

As example, a crew size of 3 pirates, with a previous day treasure expirated rate of 0.5 gives:

$rounded(3 \* 0.5) = 2$

That is 2 ship wrecks will be spawned for the hunt.

### Location

Ship wreck location works the same as treasures.

?> See [Treasures](game_concept/treasures.md) for more details.

### Expiration delay

Ship wreck expiration delay works the same as treasures.

?> See [Treasures](game_concept/treasures.md) for more details.

### Rewards

Ship wreck reward may be: PGLD or / and pirates.

#### Pirates

Ship wrecks contain pirates only if the crew ship capacity is not reached.

For example, if ship capacity is 4, and the crew has only 3 pirates, wrecks may contain at least one pirate.

However if the ship capacity is reached (4 pirates), wrecks will not contain any pirate.

The number of pirates in a wreck is set randomly with a limit set to 2 or the ship reamining capacity.

#### PGLD

PGLD value containes in wreck applies the same formula applied to treasures but with a 0.5 factor, that is:

> $((st + nt)\* (mtv / 2000)) \* r \* 0.5$

?> See [Treasures](game_concept/treasures.md) for more details.
