Pirate Gold (PGLD) is the game token.

It can be used to buy ships or items. And can be changed into crypto currency as well.

PGLD owned by the game is redistributed as follows:

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "PGLD game redistribution.",
  "data": {
    "values": [
      {"Usage": "Sold by the team and redistributed into rewards", "Pct": 0.01},
      {"Usage": "Used for rewards", "Pct": 0.99}
    ]
  },
  "encoding": {
    "theta": {"field": "Pct", "type": "quantitative", "stack": true},
    "color": {"field": "Usage", "type": "nominal", "legend": null}
  },
  "layer": [{
    "mark": {"type": "arc", "outerRadius": 80}
  }, {
    "mark": {"type": "text", "radius": 130},
    "encoding": {
      "text": {"field": "Usage", "type": "nominal"},
      "color": {"field": "Usage", "type": "nominal", "legend": null}
    }
  }, {
    "mark": {"type": "text", "radius": 130, "yOffset": 20},
    "encoding": {
      "text": {"field": "Pct", "type": "nominal",  "format": ".0%"}
    }
  }]
}
```

## Supply

The PGLD has a limited supply of 21 000 000 (21 millions tokens, like bitcoin).

## Minting

New PGLD tokens are minted every day at 00:00 CET.

The daily minted amount is caped and determined by a look alike bitcoin decay formula, in order to preserve the token value over time.

PGLD mint value per day formula is:

> $(x - y) * (X / Y)$

where:
- $x$ is the remaining supply mintable ($MAX SUPPLY - CIRCULATING SUPPLY$)
- $y$ is the last day minted PGLD 
- $X$ is an arbitrary first day PGLD minted value (20 000)
- $Y$ is the max supply (21 000 000)

PGLD per day minted example :
- 1st day : $20 000$ PGLD
- 2nd day : $(21 000 000 - 20 000) * (20 000 / 21 000 000) = 19 981$ PGLD
- 3rd day : $(20 980 000 - 19 981) * (20 000 / 21 000 000) = 19 962$ PGLD

On the first 4000 days, this gives:

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "Stock prices of 5 Tech Companies over Time.",
  "data": {
    "values": [
      {"Day": 0, "Supply": 20000},
      {"Day": 100, "Supply": 1926763.397},
      {"Day": 200, "Supply": 3660230.958},
      {"Day": 300, "Supply": 5236152.641},
      {"Day": 400, "Supply": 6668846.976},
      {"Day": 500, "Supply": 7971331.152},
      {"Day": 600, "Supply": 9155439.297},
      {"Day": 700, "Supply": 10231929.99},
      {"Day": 800, "Supply": 11210584.03},
      {"Day": 900, "Supply": 12100293.28},
      {"Day": 1000, "Supply": 12909141.47},
      {"Day": 1100, "Supply": 13644477.64},
      {"Day": 1200, "Supply": 14312982.92},
      {"Day": 1300, "Supply": 14920731.23},
      {"Day": 1400, "Supply": 15473244.44},
      {"Day": 1500, "Supply": 15975542.59},
      {"Day": 1600, "Supply": 16432189.47},
      {"Day": 1700, "Supply": 16847334.08},
      {"Day": 1800, "Supply": 17224748.35},
      {"Day": 1900, "Supply": 17567861.39},
      {"Day": 2000, "Supply": 17879790.67},
      {"Day": 2100, "Supply": 18163370.31},
      {"Day": 2200, "Supply": 18421176.88},
      {"Day": 2300, "Supply": 18655552.74},
      {"Day": 2400, "Supply": 18868627.39},
      {"Day": 2500, "Supply": 19062336.79},
      {"Day": 2600, "Supply": 19238440.95},
      {"Day": 2700, "Supply": 19398539.92},
      {"Day": 2800, "Supply": 19544088.32},
      {"Day": 2900, "Supply": 19676408.58},
      {"Day": 3000, "Supply": 19796702.94},
      {"Day": 3100, "Supply": 19906064.37},
      {"Day": 3200, "Supply": 20005486.51},
      {"Day": 3300, "Supply": 20095872.68},
      {"Day": 3400, "Supply": 20178044.12},
      {"Day": 3500, "Supply": 20252747.43},
      {"Day": 3600, "Supply": 20320661.34},
      {"Day": 3700, "Supply": 20382402.91},
      {"Day": 3800, "Supply": 20438533.11},
      {"Day": 3900, "Supply": 20489561.92},
      {"Day": 4000, "Supply": 20535952.99}
      
    ]
  },
  "mark": {
    "type": "line"
  },
  "encoding": {
    "x": {"type": "quantitative", "field": "Day"},
    "y": {"field": "Supply", "type": "quantitative"}
  }
} 
```

## Rewards

PGLD is used for rewards.

total maximum daily rewards amount is composed of :
- PGLD daily minting => 
   Refer to the mint formula above.
- PGLD collected by ship and item sales => 
   It depends on how much users buy items and ship on the app.
- Last days undistributed PGLD stock.
- PGLD sold by users.

## Sale

PGLD sold by users is bought with liquidity provided by Pirates sales and injected into rewards.

## Staking

>TBD
