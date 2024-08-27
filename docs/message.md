# Messages

`Message` is a single object type that establishes communication between hubs and users.

```
{
    "id": <32-bytes lowercase hex-encoded sha256 of the serialized message data>,
    "tpub": <32-bytes lowercase hex-encoded public key of the message sender>,
    "created_at": <unix timestamp>,
    "type": <integer>,
    "content": [
        ["<information name>", "<value 1>", "<value 2>"],
        ["<information name>", "<value 1>", "<value 2>"],
        ["<information name>", "<value 1>", "<value 2>"]
    ],
    "sig": <64-bytes lowercase hex of the signature of the sha256 hash of the serialized message data; the same as the "id">
}
```

Format based on the [Nostr NIP-01](https://github.com/nostr-protocol/nips/blob/master/01.md) concept.

## Type

* `0` - new funding event - creates a new `tevent` record
* `1` - new block - creates a new `tblock` record
* `2` - new outgoing transaction - creates a new record (vote) under a `tblock`
* `3` - new hero reaction - creates a new record (hero_reaction) under a `tblock`
* `4` - new donation - creates a new record under hub's [donation registry](donations.md)
* `5` - inviting a hero - creates a new record under a `tblock`
*` 6` - email-to-tpub - adding the related tpub to the database based on previously recorded email

When addressing in documentation, types are named `T-00` to avoid misunderstandings.

## Content

Additional information required by hubs to record a message in databases.

### T-00

```
{
    "type": 1,
    "content": [
        ["application_time", "<time_start unix timestamp>", "<time_end unix timestamp>"],
        ["voting_time", "<time_end unix timestamp>"], # voting_time_start = application_time_end
        ["work_time", "<time_end unix timestamp>"] # work_time_start = voting_time_end
    ]
}
```

The `id` of the message to be saved with the prefix `tevent`

### T-01

```
{
    "type": 1,
    "content": [
        ["tevent", "<tevent id>"],
        ["requested_funding", <integer>],
        ["threshold_funding", <integer>],
        ["group_size", <integer>],
        ["builders", "<builder 1 email>", "<builder 2 email>", "<...>"]
    ]
}
```

### T-02

```
{
    "type": 2,
    "content": [
        ["tblock", "<tblock id>"], # tblock recepient
        ["thl_amount", <integer>]
    ]
}
```

### T-03

```
{
    "type": 3,
    "content": [
        ["tblock", "<tblock id>"], # tblock recepient
        ["reaction", <integer 1 OR -2>] # 1 for like, -2 for dislike
    ]
}
```

### T-04

```
{
    "type": 4,
    "content": [
        ["donation_amount", <integer>],
        ["currency", "<currency code according to ISO 4217>"],
        ["invite_funder", "<funder 1 email>"]
    ]
}
```

### T-05

```
{
    "type": 5,
    "content": [
        ["tblock", "<tblock id>"],
        ["invite_hero", "<hero 1 email>"]
    ]
}
```

### T-06

```
{
    "type": 6,
    "content": [
        ["email", "<email address>"], # email previously saved using T-01, T-04, T-05
    ]
}
```

## Signatures

TBC. Resources for further work:
+ [NIP-01](https://github.com/nostr-protocol/nips/blob/master/01.md)
+ [Schnorr signatures](https://bips.xyz/340)

## Serialization

TBC.