# Users

+ To communicate with a hub user generates a keypair based on public/private key cryprography. 
+ The public key is presented as a string with the prefix `tpub`, and the private key with the prefix `tsec`
+ Users communicate with hubs using [Messages](message.md)


## Roles

All users are allowed to vote during funding events based on the [voting rules](voting.md).

### Promoters
+ Individuals submitting new blocks during `application time` ([Funding events](funding_events.md)). Responsible for organizing blocks
+ Individuals sending `T-02` message (creating new `tblock`) are recognized as promoters
+ Allowed to modify their `tblocks`
+ Permission to invite `builders` and `heroes`

### Builders
+ Individuals working directly with participants during `blocks`
+ Generating `tpub/tsec` keypairs based on `promoter` invitation

### Fundraisers
+ Individuals or nonprofit organizations raising money
+ Individuals sending `T-04` message (new donation) are recognized as fundraisers
+ Further rules TBC

### Funders
+ Entities donating money for a hub
+ Generating `tpub/tsec` keypairs based on `hub admin` or `fundraiser` invitation

### Heroes
+ Block participants
+ Generating `tpub/tsec` keypairs based on `promoter` invitation

### Hub admin
+ Individuals or organizations that own a hub and its supporting infrastructure (including the server)
+ Authorized to create a new `funding event` by sending a `T-00` message (`tevent`)
+ Authorized to establish [communication between hubs](hubs.md#communication-between-hubs) for joint funding events