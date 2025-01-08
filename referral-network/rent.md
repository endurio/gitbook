# Rent

Anyone can join the referral network, but nodes must pay rent to qualify for receiving commissions from the mining rewards of descendant nodes. Rent is paid in ENDU tokens, which are then burned, permanently removing them from circulation.

The higher the rent a node pays, the greater its chance of receiving commissions. Moreover, the closer a node is to the miner in terms of cumulative rent, the higher its likelihood of earning commissions.

Rent is paid for a minimum period of two weeks (RentEpoch). The next rent can only be paid after the previous rent has expired. While the next rent can be reduced without any restrictions or costs, increasing the rent incurs fees and is subject to rate limitations.

## **Rent Upgrade Fee**

$$Fee = \left[\dfrac{min(cR, nR-cR)}2 + max(0, nR-2cR)\right] \times RentEpoch$$

With:

* cR: current rent (with inactivity reducing)
* nR: new desired rent
* RentEpoch: 2 weeks

## **Inactive Rent Reduce**

An inactive or expired node will have its rent reduced linearly over the rent epoch. This reduced rent will serve as the current rent (cR) when the node is reactivated.

$$cR = lastRent \times (1 - \dfrac{now - lastExpiry}{RentEpoch})$$
