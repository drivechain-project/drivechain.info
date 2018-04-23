---
layout: page
title: Frequently Asked Questions
---

Updated 04/2018

Be sure to watch ["Drivechain - Overview and Misconceptions"](https://www.youtube.com/watch?time_continue=5892&v=gUbGT70wy5k), my latest YouTube video. I know many people prefer the YouTube format these days.

## 0. Four Common Misconceptions

Here I highlight four big hangups that people seem to have over and over.

### i. "51% hashrate can steal BTC" ### {#i}

It is said that "51% of the miners can steal all of the funds on the sidechain".

It is true that 51% hashrate can overwhelm the 13,150 ACK requirement (ie, the ["train metaphor"](https://youtu.be/gUbGT70wy5k?t=1h13m55s)), and (if unopposed) include any withdrawal they like (namely, one that pays them all of the sidechain's BTC). At 51% hashrate, this takes 6 months to accomplish; at 100% hashrate, it takes 3 months.

To compare apples to apples, this [6 months of 51% miner-attacking, or 3 months of 100% attacking] is equivalent to a 13,150-block reorganization.

 ( The reorg attack is much easier, in the 51% case, because the reorg-attackers may work in secret. In DC, they must announce the attack in advance, and then continue it openly each block. Secondly, because of their hashrate superiority of 2%, they can start their new chain as many as ~526 blocks into the past. )

During the reorganization, the attacking miners can steal all BTC transacted on the mainchain -- either by making BTC purchases themselves (and refunding themselves via doublespend), or by collaborating with other purchasers (by rewarding them "epsilon" if they sign a doublespend txn directing the merchant's money to miners).

How much BTC would this be?

Well, at [200,000 BTC transacted per day](https://blockchain.info/charts/estimated-transaction-volume?timespan=1year), this would be ~1400 BTC transacted per block. Over 13,500 blocks, the stolen BTC would total 18.4 million BTC. This value is greater than the current number of Bitcoins in existence [~17 million], and so *all* circulating coins would be stolen. And because [~3.8 million BTC are estimated to be lost forever](http://fortune.com/2017/11/25/lost-bitcoins/), it is more BTC than could ever be deposited onto any sidechain ever.

So, it is true that 51% hashrate can steal all the BTC on the sidechain. But they can also steal all of the BTC on the mainchain. And the mainchain theft is easier and pays more.

Of course, this leads us to the next two fallacies...

### ii. Autonomous Miners Fallacy ### {#ii}

Some people believe that miners are free to do whatever they like. This view is often simplified [perhaps for politeness reasons] as sorting miners into two "types", the "honest" type that tend to choose to do friendly things, and the "dishonest" type that tend to choose to do unfriendly things (ie, short-term, narrowly selfish, deceptive, etc).

In reality, though, miners have no choice but to profit-maximize.

Here are some passages which explain this well: 

* ["if so many miners stick to their guns that the ROI on the old currency continues to be high, then all the obstinate miners will have accomplished is in making a gift to the more practical ones."](https://medium.com/@bramcohen/bitcoin-s-ironic-crisis-32226a85e39f) -- Bram Cohen, June 2015
* ["if a miner would rather hold B2X, they could earn it four times faster by mining B1X and trading it for B2X"](https://medium.com/@danrobinson/the-cost-of-supporting-the-b2x-fork-how-to-lose-100m-in-ten-days-6797f7ef52da) -- Dan Robinson, Nov 2017

Two days after Dan Robinson's post, [miners cancelled their SegWit2x project](https://news.bitcoin.com/breaking-news-segwit2x-fork-cancelled/), which they --seemingly-- wanted very badly. But not as badly as they wanted more MONEY!

Please see [the published security model](http://www.truthcoin.info/blog/drivechain/#drivechains-security) and also panes 5 and 6 of [this meme](http://www.drivechain.info/media/meme3.png) for details on what miners would find to be more or less profitable.

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

### iv. Ethereum Immunodeficiency Syndrome ### {#iv}

Some "smart contracts" are actually bad, and we *want* to get rid of them.

This is near-impossible to do, if the smart contract system is too general purpose (as in Ethereum). See my ["Smart Contract Ecology" presentation](https://www.youtube.com/watch?v=xGu0o8HH10U&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=1) (or [answer below](www.drivechain.info/faq/#categorical-control) for details.

However, it is also impossible to do, if no one has an incentive to do it. Without an incentive to curate the portfolio of active sidechains, we will have a free rider problem -- who will take out the trash? 

We solve this by harmonizing ownership and control -- the miners are the only ones with enough skin in the game to make this decision, so they should be the ones who control which sidechains are "evicted". So the 51% theft possibility is actually a *feature*, not a bug. We want it there, filtering out sidechains that interact badly (just like we want miners to "evict" txns that are double spends).

### v. User Paternalism Fallacy ### {#v}

Some sidechains are bound to be "low quality", for whatever reason. Perhaps because they are not popular enough to be secure, or perhaps they have been constructed by saboteurs. Depositing into these would be a bad idea.

It is natural to want to "protect" people from their mistakes.

But it is neither possible nor desirable. If the user can't get what they want from a sidechain, they'll get it from an Altcoin. And -- as they should! The user is sovereign.



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


### Does Drivechain rely on a UASF to prevent a sidechain theft? ### {#uasf-reliance}

The phrase "rely on" is ambiguous in this case, but I believe the answer is "no". I will give the answer in three sections.

##### (i) A Background Point

In the real world, most contracts do not "rely" on a court to be enforced. The two [parties](https://en.wikipedia.org/wiki/Party_%28law%29) will work together to enforce the contract on each other, and it will only "go to court" as a last resort. So, at first glance the court is superfluous.

On the other hand, we would wonder how the *absence* of a judicial system might affect people's willingness to fulfill their contractual obligations. Perhaps, without the threat of legal action, no one would fulfill their contractual obligations. Or perhaps, something else, such as private credit reporting agencies (Experian / TransUnion in the USA) would take on a greater role in society, and the threat of "bad credit" would be intimidating enough to persuade individuals to [fulfill](https://www.ag.ndsu.edu/aglawandmanagement/appliedaglaw/coursematerials/fulfillcontract) their contracts.

If a "court" is a way of preventing sidechain-theft, then Drivechain has two of them. The UASF would be the second (like a "Supreme Court"). The first would be [the security model](http://www.truthcoin.info/blog/drivechain/#drivechains-security), specifically: the observation that a sidechain-enabled network is likely to be more valuable to miners than a non-sidechain network -- sidechain-enabled tokens are worth more (ie have a higher exchange rate and can purchase more electrical power) and they provide miners with additional fee revenues.

All withdrawals take effort, including thefts. So the possibility that the second court [the UASF] might 'strike down' an [otherwise imminent] theft, is likely to deter theft in the first place. In that sense, having the UASF around is a strict improvement.

##### (ii) "Preventing" Theft

If miners do attack a sidechain, then the best recourse the victims have is to use a UASF to split the chain, and then [1] hope that exchanges support [what will be, by definition] a minority hashrate chain (ie a "new" chain) [newer, decentralized, atomic-swap-based exchanges should make this much easier]; and then [2] hope that the free market decides that the UASF-coins are more valuable than the non-UASF-coins. If those two conditions are met, miners will be forced to extend the UASF-chain (ie the non-theft chain), and it will become the longest chain (re-fusing them into one chain). Thus, the UASF "prevents" the sidechain-theft.

##### (iii) "Guaranteeing" Theft (!)

However, the UASF technique is so general that it could also, in principle, *guarantee* the sidechain-theft. Or it could guarantee that all sidechain-withdrawals always fail (whether theft or honest), or else that all honest withdrawals always succeed as quickly as possible, or else that all thefts always succeed on precisely the 22,222nd block after they are attempted (or any other number between 13,150 and 26,300). So it is not meaningful to imbue the UASF with an "anti-theft" feature. Instead, the UASF is simply a vehicle through which users clarify, VERY loudly, exactly what it is they want to buy from miners when they hand over 140,000 USD (at 2/18/2018 prices) in exchange for the newest 13.5 BTC (assuming 1 BTC of tx fees).

"The UASF" is just a stand-in for "the free market". After all, [some sidechains are bad, and we *want* miners/investors to get rid of them for us](http://www.truthcoin.info/blog/wise-contracts/). So who's to say that a given theft is even a bad thing? And who is to say that it even is theft in the first place (this could only be justified by appealing to the sidechain node, which is exactly what sidechains are uninterested in doing).

### Isn't that [UASF reliance] solution [socially unscalable](https://twitter.com/theinstagibbs/status/965315428686934016)? ### {#social-scalability}

Despite the previous answer, where I say that drivechain does NOT rely on a UASF, I will answer this question. I believe the answer to this one is also a no, because UASFs can in fact be made to be [socially scalable](http://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html).

First, let us imagine that mining conditions have reached a point of extreme hostility, such that each withdrawal *must* be manually escorted across the finish line by a new UASF. (In this way, the withdrawals would "rely on" UASFs.)

Is this technique "socially scalable"?

Greg Sanders [suggests on Twitter](https://twitter.com/theinstagibbs/status/965315428686934016) that the answer is "no". Surely, if this technique worked at scale, mining itself would be unnecessary. Bitcoin would just let the blockchain grow arbitrarily, and leave "the free market" to sort it all out somehow (presumably, with thousands of UASFs per day).

But I think that the answer is actually "yes".

The key difference lies in the user's *alternatives*. If were trying to create a blockchain from scratch ("Proof-of-UASF-Coin"), then your users have no alternatives, and are held hostage to PoUSAF-Coin's success. In this sense I agree with Greg Sanders that the UASF is a non-solution.

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


### Why does drivechain allow miners to deny the creation of a given sidechain? Are you against permissionless innovation? Are you a BitMain shill?? ### {#categorical-control}

Unlike other projects, drivechain explicitly aims to allow miners to censor certain types of smart contract. I call this feature **"categorical control"**. Simple-minded people misinterpret this design goal as an affront to permissionless innovation -- "After all", they think, "if miners can censor a type of smart contract, how can it be a permissionless system?".

I have been repeating myself on this topic for years (both in person and [via YouTube lecture](https://www.youtube.com/watch?v=xGu0o8HH10U&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=1)), and [replied on bitcoin-dev about it](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-May/014453.html), and [written about it](http://www.drivechain.info/literature/index.html#theory) on my blog (and in the BIP documentation) on several occasions. It is certainly one of the most frequently-asked-questions, especially among Bitcoin-experts who should know better.

The short answer is that **Bitcoin users might disagree with the <i>intended behavior</i> of the sidechain**. It is assumed that miners must meet the needs of users as best they can (and that, at worst, there can be confusion among miners over what it is that user want). The group "Bitcoin users" can be defined either as [1] the subset of users known as "the economic majority", or as [2] "the entire population of sincere users"; it doesn't matter.

In other words, I am saying that all of the users, taken together, would *all* prefer it to be the case that certain types of smart contracts become impossible. I have provide concrete examples of such cases [here](http://www.truthcoin.info/blog/wise-contracts/#wise-contracts)). And it is not so strange -- any population of humans will *all* prefer that the crime of theft be universally impossible. And, (closer to home) the population of Bitcoin users prefers that it be impossible for miners to create Bitcoin blocks that contain double-spent txns (in which case we would not need nodes, as all necessary validation could be client-side and off-chain).

Therefore, the idea of "allowing miners to censor sidechains by category" is not a rejection of permissionless innovation, even though it may seem that way. The activities in question are *already censored* by the laws of economics. Users will never be able to use a "parasite contract", in practice, because the host will either already be dead or [more likely] will never be built. So, the ability of miners to "censor" these parasites is a moot point. However, with a little 'categorical control' the tables are turned -- the parasites can be deleted as a category, and it is therefore the parasites which we will probably never see. Instead, we will get all the good stuff, and it will all still be permissionless.


In general, I think that the people who have trouble understanding these explanations are falling victim to a [cryptography vs game theory](link-forthcoming) disparity that I have elsewhere described. At our current level of e-cash technology, the "cryptographer nirvana" of 'complete independence from the miners' is unattainable. Instead, users, developers, investors, and miners all interact with each other and are dependent on each other. By understanding this interdependence we can try to solve problems, but by rejecting interdependence we really just *give up* on solving them.

This is why the strongest cryptographers often have no solutions to Bitcoin's largest problems: scaling, outreach, competition from Altcoins / rival systems, dissatisfied collaborators, and too few developers / dev turnover. Instead, these people tinker with obscure mathematical toy problems, which are very complex and impressive...but have less actual significance.

( Incidentally, it is also why I believe that general-purpose smart contracting systems, like Ethereum and Rootstock, are misguided. These "general-purpose" systems actually *can't do as much* as a subset of individually selected smart contracts -- ironically, their [generality limits their usefulness](http://www.truthcoin.info/blog/contracts-oracles-sidechains/). )


### In the security model you mention ["sounding the alarm"](http://www.truthcoin.info/blog/drivechain/#security-models), where users and miners warn other users and miners. Isn't this centralization / collusion? ### {#sound-the-alarm}

One reddit user [writes](https://www.reddit.com/r/Bitcoin/comments/6ztp3b/lets_discuss_something_techrelated_for_a_change/dn0rsdo/?utm_content=permalink&utm_medium=front&utm_source=reddit&utm_name=Bitcoin): "Drivechains have 1008-block cycles ostensibly to protect against theft, so that someone can 'raise the alarm' and tell miners to downvote a particular theft withdrawal, but that sounds too much like centralized collusion to me."

In this case, the word 'collusion' is misused. In one sense, the word is neutral, meaning "working together". One could say that there is already a lot of Bitcoin collusion today, because all Bitcoin users and miners are coordinating in order to run mutually-compatible versions of Bitcoin. Everyone *is* colluding, but everyone wants to get the right answer. So in this case collusion is a good/neutral thing.

In the second more negative sense, 'collusion' implies some secrecy and nefariousness (to gain an edge on a different group, one made up of earnest and independent people). But that sense does not apply here. Sounding the alarm is 100% transparent. In fact, it is an alarm! Very loud!

And this "collusion" [of sounding the alarm] is only possible if the bad guys have themselves just "colluded". The baddies have to collude first (over which WT^ to upvote). In response, the defenders have to do exactly as much colluding work. But it is easier for the defenders because they can move second -- the do not need to lift a finger until after the attackers have invested the effort of attacking.

While this is collaboration, it is not centralization. Drivechain is designed so that everyone can **independently** respond to the alarm by doing the right thing. They do not need to coordinate with a leader, or a large miner or other users, or anything else. They simply know what to do, because, by design, it is very easy for them to learn what to do. In this case the design is much better than, [the March 2013 consensus failure emergency](http://www.truthcoin.info/blog/against-the-hard-fork/#3-coordination-and-ambiguity). A drivechain theft would be exactly like that event (in which everything worked out just fine), except that it would be much *better*, because **everyone** would [1] have plenty of warning, and time to respond (two months or so), and [2] would already know what to do (either downvote everything, or manually upvote the winner, both will work).



## 2. Comparisons 

### How does this proposal compare to the proposal in [the Oct 2014 paper "Enabling Blockchain Innovations with Pegged Sidechains"](https://blockstream.com/sidechains.pdf)? ### {#blockstream}

Well, that paper was chiefly a broad discussion of possible techniques. In Appendix B, "Efficient SPV proofs", there is a concrete suggestion, although it is immediately qualified with the sentence "A detailed analysis of this problem and its possible solutions is out of scope for this document". So, according to the authors, the 2014 paper does not actually advance any particular sidechain proposal for review.

Nonetheless, I will compare drivechain to their suggestion.

First, the sidechain challenge is to create a SPV-proof for side-to-main transfers. In other words, we must define conditions under which main-to-side payments can be re-unlocked on the mainchain.

Their suggestion involves two things: [1] add a second Merkle tree (to both chains) such that each block commits to all earlier blocks, and [2] to actually insert a big chunk of stuff into the bitcoin txn withdrawing the funds. This "big chunk of stuff" is the txn that was included in the sidechain, along with the sidechain's block header, as well as many of the sidechain's headers. In this way, they literally "SPV prove" the spend. I say "literally" because this idea strongly resembles the way an actual SPV wallet works: it downloads many headers, and checks these headers for valid work, and finally checks the given txn to see if it was included.

They then use some statistical logic to greatly reduce the number of headers needed, in general. This is a very cool trick, but since each header is ~80 bytes (or ~160 if merged mined), and since each must be selected somehow, the proof size ends up "in the tens of kilobytes range". The midpoint of this phrase, 50 KB, is about 100 times the size of the the average Bitcoin txn, which (everything included) is about 0.5 Kb. So their proof requires a txn to be much larger.

What we do in drivechain is actually very similar, although it is simpler and better. We do use each Bitcoin block to commit to many earlier blocks...after a fashion. To do it, we keep a running cumulative total of the 'ACK count' for a txn. In this way, we get a proof that is much smaller, easier to compute, is robust to changes in difficulty, and is more consistent as it is not constantly changing size as a function of stochastic block hashes. Both proposals require a new Merkle tree, and both must contain the txn's inputs and outputs. Instead of block headers (tens of KB), Drivechain requires that the TxID itself be included in a block (32 bytes), and then it requires [an out-of-block message which might be as small as zero bytes](https://github.com/drivechain-project/docs/blob/master/bip1-hashrate-escrow.md#m4----ack-withdrawal) per sidechain per block, or, worst case, is 6 bytes per sidechain per block. And, worst case, this message would be required in 100% of blocks for 3 months worth of blocks, for total size of 78840 (to prove 13140 blocks). So even in a highly unrealistic worst-case scenario, drivechain's proof totals 78879 bytes which is also in the tens of kilobytes range. Best case it may total 39 bytes. And the outcome is not random -- the worst case is only possible when miners run amok for *no* benefit at a cost to themselves. So it is reasonable to expect the very best case.

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



## 3. Usefulness ## {#usefulness}

### I have heard that it will take 3-6 months to transfer money from the sidechain to the mainchain. Won't that be too slow to be useful?

Yes, [per sidechain] only one withdrawal can succeed every 3 months. Two can be in progress at once, if and only if one is more than halfway finished. Which means that we can expect total withdrawal time to take between 3 months (best case) and 4.5 months (worst case).

Some complain that such a system would be too slow to be usable, but replies of this kind disregard the effect of atomic cross-chain swaps, which are instant.

( Furthermore, while side-to-main transfers are slow, main-to-side transfers are quite fast, x~=10 confirmations. I would go as far as to say that, just as the Lightning Network is enabled by SegWit and CSV, Drivechain is enabled by the atomic swaps and of Counterparty-like 'embedded consensus'. )

Thanks to atomic swaps, someone can act as an investment banker or custodian, and purchase side:BTC at a (tiny, competitive discount) and then transfer those side-to-main at a minimal inconvenience (comparable to that of someone who buys a bank CD). Through market activities, the *entire system* becomes exactly as patient as its most-patient members. As icing on the cake, people who aren't planning on using their BTC anytime soon (ie "the patient") can even get a tiny investment yield, in return for providing this service.

### With respect to a "LargeBlock sidechain" specifically ...

#### ...why should I need to xfer my UTXOs from main-to-side at all? That's inconvenient -- with a hard fork, they just show up there. #### {#vs-hf}

Sidechains are "opt in". So if you want to use the new feature, you must "opt in" to it.

#### ...will the "SmallBlock mainchain" even have enough tx-bandwidth for all of our [LargeBlocker] coins to escape? #### {#trapped-utxos} 

Well -- eventually, each UTXO on the mainchain must be spent, if it is to have any effect at all on anything. So, if there is not enough bandwidth, then your mainchain UTXOs are lost in any case, and you have no choice but to hope for a hardfork blocksize increase.

However, the sidechain does not *need* to source its growth from main-to-side txns.

Two questions ago, I mentioned that an 'investment banker' type person could "specialize in patience". They would hold sidechain coins and walk them side-to-main.

The same principle applies main-to-side. A very wealthy individual "Wally" could use a few main-to-side transfers to xfer a high *quantity of coins*. Wally could then charge a tiny premium on selling these coins in any manner -- for example: via mainchain atomic swaps, in exchange for mainchain lightning-payments, in exchange for real-life goods and services.

So sidechains can grow in all the ways that Altcoins can grow.


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

Bitcoin Miners are actually the chief *victims* of Altcoin-value-dilution -- other miners are getting money that *they* could have for free, if the Altcoins were instead merged-mined sidechains.

I think the issue is confusing, because most of the Altcoins we see today are *not* useful and therefore we would *not* want to absorb them into Bitcoin. And therefore, it is hard for Bitcoiners of today to imagine that absorption happening.

But really, if you think about it, if a given Altcoin persists as an Altcoin [and is not made into a sidechain], then that very fact is *evidence* that the Altcoin in question probably isn't useful to anyone. Or else, it is because it has features that *can't* be copied by *any* sidechain (see Monero answer), in which case this question is moot.



## 4. Abilities and Limitations ## {#abilities}


### Can we have a sidechain that uses Proof of Stake? ### {#pos}

Yes, we could. The concept of the 1st sidechain BIP, hashrate escrows is flexible enough to copy *any* blockchain -- public or private, proof-of-stake, proof-of-space, proof-of-steak, etc. Even weirdo stuff like [Corda](https://www.corda.net/).

However, Drivechain ships with a specialized, customized feature called 'blind merged mining' (BMM), which makes consensus on the sidechain *free*. As in, free in both the economic and engineering sense (see below). If a chain uses BMM, it freely inherits all of Bitcoin's proof of work security. In fact, the sidechain gets all of Bitcoin's security, even if its transaction fees [or its other miner-revenue-sources] fall to zero.

For those reasons, BMM is the recommended consensus algorithm for Bitcoin drivechains.

 ( ...perhaps we should invent some sexy-sounding "proof-of-X" name for BMM, like "Proof of Merge"? And bundle it with ridiculous-sounding (but technically true) claims like "even more efficient than PoS". )


### How is Blind Merged Mining doing achieving consensus for free (above)? ### {#how-bmm}

The original specification for this is [here](http://www.truthcoin.info/blog/blind-merged-mining/), but I will try again.

In general, BMM is a kind of ["embedded consensus"](https://counterparty.io/docs/faq/), as though each sidechain blockheader were a Counterparty txn. BMM only allows one side:block to be found per main:block. This side:block is controlled by a kind of "critical coinbase tx real estate", which the mainchain miners auction off to the highest bidder. We thus know that each sidechain block "wasted" the "most" resources. And since the blocks are forced to refer to their parents, we can determined the "most waste" chain. It is waste of BTC instead of PoW-hashing, however.

[Here is a more detailed explanation.](/media/blind-merged-mining-sequence.txt)

Since it relies on embedded consensus, this trick requires a "regular" PoW blockchain to already exist -- it can't work all by itself. (Ie, Bitcoin Core can't "switch" to it.) All the money earned by all sidechains will ultimately go to mainchain Bitcoin miners, so, economically, it really is as if miners were actually mining several chains at once. Except, in this case they only need to run a Bitcoin node.


### A crazy person on Twitter is saying that miners don't get all of the txn-fee revenues under BMM. So BMM is at a disadvantage and miners will not want to use it? ### {#bmm-econ}

It is true that sidechain nodes (called "Simons") do get to keep a portion of the sidechain's tx fees. Therefore, not all of it will go to the mainchain miners (called "Marys"). However, the Simons compete on making this portion as low as possible, and the technical details allow it to go quite low, even (theoretically) to the Satoshi or sub-satoshi level. In contrast, a Bitcoin full node today may cost $20 or $50 per month in bandwidth alone. And the complaints regarding "miner centralization" all concern bandwidth-hog sidechains where the cost may be 10 or even 1000 times higher. For a super-intensive "ESPN 4K Sidechain" of some kind, miners have the option of killing their full node, and using BMM instead. Instead of paying thousands per month on the sidechain node, they (or their pool admin) can simply surrender a $0.10 gratuity per block (which comes to $432 per month). Or, as I say above, the gratuity may fall even further than that, as little prevents it from taking on the smallest possible value.

If the fullnode costs are too *low* to justify BMM...well that simply indicates that there's no problem and no one needs to care. 

[Here is a more detailed explanation.](/media/blind-merged-mining-econ/)



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

They are similar -- SegWit requires miners to support a new block structure, and to enforce [new rules for a new address types (P2WPKH, P2WSH)](https://github.com/bitcoin/bips/blob/master/bip-0142.mediawiki). Sidechains also require miners to support a new block structure (one which contains a "withdrawal-vote-database" of minimal size"), and to enforce new rules for a new address type. But the two are requirements are entirely independent of each other. **You could have one, the other, both, or none.**

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
