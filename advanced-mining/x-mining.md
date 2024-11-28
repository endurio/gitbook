# X-Mining

If quasi-relaying a Bitcoin transaction to Ethereum is costlier than the reward, or the transaction is mined in some alt-chain with very little reward, miners can opt for x-mining to increase the reward share by decreasing the winning chance proportionally.

To x-mine a brand, the brand memo (in OP\_RET) is appended with one space character (ASCII 0x20), an `x`, and the decimal string of reward multiplier number `m`.

```
OP_RET "endur.io x6"
```

An x-mining transaction is valid only in a block with `KECCAK(BlockkHash) % m == 0` and the reward will be $$m \times Reward$$.
