# Treasure Sites

### **Treasures – Geolocated Rewards for Players**

Treasures are **geolocated rewards**, hidden across the world for players to discover. Each **treasure** is defined by:

* **📍 Location** – A precise **longitude (lon) and latitude (lat)** coordinate.
* **💰 GOLD Amount** – The **reward contained within the chest**, which is **pre-determined** using the **Captain’s Algorithm**.

#### **🧭 The Navigator’s Utility – Unlocking More Treasures**

When a hunt begins, **treasures are unlocked around the player's current location**. The **Navigator’s level** directly influences how many treasures appear during a hunt.

* **Higher-level Navigators** unlock **more treasure sites**, increasing opportunities for GOLD.
* **Lower-level Navigators** generate **fewer dig sites**, limiting potential rewards.
* **All chest values are pre-determined** based on the **Captain’s Algorithm**, ensuring a structured reward system.

A skilled **Navigator** expands the **scope of every expedition**, ensuring **greater treasure-hunting potential** with every voyage.

<table><thead><tr><th width="344">The Navigators Level</th><th>Expected treasures</th></tr></thead><tbody><tr><td>Common</td><td>2</td></tr><tr><td>Uncommon</td><td>4</td></tr><tr><td>Rare</td><td>6</td></tr><tr><td>Epic</td><td>8</td></tr><tr><td>Legendary</td><td>10</td></tr></tbody></table>

### **Treasure Locations**

Treasure locations are **dynamically placed within a 1.5km radius** around the player when they begin a hunt. The exact **distance to each treasure** is influenced by the **ship's speed**—the **faster the ship**, the **higher the probability** of treasures appearing **closer** to the player.

#### **⚓ How Ship Speed Affects Treasure Distance**

* **Faster ships** increase the chance of treasures spawning **nearer** to the player.
* **Slower ships** may result in treasures appearing **farther away**, requiring longer expeditions.
* Efficiently upgrading your ship improves **travel time** and **expedition success**.

Other examples (rounded to 2 decimals):

| Random ratio | Ship speed = 1 | Ship speed = 100 | Ship speed = 200 |
| ------------ | -------------- | ---------------- | ---------------- |
| 0.1          | 1.49 km        | 1.45 km          | 1.43 km          |
| 0.2          | 1.49 km        | 1.40 km          | 1.36 km          |
| 0.3          | 1.48 km        | 1.35 km          | 1.29 km          |
| 0.4          | 1.47 km        | 1.30 km          | 1.22 km          |
| 0.5          | 1.46 km        | 1.25 km          | 1.14 km          |
| 0.6          | 1.46 km        | 1.20 km          | 1.07 km          |
| 0.7          | 1.45 km        | 1.15 km          | 1.00 km          |
| 0.8          | 1.44 km        | 1.10 km          | 0.93 km          |
| 0.9          | 1.44 km        | 1.05 km          | 0.86 km          |
| 1            | 1.43 km        | 1.00 km          | 0.79 km          |

#### **📏 Distance Computation & Balanced Spawning**

To ensure an **engaging experience**, treasure placement follows a **balanced approach**:

* **Half of the treasures spawned** are positioned **closer** to the player’s **initial location** by **30%**.
* **Example Hunt with One Player:**
  * **Two treasures are spawned.**
  * **First treasure location** follows the standard **distance computation formula**:
    * **Example: 1.48km from the player**.
  * **Second treasure** is placed **30% closer** to the player:
    * **1.48km × 0.3 = 444m**, making it significantly easier to reach.

When a hunt begins, **treasures are placed within a 1.5km range** around the player. The **exact distance** of each treasure is influenced by the **speed of the ship**—the **faster the ship**, the **higher the probability of treasures appearing closer** to the player.



### **Skipping**

During a hunt, a player can **skip a treasure** if it is **not reachable** or if they **choose not to collect it**.

### **Treasure Value Calculation**

To ensure **fair rewards** for all players, a **maximum treasure value** is applied to every **treasure value computation**.

#### **🕰️ Daily Snapshot & Allocation**

At **00:00 UTC**, a **snapshot of Captain Experience** is taken, and the following calculation is processed:

1. **User’s Captain Experience / Total Captain Experience** = **% of Daily Treasure Pool Allocated to the User’s Captain**
2. **% of Daily Treasure Pool Allocated to the User’s Captain** is then divided by the **maximum number of chests available in a day**
3. **Final Treasure Value Calculation:**
   * **% of Daily Treasure Pool Allocated to the User Captain / 10 = Treasure Value per Treasure Site**

#### **⏳ Claiming Limits & Unclaimed Treasures**

* The **User’s Daily Treasure Site Value Allocation** is now set.
* A **player’s ability to collect treasure sites** is only limited by the **rarity of their Navigator**, which determines how many sites can be explored per day.
* **Any treasure site left unclaimed by 00:00 UTC will be marked as unclaimed and burned from the GOLD supply**.

