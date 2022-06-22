The game works with an hybrid on-chain / off-chain architecture.

Player assets (pirates, ships, items, PGLD) are stored on-chain, as well as rewards (treasures and ship wrecks) in order to make sure the player stays in control all the time.

Game logic, however is run off-chain like hunts and crew management, geolocation checking, ...

```plantuml
skinparam monochrome true
skinparam ranksep 20
skinparam dpi 100
skinparam arrowThickness 0.7
skinparam packageTitleAlignment center
skinparam usecaseBorderThickness 0.4
skinparam defaultFontSize 12
skinparam rectangleBorderThickness 1

rectangle "Backend" {
  [Hunt]
  [Crew]
  [Geolocation]
}
rectangle "Blockchain" {
  [PGLD]
  [PRBT]
  [Pirates]
  [Ships]
  [Items]
  [Reward vaults]
  [Shop]
}
rectangle "<b>player</b>" as Player

Player --> Blockchain
Player --> Backend
Backend --> Blockchain

```

## Smart contracts

- PGLDToken (ERC20): value token contract
- PRBTToken (ERC20): in-game utility contract
- Pirate (ERC1155): handles pirate NFTs and performs random minting
- Ship (ERC1155): handles ship NFTs and performs random minting
- Item (ERC1155): handles item NFTs and performs random minting
- Shop: responsible on handling mint sales for every kind of NFT
- RewardVault: locked rewards (content of treasures or ship wrecks), that can be unlocked only with a private key