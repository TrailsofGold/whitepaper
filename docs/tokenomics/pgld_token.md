Pirate Gold (PGLD) is the value token.

It can be used to mint ships or items. And can be changed into crypto currency as well.

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
- $X$ is an arbitrary first day PGLD minted value (15 000)
- $Y$ is the max supply (21 000 000)

PGLD per day minted example :
- 1st day : $15 000$ PGLD
- 2nd day : $(21 000 000 - 15 000) * (15 000 / 21 000 000) = 14 989$ PGLD
- 3rd day : $(20 995 000 - 14 989) * (5 000 / 21 000 000) = 14 978$ PGLD

On the first 3000 days, this gives:

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "Stock prices of 5 Tech Companies over Time.",
  "data": {
    "values": [
      {"Day": 0, "Supply": 15000},
      {"Day": 100, "Supply": 1462146.226},
      {"Day": 200, "Supply": 2809495.827},
      {"Day": 300, "Supply": 4063930.874},
      {"Day": 400, "Supply": 5231858.848},
      {"Day": 500, "Supply": 6319245.36},
      {"Day": 600, "Supply": 7331644.63},
      {"Day": 700, "Supply": 8274227.851},
      {"Day": 800, "Supply": 9151809.607},
      {"Day": 900, "Supply": 9968872.462},
      {"Day": 1000, "Supply": 10729589.86},
      {"Day": 1100, "Supply": 11437847.44},
      {"Day": 1200, "Supply": 12097262.88},
      {"Day": 1300, "Supply": 12711204.38},
      {"Day": 1400, "Supply": 13282807.87},
      {"Day": 1500, "Supply": 13814993.03},
      {"Day": 1600, "Supply": 14310478.17},
      {"Day": 1700, "Supply": 14771794.17},
      {"Day": 1800, "Supply": 15201297.37},
      {"Day": 1900, "Supply": 15601181.6},
      {"Day": 2000, "Supply": 15973489.42},
      {"Day": 2100, "Supply": 16313429.82},
      {"Day": 2200, "Supply": 16642851.48},
      {"Day": 2300, "Supply": 16943324.73},
      {"Day": 2400, "Supply": 17223077.04},
      {"Day": 2500, "Supply": 17483537.36},
      {"Day": 2600, "Supply": 17726036.08},
      {"Day": 2700, "Supply": 17951811.85},
      {"Day": 2800, "Supply": 18162017.9},
      {"Day": 2900, "Supply": 18357727.94},
      {"Day": 3000, "Supply": 18539941.62}
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

## Earning

PGLD is earned by players when they find treasures or ship wrecks.

## Rewards

PGLD is used for rewards.

PGLD tokens are kept in the game a reward pool.

Total maximum daily rewards amount is composed of :
- PGLD daily minting :refer to the mint formula above.
- PGLD collected by ship and item sales: it depends on how much users buy items and ship on the app.
- Previous days undistributed PGLD supply.
- PGLD sold by users (see below).

## Sale

PGLD can be sold at anytime by players to the game for crypto currency.

The sale price is determined by ???

> TODO: usage of liqudity pool

