# Voting

## Sequence

1. On the last day of the `application time`, the [mint](docs/mint.md) generates new `THL` (votes) based on its algorithm. New THLs are recorded as `incoming transactions` in the [ledger](docs/ledger.md)
2. During the [open voting time](docs/funding_events.md), users `vote` on the blocks they want to support. Each vote cast is registered as an `outgoing transaction`
8. On the last day of the `open voting time`, voting closes and the matched funding list is generated for the `hub admin`

## Quadratic voting formula

### QV parameters

The following parameters are taken into the formula:

+ sum of `requested funding` for the given `tevent`

plus, for each `blockid`:

+ `requested funding` - the requested budget to run the `block`
+ `treshold funding` - the minimum acceptable budget to commit to the `block` completion
+ number of `voters` - how many `funders`, `promoters`,`builders` and `heroes` voted for a block
+ number of `votes` - how many votes ([THLs]) a given block received

It's important to note that voters have full autonomy over how many `votes` they commit to each `block`, so the number of voters and votes will likely vary.

### QV script

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