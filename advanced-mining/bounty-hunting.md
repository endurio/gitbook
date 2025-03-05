# Bounty Hunting

Bounty hunting is to mine a brand and sending some random recent transactors a _useful amount of coin_.

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Bounty Hunting Transaction</p></figcaption></figure>

Bounty outputs are all outputs after the first OP\_RET except the last one (reserved for coin change). A transaction can have up to 8 bounty outputs, but only one of the bounty output is randomly sampled for verification.

The index of sampling bounty output in the bounty outputs array is $$BlockHash % N$$$$BlockHash % N$$`BlockHash % N` where `N`$$N$$ is the number of the bounty outputs.

## Bounty Recipient

Bounty recipient must be the recipient address of the last output (usually the coin change address) of a transaction in a recent block and

A recent block is a block with a timestamp no earlier than 1 hour from the mining block. The reward is calculated by the lower difficulty of the recent block and the mining block.

To make the bounty recipients different for each miner, the recent transaction is eligible for bounty output of a mining transaction must also have this condition fulfilled:

`KECCAK256(FirstOutpointID + BountyTxID) % 32 = 0`

* FirstOutputID is the first input outpoint ID (LE) of the mining transaction
* BountyTxID is the recent transaction ID (LE)

## Bounty Reward

Bounty rewards have diminishing returns based on the total number of bounties mined. This creates a dynamic where each miner must develop their own strategy to optimize the number of bounties they choose to mine, balancing effort and reward efficiency.

<table><thead><tr><th width="98">Bounty</th><th width="96">Share</th><th width="94">Effective</th><th width="126">Reward Rate</th></tr></thead><tbody><tr><td>1</td><td>1</td><td>55%</td><td>2</td></tr><tr><td>2</td><td>0.95</td><td>48%</td><td>2.95</td></tr><tr><td>3</td><td>0.9</td><td>40%</td><td>3.85</td></tr><tr><td>4</td><td>0.85</td><td>32%</td><td>4.7</td></tr><tr><td>5</td><td>0.8</td><td>24%</td><td>5.5</td></tr><tr><td>6</td><td>0.75</td><td>16%</td><td>6.25</td></tr><tr><td>7</td><td>0.7</td><td>9%</td><td>6.95</td></tr><tr><td>8</td><td>0.65</td><td>1%</td><td>7.6</td></tr></tbody></table>
