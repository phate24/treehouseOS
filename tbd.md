# To be discussed
Open issues and challenges for further discussion

## Must-have

### Email invite - tpub/tsec linking

The challenge relates to `builders`, `funders`, and `heroes` who are invited by `promoters` and `fundraisers` by providing their e-mail addresses.

Example flow in the current arrangement:
1. `Promoter` sends a [T-02](docs/message.md#t-02) message in which he "invites" the `builder` (marks his `email` in the message)
2. The new `tblock` is saved in the database without specifying the builder's `tpub` (only his email)
2. The `hub` sends an automatic invitation to the `builder`
3. After the `builder` creates a `tpub/tsec`, he sends a [T-06](docs/message.md#t-06) message
4. The hub associates the received `tpub` with a record in the `tblock` database

## Nice-to-have

TBC.