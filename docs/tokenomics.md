# Tokenomics

Pirate Gold (PGLD) is the game token.

It can be used to buy ships or items. And can be changed into crypto currency as well.

PGLD owned by the game is redistributed as follows:

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "PGLD game redistribution.",
  "data": {
    "values": [
      {"Usage": "Put on sale", "Pct": 0.2},
      {"Usage": "Used for rewards", "Pct": 0.5},
      {"Usage": "Kept for staking", "Pct": 0.3}
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

## Rewards

PGLD is used for rewards.

total maximum daily rewards amount is composed of :
- PGLD daily minting
- PGLD collected by ship and item sales

## Minting

New PGLD tokens are minted every day at 00:00 CET.

The daily minted amount is caped and determined by the exponential decay formula, in order to preserve the token value over time.

> TODO: explain mint formula here.

## Sale

PGLD collected from ships and items sales is put on sale on a DEX on a daily basis.

Every day at 00:00 CET: 20% of PGLD collected by the game are put on sale for 20% of the blockhain coins collected by the game (from pirate sales).


## Staking

>TBD
