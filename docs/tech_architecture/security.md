## Geolocation anti-spoofing system

In order to prevent geolocation cheating, the anti-spoofing system checks:
- The move speed of the player between his/her starting point and treasures / wrecks, and in between teasures and wrecks.
- When checking for an acutal location, the game system also relies on the smartphone health data, to be sure a move was detected.

## Reward vault opening

When the game system creates a reward vault for a treasure or a ship wreck, it generates a public / private keep pair.
- The public key in stored with the reward vault (in a smart contract)
- The private key is stored in the backend database

When the player location is validated by the backend, the private key is revealed to the player (to the app), allowing the opening of the vault.