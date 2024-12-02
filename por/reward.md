# Reward

## Base Reward

The total reward paid for all mining transactions in a Bitcoin block is calculated based on the block's Target and PayRate of the mining _brand_.

$$BaseReward = PayRate \times {BaseTarget \over Target}$$

The PayRate of the system brand [_endur.io_](http://endur.io/) is 1.0.\
The PayRate of _user brand_ is set by the campaign owner in the Brand Market.

The BaseTarget is an immutable system value initialized at the protocol's launch to match the current Bitcoin mining Target at that time. (i.e. $$BaseTarget \over Target$$ is set to 1.0 initially, and its increases or decreases follow the Bitcoin network difficulty).

## Boosted Blocks

Day $$n$$ (starting with block `144×n`) contains at most 12 boosted blocks, where the $$i^{th}$$ boosted block is calculated using the following formula to ensure a consistent mining schedule every day for a week:

```
144×n + KECCAK(n/7 | i) % 144
```

Boosted blocks with significantly higher rewards are designed to engage human miners, making miner bots less advantageous during the initial phase of the protocol. The mining reward for the i-th boosted block is calculated as:

$$2^{6-i} \times BaseReward$$

With $$2^{6-i}$$ is the _reward coefficient_ of the block.

For example, if the **BaseReward** is 1 END, the rewards for boosted blocks in a day will include:

* a 64x block with 64 END,
* a 32x block with 32 END,
* a 16x block with 16 END,
* a 8x block with 8 END,
* a 4x block with 4 END,
* and so on.

**Note:** Boosted blocks of different orders can collide, meaning some of the daily boosted rewards may be lost.

## Non-Boosted Blocks

All blocks other than the 12 boosted blocks are considered **non-boosted blocks** and have a _reward coefficient_ of $$2^{-12}$$. Hence, their mining rewards are calculated as:

$$2^{-12} \times BaseReward$$

## Development **Vault**

For the first reward claimed of a target block, there's a 1/32 chance that an additional subsidy of the same amount goes to the **Development Vault** (\~3% mining reward).

The **Development Vault** reward condition is cryptographically randomized as follow:

`KECCAK(KECCAK(memo) | BlockHash) % 32 = 0`
