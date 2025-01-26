# Token Distribution

### Allocation

```vegalite
```

| Allocation   | Share | Amount     | Unlock rule                                                                         |
| ------------ | ----- | ---------- | ----------------------------------------------------------------------------------- |
| Play & Earn  | 50%   | 10 500 000 | <p>5% unlocked on game start.<br>Then game activity related onlock on 500 days.</p> |
| Treasury DAO | 50%   | 10 500 000 | No time-lock, controlled by DAO members, through proposals.                         |

### Play & Earn unlock schedule

Play & Earn unlock starts on game launch with a initial amount of 525 000 PGLD on day 1 (5%). Then unlocked amount is updated every day for 500 days.

To avoid PGLD devaluation and preserve the game interest, the unlock schedule is not linear and depends on the number of rewards distributed everyday.

The formula to determine the amount of tokens unlocked on a given day is:

> $((t-u)/(n-d))\*(r/r0)^2$

where:

* $d$ is the current day index (starts at 0, 1 is the second day of the schedule)
* $r0$ is the number of rewards distributed on $d-1$
* $r$ is the number of rewards distributed on $d$
* $t$ is the initial token amount to unlock (10 500 000)
* $u$ is the already unlocked token amount
* $n$ is the unlock schedule duration in days (500)

If $r0$ is $0$, the released amount is $0$.

It the result is negative, the released amount is $0$.

As an example, if on day 50, there was a reward count of 3000, and the reward count was 2200 on the previous days. And the already unlocked amount is 1 649 356.56, then unlocked amount for day 50 is:

$((10 500 000 - 1 672 273.02)/(500-49)\*(3000/2200)^2) = 22 916.4631$ PGLD
