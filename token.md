# The Token

ENDU is the crypto token of the Endurio Protocol.

* ENDU's initial supply is 0 (zero). No token is pre-mined.
* ENDU is freshly minted only by successful [mining](por/mining.md) `endur.io`
* In the [Brand Market](./):
  * ENDU is required to fund _user brand_ campaign
  * ENDU is paid by campaigns to the miners mining _user brand_
  * A portion of ENDU is burnt along the campagn fund.
* In the [Referral Network](refnet/):
  * ENDU is burnt to pay for rent.
  * ENDU is paid as a commission for each successful mining.

### Supply Cap

The supply of ENDU is always targeted to reach 21 million tokens, and the daily reward will halve approximately every 4 years.

<figure><img src=".gitbook/assets/image (16).png" alt=""><figcaption><p>Daily Token Emission</p></figcaption></figure>

In maximum capability, the total daily mining reward is always less than **7,490** ENDU. The total daily commission is capped at 30% of this amount, which equals **2,247** ENDU.

Thus, the total daily token emission is always less than **9,970** ENDU, and this value decays by half every 4 years. Mathematically, the maximum ENDU supply over time is as follows:

* 3,341,175 tokens in the first year,
* 6,150,758 tokens in the first 2 years,
* 10.5 million tokens in the first 4 years,
* \~21 million tokens over the lifetime of the universe.

In practice, the actual token supply will be much lower due to miner [inefficency](por/efficiency.md), missed [commission](refnet/commission.md), and conflicts or missed opportunities in [slot rewards](por/reward.md).

### Deflationary

Along with a capped supply, and to further strengthen the tokenomics, the ENDU token is burned and removed from circulation through the following mechanisms:

* Paying [node rent](refnet/rent.md) to receive commissions.
* Paying [brand campaign](brand-market/) funds.
