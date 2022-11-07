## Geolocation anti-spoofing system

In order to prevent geolocation cheating, the anti-spoofing system checks:
- The move speed of the player between his/her starting point and treasures / wrecks, and in between teasures and wrecks.
- When checking for an actual location, the game system also relies on the smartphone health data, to be sure a move was detected.
- The use of a mobile cell network connection is mandatory to claim a treasure.

## Private key storage in app

The wallet private key is securely stored on the smartphone using buit-in securited storage:
- On iOS, the private key is stored inside the [Keychain](https://support.apple.com/fr-fr/guide/security/secb0694df1a/web)
- On Android, the private key is stored inside the [Keystore system](https://developer.android.com/training/articles/keystore)
