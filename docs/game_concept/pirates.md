<p align="center">
  <img width="128" height="128" src="./img/pirate1.png">
  <img width="128" height="128" src="./img/pirate2.png">
  <img width="128" height="128" src="./img/pirate3.png">
  <img width="128" height="128" src="./img/pirate4.png">
</p>

## Seasons

Pirates NFTs are gathered into collections (Smart Contracts) named "seasons".

Each season provides a set of pirates, and each pirate has a variable mint occurence according to his skills (the best the skills are, the rarest the pirate is).

## Rarity level

Each season contains pirate of different rarity levels. The rarest a pirate is, the best his skills are.

| Level     | Sum of skill points | Mint occurence |
|-----------|---------------------|----------------|
| Common    | 100                 | 60             |
| Rare      | 150                 | 35             |
| Epic      | 250                 | 30             |
| Legendary | 350                 | 25             |

For example, if a season has 4 common pirates, 3 rare pirates, 2 epic pirates and 1 legendary pirate, the sum of occurences are:

$4 * 60 + 3 * 35 + 2 * 30 + 25 = 430$

Meaning that a player has :
- 25 chances out of 430 to get a lengendary pirate
- 60 chances out of 430 to get an epic pirate
- 105 chances out of 430 to get a rare pirate
- 240 chances out of 430 to get a common pirate

## Attributes and skills

<p align="center">
  <img src="./img/pirate_skills.png">
<p>

Pirates are defined by a set of physical attributes and a set of skills.

Physical attributes do not affect the game mechanics, but skills do.

Skills are :
- Navigation
- Combat
- Strategy
- Mercy

They range from 0 (minimum) to 100 (maximum) and have an impact on different actions during a hunt.
