
## Peer Review (and Drivechain Controversies)


Visit the [old peer review page](http://www.drivechain.info/peer-review/index.html).

## What are the major remaining critiques of Drivechain?

Most critiques have been asked-and-answered. And the overwhelming majority of people are excited about the potential. But two major critiques persist.

They boil down to the following:

1. "miners can steal sidechain funds"
2. "merged minded sidechains increase pool overhead, making txn-censorship easier"

It is somewhat distressing that these critiques remain, because both of them are completely false. Each is a complex blend of false premises, self-contradiction, ignoratio elenchi, and even outright deception. For each, there is so much to say, about how wrong they are, that --when I am speaking in person-- I often trip myself up by trying to articulate all of them at once.

<h3 id="1">
1. Does drivechain allow miners to steal funds?
</h3>

Short Answer: This seemingly innocuous question is [very misleading](https://english.stackexchange.com/questions/261148/whats-the-term-for-fallaciously-including-an-assumption-in-a-question?noredirect=1&lq=1) -- it is a bit like asking "Does the free market allow entrepreneurs to go bankrupt?". If an entrepreneur is servicing their customers poorly, then they should, and will, go bankrupt.

Similarly, the drivechain security model assumes that the sidechain is "popular" -- useful to both users and miners. If so, it is safe. If not, then it is not.

Longer Answer (in 5 parts):

First, it is admittedly true that all SPV-proofs (drivechain or otherwise) must allow miners to forge a withdrawal of funds, because SPV-proofs are only gated by proof-of-work. This design choice is intentional, as it is precisely what allows the sidechain to be optional. If we wanted to prevent miner-theft, then we could do so easily by requiring mainchain full nodes to validate all sidechain blocks, and all sidechain rules (this would be the so-called "evil fork"). But this would be a de facto unlimited blocksize increase and therefore an unlimited loss of decentralization.

Therefore, we must choose one of these three options: [1] mandatory sidechains (evil forks); or [2] Altcoins (whose mere existence violates the 21 million coin limit); or else [3] sidechains whose withdrawals rely *only* on SPV-proofs. So, people who criticize drivechain for its use of SPV-security, probably do not realize that they are necessarily instead supporting either [1] unlimited loss of full node decentralization (mandatory sidechains); or else [2] unlimited inflation-tax on Bitcoiners (Altcoins).

Second, while all SPV-proofs are vulnerable to miner-tampering, Drivechain's has extra features (which are mainchain full node enforced) designed specifically to thwart tampering. All of a sidechain's activities over a 3 month period are compressed into a mere 32 bytes. On the mainchain, these bytes are announced and then forced to march very slowly --one step per block-- across a finish line that is 13,150 steps away. Even with 100% hashrate participation, this takes 3 months. While new contestants can begin the race at any time, only one racer can step forward at a time. Whichever 32-bytes crosses the finish line, is considered to be canonically "what happened" on the sidechain. Meanwhile, the sidechain nodes (both full and SPV) will be broadcasting these 32 bytes as loudly as possible to anyone who will listen. So, even if there is constant, maximum-scale professional tampering, it will all be very easy for the user to observe and demonstrate to others.

Investors and users will have plenty of time to react to tampering. One reaction would be to UASF to block any tampered 32-bytes from crossing the final finish line. This is much easier than the SegWit UASF, because it requires no software development, and no real-life coordination on actions and timing. If the UASF fails, and if the sidechain was objectively valuable, BTC's total transaction fees and exchange rate should fall, punishing the very miners who instigated the tampering.

[More reading.](http://www.truthcoin.info/blog/drivechain/#drivechains-security)

Third, some sidechains are "bad", and it is actually a good thing if miners have an incentive to "evict" them. It is rather analogous to a city with a large criminal homeless population: some sidechains can be *designed* purposefully, to "leech" off of other sidechains, or even to attack the mainchain directly. How can we make sure that all of the best sidechains are let in, and all of the worst ones are kept out? By giving the decision to whoever has the most skin-in-the-game. Miner's profits are highest when they maximize exchange rate and total transaction fees, so it is reasonable to give the add/remove-sidechain decision to them.

In other words, if a particular sidechain is holding Bitcoin's exchange rate down, we would *HOPE* that miners steal from it, and quickly! In the same way that we would hope oncologists would assassinate our cancer cells; or that poorly-run businesses will fall apart and free up capital for better entrepreneurs.

[Further reading](http://www.truthcoin.info/blog/wise-contracts/). [And watching](https://www.youtube.com/watch?v=xGu0o8HH10U&index=1&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4).

Fourth, the very idea of "can" (in the phrase "miners can steal") is a complete misrepresentation of how Bitcoin works. In a naive sense, miners can always steal BTC, whether it is on drivechains on the mainchain or even in LN-channels. This is because miners control the contents of The Blockchain absolutely. But the true question has always been: "will" miners steal. And, in answering it, we have always relied on *theories* about miners' choices, motivations, and behavior. We then apply these theories to a given design -- in vanilla Bitcoin, we observe that miners must make choices and pay their costs in advance, are next held hostage for a while, and are then ultimately paid out by the protocol *in BTC*. 

The purport of this "can"-language, I think, is to imply --falsely-- that the Drivechain design puts user's BTC into immediate risk of being easily claimed by miners in the very next block. And, therefore, that I am being naive in assuming that miners will not do this! But the truth is that I built features into Drivechain (especially the slow, transparent, high-effort withdrawal process), that I assume will convince *profit-maximizing* miners that harvesting the sidechains (for their txn-fees and value-boosting properties) is more lucrative than devouring them.

Fifth, and most important, the argument only applies to BTC that users have deposited to a sidechain! Non-sidechain funds are completely unaffected by sidechains, of course.

Consumer sovereignty is a basic principle of Bitcoin. Users are allowed to handle their funds however they like -- to use unproven wallets, invest in dubious projects, and even to sell -or just straight-up [destroy](https://www.blockchain.com/btc/address/1BitcoinEaterAddressDontSendf59kuE)- their BTC. In particular, they can send BTC into LN-channels, despite the weaker security model. This is because the LN has benefits that (as the user sees it) make up for its risks. It is exactly the same with Drivechain.

Those who say otherwise have simply betrayed the liberty movement and the free software movement.


<h3 id="2">
2. Does Drivechain increase the risk of txn-censorship by giving economic advantages to large pools, making them inevitable; while simultaneously making large pools less anonymous and more susceptible to coercion?
</h3>

Short Answer: No.

Longer Answer:

This complaint imagines, for example, that it costs $5 million / year to run all sidechains (or one big sidechain), and that these chains produce $100 million / year in transaction fees. Then, a miner with only 4% of the hashrate will pay $5M, but can only earn $4M. So they'll have to shut down their node, and move to a larger pool.

Separately, it alleges that pool operators who mine profitable sidechains, will have an edge over pools who do not. And, of course: no hasher will want to partner with a pool that declines to give them their share of some free money. Therefore, eventually, running all of the sidechains will become de facto mandatory.

Thirdly, it alleges that sidechain software makes the pool operators less anonymous and easier to coerce. Specifically, regulators will be able to force pool operators to censor transactions.

This plausible-sounding story is false from beginning to end.

First, Drivechain contains something called [blind merged mining](http://www.truthcoin.info/blog/blind-merged-mining/), designed to address this "problem". It allows pool operators (or solo miners) to collect all of the chain's txn-fees, without needing to run a node. It does this by outsourcing the block-assembly work to sidechain full nodes (ie, users), who are doing it anyway. Mainchain miners just watch the mainchain for "bids", and include only the highest bid. The sidechain network activity, no matter how burdensome, is compressed into a small, fixed number of mempool messages.

While it addresses the critique completely, I now regret developing it. It took up a lot of time, and it lent undeserved credibility to this "problem".

In truth the problem is nonsense. Let me explain why with five reasons.

First, the 'second act' (of the story above), conflates "an inducement" with outright "slavery". It says that, if miners earn $0.10 of profit by selling t-shirts or something, then eventually t-shirts will become a mandatory part of the protocol, and that whoever can control t-shirts can control Bitcoin mining.

This premise is almost certainly false. The claim that 'wasteful competitors will go bankrupt in the long run' is quite different from the claim that 'every $0.10 of profit is mandatory'. Intelligent humans can decline to take $0.10, if they have any real or imagined concerns about running the sidechain.

But, even if this premise were true, the argument ends up contradicting itself. Remember that the third act called upon us to believe that pools would bow to coercive forces, and start censoring transactions from blocks. But, crucially: pools lose profits when they censor. Each time they decline to include a valid fee-paying txn, they pay the opportunity cost of those lost fees, and they save nothing on "costs". So it comes directly out of profit.

But earlier we assumed that 'every $0.10 of profit is mandatory'. Which means that censorship is absolutely prohibited. So, either the pools are "required" to earn every cent, in which case they can never censor a single txn, or else they aren't (in which case they do not necessarily need to run every sidechain).

And it gets worse. Consider that the fees that are *first* to be censored would certainly be the sidechain's high-overhead, low-fee-magnitude txns. At absolute worst, the system would regress toward exactly the state it is in right now: one with all of the sidechain-txns censored. If pool-coercing censorship is still possible after *that* point, then sidechains are not to blame for it, by definition.

Second, as with the "miners can steal" language, this critique is grounded in poor Bitcoin Philosophy. Critics intentionally conflate "node centralization" and "miner centralization", in the hopes that, by reusing a word, the audience can be tricked into thinking that the two concepts are similar to each other. In reality they have nothing to do with each other. Node centralization (the [real one](http://www.truthcoin.info/blog/measuring-decentralization/)) makes life harder for the user, and is self-evidently bad.

But with mining it is a different story. While "mining", the process, is the core element of Bitcoin's design, the mere act of "finding a block" is utterly neutral. If this block contributes to the longest chain, it is good; if it contributes to a reorg chain, then it is bad. So if we make mining "easier", we also make attacking Bitcoin easier. And in fact, when the difficultly adjusts upwards, there is cheering and applause (as there was with the SegWit UASF).

Miners are not customers, they are suppliers. After a certain point, what is good for one is *bad* for the other. For example: "forced teamwork in the name of efficiency" (aka "mining centralization") is inconvenient for miners...but good for users.

Third, txn-censorship is a privacy-failure; it has nothing to do with pools or sidechains or merged mining. If Bitcoin had strong privacy, users would be protected from censorship. Adversaries could only respond by 'censoring everything'; but if they can manage that, then we are doomed in any case. 

Fourth, while critics bill out merged mining as threat to Bitcoin, the reverse is probably the case: going *without* merged-mining is the bigger threat to Bitcoin. For MM is likely to be the only decentralization-preserving way to boost on-chain fee-revenues; and [these need to be boosted](http://www.truthcoin.info/blog/security-budget/).

Fifth, and again most importantly, merged mining (the vanilla, non-blind version) is unblockable. There is nothing the user can do to prevent miners from doing it. And miners earn more money by doing it. So, even if we make every possible concession to Critique 2, that it is bad and that everything in it will happen, then we would just end up in a world where experimental software takes the form of Altcoins -- these would be vanilla merged mined and ultimately we would reach the same "high overhead pool" result.


### Other Critiques

Critiques 1 and 2 are the big ones.

Other critiques are possible, of course. But, in general, they are just statements about risk, the same way we might warn people about [the big unsolved](https://twitter.com/peterktodd/status/1092561610831421441) [problem with LN-channels](https://www.reddit.com/r/Bitcoin/comments/7pwna9/lightning_network_megathread/dslnc12). Advice is always helpful, but the final decision always rests with each individual.

In other words, it is possible to dis-prefer Drivechain, but still agree that some users may find it useful.

Watch: ["Drivechain: Overview and Misconceptions"](https://www.youtube.com/watch?v=gUbGT70wy5k)


### Dissenters

I have presented these arguments several times, in various media (writing, youtube, meme, conference presentation). But, I admit, some remain unconvinced.

In the interest of honesty and full disclosure, here are some technical experts who still endorse Critique #1:

* Peter Todd ([Feb 2019](https://cryptodaily.co.uk/2019/02/peter-todd-explains-why-mimblewimble-should-not-be-implemented-as-bitcoin-sidechain))
* Giacomo Zucco ([Jan 2019](https://twitter.com/giacomozucco/status/1090720661696364558))
* Jimmy Song (["at least a little bit"](https://www.youtube.com/watch?v=-Re9xVzmYeI))
* Gregory Maxwell ([July 2017](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-July/014726.html))



And here are those who endorse Critique #2:


* Peter Todd ([Feb 2019](https://cryptodaily.co.uk/2019/02/peter-todd-explains-why-mimblewimble-should-not-be-implemented-as-bitcoin-sidechain))
* Andrew Poelstra / Gregory Maxwell ([Dec 2018](https://youtu.be/NA1xSe2nLoY?t=5635))
* Matt Corallo (Oct 2016)


### Wall of Fame

Notable people who never fell for either mistake, or who came around:

* Person 1 (May 2017)
* Person 2 (June 2017)
* Person 3 (June 2018)
* Person 4 (Feb 2019)

( Names blanked out temporarily, and mixed in below. )

### Unknown 

People whose opinion on Drivechain we don't know (please tell us!), plus the four people above:

* Adam Back
* Bryan Bishop
* Luke Dashjr
* ฿tcDrak
* Andrew Chow
* Christian Decker
* Nicolas Dorier
* Thaddeus Dryja
* Johnson Lau
* Eric Lombrozo
* Jameson Lopp
* Cory Fields
* Mark Freidenbach
* Alex Morcos
* John Newbery
* Laolu "roasbeef" Osuntokun
* Joseph Poon
* Jeremy Rubin
* Rusty Russell
* Gregory Sanders
* Jonas Schnelli
* Patrick Strateman
* Amir Taaki
* Warren Togami
* Wladimir van der Laan
* Pieter Wuille

### See Also

* [Why Drivechain is Hard to Understand](http://www.drivechain.info/blog/hard-to-understand/) -- Strange quirks of DC that make it different from previous soft forks of Bitcoin.
* (forthcoming) [Conflicts of Interest](/link-forthcoming/) -- Almost everyone who could peer review drivechain, stands to lose a lot of money if it succeeds.