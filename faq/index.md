---
layout: page
title: Frequently Asked Questions
---

Updated March 2023

## 1. Security ## {#security}

### How are drivechains secured? ### {#sidechain-theft}

Miners "farm" sidechains for their txn fees (and exchange-rate value-add). Why kill the "goose that lays the golden eggs"?

Well, it depends on:

* How many eggs they lay
* How much the dead goose is worth, and
* How much effort it takes to actually kill the goose.

So, no two drivechains will have the same level of security.

Some will lay many "eggs". These will have high fee-revenues, and/or will enhance the underlying coin-utility.

Similarly, some drivechains are more valuable to "kill" than others. The more coins on a drivechain, the higher the incentive to "kill" it (and take all those coins).

Finally, how to "kill" such a drivechain?

Because of the "slow return" feature of BIP300, it isn't easy. Miners must 51% attack in a very transparent and obvious way, in full view of everyone, for a continuous 3-6 months, *before* the coins can be stolen.

The formal security model is [here](http://www.truthcoin.info/blog/drivechain/#drivechains-security).

In general, Drivechain security is higher when:

* The drivechain in question is popular with users.
* There are many popular drivechains.


### What if a sidechain isn't popular?? Can miners "steal" from a sidechain? ## {#unpopular-sc}

An unpopular sidechain is one which:

* Has low total txn fees, AND/OR
* If the sidechain went away, the market price of Bitcoin would NOT fall significantly.

In such a case, Miners lose very little, economically, by taking the sidechain's coins. Especially if mining turnover is low (among pools/devices), and hashrate is stable.


### Isn't that bad? ### {#user-sovereignty}

Not really. 

We currently have ZERO sidechains. So even a 99.99% unpopularity rate (and a 100% failure rate of unpopular sidechains) would be an improvement over the status quo. At least we'd improve from 0% to 00.01%.

The risk-reward decision is one each user should make. Not you! If you don't like a particular sidechain, or sidechains in general, then don't use them! It's like that slogan: "If you don't Like Gay Marriage, don't get one!".

Users today sell their BTC for goods/services; for fiat; and for Alts. Why deny them the option to move their coins to a sidechain? They are the owner. Not you! Mind your own business!!


### What negative impact could sidechains have on the mainchain (ie, Bitcoin Core)? ### {#harms}

There are none, actually.

I looked into it in detail, [in 2016](https://www.youtube.com/playlist?list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4).


### Really?! What about miner incentives? ### {#mining-incentives}

Sidechain merged-mining is a new revenue stream for miners, yes.

But [Altcoin merged-mining(https://medium.com/braiins/why-slush-pool-merge-mines-rsk-and-not-elastos-or-vcash-156a8a0c470c) has existed for years. It was invented by Satoshi in 2010. And has been in [widespread use](https://blog.bitmex.com/the-growth-of-bitcoin-merge-mining/) ever since.

All BIP300 does, is supercharge MM. With sidechains, miners would (hopefully) get huge revenues (and profits) from MM... instead of the pittance they get from MM today.


### Are you sure that isn't bad? ### {#miner-profits-bad}

Yes, I'm sure.

Profits are good for miners. And good for us. They increase Bitcoin's [security budget](https://www.truthcoin.info/blog/security-budget-ii-mm/). They increase the network Difficulty. They deter 51% attacks (by making them more expensive).

Mining has seen many "changes" that have increased profits:

* Using ASICs, instead of CPUs
* Using a pool whose software maximizes txn-fees (vs one that leaves this "free" money on the table)
* Collecting [natgas tax credits](https://www.forbes.com/sites/christopherhelman/2021/08/02/green-bitcoin-mining-the-big-profits-in-clean-crypto/?sh=275922a534ce), while taking advantage of stranded energy
* Negotiating lower-than-normal energy prices via a ["demand response"](https://www.newsweek.com/bitcoin-mining-americas-most-misunderstood-industry-opinion-1669892) contract

Merged mining is no different than those changes.


### But this is a change that affects the protocol! ### {#affects-protocol}

BIP300 affects the L1 Bitcoin protocol; the sidechains *themselves* do not.

The L1 protocol *never* behaves differently, based on something a sidechain does, ever. It only behaves differently based on what the BIP300 messages do. **All** BIP300 messages are included in the L1 blockchain -- your node has to look at them anyway. Enforcing BIP300, does NOT mean downloading sidechain software, nor seeing sidechain blocks nor sidechain transactions.

Whether the *miners* download sidechain software, and collect coins over there... that's *their* business, not yours. They already face this decision with merged-mined Altcoins. And they make it without any input from you! Mind your own business!


### Are you absolutely sure about that? It sounds heretical. ### {#blockstream-mistake}

Unfortunately, [Blockstream's paper](https://www.blockstream.com/sidechains.pdf) mistakenly defined "mining centralization" as: "when any miner increases their profits". (Read Section 4.3 and see for yourself.)

This mistake is the worst thing to happen to Bitcoin in its history. It led to years of irrational prejudice against merged mining. Years of "miner centralization bad" = "any increase in miner profits bad" = "miners collecting more txn fees sometimes, is bad". Which is unfortunate because the opposite is true. Of course.

BIP300 forces miners to care about something new: maximizing sidechain utility, and sidechain txn fees. This is *good* for us -- one more task that our mining servants perform, for us. And if they don't perform --if they don't work as hard as they possibly can, as hard as all their rivals at least-- then they are fired.

Miners have to care about new stuff all the time (such as natural gas credits example, two answers ago). This is heathy and normal.


### What is the correct definition of "mining centralization", then? ### {#mining-centralization}

If you ask me, the correct definition of "mining centralization" is: the cost of starting up a new, viable **mining pool**. Thus, we can increase decentralization by making it easy to pool hop, and making high-quality open source pool software widely availiable for free.

The centralization you should focus on, is [CONOP centralization](https://www.truthcoin.info/blog/measuring-decentralization/) -- the cost of starting up a new full node. CONOP centralization is the "real" form of centralization, and it is unaffected by the arrival of a new BIP300 sidechain. (There is a microscopic, fixed increase in CONOP, due to enforcement of [the BIP300 rules](https://github.com/bitcoin/bips/blob/master/bip-0300.mediawiki), but by the time BIP300 activates, this increase will have been offset 1000x by everyday advances in computer power/cost.)

Your node only enforces the BIP300 rules on L1 messages; your node does not look at any L2 messages.


### How are sidechains secure, if my L1 node isn't looking at them? ### {#blind}

For block-finding, it is the same as merged mined Namecoin which has existed for years.

For the withdrawals -- well, why wouldn't miners steal from them?

1. It would end the flow of sidechain txn fees.
2. It might negatively affect the price of Bitcoin.
3. The slow, rare nature of the BIP300 withdrawal makes it very easy for everyone to audit a theft. Even laypeople will know, with certainty, who is stealing from who. It's like shoplifting, but you are on national live television, and can only move in ultra-slow motion. The theft will be noticed, understood, communicated worldwide, and universally condemmed, several months before it can actually "go through".

More details are in [the original 2015 post](https://www.truthcoin.info/blog/drivechain/#drivechains-security).


### If withdrawals are so slow, won't users hate that? ### {#withdrawal-speed}

No. Only specialists will use the BIP300 withdrawal. It can only pay out to 20,000 L1 destination UTXOs, anyway. So it is capped at 20,000 outputs per 3-6 months.

Everyone else will transact *with* those specialists. The specialists will be exchanges like Coinbase/Kraken, or they will be private users trustlessly swapping coins with HTLCs.

The specialist charges a fee, but users get to move their coins from L2 back to L1 immediately. The layperson customer never has to wait.


### What if a sidechain becomes so successful, that it becomes the dominant chain? ### {#sc-success}

Drivechain is asymmetric. The child sidechain is subordinate to the parent mainchain, always. If the mainchain ceases to exist, then all child sidechains cease to exist as well.


### Does Drivechain rely on a UASF to prevent a sidechain theft? ### {#uasf-reliance}

No.

I will unpack this answer in three sections.

##### (i) Live by the UASF, Die by the UASF

A UASF can block a sidechain-theft... but a different UASF can *force* a sc-theft to go through!

And everything in between: a UASF could guarantee that all sc-withdrawals always fail (whether these be theft-withdrawals or honest-withdrawals); or, it could force all honest withdrawals to succeed as quickly as possible. Or: that all thefts always succeed on precisely the 22,222nd block after they are attempted (or any other number between 13,150 and 26,300).

So it is not meaningful to imbue the UASF with an "anti-theft" feature. Instead, the UASF is simply a vehicle through which users clarify, VERY loudly, exactly what it is they want to buy from miners when they hand over 140,000 USD (at 2/18/2018 prices) in exchange for the newest 13.5 BTC (assuming 1 BTC of tx fees).

If a UASF fails, then it had no effect. If a UASF succeeds, then by definition it has defeated the miners. So, yes, a UASF can block miner-theft.


##### (ii) "Preventing" Theft

If miners are determined to theft-attack a sidechain, then the victims should try to UASF. It costs nothing to them, nothing to anyone else, and it might succeed (in blocking the theft).

The anti-theft UASF will split the chain, at the time (3 months from now) when the withdrawal finally goes through. 

Victims (the UASFers) will hope that the free market favors their UASF coins, with a higher price (higher than the non-UASF-coins). If so, then the UASF will succeed and the miners will be defeated. Miners must extend the higher-value chain (see [here](https://medium.com/@bramcohen/bitcoin-s-ironic-crisis-32226a85e39f) and [here](https://medium.com/@danrobinson/the-cost-of-supporting-the-b2x-fork-how-to-lose-100m-in-ten-days-6797f7ef52da)). The network will re-fuse into one blockchain where the theft *could* have been included in a block, but never was.

If that doesn't happen, then the UASF fails. But it only affects the people who voluntarily opted-in to it. The sidechain theft goes through, but new bad thing happens, to anyone. So it is free to try.

Here, the UASF "prevents" the sidechain-theft. But only if the UASF increases the market price. So, really, DC "relies" on market price, not UASF.


##### (iii) What does DC "Rely" On, if not UASFs?

Sidechain popularity -- sidechain-enabled coins, are *worth more* than mono-chain coins -- this is [the "m" parameter](http://www.truthcoin.info/blog/drivechain/#drivechains-security). And they give fee revenues (the "b" parameter). But only while they are safe to use.


<!---

### Isn't that [UASF reliance] solution [socially unscalable](https://twitter.com/theinstagibbs/status/965315428686934016)? ### {#social-scalability}

Drivechain does not rely on UASFs, but I will answer anyway.

No.

UASFs can be made to be [socially scalable](http://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html).

First, imagine miners are super-evil and each withdrawal *must* be escorted to safety via a fresh UASF. (Ie, BIP300 withdrawals "rely on" UASFs.)

Is that "socially scalable"?

Greg Sanders [suggests on Twitter](https://twitter.com/theinstagibbs/status/965315428686934016): "no". He says coordination is hard (if it were easy, who would need blockchains?).

Usually coordination is hard, but not here. 

The key difference is the user's *alternatives*. The *first* blockchain ever invented, could not rely on UASF to work.

But once a few exist, the user can simplye *wait*.

However, once we already have a few different blockchains set up, the user has an option to simply *wait*. So, the default policy of everyone could be to prevent all withdrawals, unless the evidence of their honesty is overwhelming. (It is a little like how, if you actually go to court, you need to have all of your documents very organized -- you cannot waste the judge's time.) The social scalability can be increased arbitrarily, at a cost of making all of the withdrawals more likely to fail (ie, time out) or else by simply making them all take much longer. In other words, instead of checking in on a sidechain once every 3 months, you could check in on each sidechain once every year, or once every two years.

And, as luck would have it, "slowing everything down" yet another difference between our case and the 'from scratch' case. There, slow means slow, and degraded performance for everyone. But in our multi-network case, only the side-to-main PegOut withdrawals are delayed...users can *immediately* use Atomic Swaps to sell their side:BTC for main:BTC. Speculators will compete to give them the best prices, and, through the magic of the market, every single sidechain user will become precisely as patient as the most patient person in the network.

So the social scalability can be reclaimed, without the entire system failing. Instead, one aspect of it simply becomes a little bit more expensive.



### Isn't that ["relying" on a UASF] an example of sidechains affecting mainchains ("mainchain contagion")? And thus, a sidechain could have an impact on the mainchain (and your whole goal was to avoid exactly that)? ### {#uasf-contagion}

It is true that a sidechain-induced UASF can cause a mainchain reorganization.

This requires five things to happen, in a row:

1. Attackers are not deterred from attacking, and they initiate a theft.
2. Some users decide that they will UASF to prevent the theft.
3. Miners carry a theft 13,150 places (ie, the attack succeeds).
4. Most miners guess that the non-UASF side will win... (ie, there is no immediate surrender, and the chain splits).
5. ...but this guess is wrong. (The UASF ultimately wins and the chains refuse.)

I have some remarks about this complaint before I respond:

* This is a complaint that the UASF *succeeds* in blocking SC-theft. It prefers that user's funds be stolen. Instead of worrying that [1] the UASF wouldn't work, or [2] that users would not be motivated UASFing, this complaint is the opposite: that people put in the effort and that they succeed.
* Miners always have to "choose" the side of the fork that the investors choose. Even if the miners prefer Coin B to Coin A, if the market price of Coin A is highest, then miners can *maximize their number of Coin B* by mining the A network and selling those A_coins immediately for B_coins. Indeed, this realization is exactly what killed off the misguided SegWit2x fork.
* This complaint requires the miners to pick the "wrong" side (ie the side opposed by the investors), despite the fact that miners want to always pick the "right" side. Miners have some (small) opportunity to discover which side is right ahead of time, so this complaint requires the miners to act against their self interest. Each block of the non-UASF chain is mined at full strength, but will ultimately be worthless.
* This "complaint" is not just that DC causes the mainchain to reorg, but also that it causes the mainchain's coins to become *more valuable*.
* * This is because the reorganization will only take place, if investors decide that the non-UASF side will not win (and therefore that the coins on that side are worth less). However, at this point in the timeline, the non-UASF side is the "real" side -- it is the heaviest (most-work) mainchain. So this reorg can only be one that significantly increases the value of everyone's mainchain BTC hodlings.
* * By a utilitarian criterion, the reorganization is "the right thing to do". This is because the market price is an objective measurement (of subjective factors). The non-UASF-price is the price of "theft-laden" token, and the UASF-price is the price of a "reorg-laden" token. If the UASF price is higher, the damage of the reorg [to mainchain Bitcoin value] is smaller than the damage of the theft [to same]. So this is a complaint that the network will automatically do the right thing.
* * In other words, the complaint here is that Bitcoin investors love Drivechain so much that they are willing to reorg for it.

Now, my responses:

1. I'm not sure that this complaint is logically consistent. It requires two things: first, that the investors and some users challenge the miners and defeat them, but also second, that the miners not to be deterred from attacking in the first place. In other words, in the list above, items 4 and 5 seem to contradict items 1 and 3.
2. Miners lose big by betting against the wrong side of the fork. They have an incentive to defect to the winning side as quickly as possible.
3. This complaint is not really a conflict between miners and users. Instead, it is a conflict between investors (who prefer reorgs over SC-theft) and merchants (who prefer SC-theft over reorgs). The investors are strictly more important (in part because they *contain* opinions about what is best for merchants, but the reverse is not necessarily true).
4. The problem mostly solves itself, because of txn replay. We might tighten the UASF further, so as to neutralize the impact of the reorg. We force the UASF chain to be aware of its rival [the non-UASF chain], and we force it to "replay" as many of those txns as possible. In particular, the UASF chain would watch the non-UASF for "buried" blocks (those with 6 or more confirmations), and it would then be required to replay as many of those txns as possible. Of course, we do not want to do this perfectly, because we want speculators to take sides and establish different prices for the two tokens. So instead, we might simply decide to do nothing, and let txn replay naturally confer double-spend-protection to many people. Perhaps, the only thing we'd do, is disable RBF for buried non-UASF txns.
5. Independent of Drivechain, we should already have protection built into wallet software that warns people of a rival blockchain.

The most important response of all, is to point out how out-of-context this complaint is. Complaints such as these scratch the bottom of the barrel as far as relevancy. Meanwhile, Bitcoin has serious competition in the form of "dumb but popular" Altcoins (think Qwerty keybord vs. Esperanto the "best" language; VHS vs BetaMax etc), messy hard fork campaigns, and fundamental [not-resolvable] disagreements over how much it should cost to run a Bitcoin node. These are serious problems that Drivechain has a shot at solving. What is presented in the complaint above is as follows: that there might occasionally, with overwhelming advance warning, be a small mainchain reorg, supported by the economic majority, to prevent sidechain theft, if numerous people act against their own self interest all at once. Contrast that with how much "mainchain contagion" we would have if Ethereum simply displaced Bitcoin as the Internet's money.

-->


### Why does drivechain allow miners to deny the creation of a given sidechain? Are you against permissionless innovation? Are you a BitMain shill?? ### {#categorical-control}

Miners will add a sidechain if it makes money to do so.

Also, Miners will remove a sidechain, if it makes money to do so.


### Miners earn more, by removing a sidechain?! How could that happen?? ### {#categorical-control-2}

If one sidechain prevents a 2nd from reaching its full potential, then the 1st sidechain is a troublemaker. It should be gotten rid of, the same way that security guards keep out thieves.

See my ["Smart Contract Ecology" presentation](https://www.youtube.com/watch?v=xGu0o8HH10U&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=1) (or [answer below](www.drivechain.info/faq/#categorical-control) for more details.

This is actually why a sidechain-system is superior to one single general purpose blockchain (as in Ethereum). 



### In the security model you mention ["sounding the alarm"](http://www.truthcoin.info/blog/drivechain/#security-models), where users and miners warn other users and miners. Isn't this centralization / collusion? ### {#sound-the-alarm}

One reddit user [writes](https://www.reddit.com/r/Bitcoin/comments/6ztp3b/lets_discuss_something_techrelated_for_a_change/dn0rsdo/?utm_content=permalink&utm_medium=front&utm_source=reddit&utm_name=Bitcoin): "Drivechains have 1008-block cycles ostensibly to protect against theft, so that someone can 'raise the alarm' and tell miners to downvote a particular theft withdrawal, but that sounds too much like centralized collusion to me."

While this is collaboration, it is not centralization. Drivechain is designed so that everyone can **independently** respond to the alarm by doing the right thing. They do not need to coordinate with a leader, or a large miner or other users, or anything else. They simply know what to do, because, by design, it is very easy for them to learn what to do. In this case the design is much better than, [the March 2013 consensus failure emergency](http://www.truthcoin.info/blog/against-the-hard-fork/#3-coordination-and-ambiguity). A drivechain theft would be exactly like that event (in which everything worked out just fine), except that it would be much *better*, because **everyone** would: [1] have plenty of warning, and time to respond (two months or so), and [2] would already know what to do (either downvote everything, or manually upvote the winner, both will work).


### Why can there be only 256 sidechains? Won't we run out?? There are 600,000 Altcoins on coinmarketcap!

256 is the right number. The people who disagree, fail to grasp the following facts:

* The "600,000 Altcoins on coinmarketcap" represent only \~40 novel ideas. The other 599,960 coins are just a carbon-copy of one of the 40, with a different name. The name is the only new thing.
* Many of those ideas are novel consensus mechanisms.
* * They replace proof-of-work with something else. (This is near-certain to fail.)
* * They try to solve a problem that has already been solved by Merged-mining. So they add no value to a merged-mined Bitcoin sidechain.



## 2. Comparisons

### How does this proposal compare to the proposal in [the Oct 2014 paper "Enabling Blockchain Innovations with Pegged Sidechains"](https://blockstream.com/sidechains.pdf)? ### {#blockstream}

Only in Appendix B is there a concrete suggestion. It was never implemented in the real world, and in the paper it is immediately qualified with the sentence "A detailed analysis of this problem and its possible solutions is out of scope for this document".

Nonetheless we can compare.

In Drivechain it is impossible to conduct a surprise attack, impossible to harass the community writ large with many withdrawal attempts (ie a "mosquito strategy"), and very easy for users to understand that the attack is happening, long before it actually happens. Also, each attempt is very simple, one question of 'Endorse'/'Reject' -- quite comparable to the [the March 2013 anti-consensus event](https://freedom-to-tinker.com/2015/07/28/analyzing-the-2013-bitcoin-fork-centralized-decision-making-saved-the-day/).

A slow transparent process means that it is impossible for miners to attack the chain and claim that they didn't know that they were doing so -- with transparency, everyone knows, observers as well as the miners themselves. So it is a clearer demonstration of malice.

Blockstream's skiplist proof is "in the tens of kilobytes range". DC requires first [an M3 message, and next many M4 messages](https://github.com/bitcoin/bips/blob/master/bip-0300.mediawiki#user-content-M4__ACK_Bundles). Roughly 1 marginal byte per sidechain per block. Over 13,150 blocks, this is 13.150 KB per sidechain of course. So Drivechain's size is slightly smaller.



### What is the difference between drivechain and extension blocks? ### {#ext-blocks}

Both approaches attempt to solve the problem of extensibility -- "extending" the capabilities of Bitcoin beyond those which currently exist.

This extensibility problem is a difficult one to solve, because of Bitcoin's unique emphasis on "consensus" -- that all users agree on the state of the blockchain. Since all users must agree, and agreement isn't free, there is also an implicit agreement on a "minimum required effort" or "minimum tolerable workload". Bitcoin plays by certain rules, and if those rules are to be meaningful they must be enforced as-written.

So we have a situation where [1] the rules (including "required effort" rules) must be enforced, but simultaneously one where [2] users might like to experiment with new rules. In short, we want the benefits of a "hard fork" (and of permissionless innovation) without paying the costs (which are a loss of consensus, or non-enforcement of important rules).

The trick is to try and solve both problems at once. A 'hard fork' solves only problem [2], and 'doing nothing' solves only problem [1]. Extension blocks make some progress toward solving problem [2], at the expense of tremendous sacrifice on [1]. This is because users of the non-extended original chain, are subject to a potential barrage of messages. These messages can be sent at any time, by anyone (including an attacker), and could take on any properties (large in size, difficult to process, slow to validate)...most important of all, invalid messages can be sent for free. In this scenario, the cost of maintaining consensus over "Original" is in great danger (according to some) of rising to  "Original" + "Extension", anyway. This means that the extension block is effectively a hard fork, and we have failed to solve challenge [1].

Instead, Drivechain **[condenses](http://www.truthcoin.info/blog/drivechain/#just-right-awareness)** the from-extension-to-original messages into infrequent, easy to validate, unambiguous, chain-scale messages. It essentially flips the consensus threat on its head by arguing that the sidechain should do all of the consensus labor, and it should then present a tiny, minimal easy-to-verify proof of that labor to the mainchain at infrequent intervals. (In the sense of being "difficult to generate but easy to verify", it resembles proof-of-work itself.) This allows us to solve problem [2] without compromising on [1].

This is why Adam Back in particular emphasizes the "slow return" feature of Drivechain, whenever possible (recall that Dr. Back was a major innovator and promoter of extension blocks in early 2014).


### What about [Zmn..'s Sidechain-Headers-on-Mainchain (SHoM)](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-September/014910.html) ? ### {#shom}

Again, to repeat the answer for extension blocks (above), **the distinction between hard and soft forks isn't the point**.

The point is, instead, **the [burden](http://www.truthcoin.info/blog/measuring-decentralization/) placed on existing users**. While an extension block does allow 'oldtype nodes' to ignore the extension data, it does this at a cost of no longer being able to fully-validate the block. It is a 'backdoor hardfork', of a kind, because users need to upgrade.

Imagine five different scenarios:

1. Hard Fork to a 2.2 MB
2. Evil fork to a 2.2 MB
3. Extension Block adding +1.2 MB 
4. Segwit ExtBlock adding +1.2 MB
5. Drivechain adding +1.2 MB

Keep in mind that, in order to use Bitcoin as money, every user must check every txn for double-spending. Therefore, if we narrowly assess each of these scenarios in terms of "the burden they place on existing users", we get the following:

1. A hard fork is bad, because old users must upgrade, and track 1.2 more data.
2. An evil fork is bad, because old users must upgrade, and track 1.2 more data.
3. An extension blocks soft fork is bad, because while old users don't need to upgrade yet, they might need to have done so at any time.
4. A SegWit extension block soft fork was bad, for the exact same reasons (immediately above).
5. A drivechain is good, because it does not force you to upgrade; and if you need to upgrade you will be given plenty of warning, and ultimately even if none of the upgraded / non-upgraded people agree there are no consensus failures on the mainchain.

In my view, SHoM is too similar to an extension block. And it therefore lacks drivechain's most important features.

### What about [NiPoPoW](https://twitter.com/coindesk/status/953493657042202624) by A. Kiayias and D. Zindros ? ### {#nipopow}

I [tweeted my thoughts](https://twitter.com/Truthcoin/status/1060585538925735936) on this article. I am happy that the authors worked on this, but I do not think that I can use it for anything.


### What about [ZK Validity Rollups](https://bitcoinrollups.org/#section-1-an-introduction-to-validity-rollups)? ### {#rollups}

Rollups pack a list of txns into a smaller amount of L1 space. Thus, they are a perfectly legitimate L2.

They have several drawbacks when compared to drivechain.

First: the benefits of rollups are much lower.

Rollup's increase in onboarding capacity is capped. See an example of capped-ness [here](https://bitcoinrollups.org/#section-1-an-introduction-to-validity-rollups):

<div class="language-plaintext highlighter-rouge"><div class="highlight"><pre class="highlight"><code>The onchain transactions needed to open and settle (and
occasionally rebalance) self-custodial Lightning channels
take up a measureable amount of limited bitcoin block space.
This block space footprint results in a hard upper limit
on the number of self-custodial users who can be onboarded
to Lightning in a given period of time. The additional
transaction capacity enabled by validity rollups could
be used to support more Lightning transactions ...
For 2-P2WPKH-input-1-P2WSH-output-2-P2WPKH-output
dual-funded channels, rollups can create room for up to
3.8x more Lightning channel open transactions.
</code></pre></div></div>

In contrast, in Drivechain the onboarding growth factor is not limited to 3.8 -- instead it is unlimited.

If rollups use an account model (vs utxo), their growth factor may be 10x or 100x more (ie, it may be 38x or 380x). But I have yet to see anyone describe, design, or code this.

Furthermore, rollups do not have as much flexibility as sidechains. (Sidechains have unlimited flexibility -- everything in a rollup must in principle be *writeable* to L1, whereas sidechains are the reverse: everything experienced on the sidechain must be in principle *ignorable* on L1.)

Second, rollups require a big change to L1: L1 must validate zk-snarks. Bip300 is just an integer that counts from 1 to 13,150, which is something that anyone can understand and audit. Zk-stuff is rightly called ["spooky moon math"](https://old.reddit.com/r/ethereum/comments/6wjnou/what_is_zksnarks_spooky_moon_math/) and most experts are (or were) confounded by it (see [here](https://twitter.com/peterktodd/status/794950673280409601) and [here](https://www.youtube.com/watch?v=P6RLjcGVUnw&t=1050s)). The average person has zero chance of ever grasping the difference between a zk-proof system that is *pretending to work* (vs one that is working genuinely). You might say: so much the worse, for the average person! Rightly so, but "most L1 node runners" also have zero chance of understanding or auditing these systems. Nor does the economic center of gravity of the Bitcoin system. In contrast, things like hash functions and signatures are simple operations that a user can perform for themselves, many times -- thus they can learn the basics and "audit" their computer.

Third, rollups do nothing to solve the "data availability problem". Drivechain does not solve it either... but Drivechain is at least designed with this DA failure mode in mind. To marginally address DA, Drivechain rewards L1 miners with txn fees (via merged mining); and rewards L2 users (via useful services). Rollups are often presented as though they are impervious to failure. But really: DA is where the rubber meets the road, and rollups do nothing about this big problem.

Fourth, despite the above limitations, the main "advantage" that rollups have over DC, is very very small. The advantage is: the supposed benefit that "51% miners cannot steal from" rollups. Firstly, this comparison is weak, because in DC an actual theft requires 6 months of open, easily-demonstrated misbehavior. So DC theft is enormously impractical -- like robbing Fort Knox in slow motion. Secondly, in the rollup case, if evil miners are determined to steal (from rollups), then they can also spend six months doing something comparable: refuse to allow the L1 zk-snark message into the L1 blockchain. This holds the rollup funds hostage -- miners can refuse to allow rollup-withdrawals, unless desperate users sell their coins to the miners for pennies on the dollar. If miners start this on Jan 1, likely that many users will have given up by July 1. So the main advantage rollups have over DC is not significant.

Fifth, the "advantage" in point four is (yet again) just a misunderstanding of the DC "miners can steal" problem. "Miners can steal" is not a bug, it is a feature (for DC). See [the long presentation on "Sidechain Privatization"](https://www.youtube.com/watch?v=xGu0o8HH10U&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=1), if you want to be one of the very few people who understand why. Not that it matters much in this case, since rollups are also not flexible or general purpose enough to cause too much inter-chain damage.



## 3. Usefulness ## {#usefulness}

### How can we ensure that Great Altcoins are transformed into Sidechains? ### {#conveyor}

If Altcoins are useful, they should have fee-paying users. Therefore, miners should want to claim these fees.


### Why would anyone make a sidechain, when instead they could make a great ICO Scam and/or Altcoin? ### {#vs-alt}

It doesn't matter.

If they make an Altcoin, and the Altcoin is useful, then we will copy that Altcoin into a sidechain (as we have already done for zCash and Ethereum). This is easy to do.

If they don't make the Altcoin; or they do make it and it isn't useful, then we won't copy it.


### People buy Altcoins to make money! Not for their features, Paul! How could you make such a silly mistake? ### {#pump}

Darknet markets have switch from BTC only, to XMR only. Since no one holds the coin (the buyer, the seller, nor the DNM), this cannot be related to the coin's exchange rate. It can only be related to the XMR superior privacy feature.

But sure, if people only want to buy/flip/pump crypto-assets, then they can continue to do that, on the BitAssets sidechain.

Two sociopaths can't pump-and-dump each other. It requires at least one guillible victim. In Alt-land the guillible victim is always told **a story** that involves the coin's distinctive features. With sidechains, we can copy these features. We get the utility, AND we disable the "story". So, sidechains help in either case.



<!--
Four Part Answer:

#### i. Free Rider Problem #### {#free-rider}

First, I acknowledge that ICOs/Premines/Altcoins do help, sometimes, to solve a free-rider problem of R&D of a coin.

However, despite Bitcoin's disadvantage, it still seems to get all of the interesting, serious research. So apparently the lure of prestige is strong enough to motivate a healthy amount of R&D. Many universities regularly support Bitcoin R&D, especially MIT and Stanford.  

Also, for-profit corporations (including Blockstream on the right as well as Coinbase on the left) support project R&D.

Finally, IMHO, most interesting work is done by hobbyists. Einstein, for instance, was a patent clerk when he wrote his four famous papers. Too much "financial support" and we lose the intrinsic motivation and the hunger for success.

Whatever the case may be, a great deal of software is written and evangelized today, without the "motivation" of doing an ICO (Ubuntu, Mozilla Firefox, etc). In fact, to most Makers, token sales are *not* a real incentive, they are instead a distraction and a hindrance.

#### ii. Labor Theory of Value Fallacy #### {#LTOV}

Second, this question [mis-emphasizes the *makers*](https://en.wikipedia.org/wiki/Labor_theory_of_value) of the technology. Instead, it should emphasize *users*. It should ask, "why should users use a sidechain, over an Altcoin/ICO scam?". After all, made-but-unused things are irrelevant (and people will quickly stop making them); and vice-versa (all useful things that can be made eventually will be made).

That second question (the proper one) has some good answers: relative to Altcoins, sidechains can offer better convenience, quality control, and hashrate security. Most importantly, they shield the user from exchange rate risk.

<img src="https://img-9gag-fun.9cache.com/photo/6602736_700b_v1.jpg" width="290" height="465" />

This exchange rate risk is important in two senses. The first [trivial] sense is that the user does not have to deal with fluctuations in Altcoin/Bitcoin prices (which can be quite tremendous). The second [important] sense is that an Altcoin's price may crash to zero.

#### iii. The Death of the Altcoins #### {#alt-death}

A world without Altcoins may sound far-fetched today, but let us ask: "Where are all of these buy orders for Altcoins coming from?". Certainly, there is a mixture of "fundamental" and "greedy" motivations -- the fundamental is to take advantage of the Altcoin's distinct feature set [now or in the future], and the greedy is to later resell the Altcoin to a greater fool (or "more appreciative collector").

It should be clear that, once sidechains allow BTC to copy Alts, the fundamental motivation cannot survive. Even [recreational gambling and money-laundering](http://www.truthcoin.info/blog/altcoins-are-not-coins/) (to the extent that they are happening in Alts now, which [is unclear](http://www.truthcoin.info/blog/bitcoin-post-maximalism/#2-rising-altcoin-utility)) may continue to take place in sidechains designed for these purposes (probably a Counterparty-style "crypto Art" sidechain, and a Zcash sidechain).

I do not see how the greedy motivation can survive either. After all, "greed" alone is insufficient for scams -- there must also be *gullibility*. Specifically, there must be a *pretext* [a narrative that is plausible, but false] of future fundamental value. For example, Ethereum's pretext was "smart contracts"; for DASH it was "privacy" and sometimes "governance"; BitShares was "crypto finance" (or something). But with sidechains up and running, these pretexts cannot survive -- after all, if the "smart contract" feature is a success, it will inevitably be copied. Alts will just be the suckers, who do all of the R&D and get none of the credit.

Sidechains are unable to emulate an Altcoin's *community*. So the pretext-of-value will necessarily shift in this direction. But this is very unlikely to work for two reasons. First, as far as salience/recognizability is concerned, Bitcoin is still the leader -- no one has heard of EOS but *not* heard of Bitcoin. Second, *new* Alt-communities have literally nothing to offer to new users. So these newcomers will look around and join "the biggest" community aka Bitcoin. It is basic network effects.

A final ingredient, which I intend to provide [on a sidechain no less!], is the ability to *short Altcoins* (to [short anything](http://bitcoinhivemind.com/papers/3_PM_Applications.pdf) in fact). This allows money to be made, as the bubble pops. Currently, in contrast, there is no easy way to profit from the overvalued Altcoin market.


#### iv. InterChain Combat #### {#interchain-combat}

Currently, the blockchain projects are [at war](http://junseth.com/post/119882298052/blockchains-are-war). During the XT dispute, DoS attacks were apparently [so severe that they resulted in widespread Internet failure and even power grid failure](https://blog.plan99.net/the-resolution-of-the-bitcoin-experiment-dabb30201f7#7175)! People are...saying mean things to each other on social media, to say the least.

These behaviors are attempts to "persuade" devs/promoters to change their crypto-allegiance. But if you develop on a sidechain, you are probably safe from this bullying/harassment.

Moreover, if there were just one crypto-project, then there would be no need for all of this "persuasion" in the first place. (This is why Maximalism is a moral position. )


### I have heard that it will take 3-6 months to transfer money from the sidechain to the mainchain. Won't that be too slow to be useful? ### {#liquidity}

Yes, [per sidechain] only one withdrawal can succeed every 3 months. Two can be in progress at once, if and only if one is more than halfway finished. Which means that we can expect total withdrawal time to take between 3 months (best case) and 4.5 months (worst case).

Some complain that such a system would be too slow to be usable, but replies of this kind disregard the effect of atomic cross-chain swaps, which are instant.

( Furthermore, while side-to-main transfers are slow, main-to-side transfers are quite fast, x~=10 confirmations. I would go as far as to say that, just as the Lightning Network is enabled by SegWit and CSV, Drivechain is enabled by the atomic swaps and of Counterparty-like 'embedded consensus'. )

Thanks to atomic swaps, someone can act as an investment banker or custodian, and purchase side:BTC at a (tiny, competitive discount) and then transfer those side-to-main at a minimal inconvenience (comparable to that of someone who buys a bank CD). Through market activities, the *entire system* becomes exactly as patient as its most-patient members. As icing on the cake, people who aren't planning on using their BTC anytime soon (ie "the patient") can even get a tiny investment yield, in return for providing this service.

-->

### With respect to a "LargeBlock sidechain" specifically ...

#### ...why should I need to xfer my UTXOs from main-to-side at all? That's inconvenient -- with a hard fork, they just show up there. #### {#vs-hf}

Sidechains are "opt in". So if you want to use the new feature, you must "opt in" to it.

#### ...will the "SmallBlock mainchain" even have enough tx-bandwidth for all of our [LargeBlocker] coins to escape? #### {#trapped-utxos}

A wealthy Bitcoiner could deposit *many coins* into the sidechain in a single transaction.

He can then onboard new users over there, without consuming any marginal L1 bytes.

So sidechains can grow in all the ways that Altcoins can grow.


<!--

### What if a sidechain has too few nodes? Who will run them? Who will maintain this software?

There is an absolutely crucial distinction between:

1. A problem with a sidechain that negatively impacts its parent chain.
2. A problem with a sidechain that only impacts the sidechain users.

The first type of problem is unacceptable, but the second type of problem is actually *desirable*.

If we wanted to have the best BTC currency unit possible, we would want everyone to try all kinds of things out, *especially* the things that we think are terrible. We'd want lots of things to be tried, and for the losers to "fail fast".

In practice I highly doubt the sidechain ecosystem would be anywhere near as dynamic as NYC or Silicon Valley. But these types of question, such as "What if a sidechain breaks / has DAO-like problems?"; "What if the sidechain has only a few nodes? Who will run them?"; "Who will maintain these projects?"; -- really just miss the point. If the sidechain is garbage, that's *their* problem, not yours!

Users who aren't comfortable with the risks of new chains / new features, can simply decline to use them. If the benefits of a sidechain (to Person X) outweigh its risks (to Person X), the Person X will move some BTC there.


### What if a sidechain becomes "Too Big To Fail"?

In other words: "What if a *majority* of BTC is moved to one sidechain, and then that sidechain has some kind of problem?".

One simple solution would be to cap the quantity of BTC that can be moved to each sidechain, (perhaps at x=10% ; aka 210,000).

Other than that, I would point out that Bitcoin has always been the "money of principle", and that we survived the MtGox announcement (in which ~850,000/12,400,000 = 6.85% of the total BTC were assumed to be stolen).


-->


## 4. Abilities and Limitations ## {#abilities}


### Can we have a sidechain that uses Proof of Stake? ### {#pos}

Yes, we could. The concept of the 1st sidechain BIP, hashrate escrows is flexible enough to copy *any* blockchain -- public or private, proof-of-stake, proof-of-space, proof-of-steak, etc. Even weirdo stuff like [Corda](https://www.corda.net/).

However, Drivechain ships with a specialized, customized feature called 'blind merged mining' (BMM), which makes consensus on the sidechain *free*. As in, free in both the economic and engineering sense (see below). If a chain uses BMM, it freely inherits all of Bitcoin's proof of work security. In fact, the sidechain gets all of Bitcoin's security, even if its transaction fees [or its other miner-revenue-sources] fall to zero.

For those reasons, BMM is the recommended consensus algorithm for Bitcoin drivechains.

 ( ...perhaps we should invent some sexy-sounding "proof-of-X" name for BMM, like "Proof of Merge"? And bundle it with ridiculous-sounding (but technically true) claims like "even more efficient than PoS". )


### How is Blind Merged Mining doing achieving consensus for free (above)? ### {#how-bmm}

The original specification is [here](http://www.truthcoin.info/blog/blind-merged-mining/), and the BIP text is [here](https://github.com/bitcoin/bips/blob/master/bip-0301.mediawiki). I would first look at the table in the beginning of the BIP text.

BMM only allows one side:block to be found per main:block. This side:block hash must be inserted into "critical real estate" in the L1 coinbase. L1 miners "auction off" this real estate, to the highest bidder.

[Here is a more detailed explanation.](/media/blind-merged-mining-sequence.txt)


### Can Bitcoin L1 switch to Blind Merged Mining? ### {#root-bmm}

No. The BMM trick requires a "regular" PoW blockchain to exist. It can't work all by itself.

All the money earned by all sidechains will ultimately go to mainchain Bitcoin miners, so, economically, it really is as if miners were actually mining several chains at once. Except, in this case they only need to run a Bitcoin node.


### If Simon keeps a cut, then who would ever use BMM? Why allow Simon to keep a cut, when Mary can run a full node and collect 100% ### {#bmm-econ}

The full node might be expensive to run.

For example, a node costs $20 to run (amortized over 10 minute periods) and fees are $100 (also amortized over 10 minutes), then Simon can BMM and pay $81 to choose the next sidechain block. Mary won't run her own node.

So, Simon's cut actually helps Mary make *even more money* than she would have made otherwise. It isn't a disadvantage at all.

The equilibrium value of the cut is near zero. *Every* sidechain user is already running a side:node. So it is a sunk cost. Paying $81 to earn $100, is always profitable. It doesn't matter that the node cost $20. Paying $82 to win $100, is more profitable than losing the bid (where you pay nothing to earn nothing). So the equilibrium "cut" will always be near-zero.

If the fullnode costs are too *low* to justify BMM...well that simply indicates that there's no problem and no one needs to care. 


### Obviously, in an asymmetric system, a mainchain can have two or more sidechains. But can you do the reverse, and have a sidechain of two different mainchains at once? ### {#two-mainchains}

Yes. But this is a convoluted and terrible idea.

For example, you could have a sidechain of Bitcoin that was also a sidechain of Ethereum. The user would need to run all three full nodes, in order to validate the sidechain. The sidechain might need to be blind merged-mined on only one chain, or perhaps it could alternate chains or have an extremely strange chain-integration rule. The security/stability of the sidechain would probably be equal to that of the most insecure/unstable mainchain.


### Is there anything that drivechains can't copy? ### {#cant-copy}

The underlying consensus of L1 (PoW vs PoS), and the community.

For example, Monero has a larger anonymity set, as of this writing. And Ethereum has more txn fees and users.


### Is the 13,150 ACK parameter hardcoded? Why not let each sidechain specify it? ### {#13150}

Yes.

1. To prevent a "race to the bottom".
2. To promote solidarity among all sidechains, in the event of a theft.




## 5. Other ## {#other}

### What kind of sidechain projects can we expect? ### {#projects}

Please navigate to the [sidechain projects](http://www.drivechain.info/projects/index.html) section.

-----

For more info, watch ["Drivechain - Overview and Misconceptions"](https://www.youtube.com/watch?time_continue=5892&v=gUbGT70wy5k).


<!--

### i. "51% hashrate can steal BTC" ### {#i}

It is said that "51% of the miners can steal all of the funds on the sidechain".

It is true that 51% hashrate can overwhelm the 13,150 ACK requirement (ie, the ["train metaphor"](https://youtu.be/gUbGT70wy5k?t=1h13m55s)), and (if unopposed) include any withdrawal they like. Namely, they would include a withdrawal that pays them all of the sidechain's BTC. At 51% hashrate, this takes 6 months to accomplish; at 100% hashrate, it takes 3 months.

So, it is true that 51% hashrate can steal all the BTC on the sidechain. But, already, they can steal all of the BTC on the mainchain. In a way that full nodes cannot prevent. And the mainchain theft is easier, and pays more.

It is to simply take the assumed attack (ie, "6 months of 51% miner-attacking, or 3 months of 100% attacking"), and use it to cause a block reorganization. Specifically, a 13,150-block reorganization.

The reorg attack is easier in two ways. First, the reorg-attackers may work in secret. In contrast, the DC-attackers must announce the attack in advance, and then continue it openly each block. Secondly, because of their hashrate superiority (of at least 2%, in the 51%-case) they can start their new chain as many as ~526 blocks into the past.

The reorg attack allows miners to steal all BTC transacted on the mainchain, in two ways. First, by making BTC purchases themselves, and then refunding themselves via doublespend. Second, by collaborating with other purchasers (by rewarding them "epsilon" if they sign a doublespend txn directing the merchant's money to miners).

How much BTC could be stolen by a reorg attack?

Well, at [200,000 BTC transacted per day](https://blockchain.info/charts/estimated-transaction-volume?timespan=1year), we can expect turnover over 13,500 blocks to amount to 18.4 million BTC. This value is greater than the current number of Bitcoins in existence [~17 million], and so *all* circulating coins would be stolen (only those which hadn't moved in 6+ months would ever be safe). Interestingly, because [~3.8 million BTC are estimated to be lost forever](http://fortune.com/2017/11/25/lost-bitcoins/), 18.4 M is more BTC than could ever be deposited onto any sidechain ever.

Critics who raise this point, are really objecting to the entire philosophy of "optional sidechains". The purpose of sidechains is to allow the mainchain Bitcoin Core software to ignore BTC-activity on other networks -- this indifference frees up those networks to try experimental or controversial features. Critics who invoke "miners can steal", fail to understand this purpose. Since the only way to block "miner theft" is via full-node rule-enforcement, these critics are really advocating a sidechain security model where Bitcoin Core is required to download and validate all sidechain blocks on all sidechains. This would prevent miner-theft, but it turns each new sidechain into a mandatory hard fork!






### iii. "Infallible Miner" Fallacy ### {#iii}

A related notion is the idea that "miners" are the "owners" or "masters" or "controllers" of the Bitcoin cryptosystem -- and wherever miners lead, everyone else follows blindly and without resistance.

But the truth is the exact *opposite* of this. Whenever "miners" and "nodes" disagree, it is always nodes that get the final word. For example:

* Flag day" UASF activations -- most famously of SegWit in Summer 2017, but also [P2SH in Spring 2012](https://www.uasf.co/#why-bip148-and-not-a-direct-flag-day-uasf-for-segwit).
* The [March 2013 anti-consensus event](https://bitcoin.org/en/alert/2013-03-11-chain-fork) -- during which miners were required to reconfigure their software (at great financial loss)...but nodes were required to do "nothing".
* The Post-Scaling-III civil war, during which 51% hashrate "signaled" for Bitcoin Unlimited. This signaling ultimately had no effect whatsoever. (Once it did [cause an invalid block](https://www.reddit.com/r/Bitcoin/comments/5qwtr2/bitcoincom_loses_132btc_trying_to_fork_the/) to be formed, leading -again- to miner losses but node indifference.)
* In August 2010, miners *did as they were told* and extended [a chain that followed all of the rules](https://en.bitcoin.it/wiki/Value_overflow_incident). The problem was, some nodes later decided that they didn't like these rules, after all. So nodes changed the rules, and found new miners to enforce the new rules. The old miners, enforcing the old rules, did not get paid, and had to surrender.

These are examples of Miners being trumped by users, in a variety of contexts. Drivechain merely acknowledges this pre-existing fact.

This fallacy is similar to the ["Enough to Buy Back the Product"](http://steshaw.org/economics-in-one-lesson/chap21p1.html) and "Labor Theory of Value" fallacies. It demands that "the makers of cheap dresses should get enough to buy back cheap dresses and the makers of mink coats enough to buy back mink coats". Miners are like security guards -- watching diligently over a football game or rock concert to deal with altercations. But "a group of security guards" does not a rock-and-roll concert make...you need the guitarist. And you need the drummer, and the promoters, the record company, the guitar-maker, the producer of nylon string, etc.

[Related](https://twitter.com/Truthcoin/status/929797893413855232) -- a time when hashrate determined nothing.

While the security guards should be *obedient* they should NOT be *incompetent* -- they must be able to carry out the investor's will. That is the subject of the next misconception.

-->