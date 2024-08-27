# Donations

+ Any individual, company, or charity organization can act as a [fundraiser](users.md#fundraisers) - a proxy between `hubs` and [funders](users.md#funders).
+ The TreehouseOS protocol doesn't cover legal rules regarding donation transfers.

## Database structure

```
+ id: <t-04 id>
+ date: <timestamp>
+ created_by: <tpub> # pubkey
+ funder_email: <email address>
+ funder_id: <funder tpub> # requires active tpub
+ amount: <integer>
+ currency: <currency code according to ISO 4217>
```