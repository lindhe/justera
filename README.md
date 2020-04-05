# Justera

I'm missing a good, free solution for document sharing and signing.
I'll try to build one from scratch, but we'll see if I have the time to complete it.

This is a very early version, and anything might change.


## Subsystems

I'm thinking it should be micro service based.
Here's a first draft of what subsystems might be needed.


### Document storage

Documents needs to be stored, _at least_ temporarily.
I'm guessing Elasticsearch sounds like a good fit.
That might also open up for additional functionality down the road.

I'm banking on Elasticsearch being able to store enough metadata that we can fit the signatures in there somehow.
Otherwise, there needs to be a secondary database for that.


### Signing engine

Makes sense to offload all singing logic to one part, I hope.
As long as it's presented nicely, all we need to sign should be a hash of the document and to validate that somehow.


### Bundler

I want to make it possible to save all pertinent information offline.
The bundler should make it easy to fetch a document including its signatures.

TODO:
* Find a good format for saving signatures


### Unbundler

Like the Bundler, but uplink.
Optional.


### Unhasher

Might make sense to translate hashes to something more human readable.
Should be easy enough to create a translation service for that.


### Web front-end

Make it easy to view available documents, see revisions, and sign stuff.
Preferably also comment to make suggestions, but that sounds hard and would be awesome for someone else to implement.

The web front-end generally sounds boring so I'll delay that as much as possible.


## API

Have started to outline an API definition here: https://app.swaggerhub.com/apis/lindhe/justera/

## Documentation

https://www.bankid.com/bankid-i-dina-tjanster/rp-info


## Misc

TODO:
* Double-check that BankID is compatible with GPL.
* Read about open alternatives to BankID.

