> TODO: update

> Check https://www.bnbchain.org/en/blog/sustainable-gamefi-to-play-or-to-earn/

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