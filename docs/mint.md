# Mint

The algorithm calculating how many `THL` should be recorded for each community member. Minted THLs are recorded in the [ledger](ledger.md) as `incoming transactions`.

> [!NOTE]
> `treehouse leaf` (abbr. THL) is a quasi-currency restricted to voting purposes only. THLs are minted by the algorithm and distributed among members. After a vote is cast (`outgoing transaction`), it's written off from the ledger.

## Proof-of-work algorithm

To put it simply, during [work time](funding_events.md), every user (`tpub`) works to earn votes (`THLs`) that they will be allowed to spend during `voting time`. These votes should be treated as a reward for one's effort, commitment, and work.

>[!NOTE]
> The system is based on the concept of **proof-of-work**: the more you contribute, the more votes (THL) you get, and therefore the greater your decision-making power.

## Incoming Transactions Day

On the last day of the `application time`, the `mint` generates new `THL` (votes). New THLs are recorded as `incoming transactions` in the [ledger](docs/ledger.md).

### Basic votes

`airdrop` - initial votes for every tpub to stimulate the voting process. Each tpub receives the same amount of votes.


```
airdrop_per_tpub = sum_of_blocks # in this funding round
```


### Votes for funders and fundraisers

`funder votes` - votes rewarding funders for their donations. For every 1000 currency units, funders receive 1 vote.


```
funder_votes = sum_of_donations/1000 // # in the last 360 days
```


`fundraiser votes` - votes rewarding fundraisers for their work to raise money. Funder votes mechanics apply, with the difference that fundraiser votes are calculated based on the sum of all organized donations.


```
fundraiser_votes = sum_of_all_donations/1000 # in the last 360 days
```


**Votes rewarding contributors block submissions**

`promoter votes` - votes reward promoters based on their expected impact-to-efficiency ratio. The lower the required funding and the larger the group size, the more votes are recorded.


```
promoter_votes_per_block = block_group_size / requested_funding * 1000  # 1000x multiplier to convert to integers
promoter_votes_sum += promoter_votes_per_block  # sum over all blocks
```


`builder votes` - each block is organized in collaboration with promoters and builders; moreover, this could be one person.


```
same as promoter_votes
```


### Votes rewarding prior blocks success

After participating in a block (only within the `time work`), `heroes` can either like (+1) or dislike (-2) the block. Each `hero reaction` is recorded under the `blockid`. Reactions are translated into `karma votes` and recorded on promoter `THL` balance.

`karma votes` - votes related to hero reactions on prior blocks.


```
karma_per_block = pow(hero_reaction_balance, 2)  # square function
karma_sum += karma_per_block  # sum over all blocks

karma_sum < 0:
    airdrop = 0  # set airdrop to 0
    promoter_votes = 0  # set promoter_votes to 0
```

### Votes rewarding heroes engaged in the community

`hero votes`
Votes increase exponentially with more past hero reactions. The multiplier is reset every 360 days.

```
hero_votes = pow(airdrop * 2, total_hero_reaction_sum)  # hero_votes increase exponentially with more past reactions

# total_hero_reaction_sum: the total number of reactions each hero has given in the last 360 days
```

## Halving and PoW Reset

+ **Halving** - uncast `THLs` are halved every 360 days since corresponding `incoming transactions`.
+ **PoW Reset** - priviligies based on prior work (raised money, multipliers) are reset every 360 days since corresponding `incoming transactions`.