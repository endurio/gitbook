# Node Management

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Node management dialog can be opened by node Button (only after user miner address has linked to a parent in the [refnet](../refnet/ "mention")).

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

In this dialog, user can see their node info displayed:

* (A) the commission unit accumulated from all of the children nodes.
* (B) the commission rate that this node can take (depends on the Rent below).
* (C) the current Rent of the node, displayed in 2 weeks epoch.
* (D) the next rent expiry.
* (E) open Add Rent dialog to update the rent and expiry.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

Add Rent dialog has the following input and info:

* (F) the new Rent value (ENDU / 2 weeks epoch)
* (G) the next Expiry day (must not be sooner than 2 weeks from now)
* (H) the remain unused rent (that will be used for the next epoch)
* (I) the rent Upgrade Fee (see formular in [rent.md](../refnet/rent.md "mention"))
* (J) the new Commission Rate (see formular in [commission.md](../refnet/commission.md "mention"))
* (K) the expected amount of ENDU token to pay
