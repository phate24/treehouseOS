# TreehouseOS
Open School. Open Source. Operating System

Homo sapiens is shaped by two key relationships: one with nature and the other with our own minds. We're the only species that knows it knows. As it turns out, this privilege is not forever, and what's more, we take it away from ourselves. Commercial tech — smartphones, social media, news, games — is taking up more and more of our mental space, not only pulling us away from nature but weakening our ability (and need) to think.

As adults, we're privileged. We remember a time before or just as the internet took off. We've been to the 'treehouse'.

But our children don't have that privilege. The web is their world. Social media and junk information are shaping the way they see things, and it's not a pretty picture. Recent studies show that depression rates among children and teens have nearly doubled in recent years, with teen girls three times more likely to experience depression than boys. Between 2016 and 2022 alone, the rate of antidepressant use among children and adolescents in the U.S. increased by more than 65%.

Today's young generations are living in civilized cages when what they need is a **treehouse**.

We don't deny the world we live in. Technology is here, and it can be a beautiful thing.

Our mission is to build a strong generation that revolves around three `personas`:

+ `explorer` - fostering curiosity about the world and respect for nature
+ `freethinker` - embracing first-principles thinking, critical analysis, and the courage to question what doesn't fit
+ `creator` - understanding technology, reasoning, and programming

## Principles

**OS stands for Open School**

The concept of a public charity ecosystem that helps fund educators and contributors working to shape the future-proof generation of `explorers`, `freethinkers`, and `creators`.

**OS stands for Operating System**

Anyone who has been in a treehouse knows that good construction starts with a good plan. Our goal is to build a self-organizing, protocol-driven ecosystem that can grow with a low operating budget and is not dependent on the founders.

Created today based on a set of rules, TreehouseOS will eventually become software - an operating system.

**OS stands for Open Source**

We want to prove that technology can do a lot of good. That is why we want to make use of its biggest advantage - scalability. The project will be public, available to contributors everywhere.

# Concept

TreehouseOS is based on:

+ **Hubs** - independent organizations operating under the protocol
+ **Community governance** - mechanism for hub contributors and participants to vote on the allocation of funds
+ **Work-and-vote cycle** - 5 months of work (organizing activities, raising money, submitting new projects) followed by 1 month of community voting on projects for the next 6-month cycle.


## Hubs

The concept of `hubs` mirrors the principles of edging technology to reach high scale. A single `hub` represents an independent legal organization operating under the TreehouseOS protocol. The first `hub` will be established by Treehouse's founders with a focus on providing funding to contributors from Poland. Hopefully, in the future, new hubs run by independent charities will open around the world.

## Community

TreehouseOS consists of `blocks`, `contributors`, `blueprint`, `backyard`, `funders`, and ultimately `heroes`.

+ `Blocks` are the educational initiatives of `contributors`, e.g., workshops, classes, or other activities that fit into the `blueprint`.
+ `Contributors` include `promoters` (initiative coordinators), `builders` (instructors), `hosts` (owners of the `backyards`), and `fundraisers`.
+ `Blueprint` is an agreed matrix that defines the educational framework of the TreehouseOS project. Proposed dimensions mandatory to be defined for each `block`: main `persona` developed, target `age group`.
+ `Backyard` is the venue where the block will be organized.
+ `Funders` are individuals and companies who donate money to support the initiatives.
+ `Heroes` are the young participants of the `blocks`.

## Governance and voting

To fulfill the protocol's intent, a networked solution is needed to efficiently manage resources and fund proposed `blocks`.

Therefore, TreehouseOS is based on a mechanism that invites community members to vote on where to allocate funds. That way, funding is controlled by `funders`, `contributors`, and `heroes`.

`Open voting` is based on three principles:
+ any individual entering the ecosystem gets a unique `treehouse id`. The user identification system is based on public/private key cryptography. The public key is presented as a string with the prefix `treeid`, and the private key with the prefix `treesec`.
+ each `treeid` can support `blocks` with their `votes` stored in their `treeid wallet`.
+ `treehouse ledger` is a public database of `treeid wallet` balances and `vote transactions` (earned and spent `votes`).

The detailed rules of `open voting` are described in "Quadratic voting" below, along with details on the `treehouse ledger`.

## Work-and-vote rhythm

Funding timeblocks:
+ `work time` - a period in which `promoters` apply for funding their `blocks`, and `fundraisers` work on raising donations from `funders`. The phase is finished with a `veto review` during which the `board of directors` can use `veto power` and not admit projects that do not meet the `blueprint` criteria or if fraud is suspected.
+ `open voting time`- a period during which `funders`, `contributors`, and `heroes` vote for `blocks`. The phase is finished with the announcement of granted `blocks`.

