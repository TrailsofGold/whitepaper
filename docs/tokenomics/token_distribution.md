PGLD is minted on game launch to a Smart Contract and unlocked following a pre-determined schedule on a 5 years period.

Total PGLD supply is **21 000 000**.

## Allocation

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "PGLD token distribution.",
  "data": {
    "values": [
      {"Usage": "Play & Earn", "Pct": 0.35},
      {"Usage": "Ecosystem fund", "Pct": 0.25},
      {"Usage": "Team", "Pct": 0.15},
      {"Usage": "Private sale", "Pct": 0.10},
      {"Usage": "Public sale", "Pct": 0.05},
      {"Usage": "Liquidity provision", "Pct": 0.10}
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

| Allocation          	| Share 	| Amount    	| Unlock rule    	|
|---------------------	|-------	|-----------	|-----	|
| Play & Earn         	| 35%   	| 7 350 000 	| 7% unlocked on game start.<br/>Then degressive unlock after 30 days. 	|
| Ecosystem fund      	| 25%   	| 5 250 000 	| 30% unlocked on game start.<br/>Then linear unlock after 30 days. 	|
| Team                	| 15%   	| 3 150 000 	| 20% unlocked on game start.<br/>Then linear unlock after 300 days. 	|
| Private sale        	| 10%   	| 2 100 000 	| Linear unlock every 200 days. 	|
| Public sale         	| 5%    	| 1 050 000 	| 30% unlocked on game start.<br/>Then linear unlock after 30 days on 200 days. 	|
| Liquidity provision 	| 10%   	| 2 100 000 	| 10% unlocked on game start.<br/>Then linear unlock after 30 days. 	|

## Unlock schedule

Unlock updates occur every 30 days.

> TBD