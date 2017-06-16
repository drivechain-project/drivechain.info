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

This means that the **sidechains are [completely firewalled](http://www.truthcoin.info/blog/wise-contracts/) from each other**. The mainchain cannot be harmed by the mistakes of its child sidechain. Even the [ecological effects](https://www.youtube.com/playlist?list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4) are neutralized.

In fact, because Drivechain is asymmetric (in that the child sidechain is subordinate to the parent mainchain), the mainchains cannot be harmed even by the *success* of their sidechains. Since Bitcoin Core would be the patriarch of this family of sidechains, Core would be the safest chain of them all.



## Usefulness

### What is the difference between drivechain and extension blocks?

Both approaches attempt to solve the problem of extensibility -- "extending" the capabilities of Bitcoin beyond those which currently exist.

This problem is difficult to solve because of Bitcoin's unique emphasis on "consensus" -- that all users agree on the state of the blockchain. Since all users must agree, and agreement isn't free, there is also an implict agreement on a "minimum required effort" or "minimum tolerable workload". Bitcoin plays by certain rules, and if those rules are to be meaningful they must be enforced as-written.

So we have a situation where [1] the rules (including "required effort" rules) must be enforced, but simultaneously one where [2] users might like to experiment with new rules. In short, we want the benefits of a "hard fork" (and of permissionless innovation) without paying the costs (which are a loss of consensus, or non-enforcement of important rules).

The trick is to try and solve both problems at once. A 'hard fork' solves only problem [2], and 'doing nothing' solves only problem [1]. Extension blocks make some progress toward solving problem [2], at the expense of tremendous sacrifice on [1]. This is because users of the non-extended original chain, are subject to a potential barrage of messages. These messages can be sent at any time, by anyone (including an attacker), and could take on any properties (large in size, difficult to process, slow to validate)...most important of all, invalid messages can be sent for free. In this scenario, the cost of maintaining consensus over "Original" is in great danger (according to some) of rising to  "Original" + "Extension", anyway. This means that the extension block is effectively a hard fork, and we have failed to solve challenge [1].

Instead, Drivechain condenses the from-extension-to-original messages into infrequent, easy to validate, unambiguous, chain-scale messages. It essentially flips the consensus threat on its head by arguing that the sidechain should do all of the consensus labor, and it should then present a tiny, minimal easy-to-verify proof of that labor to the mainchain at infrequent intervals. (In the sense of being "difficult to generate but easy to verify", it resembles proof-of-work itself.) This allows us to solve problem [2] without compromising on [1].

This is why Adam Back in particular emphasizes the "slow return" feature of Drivechain, whenever possible (recall that Dr. Back was a major innovator and promoter of extension blocks in early 2014).


### I have heard that it will take 3-6 months to transfer money from the sidechain to the mainchain. Won't that be too slow to be useful?

Firstly, these are customizable parameters, and open for debate -- but if withdrawals are every x=3 months, and only x=1 withdrawal can make forward progress [on the mainchain] at a time, and only x=1 prospective withdrawal can be assembled [by the sidechain] at a time, then indeed we can expect total withdrawal time to average 4.5 months [(.5)*3+3] ).

Some complain that such a system would be too slow to be usable, but replies of this kind disregard the effect of atomic cross-chain swaps, which are instant.

( Furthermore, while side-to-main transfers are slow, main-to-side transfers are quite fast, x~=10 confirmations. I would go as far as to say that, just as the Lightning Network is enabled by SegWit and CSV, Drivechain is enabled by the atomic swaps and of Counterparty-like 'embedded consensus'. )

Thanks to atomic swaps, someone can act as an investment banker or custodian, and purchase side:BTC at a (tiny, competitive discount) and then transfer those side-to-main at a minimal inconvenience (comparable to that of someone who buys a bank CD). Through market activities, the *entire system* becomes exactly as patient as its most-patient members. As icing on the cake, people who aren't planning on using their BTC anytime soon (ie "the patient") can even get a tiny investment yield, in return for providing this service.


### What if a sidechain has too few nodes? Who will run them? Who will maintain this software?

There is an absolutely crucial distinction between:

1. A problem with a sidechain that negatively impacts its parent chain.
2. A problem with a sidechain that only impacts the sidechain users.

The first type of problem is unacceptable, but the second type of problem is actually *desirable*.

If we wanted to have the best BTC currency unit possible, we would want everyone to try all kinds of things out, *especially* the things that we think are terrible. We'd want lots of things to be tried, and for the losers to "fail fast".

In practice I highly doubt the sidechain ecosystem would be anywhere near as dynamic as NYC or Silicon Valley. But these types of question, such as "What if a sidechain breaks / has DAO-like problems?"; "What if the sidechain has only a few nodes? Who will run them?"; "Who will maintain these projects?"; -- really just miss the point. If the sidechain is garbage, that's *their* problem, not yours!

