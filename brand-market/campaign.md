# Campaign

A brand campaign is created in the Brand Market to offer ENDU token payment for mining a _user brand_.

A campaign is identified by the brand _memo_ and _owner_ (or _payer_) so the same _memo_ can be paid by multiple payers via multiple brand campaigns.

A campaign has:

* memo: the UTF-8 text to mine
* payer: the owner of the campaign
* fund: ENDU tokens amount locked by the owner to pay miners
* payRate: payment rate for each successful mining transaction
* expiration: expiration date

The _campaign_ is deactivated when either:

* the expiration is reached
* all the fund is spent

An expired campaign can be manually deactivated by its owner and all the remaining locked ENDU is refunded.

An unexpired campaign can only be upgraded to either:

* increase the _pay rate_
* extending the expiration
* add more fund
