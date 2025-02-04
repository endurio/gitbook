# Commission

When a reward is claimed by a node, an additional 30% of the token reward is distributed as commission units to the node and all its ancestor nodes in the referral chain. These commission units accumulate in each node until they are either manually taken or claimed alongside the node's own rewards.

With an accumulated commission unit of C, a node can take the following amount of tokens:

$$T = C \times (1 - 2^{{-Rent}\over{RentBase}})$$

and the rest is given to its direct parent as a commission unit, which accumulates until it is claimed by the parent:

$$P = C - T$$

**RentBase** determines how much accumulated rent from miners flows up the referral chain before the commission for upstream referrers is halved. A higher value means more commission is distributed up the referral chain.

### Examples

A simple example: if all nodes have the same rent as RentBase, each node takes half of the commission and leaves the other half for its ancestor nodes.

<figure><img src="../.gitbook/assets/image (19).png" alt="" width="563"><figcaption></figcaption></figure>

Here’s another example:

If RentBase is increased, nodes higher up the chain receive a larger share of the commission because the threshold for halving the commission is raised. This allows more rent to accumulate and flow upwards before any reductions occur. Conversely, lowering RentBase would distribute less commission to upper nodes, favoring nodes closer to the miner. By adjusting RentBase, the system can ensure a more balanced and fair distribution of rewards across all levels.

<figure><img src="../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

There is always a portion of the commission that is not distributed to any nodes, represented by the blank area beyond the last node in the referral chain. This occurs when the accumulated rent surpasses the limits of the referral structure, leaving no eligible nodes to receive the remaining commission. These undisbursed commission units are accumulated in the **0x0 address** node and may later be used as an additional incentive for vesting the ENDU token, further strengthening the tokenomics.
