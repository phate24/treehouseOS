# Ledger

Ledger is a database which records THL balances and transactions for each `tpub`.

Ledger modification events:
+ Incoming transaction - the [mint](mint.md) generates new THLs based on its algorithm
+ outgoing transaction - user casts vote (THLs) for block during [voting](voting.md)

## Database structure

```
+ transaction id: `id`
+ date: `timestamp`
+ from: `tpub` (if outgoing transaction) OR `mint` (if incoming transaction)
+ to: `tblock` (if outgoing transaction) OR `tpub` (if incoming transaction)
+ amount: `THL`
```

TBC - tpub wallet balance.
