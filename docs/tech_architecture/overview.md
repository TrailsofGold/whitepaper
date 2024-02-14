The game works with an hybrid on-chain / off-chain architecture.

Player assets (pirates, ships, items, PGLD, PRBT) are stored on-chain in order to make sure the player stays in control all the time.

Game logic, however is run off-chain like hunts and crew management, geolocation checking, rewards calculation...

```plantuml
skinparam monochrome true
skinparam ranksep 20
skinparam dpi 100
skinparam arrowThickness 0.7
skinparam packageTitleAlignment center
skinparam usecaseBorderThickness 0.4
skinparam defaultFontSize 12
skinparam rectangleBorderThickness 1

rectangle "Game Server" {
  [Hunt]
  [Crew]
  [Geolocation]
  [Rewards calculation]
}
rectangle "Store Purchase Server" {
  [In-App Payment]
}
rectangle "Blockchain" {
  [PGLD]
  [PRBT]
  [Pirates]
  [Ships]
  [Items]
  [Shop]
  [RewardPool]
}
rectangle "<b>Player</b>" as Player

Player --> Blockchain
Player --> "Game Server"
Player --> "Store Purchase Server"
"Game Server" --> Blockchain
"Store Purchase Server" --> Blockchain

```

## Game smart contracts

- PGLDToken (ERC20): value token contract
- PRBTToken (ERC20): in-game utility contract
- Pirate (ERC1155): handles pirate NFTs and performs random minting
- Ship (ERC1155): handles ship NFTs and performs random minting
- Item (ERC1155): handles item NFTs and performs random minting
- Shop: responsible of handling mint sales for NFTs bought with PRBT and/or PGLD
- In-App Payment: responsible of bridging in-app payment with pirate purchase (minting)
- RewardPool: handles game (play & earn) rewards unlocking and distribution