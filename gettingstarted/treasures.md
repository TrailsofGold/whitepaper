# Checkpoints

### **Geolocated Rewards for Players**

Checkpoints are **geolocated rewards**, hidden across the world for players to discover. Each **checkpoint** is defined by:

* **📍 Location** – A precise **longitude (lon) and latitude (lat)** coordinate.
* **💰 GOLD Amount** – The **reward contained at each checkpoint**, which is **pre-determined** using the **Captain’s Algorithm**.

**💧 WATER BOTTLE**

Your Endurance Role: Unlocks the path ahead. Function: Hydration equals opportunity. The rarity of your Water Bottle determines how many Checkpoints appear on your route during a session. Impact: Higher rarity bottles unlock more Checkpoints, giving you more opportunities to earn. Upgrade With: GOLD – Enhance your bottle to reveal more Checkpoints and higher quality rewards.

<table><thead><tr><th width="344">Water Bottle Rarity</th><th>Unlocked Checkpoints</th></tr></thead><tbody><tr><td>Common</td><td>2</td></tr><tr><td>Uncommon</td><td>4</td></tr><tr><td>Rare</td><td>6</td></tr><tr><td>Epic</td><td>8</td></tr><tr><td>Legendary</td><td>10</td></tr></tbody></table>

### **Checkpoint Locations**

**Checkpoint** locations are **dynamically placed within a 1.5km radius** around the player when they begin a hunt. The exact **distance to each Checkpoint** is influenced by the **Sneakers Rarity**—the **higher the rarity**, the **higher the probability** of checkpoints appearing **closer** to the player.

**👟 SNEAKERS**

Your Gear Role: Your engine on the pavement. Function: High-tier kicks are essential. Upgrading your Sneakers elevates your account status toward Steplete rank and dictates how quickly you reach objectives. Impact: Better Sneakers mean more efficient runs and quicker Checkpoint collection. Upgrade With: GOLD – Use rewards to improve efficiency and reduce the distance requirements between Checkpoints.

Other examples (rounded to 2 decimals):

| Random ratio | Sneaker speed = 1 | Sneaker speed = 100 | Sneaker speed = 200 |
| ------------ | ----------------- | ------------------- | ------------------- |
| 0.1          | 1.49 km           | 1.45 km             | 1.43 km             |
| 0.2          | 1.49 km           | 1.40 km             | 1.36 km             |
| 0.3          | 1.48 km           | 1.35 km             | 1.29 km             |
| 0.4          | 1.47 km           | 1.30 km             | 1.22 km             |
| 0.5          | 1.46 km           | 1.25 km             | 1.14 km             |
| 0.6          | 1.46 km           | 1.20 km             | 1.07 km             |
| 0.7          | 1.45 km           | 1.15 km             | 1.00 km             |
| 0.8          | 1.44 km           | 1.10 km             | 0.93 km             |
| 0.9          | 1.44 km           | 1.05 km             | 0.86 km             |
| 1            | 1.43 km           | 1.00 km             | 0.79 km             |

#### **📏 Distance Computation & Balanced Spawning**

To ensure an **engaging experience**, checkpoint placement follows a **balanced approach**:

* **Half of the Checkpoints spawned** are positioned **closer** to the player’s **initial location** by **30%**.
* **Example Activity with One Player:**
  * **Two Checkpoints are spawned.**
  * **First Checkpoint location** follows the standard **distance computation formula**:
    * **Example: 1.48km from the player**.
  * **Second Checkpoint** is placed **30% closer** to the player:
    * **1.48km × 0.3 = 444m**, making it significantly easier to reach.

### **Remote Claim**

During an Activity, a player can complete a checkpoint remotely if the have completed 1,000 Steps

### **Checkpoint Value Calculation**

To ensure **fair rewards** for all players, a **maximum gold value** is applied to every **gold value computation**.

#### **🕰️ Daily Snapshot & Allocation**

At **00:00 UTC**, a **snapshot of Steplete Level** is taken, and the following calculation is processed:

1. **User’s  Steplete Level** **/ Total Steplete Level** = **% of Daily Gold Pool Allocated to the User.**
2. **% of Daily Gold Pool Allocated to the User’s Steplete** is then divided by the **maximum number of Checkpoints available in a day**
3. **Final** Checkpoint **Value Calculation:**
   * **% of Daily Gold Pool Allocated to the User Steplete / 10 = Average Gold Value per Checkpoint**

#### **⏳ Claiming Limits & Unclaimed Checkpoints**

* The **User’s Daily Checkpoint Value Allocation** is now set.
* A **player’s ability to collect checkpoints** is only limited by the **rarity of their Water Bottle**, which determines how many Checkpoints can be completed each day.
* **Any checkpoint left incompmpleted by 00:00 UTC will be marked as unclaimed and burned from the supply**.

