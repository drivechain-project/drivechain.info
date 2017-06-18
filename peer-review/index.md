---
layout: page
title: Peer Review
---


This page is under construction. When complete, it will contain things like "Endorsements", "ACK" (acknowledgements as 'acceptable'), or "Objections".

It will also contain links to relevant discussion on [bitcoin-dev] and [bitcoin-discuss]. It may also link to media or social media, if appropriate.

### My Meta-Review

1.  06.10.2017 -- [A Review of Bitcoin-Dev Discussions](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-June/014559.html)

### Mailing List Discussions

* [Original Request for Discussion](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-May/014364.html) -- See Discussion in [May](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-May/thread.html#14364) and [June](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-June/thread.html#14557)
* [Scaling Sidechain - Possible Edits to the Mainchain](https://lists.linuxfoundation.org/pipermail/bitcoin-discuss/2017-June/000147.html)
* [Scaling Sidechain - Capacity Planning](https://lists.linuxfoundation.org/pipermail/bitcoin-discuss/2017-June/000148.html)


## Endorsements

1. 12.06.2017 -- [Jimmy Song supports](https://medium.com/@jimmysong/how-to-give-everyone-more-control-b3391c0f7816) on grounds of political pragmatism.
2. 16.06.2017 -- [Luke-Jr weighs in](https://lists.linuxfoundation.org/pipermail/bitcoin-discuss/2017-June/000149.html) , this post later [became stickied on r/bitcoin](https://www.reddit.com/r/Bitcoin/comments/6hpkqd/how_to_get_both_decentralisation_and_the/).



## Objections (and Responses)


<h3 id="solana-wright">16.06.2017 -- Jasmine Solana / Dr. Craig Wright</h3>

#### Summary

Jasmine wrote [an article](https://calvinayre.com/2017/06/16/bitcoin/dont-let-syntax-fool-creative-sidechain-basically-return-banking/) , which is theoretically a critique of [Jimmy Song's piece](https://medium.com/@jimmysong/how-to-give-everyone-more-control-b3391c0f7816).

The title claims that the "sidechain is basically a return to banking". The article spends its first 316 words (66.2% of the total 477 words) summarizing sidechains for the reader. The very next sentence asserts that "sidechain is just another kind of **fractional reserve banking**, which could herald a return to banking as we know it." (emphasis added). Apparently, sidechains "remove scarcity" and they even put Bitcoin back at the mercy of the evil Central Bankers.

After making these claims, Jasmine supports them in only a single way (...after all, throw in another quote from Song and she's only got a scant three sentences left) which is to quote the [known](https://www.reddit.com/r/Bitcoin/comments/3w027x/dr_craig_steven_wright_alleged_satoshi_by_wired/cxslii7/) [fraud](https://www.reddit.com/r/Bitcoin/comments/4hflr3/craig_wrights_signature_is_worthless/) Dr. Craig S. Wright so that he may assert four solitary words: “sidechains are bitcoin’s inflation”.

Jasmine's penultimate sentence is a doozy, and does more to discredit the article than anything I could write myself: "And since developers—who, let’s admit, do not have a strong understanding of economics—believe such things are irrelevant, this paves the way for groups who want inflation to gain control."

#### My Response

To the extent that this article is not a joke, it's central (and only) complaint is about inflation. Drivechain does not encourage inflation of any kind. In fact, the original mainchain Bitcoin that you know and love, is actually doing a kind of passive accounting for all sidechains. After all, how could it not? The deposits "to" a sidechain, or withdrawals "from" a sidechain, must -per the rules of softfork- be valid txns under all old rules.

What is possible, is for a sidechain to have an error in which a Bitcoin is counterfeited. This would immediately result in a "bank run", where everyone would attempt to withdraw from the sidechain, at the pegged 1:1 rate. Those who withdrew early would be paid in full, and those who withdrew late would not be paid at all. Thus the chain would go "bankrupt" immediately. In other words no one would do this intentionally (and it is pretty difficult to do mistakenly..just check make sum(inputs)=sum(outputs) a tx rule or block rule).

**Aside**: The origin of this myth is probably page 15 of [the Blockstream Oct 2014 paper](https://blockstream.com/sidechains.pdf) which has a section "Economic experimentation" (as well as p16's "Demurrage" and "Subsidy" sections). Even though the paper is clear on the inflation distinction, readers have departed from them confused. I distinctly recall, in Japan in July 2015, Warren Togami giving a sidechains talk, and people asked him questions about issuing more coins. Warren appeared to have no idea what they were even talking about, and when I interjected to reference the appropriate sections (from memory) Warren appeared to be surprised that such sections were in the paper, and said (something like) "I don't know why anyone would do that".

Certainly, Wright would scour the landscape for anything to use against [his arch-nemesis, Greg Maxwell](https://arstechnica.co.uk/information-technology/2016/08/craig-wrights-proof-that-he-invented-bitcoin-fuck-off-im-not-going-to-jump-through-hoops/).


<h3 id="slepak">16.06.2017 -- Greg Slepak</h3>

Possibly Solara is more influential than I thought! I can't recall ever hearing this "banking" comparison come up before. But, it seems to be spreading, because...

####  Summary

Here's Greg's actual critique:

https://twitter.com/taoeffect/status/876227634593583104

Here's my version of Greg's critique, which I wrote for fun, because Bitcoin isn't serious, it's about egos and making fun of people:

Later that very day, Greg [took to Twitter](https://twitter.com/taoeffect/status/875850514558210048) to express his opinion --which, in addition to $3.75 will get you an iced mocha frappuccino at Starbucks--  that the [Drivechain security model](http://www.truthcoin.info/blog/drivechain/#drivechains-security) is "a complete regression back to banking". He also [implied](https://twitter.com/taoeffect/status/875949046225031169) that DC would "[turn] miners into the exchange everyone goes through" and that DC "defeats the purpose of Bitcoin."

However, during the ensuring conversation, he admitted to have not done any background reading whatsoever. Mashuri Clark then asked ["If you’re not going to read up on it then why should anyone listen to your critiques?"](https://twitter.com/MashuriBC/status/875828093780230144) to which Greg replied ["I agree, they shouldn't"](https://twitter.com/taoeffect/status/875828528121495552).

#### My Response

[ Fill in with your response, less BS ]

## Footnote

Please [submit a pull request](https://github.com/drivechain-project/drivechain.info/blob/gh-pages/peer-review/index.md) or contact me with any links I've overlooked...if you think it is worth replying to. It is hard to track everything that's written!
