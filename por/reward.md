# Reward

Rewards are distributed in 30-minute time slots, with 48 slots per day. The reward for each slot is shared among all successful miners within that slot based on their block target difficulty and [mining coefficient](../advanced-mining/).

If the mining brand is a user-defined brand (not `endur.io`), the reward is determined by its campaign owner in the [Brand Market](../brand-market/).

## Slots

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

Daily rewards are distributed across 48 slots (30 minutes each). Some slots, with significantly higher rewards, are specifically designed to engage human miners and reduce the advantages of mining bots during the initial phase of the protocol.

The mining reward for the 𝑖-th boosted slot is $$3745 \times 2^{-i}$$ ENDU.

The time position of the 𝑖-th boosted slot is calculated using the following formula, ensuring a consistent mining schedule every day for a week:

<pre><code><strong>48×n + KECCAK(n/7 | i) % 48
</strong></code></pre>

Thus, the rewards for slots in a day will include:

* a slot with 3,745 ENDU,
* a slot with 1,873 ENDU,
* a slot with 937 ENDU,
* a slot with 469 ENDU,
* a slot with 235 ENDU,
* and so on.

**Note:** Slots of different rewards may collide, meaning some daily rewards could be lost.

## Development **Vault**

For each slot mined, an additional 1/32 of the slot's rewards is minted to the Development Vault, accounting for approximately 3% of the mining rewards.
