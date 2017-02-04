---
layout: page
title: Frequently Asked Questions
---


## Security

### Are merged-mined sidechains secure?

The [security model](http://www.truthcoin.info/blog/drivechain/#drivechains-security) is comparable to Bitcoin's. Bitcoin protects all of the transactions over a recent period of time. Drivechain protects only a subset of these transactions, but it does so over a much longer period of time.

Security is higher when:

* The sidechain in question is popular with users.
* There are many popular sidechains.

A **more important point is this**: the risk-reward decision is one which should be up to each individual user. If you don't like a particular sidechain, or sidechains in general, then you don't have to use them!

But don't try to decide on behalf of other people! If each individual user is free to sell his/her BTC in exchange for an Altcoin (or for fiat), we can hardly deny users the opportunity to move *their money* between two sidechains.

### What negative impact could sidechains have on the mainchain (ie, Bitcoin Core)?

There are none, actually.

Users are free to ignore any sidechain software they don't like. And, thanks to something called ["blind merged mining"](http://www.truthcoin.info/blog/blind-merged-mining/), even miners are free to ignore sidechain software they don't like (while still being able to mine these sidechains for transaction fees).

This means that the sidechains are [completely firewalled](http://www.truthcoin.info/blog/wise-contracts/) from each other. The mainchain cannot be harmed by the mistakes of its child sidechain. Even the [ecological effects](https://www.youtube.com/playlist?list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4) are neutralized.

In fact, because Drivechain is asymmetric (in that the child sidechain is subordinate to the parent mainchain), the mainchains cannot be harmed even by the *success* of their sidechains. Since Bitcoin Core would be the patriarch of this family of sidechains, Core would be the safest chain of them all.

## Implementation

### When will be able to use Drivechain? What's your strategy for getting it into Bitcoin and activated?

I confidently estimate July 1st or earlier, but this will depend on feedback from users.

While technically, the Bitcoin network can upgrade via soft-fork at any time, traditionally we have always used a friendly ("patient"), process of accruing a 95% activation threshold. Which leaves the vote entirely up to the miners.

I expect Drivechain to be popular with miners. Sidechains mean more transaction fees for miners. They also mean a much cooler Bitcoin, which should mean a higher BTC price. Finally, Drivechain enables [larger blocks through a heavier sidechain](https://youtu.be/Gzg_u9gHc5Q?t=1h49m27s). Therefore, one might expect miners to activate the soft fork quickly. Optimistically, Drivechain could be available four weeks after miners decide to support it.

If miners refuse to activate the soft fork, it is still possible for users to activate it, and force it upon the miners (just as today's users force miners to enforce all activated soft forks -- activation of past soft forks is no longer optional for miners). This is riskier, but still very safe if user-support is overwhelming. If user-support is merely lukewarm (or unmeasureable), then we might turn to the exchanges for help.

The "blind merged mining" technology has not been developed. It will take an unknown amount of time to code and review.

### What's the rush? Aren't you worried about bugs?

I am worried about bugs! However, Drivechain's bugs can (probably) be found and fixed "in the wild". Bitcoin's design (particularly, the soft fork model), prevents any bugs in this software from affecting version that don't have Drivechain. This limits the potential damage tremendously (if not completely).

Secondly, software developers are often overworked, and can't prioritize their scarce review-time. Therefore, sadly, the projects that get the most attention are often those that "charge the mound", so to speak.

### Does Drivechain require SegWit?

No.

They are similar -- SegWit requires miners to support a new block structure, and to enforce [new rules for a new address types (P2WPKH, P2WSH)](https://github.com/bitcoin/bips/blob/master/bip-0142.mediawiki). Sidechains also require miners to support a new block structure (one which contains a "withdrawal-vote-database" of minimial size"), and to enforce new rules for a new address type. But the two are requirements are entirely independent of each other. You could have one, the other, both, or none.

However, the two systems could work together. Lightning Network allows instant/fully-reliable transactions *across sidechains*, which would be a nice feature to have.

## Other

### What kind of sidechain projects can we expect?

Please navigate to the [sidechain projects](http://www.drivechain.info/projects/index.html) section.

### Can sidechains really help with Scaling?

I believe that sidechains can solve the *scaling contention*, precisely **because** sidechains do *not* solve scaling itself.

Let me explain.

We might define "resources needed" as X, and "production output" as Y. Then, everyone would want r = Y/X to always be as high as possible.

In Bitcoin's case, the "resources needed" are the node costs -- specifically, the infamous **blocksize**. The "production output" is the network's ability to perform as advertised (as P2P e-cash), specifically the **transactions per second**.

If we define "scalability" as r (in other words, if we define scalability as "transactions per second" divided by "blocksize"), then there is no controversy. Everyone wants to r to be as high as possible. Everyone wants the most scalability.

However, my belief is that the true "contention" is about *choosing the right X*. Even if r were very high (and even if we doubled r, or multiplied it by a factor of 100), there would still be disagreements over X. Some would feel that X is too small, others would feel that X is too large.

This may explain why debates over scalability still persist, despite the surprising discovery of the Lightning Network, which multiplies r by a large factor.

Sidechains are different, in that they allow people to "choose their own X". This does not (directly) impact r, but it should eliminate most of the controversy.

(Interestingly, sidechains may also indirectly impact r, by allowing for [synergy between two chains](https://www.youtube.com/watch?v=Gzg_u9gHc5Q&t=6575s), or by exploiting [a] UTXO commitments, [b] the SC security model, and [c] the mainchain's management of the 21 M limit, to allow sidechains to simply discard old blocks.)
