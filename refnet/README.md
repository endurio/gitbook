# Referral Network

Referral Network (RefNet) is a referral affiliate network represented as a forest data structure.

Each node can refer to a parent node. A node with no parent is considered a root node, and root nodes accumulate only half of the [experience](../por/efficiency.md) when claiming rewards. The parent node reference cannot be changed or removed.

For each mining reward claimed, up to 30% of the reward is minted to a single node in the miner's referral chain as a commission.

