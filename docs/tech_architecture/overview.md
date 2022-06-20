The game works with an hybrid on-chain / off-chain architecture.

Player assets (pirates, ships, items, PGLD) are stored on-chain, as well as rewards (treasures and ship wrecks) in order to make sure the player is in control all the time.

Game logic, however is run off-chain like hunts management geolocation.

## Smart contracts

- PGLDToken (ERC20): token contract
- Pirate (ERC1155): handles pirate NFTs and performs random minting
- Ship (ERC1155): handles ship NFTs and performs random minting
- Item (ERC1155): handles item NFTs and performs random minting
- Shop: responsible on handling mint sales for every kind of NFT
- Vault: locked rewards (content of treasures or ship wrecks), that can be unlocked only with a private key