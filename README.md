# TreehouseOS

**OS stands for Open School**

The concept of a public charity ecosystem that helps fund educators and contributors working to shape the future-proof generation of explorers, freethinkers, and creators.

**OS stands for Operating System**

Anyone who has been in a *treehouse* knows that good construction starts with a good plan. Our goal is to build a self-organizing, protocol-driven ecosystem that can grow with a low operating budget and is not dependent on its founders.

**OS stands for Open Source**

We want to prove that technology can do a lot of good. That is why we want to make use of its biggest advantage - scalability. The project will be public, available to contributors everywhere.

## How it works

The project is still in discovery stage, but the idea is simple:

1. **Start your own hub server**
2. **Launch charity projects**
3. **Get local community on board**
4. **Synergize with other hubs to make a bigger impact**

# No-code definitions

## Hubs
`hubs` mirror the principles of edging technology to reach high scale. A single hub represents an independent legal organization operating under the TreehouseOS.

The first hub will be established by founders of TreehouseOS with a focus on funding educational initiatives in Poland. Here's [the hub's mission](hub01-mission.md).

Hopefully, in the future, new hubs run by independent charities will open around the world.

> [!NOTE]
> From a technical perspective, hubs act as backend servers - storing information and broadcasting it to other connected hubs.

## Blocks
`blocks` are the educational initiatives of contributors, e.g., workshops, classes, or other activities that fit into a hub's mission.

## Community
`promoters` are responsible for organizing blocks. They can be individuals or nonprofit organizations.

`builders` are instructors who work directly with participants.

`fundraisers` are individuals or nonprofit organizations that raise money. They usually work on behalf of a hub.

`funders` are individuals or organizations who donate money to support hub's initiatives.

`heroes` are blocks' participants.

## Funding events

Hub-defined `funding events` constitute a full funding cycle (apply-vote-work).

Each funding event consists of three parts:
1. application time - window for submitting new blocks
2. open voting time - the community votes on blocks
3. work time - organizing initiatives

> [!NOTE]
> Fundraising is an ongoing process that is carried out by hubs and fundraisers, so it's not directly integrated into a funding event.

## Voting process
To fulfill the protocol's intent, a networked solution is needed to efficiently manage resources and fund proposed blocks.

Therefore, TreehouseOS is based on a mechanism that invites community members to vote on where to allocate funds. That way, funding is controlled by promoters, builders, fundraisers, funders, and heroes.

### Quadratic voting (QV)

A mechanism designed by Vitalik Buterin ([source paper](https://arxiv.org/pdf/1809.06421)) in which the final distribution of funds is calculated by using the quadratic funding formula, where the number of voters matters more than the number of votes contributed.

In the context of TreehouseOS, QV provides a real voice for smaller but dedicated community members, especially promoters, builders, and heroes.

## Votes and the ledger
To enable fair community voice it was needed to introduce a concept distributing vote power proportionally to members' involvement.

Therefore we introduced three solutions:

### 1. Votes

`treehouse leaf` (abbr. THL) is a quasi-currency restricted to voting purposes only. THLs are *minted* by the algorithm and distributed among members.

The system is based on the concept of proof-of-work:
the more you contribute, the more votes (THL) you get, and therefore the greater your decision-making power.

### 2. Mint

`mint` is an algorithm calculating how many THL should be recorded for each community member. Minted THLs are recorded in the `ledger`.

### 3. Ledger

`ledger` contains THL account balances and "transactions" of each community member.

# Basic Flow
More detailed documentation at the links.

1. Individual or organization decides to use the TreehouseOS protocol
2. By starting a new [Hub](docs/hubs.md) server, [hub admin](docs/users.md#hub-admin) user is created
3. [Hub admin](docs/users.md#hub-admin) launches first [funding event](docs/funding_events.md) sending [T-00](docs/message.md#t-00) message to the server
4. [Promoters nad fundraisers](docs/users.md#roles) can submit new `blocks` and `donations`
5. During the [application time](docs/funding_events.md), `promoters` use [T-01](docs/message.md#t-01) message to submit new blocks and invite [builders](docs/users.md#roles) to the project
6. On the last day of the `application time`, the [mint](docs/mint.md) generates new `THL` (votes) based on its algorithm. New THLs are recorded as `incoming transactions` in the [ledger](docs/ledger.md)
7. During the [open voting time](docs/funding_events.md), users [vote](docs/voting.md) on the blocks they want to support. Each vote cast is registered as an `outgoing transaction`
8. On the last day of the `open voting time`, voting closes and the matched funding list is generated for the `hub admin`
9. Then, the [work time](docs/funding_events.md) officially starts
10. During the `work time`, promoters organize blocks and invite participants ([heroes](docs/users.md#heroes))

Additionaly to the above flow:
+ `Fundraisers` use [T-04](docs/message.md#t-04) message to submit information on new donations and invite [funders](docs/users.md#roles) to the hub
+ `Promoters` prompt heroes to share their opinions on prior blocks using [T-03](docs/message.md#t-03) message
+ `Hub admins` open new `funding events`

# High-level docs

* [Hubs](docs/hubs.md)
* [Users](docs/users.md)
* [Messages](docs/message.md)
* [Funding events](docs/funding_events.md)
* [Voting](docs/voting.md)
* [Mint](docs/mint.md)
* [Ledger](docs/ledger.md)
* [Donations](docs/donations.md)

# Contributors

+ **[Tom Ogrodzki](https://tomogrodzki.com)** – building next-gen commercial real estate with proptech, data, and AI. CEO @ [REDD Platform](https://www2.reddplatform.com)
+ this is where your name can be!
