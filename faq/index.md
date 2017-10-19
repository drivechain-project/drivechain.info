---
layout: page
title: Frequently Asked Questions
---

Updated 10/2017

Here is [a great video FAQ I did with Michael Tidwell](https://www.youtube.com/watch?v=XSPhSRlemvA) where we covered many interesting questions. I know many people prefer the YouTube format these days.

## 1. Security ## {#security}

### Are merged-mined sidechains secure? Can miners "steal" from a sidechain? ## {#sidechain-theft}

The [security model](http://www.truthcoin.info/blog/drivechain/#drivechains-security) is comparable to Bitcoin's. Bitcoin protects a given txn by bundling it with all of the other recent txns (such that the miners cannot revert a txn without attacking the entire chain). Drivechain protects only a subset of the total Bitcoin txns, but it compensates for this by bundling these txns over a much longer period of time.

Security is higher when:

* The sidechain in question is popular with users.
* There are many popular sidechains.

A **more important point is this**: the risk-reward decision is one which should be up to each individual user. If you don't like a particular sidechain, or sidechains in general, then you don't have to use them!

But don't try to decide on behalf of other people! If each individual user is free to sell his/her BTC in exchange for an Altcoin (or for fiat), we can hardly deny users the opportunity to move *their money* between two sidechains.


### What negative impact could sidechains have on the mainchain (ie, Bitcoin Core)? ### {#harms}

There are none, actually.

Users are free to ignore any sidechain software they don't like. And, thanks to something called ["blind merged mining"](http://www.truthcoin.info/blog/blind-merged-mining/), even miners are free to ignore sidechain software they don't like (while still being able to mine these sidechains for transaction fees).

This means that the **sidechains are [completely firewalled](http://www.truthcoin.info/blog/wise-contracts/) from each other**. The mainchain cannot be harmed by the mistakes of its child sidechain. Even the [ecological effects](https://www.youtube.com/playlist?list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4) are neutralized.

In fact, because Drivechain is asymmetric (in that the child sidechain is subordinate to the parent mainchain), the mainchains cannot be harmed even by the *success* of their sidechains. Since Bitcoin Core would be the patriarch of this family of sidechains, Core would be the safest chain of them all.


### Why does drivechain allow miners to deny the creation of a given sidechain? Are you against permissionless innovation? Are you a BitMain shill?? ### {#categorial-control}

Unlike other projects, drivechain explicitly aims to allow miners to censor certain types of smart contract. I call this feature **"categorical control"**. Simple-minded people misinterpret this design goal as an affront to permissionless innovation -- "After all", they think, "if miners can censor a type of smart contract, how can it be a permissionless system?".

I have been repeating myself on this topic for years (both in person and [via YouTube lecture](https://www.youtube.com/watch?v=xGu0o8HH10U&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=1)), and [replied on bitcoin-dev about it](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-May/014453.html), and [written about it](http://www.drivechain.info/literature/index.html#theory) on my blog (and in the BIP documentation) on several occasions. It is certainly one of the most frequently-asked-questions, especially among Bitcoin-experts who should know better.

The short answer is that **Bitcoin users might disagree with the <i>intended behavior</i> of the sidechain**. It is assumed that miners must meet the needs of users as best they can (and that, at worst, there can be confusion among miners over what it is that user want). The group "Bitcoin users" can be defined either as [1] the subset of users known as "the economic majority", or as [2] "the entire population of sincere users"; it doesn't matter.

In other words, I am saying that all of the users, taken together, would *all* prefer it to be the case that certain types of smart contracts become impossible. I have provide concrete examples of such cases [here](http://www.truthcoin.info/blog/wise-contracts/#wise-contracts)). And it is not so strange -- any population of humans will *all* prefer that the crime of theft be universally impossible. And, (closer to home) the population of Bitcoin users prefers that it be impossible for miners to create Bitcoin blocks that contain double-spent txns (in which case we would not need nodes, as all necessary validation could be client-side and off-chain).

Therefore, the idea of "allowing miners to censor sidechains by category" is not a rejection of permissionless innovation, even though it may seem that way. The activities in question are *already censored* by the laws of economics. Users will never be able to use a "parasite contract", in practice, because the host will either already be dead or [more likely] will never be built. So, the ability of miners to "censor" these parasites is a moot point. However, with a little 'categorical control' the tables are turned -- the parasites can be deleted as a category, and it is therefore the parasites which we will probably never see. Instead, we will get all the good stuff, and it will all still be permissionless.


In general, I think that the people who have trouble understanding these explanations are falling victim to a [cryptography vs game theory](link-forthcoming) disparity that I have elsewhere described. At our current level of e-cash technology, the "cryptographer nirvana" of 'complete independence from the miners' is unattainable. Instead, users, developers, investors, and miners all interact with each other and are dependent on each other. By understanding this interdependence we can try to solve problems, but by rejecting interdependence we really just *give up* on solving them.

This is why the strongest cryptographers often have no solutions to Bitcoin's largest problems: scaling, outreach, competition from Altcoins / rival systems, dissatisfied collaborators, and too few developers / dev turnover. Instead, these people tinker with obscure mathematical toy problems, which are very complex and impressive...but have less actual significance.

( Incidentally, it is also why I believe that general-purpose smart contracting systems, like Ethereum and Rootstock, are misguided. These "general-purpose" systems actually *can't do as much* as a subset of individually selected smart contracts -- ironically, their [generality limits their usefulness](http://www.truthcoin.info/blog/contracts-oracles-sidechains/). )



## 2. Comparisons 

### How does this proposal compare to the proposal in [the Oct 2014 paper "Enabling Blockchain Innovations with Pegged Sidechains"](https://blockstream.com/sidechains.pdf)? ### {#blockstream}

Well, that paper was chiefly a broad discussion of possible techniques. In Appendix B, "Efficient SPV proofs", there is a concrete suggestion, although it is immediately qualified with the sentence "A detailed analysis of this problem and its possible solutions is out of scope for this document". So, according to the authors, the 2014 paper does not actually advance any particular sidechain proposal for review.

Nonetheless, I will compare drivechain to their suggestion.

First, the sidechain challenge is to create a SPV-proof for side-to-main transfers. In other words, we must define conditions under which main-to-side payments can be re-unlocked on the mainchain.

Their suggestion involves two things: [1] add a second Merkle tree (to both chains) such that each block commits to all earlier blocks, and [2] to actually insert a big chunk of stuff into the bitcoin txn withdrawaing the funds. This "big chunk of stuff" is the txn that was included in the sidechain, along with the sidechain's block header, as well as many of the sidechain's headers. In this way, they literally "SPV prove" the spend. I say "literally" because this idea strongly resembles the way an actual SPV wallet works: it downloads many headers, and checks these headers for valid work, and finally checks the given txn to see if it was included.

They then use some statistical logic to greatly reduce the number of headers needed, in general. This is a very cool trick, but since each header is ~80 bytes (or ~160 if merged mined), and since each must be selected somehow, the proof size ends up "in the tens of kilobytes range". The midpoint of this phrase, 50 KB, is about 100 times the size of the the average Bitcoin txn, which (everything included) is about 0.5 Kb. So their proof requires a txn to be much larger.

What we do in drivechain is actually very similar, although it is simpler and better. We do use each Bitcoin block to commit to many earlier blocks...after a fashion. To do it, we keep a running cumulative total of the 'ACK count' for a txn. In this way, we get a proof that is much smaller, easier to computer, is robust to changes in difficulty, and is more consistent as it is not constantly changing size as a function of stochastic block hashes. Both proposals require a new Merkle tree, and both must contain the txn's inputs and outputs. Instead of block headers (tens of KB), Drivechain requires that the TxID itself be included in a block (32 bytes), and then it requires [an out-of-block message](https://github.com/drivechain-project/docs/blob/master/bip1-hashrate-escrow.md) which [might be as small as zero bytes](https://github.com/drivechain-project/docs/blob/master/bip1-hashrate-escrow.md#m4----ack-withdrawal) per sidechain per block, or, worst case, is 6 bytes per sidechain per block. And, worst case, this message would be required in 100% of blocks for 3 months worth of blocks, for total size of 12096. So even worst-case, drivechain's proof scratches the low-end of the tens of kilobytes range. Best case it may be it 39 bytes.

The security is also vastly superior in drivechain. Both approaches fail, and permit miner-theft if 51% attacked. However, drivechain holds up better under attack than the skiplist. This is mainly due to the drivechain's slow transparent withdrawal process. In drivechain the attempts are delayed substantially before they are ACKed, and the ACKs themselves are slow. So it is impossible to conduct a surprise attack, impossible to harass the community writ large with many withdrawal attempts (ie the "mosquito strategy"), and very easy for users to understand that the attack is happening, long before it actually happens. Also, each attempt is very simple, one question of 'Endorse'/'Reject' -- quite comparable to the [the March 2013 anti-consensus event](https://freedom-to-tinker.com/2015/07/28/analyzing-the-2013-bitcoin-fork-centralized-decision-making-saved-the-day/). Except that the March 2013 event was a sudden surprise, we did not know about it until after it had happened. Skiplist-sidechains would also work in this 'surprising' way, but in drivechain there are no surprises, because we are given many week's worth of clear warning that the anti-consensus event will happen. Finally, a slow transparent process means that it is impossible for miners to attack the chain and claim that they didn't know that they were doing so -- with transparency, everyone knows, observers as well as the miners themselves. So it is a clearer demonstration of malice.



### What is the difference between drivechain and extension blocks? ### {#ext-blocks}

Both approaches attempt to solve the problem of extensibility -- "extending" the capabilities of Bitcoin beyond those which currently exist.

This extensibility problem is a difficult one to solve, because of Bitcoin's unique emphasis on "consensus" -- that all users agree on the state of the blockchain. Since all users must agree, and agreement isn't free, there is also an implicit agreement on a "minimum required effort" or "minimum tolerable workload". Bitcoin plays by certain rules, and if those rules are to be meaningful they must be enforced as-written.

So we have a situation where [1] the rules (including "required effort" rules) must be enforced, but simultaneously one where [2] users might like to experiment with new rules. In short, we want the benefits of a "hard fork" (and of permissionless innovation) without paying the costs (which are a loss of consensus, or non-enforcement of important rules).

The trick is to try and solve both problems at once. A 'hard fork' solves only problem [2], and 'doing nothing' solves only problem [1]. Extension blocks make some progress toward solving problem [2], at the expense of tremendous sacrifice on [1]. This is because users of the non-extended original chain, are subject to a potential barrage of messages. These messages can be sent at any time, by anyone (including an attacker), and could take on any properties (large in size, difficult to process, slow to validate)...most important of all, invalid messages can be sent for free. In this scenario, the cost of maintaining consensus over "Original" is in great danger (according to some) of rising to  "Original" + "Extension", anyway. This means that the extension block is effectively a hard fork, and we have failed to solve challenge [1].

Instead, Drivechain **[condenses](http://www.truthcoin.info/blog/drivechain/#just-right-awareness)** the from-extension-to-original messages into infrequent, easy to validate, unambiguous, chain-scale messages. It essentially flips the consensus threat on its head by arguing that the sidechain should do all of the consensus labor, and it should then present a tiny, minimal easy-to-verify proof of that labor to the mainchain at infrequent intervals. (In the sense of being "difficult to generate but easy to verify", it resembles proof-of-work itself.) This allows us to solve problem [2] without compromising on [1].

This is why Adam Back in particular emphasizes the "slow return" feature of Drivechain, whenever possible (recall that Dr. Back was a major innovator and promoter of extension blocks in early 2014).


### What about [Zmn..'s Sidechain-Headers-on-Mainchain (SHoM)](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-September/014910.html) ? ### {#shom}

Again, to repeat the answer for extension blocks (above), **the distinction between hard and soft forks isn't the point**.

The point is, instead, **the burden placed on existing users**. While an extension block does allow 'oldtype nodes' to ignore the extension data, it does this at a cost of no longer being able to fully-validate the block. It is a 'backdoor hardfork', of a kind, because users need to upgrade.

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



## 3. Usefulness ## {#usefulness}

### I have heard that it will take 3-6 months to transfer money from the sidechain to the mainchain. Won't that be too slow to be useful?

Firstly, these are customizable parameters, and open for debate -- but if withdrawals are every x=3 months, and only x=1 withdrawal can make forward progress (on the mainchain) at a time, and only x=1 prospective withdrawal can be assembled (by the sidechain) at a time, then indeed we can expect total withdrawal time to average 4.5 months [(.5)*3+3].

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


### How can we ensure that Great Altcoins are transformed into Sidechains? ### {#conveyor}

It actually shouldn't be difficult at all! If Altcoins are useful, they should have fee-paying users. Therefore, miners should want to claim these fees by making the Altcoin a blind-merged-mined drivechain.

Bitcoin Miners are actually the cheif *victims* of Altcoin-value-dilution -- other miners are getting money that *they* could have for free, if the Altcoins were instead merged-mined sidechains.

I think the issue is confusing, because most of the Altcoins we see today are *not* useful and therefore we would *not* want to absorb them into Bitcoin. And therefore, it is hard for Bitcoiners of today to imagine that absorbtion happening.

But really, if you think about it, if a given Altcoin persists as an Altcoin [and is not made into a sidechain], then that very fact is *evidence* that the Altcoin in question probably isn't useful to anyone. Or else, it is because it has features that *can't* be copied by *any* sidechain (see Monero answer), in which case this question is moot.



## 4. Abilities and Limitations ## {#abilities}


### Can we have a sidechain that uses Proof of Stake? ### {#pos}

Yes, we could. The concept of the 1st sidechain BIP, hashrate escrows is flexible enough to copy *any* blockchain -- public or private, proof-of-stake, proof-of-space, proof-of-steak, etc. Even wierdo stuff like Corda.

However, Drivechain ships with a specialized, customized feature called 'blind merged mining' (BMM), which makes consensus on the sidechain *free*. As in, free in both the economic and engineering sense (see below). If a chain uses BMM, it freely inherits all of Bitcoin's proof of work security. In fact, the sidechain gets all of Bitcoin's security, even if transaction fees [or other miner-revenue-sources] fall to zero.

For those reasons, BMM is the recommended consensus algorithm for Bitcoin drivechains.

...perhaps we should invent some sexy-sounding "proof-of-X" name for BMM, like "Proof of Merge"? And bundle it with ridiculous-sounding (but technically true) claims like "even more efficient than PoS".


### How is Blind Merged Mining doing all of that stuff (above) for free? ### {#how-bmm}

First, notice that the mere existence of an SPV-proof implies that all sidechain money is already at SPV-level security. This is true of any output locked to any SPV-proof (whether Drivechain or Blockstream's skiplist or anything else). Further, notice that, at SPV-level security, the metric "heaviest valid chain" is assumed to be equal to the metric of "heaviest chain".

Therefore, it follows that our task is merely to recreate the concept of being 'heaviest'.

Secondly, notice that, at any given point in time, there will be one global "hashing cost" (X $/hash). If this cost is priced in BTC itself ("BTC per hash"), then the 'heaviest chain rule' simply becomes a 'most-BTC-spent hashing-this-chain rule'. The two are the same thing, merely expressed in different units.

Thus, we see that our task in the first part (to recreate 'heaviest [chain]'), is equivalent to the task of 'assessing who has spent the most BTC [on hashing a chain]'. In this way, BMM transforms regular BTC transactions into full-strength proof-of-work. 

This trick requires a "regular" PoW blockchain to already exist -- it can't work all by itself. (Ie, Bitcoin Core can't "switch" to it.) All the money earned by all sidechains will ultimately go to mainchain Bitcoin miners, so, economically, it really is as if miners were actually mining several chains at once. Except, in this case they only need to run a Bitcoin node.


### Obviously, in an asymmetric system, a mainchain can have two or more sidechains. But can you do the reverse, and have a sidechain of two different mainchains at once? ### {#two-mainchains}

Yes. For example, you could have a sidechain of Bitcoin that was also a sidechain of Ethereum. The user would need to run all three full nodes, in order to validate the sidechain. The sidechain might need to be blind merged-mined on only one chain, or perhaps it could alternate chains or have an extremely strange chain-integration rule. The security/stability of the sidechain would probably be equal to that of the most insecure/unstable mainchain.

I'm really not sure why you would want to do this, however.

### Is there anything that drivechains can't copy? ### {#cant-copy}

Well, the only thing that comes to mind is the fact that Monero has a larger anonymity set. You see, users will probably want to move quickly from one drivechain to the next, and they will probably also want to settle to the mainchain whenever possible. So, fewer people will be leaving their money on a Monero-sidechain.

On the other hand, the quantity "number of transactions per day" should be the same, whether it is on a Monero sidechain or on regular Monero. So perhaps it actually is the same anonymity set.

Some people say that txns on a hypothetical Monero side would be de-anonymized with they move side-to-main (in other words, when users pull their money from the Monero sidechain back to the regular Bitcoin chain). I'm not sure that this is the case. However, by leaving the Monero cryptosystem, these txns *are* shirking their responsibility to "add to the Monero anonymity set" -- side-to-main xfers are not sidechain txns, they are mainchain txns. In this way, selling Monero for BTC contributes to Monero's anonymity, but moving from side-to-main (or main-to-side) does not.



## 5. Implementation ## {#implementation}


### When will be able to use Drivechain? What's your strategy for getting it into Bitcoin and activated? ### {#when-drivechain}

I confidently estimate <del>July 1st or earlier, but this will depend on feedback from users</del>. The delay is not actually due to the planning fallacy (as would otherwise be the case). Instead it is because the project scope expanded to include Blind Merged Mining, which is itself a significant project. However, based on the feedback received as of June, it seems that Drivechain could be active in a January 2018 release of Bitcoin.

While technically, the Bitcoin network can upgrade via soft-fork at any time, traditionally we have always used a friendly ("patient"), process of accruing a 95% activation threshold. Which leaves the vote entirely up to the miners.

I expect Drivechain to be popular with miners. Sidechains mean more transaction fees for miners. They also mean a much cooler Bitcoin, which should mean a higher BTC price. Finally, Drivechain enables [larger blocks through a heavier sidechain](https://youtu.be/Gzg_u9gHc5Q?t=1h49m27s). Therefore, one might expect miners to activate the soft fork quickly. Optimistically, **Drivechain could be available 2-4 weeks after miners decide to support it**.

If miners refuse to activate the soft fork, it is still possible for users to activate it, and force it upon the miners (just as today's users force miners to enforce all activated soft forks -- activation of past soft forks is no longer optional for miners). This is riskier, but still very safe if user-support is overwhelming. If user-support is merely lukewarm (or unmeasureable), then we might turn to the exchanges for help.

The "blind merged mining" technology <del>has not been developed</del> is under development. It will <del>take an unknown amount of time to code and review probably be finished by the end of the summer</del> has recently been finished.


### What's the rush? Aren't you worried about bugs? ### {#rushing}

I am worried about bugs! However, **Drivechain's bugs can (probably) be found and fixed "in the wild"**. Bitcoin's design (particularly, the soft fork model), prevents any bugs in this software from affecting version that don't have Drivechain. This limits the potential damage tremendously (if not completely).

Secondly, software developers are often overworked, and can't prioritize their scarce review-time. Therefore, sadly, the projects that get the most attention are often those that "charge the mound", so to speak.


### Does Drivechain require SegWit? ### {#need-segwit}

No.

They are similar -- SegWit requires miners to support a new block structure, and to enforce [new rules for a new address types (P2WPKH, P2WSH)](https://github.com/bitcoin/bips/blob/master/bip-0142.mediawiki). Sidechains also require miners to support a new block structure (one which contains a "withdrawal-vote-database" of minimial size"), and to enforce new rules for a new address type. But the two are requirements are entirely independent of each other. **You could have one, the other, both, or none.**

However, the two have tremendous synergy. Lightning Network allows instant/fully-reliable transactions *across sidechains*, which is very cool for both Sidechains and LN.


## 6. Other ## {#other}


### What kind of sidechain projects can we expect? ### {#projects}

Please navigate to the [sidechain projects](http://www.drivechain.info/projects/index.html) section.


### Can sidechains really help with Scaling? ### {#scaling}

I believe that sidechains can solve the *scaling contention*, precisely **because** sidechains do *not* solve scaling itself.

Let me explain.

We might define "resources needed" as X, and "production output" as Y. Then, everyone would want r = Y/X to always be as high as possible.

In Bitcoin's case, the "resources needed" are the node costs -- the infamous **blocksize**. The "production output" is the network's ability -- the **transactions per second**.

If we define "scalability" as r (ie "transactions per second" / "blocksize"), then there is no controversy about r. Everyone wants to r to be as high as possible. Everyone wants the most scalability.

However, my belief is that the "contention" (ie, the "reason everyone is upset") is about *choosing the right X*. No matter the r, some people feel that X is too small (and others feel that X is too large). (This may explain why debates over scalability still persist, despite the surprising discovery of the Lightning Network, which multiplies r by a large factor.)

Sidechains are different, in that they allow people to "choose their own X". This does not (directly) impact r, but it should eliminate most of the controversy.

(Interestingly, sidechains may also indirectly impact r, by allowing for [synergy between two chains](https://www.youtube.com/watch?v=Gzg_u9gHc5Q&t=6575s), or by exploiting [a] UTXO commitments, [b] the SC security model, and [c] the mainchain's management of the 21 M limit, to allow sidechains to simply discard old blocks.)
