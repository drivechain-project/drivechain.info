---
layout: page
title: Literature
---

### Specification

[Original Post and Specfication](http://www.truthcoin.info/blog/drivechain/)

To this, only three modifications have since been made:

* Introduction of [blind merged mining](http://www.truthcoin.info/blog/blind-merged-mining/).
* Forcing deposits to select the sidechain-UTXO as an input, such that all of the sidechain's money is always in a single UTXO.
* Lengthening the withdrawal period from a configurable "two weeks" to mandatory/standardized three months (13,150 ACKs), and removing the waiting period.


## Blog Posts

### Theory

* [Sidechain Governance via Miners](http://www.truthcoin.info/blog/contracts-oracles-sidechains/).
* [Drivechain OP Code, Sidechains vs Smart Contracts](http://www.truthcoin.info/blog/drivechain-op-code/).
* [Upgrading Smart Contracts to "Wise Contracts"](http://www.truthcoin.info/blog/wise-contracts/).

### Response to Criticism (re: "Miner Centralization")

* [The Mirage of Miner Centralization](http://www.truthcoin.info/blog/mirage-miner-centralization/)
* [Miner Threat Model and Equilibrium Analysis](http://www.truthcoin.info/blog/mining-threat-equilibrium/)
* [Blind Merged Mining](http://www.truthcoin.info/blog/blind-merged-mining/)



## Presentations


### Anarchapulco 2024

[pdf](https://www.drivechain.info/media/slides/ap-2024.pdf)
[pptx](https://www.drivechain.info/media/slides/ap-2024.pptx)
[speech](https://www.drivechain.info/media/slides/ap-2024-script.pdf)

### NABS 2023

[pdf](https://www.drivechain.info/media/slides/NABS-2023.pdf)
[pptx](https://www.drivechain.info/media/slides/NABS-2023.pptx)
[speech](https://www.drivechain.info/media/slides/NABS-2023-speech.pdf)


### PlebFi 2023

[pdf](https://www.drivechain.info/media/slides/plebfi-2023.pdf)
[pptx](https://www.drivechain.info/media/slides/plebfi-2023.pptx)


### Bitcoin++ 2023

[pdf](https://www.drivechain.info/media/slides/bitcoin-plus-2023.pdf)
[pptx](https://www.drivechain.info/media/slides/bitcoin-plus-2023.pptx)


### MIT 2023

[pdf](https://www.drivechain.info/media/slides/mit-2023.pdf)
[pptx](https://www.drivechain.info/media/slides/mit-2023.pptx)
[speech](https://www.drivechain.info/media/slides/mit-2023-speech.pdf)


### Baltic Honeybadger 2022 ### {#baltic-2022}

A 20 minute whirlwind tour of what Bip300 is, and what you could do with it. For a general audience.

* [Slides](/media/slides/baltic-2022.pdf)

### TabConf 2021 ### {#tabconf2021}

A 20 minute whirlwind tour of what Bip300 is, and what you could do with it. For a general audience.

* [Slides](/media/slides/tabconf2021.pdf)
* [Transcript](/media/slides/tabconf-speech.pdf)
* [Performed Live! w/ Audience Questions](https://youtu.be/reKjNYQSZaQ?t=23595)

### Bitcoin 2021 ### {#bitcoin2021}

A 15 minute whirlwind tour of what Bip300 is, and what you could do with it. For a general audience.

* [Slides](/media/slides/bitcoin2021.pdf)
* [Transcript](/media/slides/bitcoin2021-transcript.pdf)
* [Performed Live](https://www.youtube.com/watch?v=oga8Pwbq9M0)


### Modern Overviews ### {#about}

These are two good interviews, each recorded *after* the DriveNET software release:

1. [51 Minutes (0:26:00 to 1:17:40)](https://www.youtube.com/embed/VmN6riYe2tI?&rel=0&autoplay=1&start=1605&end=4660) during an Oct 14 Whalepool Talk on Bitcoin, Drivechain, and Hivemind
2. A [Let’s Talk Bitcoin Episode (#377)](https://letstalkbitcoin.com/blog/post/lets-talk-bitcoin-377-sidechains-drivechains-and-the-apple-store)


### ZCash Demo Video ### {#zside}

On [YouTube](https://www.youtube.com/watch?v=N33iJK2FdpE). Covers all the steps needed to use a ZCash sidechain on Bitcoin.


### Construct 2019 (at Consensus NYC) ### {#consensus-2019}

20 minute overview of Drivechain design and security model. Includes comparison with the Lightning Network.

* [Slides](/media/slides/construct-2019.pdf)
* [Transcript](/media/slides/construct-2019-speech.pdf)
* Video (coming soon)



### TabConf 2019 ### {#tab-2019}

I give an update on the state of Drivechain Peer Review. I also attempt to describe "leeching" --how different chains can attack each other-- and how Drivechain is the only thing that prevents it.

* [Slides](/media/slides/tab-2019.pdf)
* [Video](https://www.youtube.com/watch?v=uJSWSTEDOF0)
* Bonus: [Me on a panel](https://www.youtube.com/watch?v=V3cvH2eWqfU).

### Consensus and Dissent -- July 2018 ### {#bob}

Judging from the questions, some people were confused by this talk. So below is a 'watching guide'.

The talk was about sidechains, and was in two parts:

I. Sidechain myths:

  1. The myth that: "sidechain can have a **negative effects** on their parent chain(s), merely by existing".
  * This myth relies on the premise that "miners will yield to temptation that harms their network". It is false because it conflates revenue (costless benefit) with profit (benefits net of costs).
  * Moreover, it is irrelevant because it has nothing to do with sidechains (it applies to any offer of money anyone could make to a miner, including state-sponsored attacks, and merged-mined *Altcoins*).
  2. The myth that "**miners can steal** from sidechains".
  * In truth, miners "can" construct the blockchain in any way they "choose", and in so doing can can redirect all circulating BTC to themselves. The source of funds (sidechains, LN-channels, or base mainchain txns) makes no significant difference.
  * Proponents of this myth downplay, and even stigmatize, the only relevant aspect of the question: "Why aren't miners doing this today?", in other words: ["What are miners motivated to do?"](http://www.drivechain.info/media/meme3.png).
  3. The first myth is not only wrong, but backwards.
  * A sidechain's aggregate txn-fee-revenues must always exceed its aggregate node operating costs. The surplus profit, then, is converted to a higher equilibrium "security budget" (see [here](https://medium.com/coinmonks/bitcoin-security-a-negative-exponential-95e78b6b575#665a) and [here](http://www.truthcoin.info/blog/pow-and-mining/)).
  * So sidechain infrastructure is not only tame, but necessary. Without it, low-txn-fee Altcoins will proliferate, causing Bitcoins security budget to plummet. Mixed with Bitcoins low blocksize limit, the long-run implications are disastrous.

II. Agreeing on Consensus

  1. In Bitcoin, new software releases can either be optional or mandatory.
  * If they are optional, then LargeBlockers can solve their problems (including all scaling, blocksize, smart-contracting and protocol interoperability problems) with soft-forked extension blocks. But in our reality, their problems were not solved this way. Network upgrades have another feature, which I call ["loudness"](http://www.truthcoin.info/blog/protocol-upgrade-terminology/), which tends to make software upgrades mandatory.
  * However, absent sidechains, such a *mandatory* process [contradicts Nakamoto consensus](http://www.truthcoin.info/blog/against-the-hard-fork/), and reduces the concept of "running your own node" to meaninglessness.

[Watch it Here (41 mins)](https://www.youtube.com/watch?v=15lBZQTN-eg) 

[Slides](/media/slides/consensus-and-dissent.pdf)


### Overview and Misconceptions -- January 2018

This is the best presentation to watch, if you can only watch one. It has all the facts and almost all of the "criticisms".

[Slides](/media/slides/dc-overview-misconceptions.pdf)

[Video](https://www.youtube.com/watch?v=gUbGT70wy5k)


### Construct -- January 2017

"Overview / Teaser / Demo"

[Slides](/media/slides/psztorc-drivechain-construct-2017.pdf)


### Milan Presentation - October 2016 Sidechain Scaling

"Better Strategy Can Improve TX-Throughput, Even if it Can't Improve TX-Physics"

[Slides](/media/slides/psztorc-milan.pdf)

[Video](https://www.youtube.com/watch?v=Gzg_u9gHc5Q&t=6575s)


### Risk Analysis -- September 2016

1. [Intro](https://www.youtube.com/watch?v=0goYH2sDw0w&list=PLw8-6ARlyVciNjgS_NFhAu-qt7HPf_dtg&index=1)
2. [The Docile Miner](https://www.youtube.com/watch?v=91TufmffIDg&list=PLw8-6ARlyVciNjgS_NFhAu-qt7HPf_dtg&index=2)
3. [Bandwidth Paradox](https://www.youtube.com/watch?v=9Yl4zd5V1W8&list=PLw8-6ARlyVciNjgS_NFhAu-qt7HPf_dtg&index=3)
4. [Eq. Tx Fees in an Unconstrained Future](https://www.youtube.com/watch?v=YErLEuOi3xU&list=PLw8-6ARlyVciNjgS_NFhAu-qt7HPf_dtg&index=4)
5. [Orphaning and Conclusions](https://www.youtube.com/watch?v=0gRDuLWq0Vg&list=PLw8-6ARlyVciNjgS_NFhAu-qt7HPf_dtg&index=5)

[Slides](/media/slides/psztorc-sidechain-risks.pdf)

[Playlist](https://www.youtube.com/playlist?list=PLw8-6ARlyVciNjgS_NFhAu-qt7HPf_dtg)


### Sidechain Privatization -- May 2016

* "Smart Contract Ecology"
* "Why it isn't bad, that miners can rob a sidechain".

1. [Intro, Problem, and Outline](https://www.youtube.com/watch?v=xGu0o8HH10U&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=1)
2. [When Contracts Attack - Oracles](https://www.youtube.com/watch?v=2OOKgTSrITs&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=2)
3. [When Contracts Attack II - Stealing Bitcoin](https://www.youtube.com/watch?v=S-65G-fp9zM&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=3)
4. [The Benefits of Running Any Program (are Nonexistant)](https://www.youtube.com/watch?v=k3L2Rdz06NM&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=4)
5. [Why do we allow Contracts to "Censor" our "Freedom"?](https://www.youtube.com/watch?v=GsnDUAkwlOw&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=5)

[Slides](/media/slides/psztorc-sidechain-privatization.pdf)

