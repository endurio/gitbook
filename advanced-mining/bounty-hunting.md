# Bounty Hunting

Bounty hunting is to mine a brand and sending some random recent transactors a _useful amount of coin_.

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>Bounty Hunting Transaction</p></figcaption></figure>

Bounty outputs are all outputs after the first OP\_RET except the last one (reserved for coin change). A transaction can have up to 8 bounty outputs, but only one of the bounty output is randomly sampled for verification.

The index of sampling bounty output in the bounty outputs array is $$BlockHash % N$$$$BlockHash % N$$`BlockHash % N` where `N`$$N$$ is the number of the bounty outputs.

## Bounty Amount

In Bitcoin, a dust output will be ignored by wallets and recipients because it's not beneficial to spend an amount too small. In bounty hunting transaction, miner makes them an offer they can't refuse.

A useful amount is an amount large enough to pay the fee of the transaction to spend that output. The transaction fee is calculated by the mining transaction itself.

$$MinTxSize = 10+FirstInputSize+BountyOutputSize$$

$$UsefulAmount = \dfrac{MinTxSize}{TxSize} \times TxFee$$

All bounty outputs value must be no less than **UsefulAmount** regardless of which is sampled to be verified.

## Bounty Recipient

Bounty recipient must be the recipient address of the last output (usually the coin change address) of a transaction in a recent block and

A recent block is a block with a timestamp no earlier than 1 hour from the mining block. The reward is calculated by the lower difficulty of the recent block and the mining block.

To make the bounty recipients different for each miner, the recent transaction is eligible for bounty output of a mining transaction must also have this condition fulfilled:

`KECCAK256(FirstOutpointID + BountyTxID) % 32 = 0`

* FirstOutputID is the first input outpoint ID (LE) of the mining transaction
* BountyTxID is the recent transaction ID (LE)

## Bounty Reward

$$BountySlotShare=2n\times SlotShare \times \dfrac{Target}{max(Target, BountyTarget)}$$

With _n_ is the number of bounty outputs and _BountyTarget_ is the block target of the sampled bounty recipient transaction.
