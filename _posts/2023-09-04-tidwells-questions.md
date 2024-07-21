---
title: Tidwell's List of Objections
show_author: true
comments: true
date: 2023-09-04 05:00:00
---

Published on Twitter: Sept 4, 2023
Republished here: Jul 20, 2024


[Michael Tidwell](http://2022.tabconf.com/history/) collected a [list of drivechain objections](https://twitter.com/miketwenty1/status/1696943794321588383?s=20).

I [replied to them all](https://x.com/Truthcoin/status/1698749283560743282), but it is (probably) hard to follow on Twitter. So here they are again.

## The Objections

1. "No one wants it" -- Jimmy Song
2. "Elsewhere first" -- Pete Rizzo
3. "stratum V2 first" -- Matt Corallo
4. "The unpeggining" -- John Carvalho
5. "insufficient fees" -- Melvin Carvalho
6. "adoption is dangerous" -- shinobi
7. "federation is superior" -- Luke Dashjr
8. "the BMM fallacy" -- Alex Bergeron

Each of these is quite terrible.

## The Awnsers

### 1 / 4 / 7 ...and... 2 / 3

Orignal [here](https://x.com/Truthcoin/status/1697501294229921919).

[ #1, #4, & #7 ] are not actual objections to activating DC, they are just predictions that users won't want to use DC.

Nonetheless...

#1 -- pro-DC demand evidence:

* **Wrapped BTC** -- is 100,000s of BTC, vs entire lightning network (< 5,000 BTC). wBTC is the ETH-Sidechain, just on top of Ethereum instead of on top of BTC. Network effects suggests that "Eth-Sidechain" will be even bigger, if it is on the biggest network.
* **Largeblocker comments** -- During the scaling war, largeblockers said they: [1] did not mind paying higher node costs, and [2] they did not mind relying on SPV-mode. DC is SPV mode -- so it would have met the needs of largeblockers. So, at minimum, those users would have been satisfied, instead of splitting off.
* **Scaling** -- There is no realistic plan to scale BTC to a billion UTXOs (other than DC). LN is doomed, and is basically a [scam at this point](https://www.truthcoin.info/blog/ln-blackpill/). Because of network effects, ONLY the scalable network will survive. So: forget demand. DC is necessary for survival.
* **Fees** -- Total Altcoin fees, is [higher than](https://cryptofees.info/) total BTC fees. That is objective evidence of demand for non-BTC blockchains. If these networks all shared the same coin (having no exchange rate risk, and being interoperable), the total demand would likely be even higher. The total [transaction fee demand](https://www.truthcoin.info/blog/all-world-txns/) is enormous ($ X00 B per year).
* **Features** -- The software world improves constantly. See [Misinformation#5](https://www.drivechain.info/misinformation/index.html#5) for examples of developers trying very hard to innovate on top of Bitcoin, but resorting to an Altcoin at the last minute.

It is very foolish to dismiss an open system (drivechain), just because Liquid / RSK are not YET popular. Liquid / RSK are nothing like Drivechain (they use multisig / Bip16.) That would be like dismissing the Internet, because the first two INTRA-nets weren't popular. Big mistake.

#4 -- Peg not holding.

It's true -- miners can annoy DC users. They can threaten to steal DC funds. And -- they can ACTUALLY steal their funds! This question is just a repeat of #5, only milder. (Q5 is answered below.)

There is an [image on drivechain.info](https://www.drivechain.info/media/meme-vital-few.png) which explains, that some sidechains are bad and the peg SHOULD NOT and WILL NOT hold. That is a good thing. It is like how not every restaurant should succeed -- only the viable ones.

#7 -- This is a matter of taste. Luke would not use them himself, others would. (My guess is: at first, most people will only put in a little money; later they will warm to the idea. So it will not be a binary "use" vs "not use" situation.) Luke has indicated elsewhere, that he supports other people having the option to use DC, if they wish. In a way, this is a repeat of #1 and #5.

### #2 and #3

Questions #2 and #3, are not actually about Drivechain at all. They just say that Bip300-Litecoin / Stratum V2 should be built first.

(Makes no difference to me.)

Re: Litecoin, I can say this: Bip300-Litecoin is coming, one way or another (since Bip300 is so simple). So Bip300 will be tested on Litecoin -- and that is good. But notice that this "objection" is admitting defeat -- the objectors are saying: "well, I can't think of any reason why it would be a bad idea, but we should test it more, to see if a new idea appears".

As for Stratum V2, it is a poorly-run and illogical project. No actual miners support it. The main "selling point", on Twitter (job negotiation) is a contradiction: either the pool can ban a client's template (censorship), or it cannot (in which case, the pool can just become a client of themselves, and censor that way). Nonetheless, we do need better way of managing hashrate, independent of Bip300.


### Question 5 -- Fees / Miners Can Steal

Answered via [its own blog post](https://www.drivechain.info/blog/fees/).


### Question 6 -- Adoption is Dangerous

Shinobi incorrectly believes that "Drivechain is secured by UASFs". [He is flat wrong.](https://www.drivechain.info/faq/index.html#uasf-reliance)

As I have said, since the very first blog post, Drivechains are secured by fees. (See previous answer.)

We could unpack the psychology of this, if we wished. Why does shinobi (and even the great Adam Back) become *so, so confused* on a point that *I have made so, so clearly and consistently -- since [the beginning](https://www.truthcoin.info/blog/drivechain/#drivechains-security)*? It relates to their misunderstanding the very **foundation of Bitcoin** -- a transaction's security, is its **transaction fee**, not a cryptographic one-way function. And: Bitcoin is secured [by *game theory*](https://fiatjaf.com/drivechain.html), NOT cryptography.

We can also (if we want) explore contradictions in the inherent nature of the UASF. This will reveal shinobi as fake, and his complaint as B-S.

A "UASF" with >51%-hashrate behind it, is always a MASF -- never a UASF. Conversely, a "UASF" that has <51%-hashrate behind it, is actually always a **hard** fork, not a soft fork (ie, it is a UAHF, not UASF). This is because a low-hashrate-UASF must break the *heaviest valid chain* rule -- and this is, in principle, equal to breaking the blocksize limit or 21M coin limit. Only the users who run the low-hashrate-"UASF" client, will be on that chain -- this proves that it is a hard fork.

What does this have to do with Drivechain? Well, shinobi/Back's confused idea is that victims of DC-theft will use a UASF to secure their coins, and that this might be bad. But we see automatically that it is not. They would just create a spinoff-Altcoin hardfork, such as BCH. Everyone would get free coins. Either (1) the miners will switch to this coin, mining it (and taking everyone else on the network with them), in which case L1 users **will not even notice anything**. Or, the 2nd possibility is (2) the miners do NOT switch to the UA[S]F coin, in which case L1 users **will not even notice anything**. The only people who can possibly be affected, ever, are users of the sidechain -- this is the exact ideal outcome.

So, shinobi is flatly wrong. He is too lazy to read the FAQ -- and in fact, his inane ramblings are always a waste of time. And -- even were he correct about DC requiring UASFs (he is absolutely and completely incorrect) -- even then, there is no possibility of L1 users being affected by these UASFs.

In contrast, Bitcoin L1 *will* be affected if the security budget collapses, or if the BTC project fails and dies out. The best way to protect L1 from these disasters, is via DC.

The original twitter answer to #6 was [here](https://x.com/Truthcoin/status/1698731139337269504).



### Question 8 -- MEV / MEvil

#### Background: So Many Fraud Xenophobic Alarmists

New standards of *intellectual laziness* were set, with the nebulous "MEV" complaint.

For starters, [no one can agree](https://x.com/Truthcoin/status/1780610410036494368) on **a definition** of MEV.

So **my first challenge** is: write down your way of measuring MEV. Write down your MEV-ometer. If you can't do that, then (at least) make a list of everything *correlated* with MEV. If "MEV" goes up, then ___ goes up. Make the list. If you can't do that, then you don't know what you're talking about.

#### My (Correct) Definition of MEV

I can do it, for you, if you like. Here you go: MEV is *any economic benefit a miner derives, from mining a block, other than the L1 transaction fees in the coinbase*. Therefore, by my definition:

* Ordinals / "rare sats" are MEV. More precisely, if one single "rare sat" sells for 15,000,000 sats, then the MEV would be measured at 14,999,999 sats (and, to be more precise still, we would further subtract the cost of the txn fee needed to "move"/liquidate this sat).
* Classic "ethereum MEV" (such as "reording DEX transactions"), is MEV. For example, if you can front run a few trades, intercept some people trading PEPEcash on Counterparty, end up with the same portfolio of assets as when you started -- but 15,000 sats richer, then that was 15,000 sats of MEV.
* Using waste heat, to [warm a swimming pool](https://x.com/BitcoinNewsCom/status/1801730619459744078), is MEV. If swimming pool heat costs you $100 per month, but thanks to Bitcoin Mining, you get it for free, then the MEV of the block is just the $100, converted to sats, and amortized over the number of blocks you usually find in a month. (Same for [drying food](https://x.com/Truthcoin/status/1502002291662069764).)
* Conditional gifts to miners, are MEV. If Adam Back said: "I will pay 0.0005 Euros, per block, to every miner that registers with Adam Back Mining Council", then that is MEV. If Vladimir Putin declares: "Russia will pay 10 rubles, per block, to every miner who registers with us at the Ministry of Mining", then that is MEV.

MEV is like *a 2nd set* of "shadow" txn fees. New revenues, that *your Bitcoin full node does not automatically know about* (unlike txn fees, which every full node DOES automatically know about). Another way of saying MEV, is to say "out-of-band payment".

Under my definition, MEV is harmless. It is also fundamentally unpreventable. If you can buy Christmas presents for miners -- if you can invited a miner down to the bar, and buy them a drink, then you live in a world where MEV is possible.

#### The Effect of Drivechain on MEV

Drivechain is the best shield **against** MEV, in fact. To *most lessen* the *relative* impact of MEV, you would *use drivechain* to boost the total L1 txn fees collected by miners. You'd want miners to be so rich processing txns, that they would not care about trivial MEV bribe quantites.

But --more to the point-- under my definition, Drivechain **doesn't cause any MEV**. BIP-301 transforms all L2 block value (both its coinbase-txn fees, AND its MEV-shadow-fees), into L1 txn fees.

I explained this, via these 4 tweets:

* https://twitter.com/Truthcoin/status/1698587079012233435
* https://twitter.com/Truthcoin/status/1753331262063009811
* https://twitter.com/Truthcoin/status/1677318849849442307
* https://twitter.com/Truthcoin/status/1729894641510559844

And especially these 4 images:

* https://x.com/Truthcoin/status/1697669391691682303


#### Finally: The People Who Level This "MEV Critique" are Frauds

Thus, **my second challenge is**: write down an example, with numbers, of drivechain causing MEV.

No one has ever done this! Including Alex B who came up with this question.

In fact, three people messaged me to say: "I tried to do as you said -- write down an example of Drivechain causing MEV. But after I wrote down the example, I realized that you are right: it's impossible". And one person messaged fiatjaf, to say the same thing. **To me this settles the issue.**

Nonethless, I can write down a numeric example. [Here it is](https://twitter.com/Truthcoin/status/1697669391691682303), in the images above. You can see that BMM has transformed all L2 fees (both MEV and otherwise) into L1 txn fees. Eric Wall doesn't understand this either, so [I had to explain](https://twitter.com/Truthcoin/status/1687198083006763008), to him: "It doesn't matter if it is one freak $100 BMM L1 txn fee, or if instead 1,000 freak transactions that each pay $0.10 extra. It is [just] extra txn fees in one block."

From a "miner incentives" point of view, these two scenarios are identical (both non-problematic):

* A world where Drivechain never activates on BTC, but (due to demand for BTC blockspace), each of the 2500 txns in a block must pay $0.10 more than they would have otherwise.
* A world where Drivechain DOES activate on BTC, and BMM causes a single L1 txn to appear, which pays one $250 txn fee.

No one worries that the 1st scenario is "affecting miner incentives". So they should not worry about the 2nd scenario either.


## In Conclusion

Anyway, that is my response to all of the "objections" to drivechain. They were all pretty terrible. Since drivechain is our only chance at a scalable/private Bitcoin -- our only chance of making Bitcoin a success -- we should do it even if the risks are high. But there are no risks. Just a bunch of nonsense complaints.


