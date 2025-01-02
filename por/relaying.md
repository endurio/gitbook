# Relaying

To relay is to provide cryptographic proofs that a mining transaction is confirmed in a valid PoW block. Instead of full relaying, Endurio opts for quasi-relaying that accepts orphaned blocks and blocks that don't belong to any chain.

The mining transaction must be relayed no later than **48 hours** after the target Bitcoin block's timestamp or the reward is lost forever.
