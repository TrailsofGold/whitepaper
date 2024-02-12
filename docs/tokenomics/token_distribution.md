PGLD minting is managed by the DAO and has a maximumn supply of **21 000 000**.

On game start, 50% of the maximum supply is sent to the game reward pool (Play & Earn) with a progressive unlock scheduled on 500 days.

The other is kept in control of the DAO and will be used to:
- reward contributors
- provide token liquidity
- fund ecosystem

To this day, there is no private or public sale planned.

Pre game launch token distribution is reserved to contributors.

?> See [Contributing](governance/contributing.md) for more details on who can contribute, and how contrubution rewards are calculed.


## Allocation

```vegalite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "PGLD token distribution.",
  "data": {
    "values": [
      {"Usage": "Play & Earn", "Pct": 0.5},
      {"Usage": "DAO Treasury", "Pct": 0.5}
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

| Allocation          	| Share 	| Amount    	| Unlock rule    	                                                                |
|---------------------	|-------	|-----------	|-------------------------------------------------------------------------------	|
| Play & Earn         	| 50%   	| 10 500 000 	| 5% unlocked on game start.<br/>Then game activity related onlock on 500 days. 	|
| Treasury DAO        	| 50%   	| 10 500 000 	| No time-lock, controlled by DAO members, through proposals.                     |


## Play & Earn unlock schedule

Play & Earn unlock starts on game launch with a initial amount of 525 000 PGLD on day 1 (5%). Then unlocked amount is updated every day for 500 days.

To avoid PGLD devaluation and preserve the game interest, the unlock schedule is not linear and depends on the number of rewards distributed everyday.

The formula to determine the amount of tokens unlocked on a given day is:

> $((t-u)/(n-d))*(r/r0)^2$

where:
- $d$ is the current day index (starts at 0, 1 is the second day of the schedule)
- $r0$ is the number of rewards distributed on $d-1$
- $r$ is the number of rewards distributed on $d$
- $t$ is the initial token amount to unlock (10 500 000)
- $u$ is the already unlocked token amount
- $n$ is the unlock schedule duration in days (500)

If $r0$ is $0$, the released amount is $0$.

It the result is negative, the released amount is $0$.

As an example, if on day 50, there was a reward count of 3000, and the reward count was 2200 on the previous days. And the already unlocked amount is 1 649 356.56, then unlocked amount for day 50 is:

$((10 500 000 - 1 672 273.02)/(500-49)*(3000/2200)^2) = 22 916.4631$ PGLD
