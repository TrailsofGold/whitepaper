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
      {"Usage": "Used for rewards", "Pct": 0.99},
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
