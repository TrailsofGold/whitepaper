# Game Flow

```blockdiag
blockdiag {
  default_shape = roundedbox
  

  "Start" -> "Hunt";
  "Start" -> "Enhance Your Crew";

  "Enhance Your Team" -> "Hunt"
  
  "Hunt" -> "Enhance Your Crew";
  "Hunt" -> "Hunt";

  "Start" [color = "#FEF58F"];
  "Enhance Your Crew" [color = "#E0ADFA"];
  "Hunt" [color = "greenyellow"];

 
}
```

| Stage             | Description                                                                                                                                                                                      |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Start             | Embark on an epic treasure-hunting journey right from your mobile device! Begin by tapping the **"Set Sail"** button to launch your adventure.                                                   |
| Enhance Your Crew | Use your GOLD to strengthen your team and prepare for even greater adventures:                                                                                                                   |
| Hunt              | Once you've arrived at the treasure’s location, it’s time to dig! Unearth the chest to reveal the secrets hidden within—valuable treasures, GOLD, or even rare items that will aid your journey. |
