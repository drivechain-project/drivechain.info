---
title: Why Drivechain Is Harder to Understand Than Previous Soft Forks
show_author: true
comments: true
date: 2019-04-17 02:00:00
---


Drivechain is unlike previous protocol upgrades in a few important ways. 


### 1. Novel Distinction Between "Rule-breaking" and "Theft"

Drivechain draws a distinction between "enforcing the new protocol rules", and "theft". Previously, no such distinction was necessary, and in many cases no such distinction was even possible.

For example, SegWit, as a soft fork, enforced certain *new rules*. If these rules *could* be broken, then SegWit outputs would become "anyone can spend" outputs (as the name implies, "anyone" could spend these outputs, including people other than the UTXO's rightful owner). So, conceptually, "breaking the SegWit rules" equaled "stealing money from SegWit users".

Drivechain also enforces new rules via soft fork. These rules govern things like the appearance of the critical 32-withdrawal-bytes, and the march of these bytes toward a 13,150 ACK-score. Like SegWit, these rules are enforced by full nodes. So, if everyone ran an up-to-date, DC-enabled node, then the DC-rules could not be broken.

But *unlike* SegWit, it is possible for a Drivechain txn to follow all the rules, yet still result in "theft". Namely: it could follow all of the mainchain rules, and all Drivechain rules, but it might *break* one of the sidechain's rules (of which the mainchain is ignorant, by design). Thus, mis-withdrawals are possible -- they just take 3-6 months to go through (as do valid-withdrawals).


### 2. Economics / The Open Loop

Drivechain-withdrawals want to have their cake and eat it too. One one hand, they want all of the security and audit-ability of single rare slow transactions; on the other hand: they want all of the user-friendliness of multiple frequent fast txns.

And both *are* accomplished at once. But *not* through any line of code, nor any technical innovation.

Instead it is accomplished the same way Satoshi accomplished mining -- by building a *business opportunity* into the cryptosystem. In practice, users who want to withdraw from a sidechain, will be able to use a shapeshift-like service to do so immediately. The proprietor of this service will specialize in customer service, in monitoring the sidechain node for problems, and in slowly accumulating funds and slowly walking these over to the mainchain. We are thus free to make the side-to-main peg take as long as we like, providing a huge boost to its security.

I don't think critics of Drivechain really appreciate the sheer auditability-magnitude, of a txn that is identified in 32-bytes and which must hang in the air --observed by everyone-- for at least 3 months. Or else, if they do, they don't see how anything that slow could possibly ever be useful. Or else, they do not see how we have it both ways at once...because this "conveyor" is not anywhere in the codebase.


### 3. Novel "Accumulation" of Security

Once, I remarked that DC-withdrawals are probably "more secure" than regular Bitcoin transactions.

This comment stunned at least three people in the audience, who approached me afterwards to see if I was joking, or being arrogant. But instead I think it is just another misunderstanding of DC.

A normal transaction (non-Drivechain) is checked a single time, in a single block. It passes into a script interpreter; the script is evaluated; the software checks for "TRUE". Each transaction is only checked once, ever. It is like a big assembly line, with one lane (where the txns are the products).

In contrast, Drivechain withdrawals become valid (or, more precisely, escape being invalid) by "sticking around", for months at a time, slowly accumulating ACK-score. They loop back through the assembly line, at least 13,150 times (and at most 26,300 times), before finally getting kicked out one way or another. The actual "withdrawal txn" can only be included in a block, at the very *end* of this 3-6 month accumulation process.

Moreover, the ACK-score system is heavily biased toward conservatism. If 51% hashrate processed withdrawals randomly, then it isn't as though attacker gets their way half the time, and honest users get their way half the time -- instead, zero withdrawals go through at all (ie, they all fail 100% of the time).

So, assume for the moment that every DC-withdrawal that *does* go through, is one that is non-theft. In that way, DC-withdrawals are as "secure" as regular txns.

In that case, how would they be "more" secure?

Well, regular txns need to worry about being reorged out of the chain, but withdrawal-txns almost certainly do not. Miners worked 3-6 months to include withdrawals in a block, and cannot include any other variation of them for another 3-6 months. So, in the event of a large reorg, the withdrawal-txn will probably end up in the active chain; but this is not necessarily true for any of the "normal" txns.


### 4. New Mindset: Non-Core Software Might Be Good

Bitcoin-Culture has evolved [an extreme aversion to non-BTC projects](https://www.reddit.com/r/btc/comments/9i8obh/everything_wrong_with_the_btc_community_in_one/). A tremendous amount of this aversion is justified[^n], and it was highly reinforced during the 2016-2017 Scaling War, in which the Core prevailed over its rivals.

[^n]: Much of it is cognitive dissonance -- it is the only way someone can process a world, where they work hard to make obscure and under-appreciated changes to Bitcoin, while meanwhile the ICO scam down the street gets $30 million dollars in a weekend.

The problem, is that the engineering task of "how to sidechain", is basically the task of "how to most efficiently abandon the mainchain host software".

This simply baffles most Bitcoiners -- experts and laypeople included. They have been trained to think that Core is the best, and everyone using non-Core software is evil or misguided.

<!--
#### i. Upside Down

Drivechain was originally proposed around 2015-2017. Those years saw the rise of BitcoinXT, Classic, Unlimited, BCH and SV. They saw four Scaling Bitcoin conferences, and a dramatic loss of BTC's marketshare and relative recognizability[^n].

[^n]: By this, I basically mean that popular media will use the word "crypto", where a few years earlier they would have used "Bitcoin". Compare the ["Bitcoin" episode](https://thegoodwife.fandom.com/wiki/Bitcoin_for_Dummies) of "The Good Wife" (Jan 2012), to the [crypto mentions](https://www.reddit.com/r/CryptoCurrency/comments/8hkvwz/billions_tv_show_references_cryptocurrency_and/) in the show "Billions" (May 2018).

All of that should have boosted attention on sidechains, and drivechain specifically. But it didn't, really.

In fact, I have noticed the reverse: when BTC marketshare seems to be recovers; Drivechain gets more attention.

It's all upside down! But why?



#### ii. Cognitive Dissonance

The experience of working on Bitcoin is, I think, primarily one of cognitive dissonance.

 ( Recall that this is the process of resolving contradictory mental states by falsifying one's preferences (the ["sour grapes"](https://en.wikipedia.org/wiki/The_Fox_and_the_Grapes) fable). )

The *typical* Bitcoin-intellectual, puts in years of high-effort R&D work. Laypeople are unable to properly recognize this work, due its specialized nature. So the work goes under-appreciated.

Meanwhile, all around them, people are getting super-rich. Many of these people know nothing about Bitcoin at all. Many of those who made the most, were people who were already rich and took a lucky gamble. The people who made the most --were Altcoiners / ICO scammers-- made millions overnight off of a "hot industry" and a few buzzwords. Adding insult to injury, many of these scam projects (all of the good ones, anyway) were literally constructed by Bitcoiners in the first place.

In general, these people make the Bitcoin community much worse. And so, these people are using CoreDev R&D to *harm* Bitcoin and enrich themselves.

#### iii. Core Good; Non-Core Bad

As a result of this, 


-->


<!--
### 6. BTC-Sidechains Are Pro-User, But Anti-CoreDev

If someone is a Bitcoin CoreDev, then we may safely presume that their work is motivated by a desire to "make Bitcoin Core great". In contrast, the premise of sidechains is that Core is irredeemable, and we need to abandon ship.

This divergence in perspectives is shocking:

|Topic|Flattering View (Anti-Sidechain)|Pessimistic View (Pro-Sidechain)|
|:---:|:------------------------------:|:------------------------------:|
|Bitcoin Core Software...|... is ideal.|...has imperfections; improvements to Core are often blocked by self-interested Core-elites.|
|CoreDevs...|...are statesmen and innovators.|...are Feudal Lords who justify a hierarchy in which they are dominant.|
|Bitcoin Users...|...are all very happy with Core.|...are often unhappy with Core, but stay because they are (for now) enslaved to Core's network effects.|
|Non-Core People...|...are always incorrect/evil.|...often have great ideas to contribute.|

Ultimately, the anti-sidechain perspective is loyal to Bitcoin *workers*, whereas the sidechain-perspective is loyal to Bitcoin *users*. And the latter perspective is rude, almost frighteningly so.

So I don't blame many Core-supporters if they find it to be literally unthinkable (any more than I would blame FED researchers who don't see the point of Bitcoin).

-->

### 5. Unfortunate Timing / "Miners Are Bad NPCs Cheer"

Drivechain was published in Nov 2015, and I presented it at Scaling III (Oct 2016). After the first half of day one of that conference, miners walked out and immediately begin the contentious 'SegWit blockade'. In response, Bitcoin's cultural, political, and intellectual leaders moved quickly to discredit and marginalize the mining communities.

For better or for worse, they succeeded. Any talk of cooperating with miners quickly became passé, and it instead became fashionable to view miners with hatred and fear, to regard them as enemies of Bitcoin, and to dismiss them as being --not merely tame (as had previously been said), but-- pitiably inconsequential to anything

Drivechain grants miners some agency, especially in the creation/deletion of new sidechains. This is often interpreted as 'giving power to miners'. But it does not "give" power from one group to another; it creates power ex nihilo. After all, there are currently zero sidechains, and no way to create any. Furthermore, the created powers disable older more dangerous powers (such as miner-sourced hard-fork-campaigns unnecessary). And since mining is brutally competitive, they are less powers, and more "burdensome responsibilities" -- like switching an overachieving class from 'pass/fail' to 'letter grades' (groan!).

In a different time, this nuance would be easier to understand. But instead we live in the time of "miners are bad NPCs cheer".


### 6. Liquid and Contradicting Blockstream

Blockstream markets their Liquid product as "the first production sidechain":

But something in that phrase has to be false. Either [Liquid isn't a sidechain; or else (if sidechain is redefined) then Liquid isn't "the first" of that thing](http://www.drivechain.info/blog/liquid/).

The problem, is that --in order to actually launch [my real project](http://www.bitcoinhivemind.com/)-- I inadvertently need to create the Real First Bitcoin Prodution Sidechain. So, while I would much prefer to avoid contradicting Blockstream, in practice this is not possible. There's just no way to tell the truth about Drivechain without contradicting Blockstream.

Blockstream is extremely popular, and has a lot of money to award in acquisitions, consulting revenues, conference sponsorships, and sinecure jobs. And I do not give out such awards. So, the people who agree with them, shout it very loudly, and the people who agree with me, keep quiet about it for political reasons.

And as a result of all that, it just looks as though few people agree with the Drivechain project, or sees it as valuable. Ultimately, people invest less time understanding it. Which contributes to misunderstanding.


<!--

era
    miners bad npcs cheer


    but regular -- also manipulate the conditions under which they 'trust miners'

### 4. Stigma / "Trusting Miners" Misunderstanding

By channeling 3-6 months of sidechain activity into a simple 32-byte digest, Drivechain tries to emulate what Bitcoin Core already does with ["AssumeValid"](https://bitcoincore.org/en/2017/03/08/release-0.14.0/#assumed-valid-blocks).

For instance:

    Anyone who wants to verify all signatures using
    Bitcoin Core can still do so by starting the
    program using -assumevalid=0.
    ...
    The default assumed valid block in Bitcoin Core
    0.14.0 is #453354, 16 Februrary 2017...

Notice also that this process was accompanied by similar misunderstandings:

    checkpoints make it look like Bitcoin developers
    are deciding which chain is valid even though
    the intent was always to only accept the chain
    which the software had already decided was valid
-->

<!--

## Conclusion

Drivechain was published in Nov 2015, but misunderstandings about it persist to this day. Nearly all of these were anticipated (and dealt with) in the original post.

So it is worth asking why these misunderstandings persist. Above, I have listed some reasons why they might.
--->

--------

### Footnotes