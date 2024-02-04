```blockdiag
blockdiag {
  default_shape = roundedbox
  

  "Start" -> "Hunt";
  "Start" -> "Buy";
  "Start" -> "Crew setup";

  "Buy" -> "Crew setup";

  "Crew setup" -> "Hunt"
  
  "Hunt" -> "Buy";
  "Hunt" -> "Crew setup";
  "Hunt" -> "Hunt";

  "Start" [color = "#FEF58F"];
  "Buy" [color = "#BCD3FB"];
  "Crew setup" [color = "#E0ADFA"];
  "Hunt" [color = "greenyellow"];

 
}
```

| Stage      | Description                                                                                                                                                      |
|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Start      | The player can start playing with or without a pirate. Howerver, in case he/she plays without at least one pirate, he/she will not get any reward from the game. |
| Buy        | The player can buy more pirates, ships or items to increase his/her rewards and to ease his/her hunt.                                                            |
| Crew setup | A player cannot start a treasure hunt until he/she has setup a crew (crew members, ship, items).                                                                 |
| Hunt       | Once a player has a crew he/she can start a hunt to get rewards.                                                                                                 |

?> for more information on crew see [Crew](game_concept/crew.md)

?> for more information on hunts see [Hunts](game_concept/hunts.md)
