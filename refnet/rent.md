# Rent

Anyone can join the referral network, but nodes must pay rent to qualify for receiving commissions from the mining rewards of descendant nodes. Rent is paid in ENDU tokens, which are then burned, permanently removing them from circulation.

The higher the rent a node pays, the greater its chance of receiving commissions. Moreover, the closer a node is to the miner in terms of cumulative rent, the higher its likelihood of earning commissions.

Rent is paid for a minimum period of two weeks (RentEpoch). While the next rent can be reduced without any restrictions or costs, increasing the rent incurs fees and is subject to rate limitations.

## **Rent Upgrade Fee**

There's a limit that rent can be upgraded with cheaper fee:

$$L = cR \times 2^\dfrac{-|expiry - now|}{RentEpoch}$$

So the rent upgrade fee is:

$$Fee = \left[\dfrac{min(nR, L)-cR}2 + max(0,nR-L)\right] \times RentEpoch$$

With:

* nR: new desired rent
* cR: last rent set by user
* expiry: the last rent expiry
* RentEpoch: 2 weeks
