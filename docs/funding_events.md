# Funding events

Hubs record new `funding events` based on the [Message](message.md) received and signed by authorized [hub admin](users.md#hub-admin).

## Timeblocks

Each funing event consists of three parts:
1. application time - window for submitting new blocks
2. open voting time - the community votes on blocks
3. work time - organizing initiatives

Start/end dates are defined in the `content` of a `message`.

## Applying for funding

+ During the `application time`, [promoters](users.md#promoters) can submit their propositions of `blocks`
+ To submit a new `block`, the promoter sends a corresponding [message](message.md) to create a new `tblock` record in the hub's database
+ Blocks approved by `hub admin` are put to [vote](voting.md)