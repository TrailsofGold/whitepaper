# The Ship

<div align="center"><img src="img/ship1.png" alt="" height="128" width="128"> <img src="img/ship2.png" alt="" height="128" width="128"> <img src="img/ship3.png" alt="" height="128" width="128"> <img src="img/ship4.png" alt="" height="128" width="128"></div>

**The Ship**

The Ship is the lifeblood of your fleet, a steadfast vessel that carries your crew and Captain to treasures across the vast seas. A well-maintained and upgraded ship ensures smoother voyages and greater efficiency in your expeditions.

By utilizing GOLD into enhancing your ship, you can improve its capabilities, reducing the distance required to reach buried treasures. With every upgrade, the ship becomes faster and more reliable, allowing your Captain to uncover rewards with greater ease and efficiency.

A mighty ship is the key to navigating treacherous waters and shortening the path to fortune. Strengthen your vessel, and watch your adventures become swifter, safer, and more rewarding!



### Treasure Locations&#x20;

Treasure locations are set in a 1.5km range around the player when he/she starts the hunt.

The distance to the player is influenced by the ship's speed: the faster a ship is, the higher the probability is to have treasures closer to the player.

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

### Types of Ships

There are 4 Type of Genesis Ships with The Seven Seas: Trails of Gold

<table><thead><tr><th>Type</th><th>Max Speed</th><th data-hidden>Capacity</th><th data-hidden>Armament</th><th data-hidden>Gen occurence</th></tr></thead><tbody><tr><td>Fleet Commanders Ship</td><td>200</td><td>4-6</td><td>10-60</td><td>10</td></tr><tr><td>Gold Ship</td><td>100</td><td>5-10</td><td>10-70</td><td>7</td></tr><tr><td>Silver Ship</td><td>50</td><td>10-15</td><td>15-100</td><td>3</td></tr><tr><td>Bronze Ship</td><td>1</td><td>5-20</td><td>20-100</td><td>2</td></tr></tbody></table>

Note: If your Fleet Command has a Fleet Commander's Ship as the head of the Fleet - a 2x Multiplier will occur to all Ships within his/her Fleet Resulting in The Following:

<table><thead><tr><th>Type</th><th>Enhanced Speed Value</th><th data-hidden>Capacity</th><th data-hidden>Armament</th><th data-hidden>Gen occurence</th></tr></thead><tbody><tr><td>Fleet Commanders Ship</td><td>200</td><td>4-6</td><td>10-60</td><td>10</td></tr><tr><td>Gold Ship</td><td>200</td><td>5-10</td><td>10-70</td><td>7</td></tr><tr><td>Silver Ship</td><td>100</td><td>10-15</td><td>15-100</td><td>3</td></tr><tr><td>Bronze Ship</td><td>2</td><td>5-20</td><td>20-100</td><td>2</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>

\
