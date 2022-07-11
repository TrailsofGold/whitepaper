```blockdiag
blockdiag {
  default_shape = roundedbox
  

  "Tavern" -> "NFT";
  "NFT" -> "Play";
  "Play" -> "Gold", "Rum", "NFT";
  "Gold" -> "Shop";
  "Rum" -> "Shop";
  "Shop" -> "NFT";
  

  "Tavern" [color = "#BCD3FB"];
  "Shop" [color = "#E0ADFA"];
  "Play" [color = "greenyellow"];

  "Gold" [shape = circle];
  "Rum" [shape = circle];
  "NFT" [shape = circle];

 
}
```

A player buys one or more pirates (NFTs) to the Tavern in order to start playing.

While playing he/she can get Gold (PGLD), Rum (PRBT) or NFTs (items and pirates when finding wrecks).

Gold and Rum can be spent into the Shop to buy NFTs (ships and items).

Money collected by the Tavern is sent to a Treasury contract.

PGLD and PRBT collected by the Shop are sent back to the game RewardPool contract.