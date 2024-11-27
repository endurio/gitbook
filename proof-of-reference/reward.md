# Reward

The total reward paid for all mining transactions in a Bitcoin block is calculated based on the block's Target and PayRate of the mining _brand_.

$$BaseReward = PayRate \times {BaseTarget \over Target}$$

The PayRate of the system brand [_endur.io_](http://endur.io/) is 1.0.\
The PayRate of _user brand_ is set by the campaign owner in the Brand Market.

The BaseTarget is an immutable system value initialized at the protocol's launch to match the current Bitcoin mining Target at that time. (i.e. $$BaseTarget \over Target$$ is set to 1.0 initially, and its increases or decreases follow the Bitcoin network difficulty).
