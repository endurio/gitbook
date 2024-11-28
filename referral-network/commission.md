# Commission

When a $$Reward$$ is claimed by miner $$M$$, one of the nodes in the referral chain is paid a commission of $$Reward \times ComRate$$.

The chance of receiving commission for each node is proportional to their area in the following graph, where the miner is node $$0$$ and node $$i+1$$ is the parent of node $$i$$.

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>Commission Distribution</p></figcaption></figure>

The curve is $$f(x) = (\frac 1 2)^x$$, with $$r_i$$ is the effective rent of node $$i$$ and $$x_i = \displaystyle\sum_0^i{r_i \over RentScale}$$, we have: $$S_i=\displaystyle\int_{x_{i-1}}^{x_i}f(x)dx$$

Since the whole area under the curve is:

$$S = \displaystyle\int_0^\infty f(x)dx = \dfrac{1}{ln(2)}$$,

the chance of receiving commission for node $$i$$ is:

$$\dfrac{S_i}S = S_i \times ln(2)$$.

There's always a chance that no node will receive the commission, which is represented by the blank area after the last node of the referral chain $$S_3$$.

**RentScale**: how much accumulate rent from the miner up the referral chain until the commission chance is halved. The higher the value, the more commission is distributed up the referral chain.
