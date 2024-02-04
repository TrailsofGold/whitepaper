```blockdiag
blockdiag {
  default_shape = roundedbox
  

  "In-App Purchase" -> "NFT";
  "NFT" -> "Play";
  "Play" -> "Gold", "Rum", "NFT";
  "Gold" -> "Shop";
  "Rum" -> "Shop";
  "Shop" -> "NFT";
  

  "In-App Purchase" [color = "#BCD3FB"];
  "Shop" [color = "#E0ADFA"];
  "Play" [color = "greenyellow"];

  "Gold" [shape = circle];
  "Rum" [shape = circle];
  "NFT" [shape = circle];

 
}
```

A player buys one or more pirates (NFTs) from the app (in-app purchase) in order to start playing.

While playing he/she can get Gold (PGLD), Rum (PRBT) or NFTs (items and pirates when finding wrecks).

Gold and Rum can be spent into the Shop to buy NFTs (ships and items).

Money collected by the in-app purchases is sent to DAO Treasury.

PGLD collected by the Shop is also sent to DAO Treasury, PRBT is burnt.
