# Hubs

From a legal perspective, a hub is an organization that uses the TreehouseOS protocol as the basis of its operations. Technically, hubs act as backend servers - they store information, perform certain actions (`minting`, `ledger`) and communicate with `users` or other `hubs`.

## Storing information
Hubs store databases on:
+ [Funding events](funding_events.md)
+ [Blocks](blocks.md)
+ [Ledger](ledger.md)
+ [Donations](donations.md)

## Actions

### Recording incoming messages

The protocol uses a single object type [Message](message.md) to record user-initiated changes to the databases.

### Minting

As described in [Mint](mint.md), the server runs a script to determine new THL balances on the `ledger`. The action is performed automatically when `funding events > application time` end.

### Running quadratic voting

The hub uses [voting](voting.md) script to determine/ reject funding for `blocks` submitted within the `funding event`. After running the script, the `ledger` is recalculated and THL balances are adjusted (outgoing transations)

## Communication with users

Hubs expose a websocket endpoint to which users can connect. Read [Message](message.md) to learn what information can be send. 

## Communication between hubs

+ Hubs can organize joint `funding events` (for example, hubs operating in close geo)

TBC. Must specify how hubs synchronize, what information to share, and how to avoid one-sided manipulation.