# Efficiency

Mining experience and efficiency are designed to incentivize regular, consistent, and loyal miners over seasonal ones. They also discourage miners from changing their referrer in the [Referral Network](../refnet/), creating a form of effort investment in the system.

Mining efficiency is the rate of rewards a miner actually earns from their block reward. It starts at 50% for a fresh, new miner address and can only be increased by gaining experience.

As an address claims rewards, it accumulates experience, which is calculated using the [reward coefficient](reward.md#boosted-blocks) and [mining coefficient](../advanced-mining/):

$$xp=\displaystyle\sum{\text{RewardCoefficient} \times \text{MiningCoefficient}}$$

The more experience an address accumulates, the more efficient it becomes. The efficiency rate increases and approaches 100%, but it never fully reaches it. The formula for efficiency is as follows:

$$\text{Efficiency}= 1-\dfrac{1}{2\times 2^{xp\over w}}$$

Here:

* w is the **Efficiency Coefficient**, set to 115,200.
* xp is the miner's accumulated experience.

Miners without a parent in the [Referral Network](../refnet/) only accumulate half of the mining experience.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Experience and Efficiency</p></figcaption></figure>

With an Efficiency Coefficient (w) of 115,200, it is estimated to take approximately 16 days of mining all major blocks to increase efficiency to 75%, another 16 days are required to reach 87.5%, and so on.

On claiming a reward, only $$\text{Efficiency}\times \text{Reward}$$ of ENDU is minted to the miner, while the rest is not minted at all.
