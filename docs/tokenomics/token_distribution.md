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
| Play & Earn         	| 35%   	| 7 350 000 	| TBD 	|
| Ecosystem fund      	| 25%   	| 5 250 000 	| TBD 	|
| Team                	| 15%   	| 3 150 000 	| TBD 	|
| Private sale        	| 10%   	| 2 100 000 	| TBD 	|
| Public sale         	| 5%    	| 1 050 000 	| TBD 	|
| Liquidity provision 	| 10%   	| 2 100 000 	| TBD 	|

## Unlock schedule

> TBD