# security

### Device fingerprinting

Players can only use a single device (smartphone) at the same time. The active device can be updated, but only when the player is not hunting.

The active device is used to create proofs requested by the API to ensure the authenticity of provided information and their source.

### Geolocation anti-spoofing system

In order to prevent geolocation cheating, the anti-spoofing system performs several checks, such as the move speed, the cell network usage, coordinate authentication, and more...

### Private key storage in app

The wallet private key is securely stored on the smartphone using buit-in securited storage:

* On iOS, the private key is stored inside the [Keychain](https://support.apple.com/fr-fr/guide/security/secb0694df1a/web)
* On Android, the private key is stored inside the [Keystore system](https://developer.android.com/training/articles/keystore)
