# Rent

Anyone can join the referral network, but nodes must pay rent to have a chance of receiving commissions from descendant nodes' mining rewards. Rent is paid in stablecoins and used to buy back and burn END tokens through the END/USD AMM.

The higher the rent, the greater the chance a node has of receiving commissions. Additionally, the closer a node is to the miner in terms of cumulative rent, the higher its chance of earning commissions.

Rent can be decreased at any time and free of charge. However, increasing rent involves fees and time restrictions. There are two ways to increase rent: normal upgrades and instant promotions.

## **Rent Upgrade**

Conditions:

* After 1 week from the last rent upgrade or promotion.
* New rent is no higher than 2 times of old rent.

$$\text{UpgradeFee}=(\text{NewRent}−\text{OldRent})×302400$$

**Note**: 302400 is half a week in seconds.

## Instant Promotion

If the upgrade condition is not met, rent can be instantly escalated by paying 3 times the upgrade fee.

$$\text{EscalateFee}=3 \times\text{UpgradeFee}$$

The first rent setup for an uninitialized node is always a promotion.

## **Inactive Rent Decay**

An inactive/expired node will have its rent decayed overtime. This decayed rent will be used as the _current rent_ when the node is reactivated.

If a node with rent `r` is inactive for `T` week(s), its decaying rent will be $$\dfrac{r}{2^T}$$.

Technically, it might be implemented as $${\dfrac{r}{2^{\lfloor{T}\rfloor}}} (1-\dfrac{\{T\}}2)$$ to avoid floating point calculation.\
