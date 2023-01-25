
## Peer Review


### Bitcoin-Dev Links


* [May 2017](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-May/thread.html#14364), [June 2017](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-June/thread.html#14557), [My Summary](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-June/014559.html)
* [Feb 2022](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-February/019978.html), [2nd thread](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-February/019998.html), [March 2022](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-March/020030.html)


## What are the major remaining critiques of Drivechain?

The two big critiques of Drivechain, which persist (for some reason), are:

1. **"miners-can-steal"** -- 51% hashrate can empty the Bip300 sidechain of funds, sending them to a txn of their own choosing.
2. **"miner side-hustle"** -- It is bad if miners can make money on a side-hustle, because then miners will feel pressured to do the side-hustle. The side-hustle might negatively affect users of Layer1.

Both critiques are false. Each is a complex logjam of misconceptions. There is so much to say, about how wrong these critiques are, that I often trip myself up by trying to get everything out at once.

<h3 id="1">
1. Does drivechain allow miners to steal funds?
</h3>

Short Answer: This seemingly innocuous question is [totally misleading](https://english.stackexchange.com/questions/261148/whats-the-term-for-fallaciously-including-an-assumption-in-a-question?noredirect=1&lq=1) -- it is a bit like asking "Does the free market allow entrepreneurs to go bankrupt?". If an entrepreneur is servicing their customers poorly, then they should, and will, go bankrupt. 

The drivechain security model assumes that the sidechain is "popular" -- useful to both users and miners. If so, it is safe. If not, then it is not.

The "miners can steal" feature is not a design flaw, nor is it even a trade-off (as if we had to "settle" for miners-can-steal SPV proofs because they are the best we can do with present technology). Instead, miners-can-steal is the only known way of achieving ["sidechain privatization"](https://www.youtube.com/watch?v=xGu0o8HH10U&index=1&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4), which is necessary for many important sidechain designs. Thus, perhaps counterintuitively, **removing the miners-can-steal feature will cause many sidechains to become insecure**.

For comparison, *51% hashrate can also steal from the Lightning Network* (by censoring the "Justice txn" from the blockchain). Relative to DC-Miner-theft, LN-Miner-theft is faster, easier, more deniable (enormously lower risk of being caught), and can be fine-tuned so as NOT to invite retribution. Moreover, DC-theft negatively affects miner's fee revenues, whereas LN-theft may have zero effect or even a positive effect. So, if you weren't worried about miners stealing from LN, then don't worry about DC-theft, either.

Longer Answer (in 5 parts):

<h5 id="1-1">
1.1 The Validation Trilemma
</h5>

First, it is admittedly true that all SPV-proofs (drivechain or otherwise) must allow miners to forge a withdrawal of funds, because SPV-proofs are only gated by proof-of-work. This design choice is intentional, as it is precisely what allows the sidechain to be optional. If we wanted to prevent miner-theft, then we could do so easily by requiring mainchain full nodes to validate all sidechain blocks, and all sidechain rules (this would be the so-called "evil fork"). But this would be a de facto unlimited blocksize increase and therefore an unlimited loss of decentralization.

Therefore, we must choose one of these three options: [1] mandatory sidechains (evil forks); or [2] Altcoins (whose mere existence violates the 21 million coin limit); or else [3] sidechains whose withdrawals rely *only* on SPV-proofs. So, people who criticize drivechain for its use of SPV-security, probably do not realize that they are necessarily instead supporting either [1] unlimited loss of full node decentralization (mandatory sidechains); or else [2] unlimited inflation-tax on Bitcoiners (Altcoins).

<h5 id="1-2">
1.2 Four Withdrawals Per Year
</h5>

Second, while all SPV-proofs are vulnerable to miner-tampering, Drivechain's has extra features (which are mainchain full node enforced) designed specifically to thwart tampering. All of a sidechain's activities over a 3 month period are compressed into a mere 32 bytes. On the mainchain, these bytes are announced and then forced to march very slowly --one step per block-- across a finish line that is 13,150 steps away. Even with 100% hashrate participation, this takes 3 months. While new contestants can begin the race at any time, only one racer can step forward at a time. Whichever 32-bytes crosses the finish line, is considered to be canonically "what happened" on the sidechain. Meanwhile, the sidechain nodes (both full and SPV) will be broadcasting these 32 bytes as loudly as possible to anyone who will listen. So, even if there is constant, maximum-scale professional tampering, it will all be very easy for the user to observe and demonstrate to others.

Investors and users will have plenty of time to react to tampering. One reaction would be to UASF to block any tampered 32-bytes from crossing the final finish line. This is much easier than the SegWit UASF, because it requires no software development, and no real-life coordination on actions and timing. If the UASF fails, and if the sidechain was objectively valuable, BTC's total transaction fees and exchange rate should fall, punishing the very miners who instigated the tampering.

[More reading.](http://www.truthcoin.info/blog/drivechain/#drivechains-security)

<h5 id="1-3">
1.3 Delousing the Mainchain / Sidechain Privatization
</h5>

Third, some sidechains are "bad", and it is **necessary to sidechain security** that miners have an incentive to "evict" them.

Passively, sidechains do not affect each other in the slightest (which is, of course, the whole point). But what if a sidechain is *specifically designed* to interfere with some other sidechain (or the mainchain). In 2016, I researched several such problematic sidechain designs (research below). So, we now have a problem: how do we get ride of bad sidechains? Some force has to sweep through the protocol somehow, such that if a sidechain is too problematic it is eventually kicked out of the Bitcoin cryptosystem.

Luckily, an easy solution is at hand: Miner's profits happen to be the highest, when they maximize the BTC exchange rate and the total transaction fees (across all sidechains). They are also the natural "laborers" of the system, and 51% hashrate coalition already has the ability to filter out any unwanted messages from any blockchain (mainchain or sidechain). So it is natural to give the add/remove-sidechain decision to them.

In other words, if a particular sidechain is holding Bitcoin's exchange rate down, or supressing txns on a rival sidechain, then we would *HOPE* (perhaps counterintuitively) that miners steal from it, and quickly! In the same way that we would hope oncologists would assassinate our cancer cells; or that poorly-run businesses will fall apart and free up capital for better entrepreneurs. Best of all, the looming threat of sidechain failure acts as a deterrant -- sidechain developers will want to work hard to present a quality, law-abiding product.

[Further reading](http://www.truthcoin.info/blog/wise-contracts/). [And watching](https://www.youtube.com/watch?v=xGu0o8HH10U&index=1&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4). None of the people advancing the "miners-can-steal" talking point are familiar with this research. They do not know that, for example, a ZK-SNARK peg-out system (which they would presumably prefer, as miners can NOT affect withdrawal-transactions in any special way) would (among other problems) render all P2P oracle sidechains permanently insecure. And it would do so for no reason, since miners could steal from such sidechains anyway (next section).

<h5 id="1-4">
1.4 Miner-Theft Has Nothing to do With Drivechain
</h5>

Fourth, the very idea of "can" (in the phrase "miners can steal") is a complete misrepresentation of how Bitcoin works. In a naive sense, miners can always steal BTC, whether it is on drivechains on the mainchain or even in LN-channels. This is because miners control the contents of The Blockchain absolutely. So the true question has always been: "will" miners steal. (See my [Lisbon BoB talk](https://www.drivechain.info/literature/index.html#bob) for more.)

The purport of this "can"-language, is to imply that the Drivechain design is cavalier and unconcerned -- as if I would allow BTC to be snatched up by miners in the very next block! And that, therefore, I am naive (since I "assume" that miners will just not take these "up for grabs" coins).

Hopefully by now it is obvious that that is misguided. Drivechain assumes that miners *profit-maximize*, and take as many coins for themselves as they possibly can. The withdrawal-process is slow, transparent, and high-effort, and is very tamper-resistant. Miners have an alternative to stealing from sidechains: *harvesting* them, for their txn-fees and value-boosting properties. For some (but not all) sidechains, harvesting will always be more profitable than devouring.

<h5 id="1-5">
1.5 DC Is An Opt-In Layer-2
</h5>

Fifth, and most important, the "miners-can-steal" argument only applies to BTC that users have deposited to a sidechain! Non-sidechain funds are completely unaffected by sidechains, of course!

Consumer sovereignty is a core principle of Bitcoin. We all agree: users are allowed to handle their money however they like -- they can use unproven wallets, invest in dubious projects, and even to sell their BTC (or straight-up [destroy](https://www.blockchain.com/btc/address/1BitcoinEaterAddressDontSendf59kuE) their BTC). In particular, we would **all agree** that they can send BTC into LN-channels, despite the weaker security model. This is because the LN has benefits that (as the user sees it) make up for its risks. We would also **all agree** that users have the right to sell their BTC and buy an Altcoin. It is exactly the same with Drivechain.

Those who say otherwise, have simply betrayed the liberty movement and the free software movement. No one in Bitcoin should listen to what they have to say, about anything.


<h3 id="2">
2. The "Side Hustle" -- Does Drivechain give an advantage to certain mining pools? If so, does this make Drivechain inevitable for pools? Does this harm pools in some way, for example, by making pools less anonymous and more susceptible to coercion?
</h3>


Short Answer: No.

Every mining innovation, can be construed as a "side hustle". For example: mining bitcoin with [Flared Gas](https://www.reuters.com/business/sustainable-business/oil-drillers-bitcoin-miners-bond-over-natural-gas-2021-05-21/). Or: mining via [demand management](https://www.newsweek.com/bitcoin-mining-americas-most-misunderstood-industry-opinion-1669892). Each of those two techniques, requires specialized labor, special conditions, and a certain scale of operation. Each of those innovations "affects mining incentives".

Merged Mining is widely misunderstood, and even many Bitcoin Experts hold beliefs about MM which are exactly backwards from the truth. (See my section ["The Great Lie of [Merged Mining]"](https://www.truthcoin.info/blog/security-budget-ii-mm/#b-the-great-lie-about-mm
)). The simple truth is: it is good when miners earn a lot of money, it is good when miners spent that money efficiently (which includes professionalization and specialization). That drives the difficulty up as much as possible. The upward difficulty adjustments make it *difficult* to find blocks, which is what we want -- we do not want block-finding to be easy. Merged mining was invented by Satoshi in 2010, for exactly this purpose, and it has been safely in use ever since. Drivechain does not do anything new, in 2021, that Namecoin hasn't already been doing since 2011. 

Longer Answer:

<h4 id="2-overview">
Overview of Complaint
</h4>

To me, the complaint makes no sense. Nonetheless, I shall now try to explain this complaint (which I have only ever received from one person), in its absolute worst-case-scenario (ie, its most-problematic form). I hope that is not too confusing as a result. 

First, the complaint asks us to consider "burdensome sidechains" which are expensive to run, but profitable.

So imagine that all "sidechain" software costs $5 M / year to run, but "sidiechains" bring in $100 M / year (in txn fee revenue). A solo miner with only 4% of the hashrate would earn $4M from "sidechains" (just 4% of the total $100M). But "sidechains" would cost this miner a fixed $5M. So this miner does not run any sidechains. But conversely, a solo miner with 12% would run sidechains -- they'd pay $5M (fixed) and earn $12. This miner now earns a higher ROI (the $12/$5 ROI blends in with the subsistence ROI he was earning pre-sidechains). Because of sidechains, larger miners are rewarded more.

The same problem applies to pools. The pool operators who mine "sidechains", will have an edge over those who do not. Pools which turn down the free money, will not attract Hashers. Therefore, eventually, "running all profitable sidechains" will become an activity that is de facto mandatory.

So far, nothing bad or even unusual has happened -- mining has always entailed high-effort "de facto mandatory" activities (optimizing chip designs, locating cheap sources of electrical power, etc).

But the third and final part of the complaint, alleges that sidechain software (hypothetically) also makes the pool operators less anonymous and easier to coerce. Regulators will be able to force pool operators to censor transactions -- specifically, now that the pools have been forced into a vulnerable state, they will be coerced into censoring *mainchain transactions* that were previously (before the arrival of sidechains) un-censorable.

This plausible-sounding story is false from beginning to end.

<h4 id="2-0">
Blind Merged Mining
</h4>

First, Drivechain contains something called [blind merged mining](http://www.truthcoin.info/blog/blind-merged-mining/), designed to address this "problem". It allows pool operators (or solo miners) to collect all of the chain's txn-fees, without needing to run a node. It does this by outsourcing the block-assembly work to sidechain full nodes (ie, users), who are doing it anyway. Mainchain miners just watch the mainchain for "bids", and include only the highest bid. The sidechain network activity, no matter how burdensome, is compressed into a small, fixed number of mempool messages.

While it addresses the critique completely, I now regret developing it. It took up a lot of time, and it lent undeserved credibility to this "problem".

In truth the problem is nonsense. Let me explain why with five reasons.

<h4 id="2-0">
A Nonsense Problem
</h4>

<h5 id="2-1">
2.1
</h5>

First, the 'second act' of the story above ("...runnning all sidechains is de facto mandatory"), conflates "an inducement" with "total slavery". The DC-skeptics are arguing: if miners earn $0.10 of profit by selling t-shirts (or whatever), then eventually t-shirts will become a mandatory part of the protocol, and that whoever can control t-shirts can control Bitcoin mining.

That premise is as silly as it sounds. The claim that 'wasteful competitors will go bankrupt in the long run' is quite different, from the claim that 'every $0.10 of profit is mandatory'. Intelligent humans can decline to take $0.10, if they have any real or imagined concerns about running the sidechain.

But if the premise were true, the argument gets worse! It ends up contradicting itself. The end of the story called upon us to believe that pools would bow to coercive forces, and censor transactions from blocks. But, crucially: pools lose profits when they censor. Each time they decline a valid fee-paying txn, they pay the opportunity cost of those lost fees (and save nothing on "costs"). So it comes directly out of profit.

But earlier we assumed that 'every $0.10 of profit is mandatory'. Which means that censorship is absolutely prohibited. So, either the pools are "required" to earn every cent, in which case they can never censor a single txn, or else they aren't (in which case they are not "required" to run every sidechain).

And it gets worse. The *first* txns to be censored would certainly be the sidechain's high-overhead, low-fee-magnitude txns. So, even if the story of the complaint somehow comes true (inconsistent though it is), the Bitcoin system would just regress toward the state it is in now: one with all of the sidechain-txns censored. If pool-coercing censorship is still possible after *that* point, then sidechains are not to blame for it, by definition.

<h5 id="2-2">
2.2
</h5>

Second, as with the "miners can steal" language, this critique is grounded in poor Bitcoin Philosophy. Critics intentionally conflate "node centralization" and "miner centralization", in the hopes that, by reusing a word, the audience can be tricked into thinking that the two concepts are similar to each other. In reality they have nothing to do with each other.

Node centralization (the [real one](http://www.truthcoin.info/blog/measuring-decentralization/)) makes life harder for the user, and is self-evidently bad. But with mining it is a different story. While "mining", the process, is the core element of Bitcoin's design, the mere act of "finding a block" is utterly neutral -- when a new block attaches to the longest chain, it was "good"; but if a new-found block attaches to an attacking reorg chain, then it was "bad". So if we make "mining" easier, we also make "attacking Bitcoin" easier.

This is implicity recognized in Bitcoin culture -- when the difficultly adjusts upwards, there is cheering and applause. As there was with the SegWit UASF. People cheer when mining becomes *harder*.

Miners are not Bitcoin-customers, they are Bitcoin-suppliers. After all the Pareto improvements have been found, what is good for customers will be *bad* for suppliers. For example: "forced teamwork in the name of efficiency" (aka "mining centralization") is inconvenient for miners...but good for users.

<h5 id="2-3">
2.3
</h5>

Third, txn-censorship is a privacy-failure; it has nothing to do with pools or sidechains or merged mining. If Bitcoin had strong privacy, users would be protected from censorship. Adversaries could only respond by 'censoring everything'; but if they can manage that, then we are doomed in any case.

<h5 id="2-4">
2.4
</h5>

Fourth, while critics bill out merged mining as "threat" to Bitcoin, the reverse is probably the case: going *without* merged-mining is the bigger threat to Bitcoin. For MM is likely to be the only decentralization-preserving way to boost on-chain fee-revenues; and [these need to be boosted](http://www.truthcoin.info/blog/security-budget/).

<h5 id="2-5">
2.5
</h5>

Fifth, and again most importantly, merged mining (the vanilla, non-blind version) is unblockable. There is nothing the user can do to prevent miners from doing it. And miners earn more money by doing it. So, even if we make every possible concession to Critique 2, that it is bad and that everything in it will happen, then we would just end up in a world where experimental software takes the form of Altcoins -- these would be vanilla merged mined (as Namecoin is today) and ultimately we would reach the same "high overhead pool" result.

<!--
<h5 id="2-6">
2.6
</h5>

As an afterthought, it is worth noting that basically none of the premises of the story were sound.

Sidechain software that costs $5 million per year to run? Regular users (non-miners) must run SC-nodes, in order to safely use the new features. And these users earn zero txn fees (in fact, they are *paying* the txn fees)! So which users are running these "burdensome sidechains"? Wouldn't the sidechains just die off immediately? If it cost 5 million to run a Bitcoin node, that would probably just be the death of Bitcoin.

If we consider the fixed costs already faced by miners (equipment, long term power contracts, human capital) and mining pools (reputational capital), it is highly implausible that "sidechain software" could ever realistically become "burdensome" in the first place.

And pools can easily hide a node somewhere, and pass instructions to hashers via TOR/VPN. The hashers only need the BlockTemplate which is barely a few kilobytes.

-->


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