A bi-yearly `founding round` cycle is proposed:
+ `work time` - 5 months
+ `voting time` - 1 month

## Applying for funding

Any individual, company, or charity organization can submit their propositions of `blocks`.

The minimum scope of required information covers:
+ `block name`
+ block description
+ target `age group`
+ main `persona` supported
+ `group size` - number of participants (`heroes`); if the block covers multiple events, the group size should reflect the sum of participants (to assess the block's scale of impact)
+ `requested funding` - budget of the `block`
+ `threshold funding` - the minimum acceptable budget to commit to the `block` completion (assuming the remaining budget can be covered from different sources, except from the participants)
+ expected date for `block completion`
+ involved `builders` and `hosts`
+ prior experience and contributions

By submitting the application of a `block`, one automatically becomes a `promoter`.
Every `block` receives a unique identification presented as a string with the prefix `blockid`.

## Raising money

Any individual, company, or charity organization can act as a `fundraiser` - a proxy between TreehouseOS and `funders`.

The legal rules regarding donation transfers are to be proposed.

# Mechanics

The Protocol is based on three technical filars. The first two are related to the governance and voting model; the third is related to considerations about decentralized aspects of the protocol.

**Treehouse ledger**

The system has two roles:
+ voting system recording vote distribution across `blocks`
+ "vote mint" system that generates new `votes` that can be used by contributors during the `voting time`. The system is based on the proof-of-work concept (the more you contribute, the more votes you get).

**Quadratic voting**

A mechanism designed by Vitalik Buterin ([source paper](https://arxiv.org/pdf/1809.06421)) in which the final distribution of funds is calculated by using the quadratic funding formula, where the number of contributions matters more than the number of votes contributed.

In the context of TreehouseOS, QV provides a real voice for smaller but dedicated `contributors`.

It's important to note that `votes` function as the equivalent of ecosystem currency - voting participants have full autonomy over how many votes they commit to each `block`.

**Decentralized protocol**

We want to create an open and fully scalable ecosystem with hundreds of `hubs` around the world. At the same time, we don't want to create a centralized enterprise software with huge overhead and operating budgets.

To reconcile the two, we are considering building TreehouseOS as a simple server/client protocol (like [Nostr](https://nostr.com)), where each `hub` is a server with the ability to connect to other hubs.

This approach opens the way for each `hub` to develop freely and independently, while retaining the ability to join forces with, for example, hubs operating in a similar geography or niche.

## Treehouse ledger

The `treehouse ledger` records `vote balances` for each `treeid wallet`, along with earned and spent `vote transactions`. The database is used for `open voting` in accordance with quadratic voting rules.

The first `treehouse ledger` will be built during the initial `work time`, during which `contributors` and `fundraisers` work on their submissions and raising money.

### Spending votes

Each user can use their `treeid wallet` balance to vote on the `blocks` they like. When voted, the `vote balance` of the wallet will be decreased by the number of spent votes, and the `vote transaction` will be recorded in the `treehouse ledger`.

### Earning votes

To put it simply, during `work time`, every `treeid` works to earn `votes` that they will be allowed to spend during `voting time`. These votes should be treated as a reward for one's effort, commitment, and work.

After the `veto review`, when the `blocks` are accepted for `open voting`, the whole `treehouse ledger` is to be recalculated and incoming (earned) `vote transactions` are to be recorded in `treeid wallets`.


**Basic votes**

`airdrop` - initial votes for every treeid to stimulate the voting process. Each treeid receives the same amount of votes.


```
airdrop = sum_of_blocks # in this funding round
```


**Votes for funders and fundraisers**

`funder votes` - votes rewarding funders for their donations. For every 1000 currency units, funders receive 1 vote.


```
funder_votes = sum_of_donations/1000 // # in the current work time
```


`fundraiser votes` - votes rewarding fundraisers for their work to raise money. Funder votes mechanics apply, with the difference that fundraiser votes are calculated based on the sum of organized donations.


```
fundraiser_votes = sum_of_all_donations/1000 # in the current work time
```


**Votes rewarding contributors block submissions**

`promoter votes` - votes reward promoters based on their expected impact-to-efficiency ratio. The lower the required funding and the larger the group size, the more votes are recorded.


```
promoter_votes_per_block = block_group_size / requested_funding * 1000  # 1000x multiplier to convert to integers
promoter_votes_sum += promoter_votes_per_block  # sum over all blocks
```


`builder votes & host votes` - each block is organized in collaboration with promoters, builders, and hosts; moreover, this could be one person.


```
same as promoter_votes
```


**Votes rewarding prior blocks success**

After participating in a block (only within the `time work`), `heroes` can either like (+1) or dislike (-2) the block. Each `hero reaction` is recorded under the `blockid`. Reactions are translated into `karma votes` and distributed among block's contributors (including promoters, builders, and hosts).

`promoter karma votes` - votes related to hero reactions on prior blocks.


```
promoter_karma_per_block = pow(hero_reaction_balance, 2) / 2  # square function, and reduced by half (rest for builders and hosts)
promoter_karma_sum += promoter_karma_per_block  # sum over all blocks

if promoter_karma_sum < 0:
    airdrop = 0  # set airdrop to 0
    promoter_votes = 0  # set promoter_votes to 0
```


`builder karma votes` - same as above, except:


```
builder_karma_per_block = pow(hero_reaction_balance, 2) / 3 # reduced by 1/3 (rest for hosts)
(...)
```


`host karma votes` - same as above, except:


```
host_karma_per_block = pow(hero_reaction_balance, 2) / 6 # reduced by 1/6
(...)
```


**Votes rewarding heroes engaged in the community**

`hero votes`
Votes increase exponentially with more past hero reactions. The multiplier is reset every funding cycle.

```
hero_votes = pow(airdrop * 2, total_hero_reaction_sum)  # hero_votes increases exponentially with more past reactions

# total_hero_reaction_sum: the total number of reactions each hero has given in the ending funding cycle
```

## Quadratic voting

### Sequence

1. On the last day of `Work time` blocks submissions get closed. This date is considered as `Day 0`.
2. `Day 1` is the start of a 14-day `veto review` period.
3. On `Day 14`, a `hub` announces the final list of `blocks` to be voted on.
4. Approval of blocks `Day 14` triggers an algorithm to recalculate the `treehouse ledger` and distribute `votes` to `treeid wallets`.
5. On `Day 15`, the 15-day period of `open voting time` begins.
6. On Day 30, a `hub` announces the list of granted `blocks` with the amount of funding.

### QV formula

#### Parameters

The following parameters are taken into the formula:

+ sum of `requested funding`

plus, for each `blockid`:

+ `treshold funding` - the minimum acceptable budget to commit to the `block` completion
+ number of voters - how many `funders`, `contributors`, and `heroes` voted for a block
+ number of `votes` - how many votes a given block received

It's important to note that voters have full autonomy over how many `votes` they commit to each `block`, so the number of voters and votes will likely vary.

#### Script

A simple script to determine the funding for one block:

```
import math

# Replace the placeholder values with actual data for each block
voters_block = <NUMBER_OF_VOTERS_FOR_BLOCK>
votes_block = <NUMBER_OF_VOTES_FOR_BLOCK>
treshold_funding_block = <THRESHOLD_FUNDING_FOR_BLOCK>
requested_funding_block = <REQUESTED_FUNDING_FOR_BLOCK>

# Total requested funding for all blocks in the open voting time
total_requested_funding = <TOTAL_REQUESTED_FUNDING_ALL_BLOCKS>

# Step 1: Sum of square roots
sum_of_square_roots_block = voters_block * math.sqrt(votes_block / voters_block)

# Step 2: Quadratic sum for the block
quadratic_sum_block = sum_of_square_roots_block ** 2

# Total quadratic sum for all blocks (this should be pre-calculated)
total_quadratic_sum = <TOTAL_QUADRATIC_SUM_ALL_BLOCKS>

# Step 4: Matched funding for the block
matched_funding_block = math.ceil((quadratic_sum_block / total_quadratic_sum) * total_requested_funding)

# Step 5: Final withdrawal based on matched funding and thresholds
if matched_funding_block > requested_funding_block:
    final_withdrawal_block = requested_funding_block
elif matched_funding_block > treshold_funding_block:
    final_withdrawal_block = matched_funding_block
else:
    final_withdrawal_block = 0

# Output the results for this block
print(f"Matched funding (block): {matched_funding_block}")
print(f"Final withdrawal (block): {final_withdrawal_block}")

```

## Decentralized protocol

TBC

## Further considerations

+ `Blocks` must be free of charge for `heroes`
+ `Block completion` definition + rules for the release of funding

## Contributors

+ **[Tom Ogrodzki](https://tomogrodzki.com)** – building next-gen commercial real estate with proptech, data, and AI. CEO @ [REDD Platform](https://www2.reddplatform.com)
+ this is where your name can be!