Users who aren't comfortable with the risks of new chains / new features, can simply decline to use them. If the benefits of a sidechain (to Person X) outweigh its risks (to Person X), the Person X will move some BTC there.

###  What if a sidechain becomes "Too Big To Fail"?

In other words: "What if a *majority* of BTC is moved to one sidechain, and then that sidechain has some kind of problem?".

One simple solution would be to cap the quantity of BTC that can be moved to each sidechain, (perhaps at x=10% ; aka 210,000).

Other than that, I would point out that Bitcoin has always been the "money of principle", and that we survived the MtGox announcement (in which ~850,000/12,400,000 = 6.85% of the total BTC were assumed to be stolen).


## Implementation


### When will be able to use Drivechain? What's your strategy for getting it into Bitcoin and activated?

I confidently estimate <del>July 1st or earlier, but this will depend on feedback from users</del>. The delay is not actually due to the planning fallacy (as would otherwise be the case). Instead it is because the project scope expanded to include Blind Merged Mining, which is itself a significant project. However, based on the feedback received as of June, it seems that Drivechain could be active in a January 2018 release of Bitcoin.

While technically, the Bitcoin network can upgrade via soft-fork at any time, traditionally we have always used a friendly ("patient"), process of accruing a 95% activation threshold. Which leaves the vote entirely up to the miners.

I expect Drivechain to be popular with miners. Sidechains mean more transaction fees for miners. They also mean a much cooler Bitcoin, which should mean a higher BTC price. Finally, Drivechain enables [larger blocks through a heavier sidechain](https://youtu.be/Gzg_u9gHc5Q?t=1h49m27s). Therefore, one might expect miners to activate the soft fork quickly. Optimistically, **Drivechain could be available 2-4 weeks after miners decide to support it**.

If miners refuse to activate the soft fork, it is still possible for users to activate it, and force it upon the miners (just as today's users force miners to enforce all activated soft forks -- activation of past soft forks is no longer optional for miners). This is riskier, but still very safe if user-support is overwhelming. If user-support is merely lukewarm (or unmeasureable), then we might turn to the exchanges for help.

The "blind merged mining" technology <del>has not been developed</del> is under development. It will <del>take an unknown amount of time to code and review</del> probably be finished by the end of the summer.


### What's the rush? Aren't you worried about bugs?

I am worried about bugs! However, **Drivechain's bugs can (probably) be found and fixed "in the wild"**. Bitcoin's design (particularly, the soft fork model), prevents any bugs in this software from affecting version that don't have Drivechain. This limits the potential damage tremendously (if not completely).

Secondly, software developers are often overworked, and can't prioritize their scarce review-time. Therefore, sadly, the projects that get the most attention are often those that "charge the mound", so to speak.


### Does Drivechain require SegWit?

No.

They are similar -- SegWit requires miners to support a new block structure, and to enforce [new rules for a new address types (P2WPKH, P2WSH)](https://github.com/bitcoin/bips/blob/master/bip-0142.mediawiki). Sidechains also require miners to support a new block structure (one which contains a "withdrawal-vote-database" of minimial size"), and to enforce new rules for a new address type. But the two are requirements are entirely independent of each other. **You could have one, the other, both, or none.**

However, the two have tremendous synergy. Lightning Network allows instant/fully-reliable transactions *across sidechains*, which is very cool for both Sidechains and LN.


## Other


### What kind of sidechain projects can we expect?

Please navigate to the [sidechain projects](http://www.drivechain.info/projects/index.html) section.


### Can sidechains really help with Scaling?

I believe that sidechains can solve the *scaling contention*, precisely **because** sidechains do *not* solve scaling itself.

Let me explain.

We might define "resources needed" as X, and "production output" as Y. Then, everyone would want r = Y/X to always be as high as possible.

In Bitcoin's case, the "resources needed" are the node costs -- the infamous **blocksize**. The "production output" is the network's ability -- the **transactions per second**.

If we define "scalability" as r (ie "transactions per second" / "blocksize"), then there is no controversy about r. Everyone wants to r to be as high as possible. Everyone wants the most scalability.

However, my belief is that the "contention" (ie, the "reason everyone is upset") is about *choosing the right X*. No matter the r, some people feel that X is too small (and others feel that X is too large). (This may explain why debates over scalability still persist, despite the surprising discovery of the Lightning Network, which multiplies r by a large factor.)

Sidechains are different, in that they allow people to "choose their own X". This does not (directly) impact r, but it should eliminate most of the controversy.

(Interestingly, sidechains may also indirectly impact r, by allowing for [synergy between two chains](https://www.youtube.com/watch?v=Gzg_u9gHc5Q&t=6575s), or by exploiting [a] UTXO commitments, [b] the SC security model, and [c] the mainchain's management of the 21 M limit, to allow sidechains to simply discard old blocks.)
