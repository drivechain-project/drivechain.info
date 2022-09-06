---
layout: page
title: Drivechain (BIPs 300+301)
subtitle: "when devs compete, users win"
---


<head>
<style>
div.gallery {
    border: 1px solid #ccc;
}

div.gallery:hover {
    border: 1px solid #777;
}

div.gallery img {
    width: 100%;
    height: auto;
}

div.desc {
    padding: 15px;
    text-align: center;
}

* {
    box-sizing: border-box;
}

.responsive {
    padding: 0 6px;
    float: left;
    width: 24.99999%;
}

@media only screen and (max-width: 700px){
    .responsive {
        width: 49.99999%;
        margin: 6px 0;
    }
}

@media only screen and (max-width: 500px){
    .responsive {
        width: 100%;
    }
}

.clearfix:after {
    content: "";
    display: table;
    clear: both;
}



</style>
</head>

## **[DOWNLOAD Software](http://www.drivechain.info/releases/index.html)** -- **[LEARN on YouTube](https://www.youtube.com/watch?v=NK2IvzDz7pk&list=PLw8-6ARlyVciMH79ZyLOpImsMug3LgNc4&index=1)**

### Peer-to-Peer Bitcoin Sidechains

Drivechain allows Bitcoin to *create*, *delete*, *send BTC to*, and *receive BTC from* ["Layer-2"s](https://www.binance.vision/glossary/layer-2) called "sidechains". Sidechains are Altcoins that lack a native "coin" -- instead, pre-existing coins [from a different blockchain] must first be sent over.

Once on a sidechain, coins can change hands an unlimited number of times, and in an unlimited number of *new ways*. Thus, BTC-owners can opt-in to [new features or tradeoffs](http://www.drivechain.info/projects/index.html). Meanwhile, the Bitcoiners who don't opt-in, never need to care what any sidechain is doing.

Transfers from sidechain back to the mainchain (ie, from Layer 2 back to Layer 1) are not done via *verifiable proof*, but instead via *conjecture-and-refutation*. A "bundle" of transfers is asserted, and then slowly "ACKed" over time. After 3 months of ACKing, the bundle succeeds. Thus, the SC:BTC market price cannot deviate significantly from a 1:1 ratio. [More info](http://www.drivechain.info/literature/index.html#consensus-2019).


### Better for Everyone

* **Users** -- Get (eventually) *every* feature of every crypto-coin.
* **Investors** -- Permanent solution to the problem of rival coins (and hard-forking).
* **Miners** -- Automatically collect txn fees from all chains at once (no node software needed).
* **Developers** -- Freedom to manage your own blockchain, and to keep out those who would ruin your masterpiece.


### At Bitcoin 2021

<iframe width="560" height="315" src="https://www.youtube.com/embed/oga8Pwbq9M0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### ZCash Sidechain Demo

<iframe width="560" height="315" src="https://www.youtube.com/embed/N33iJK2FdpE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### The Tradeoffs

It is very risky for Bitcoin to go *without* Drivechain.

![image](/media/risk-tradeoffs.png)


### BIPs

Drivechain is made of two BIPs:

1. [**BIP 300 (Hashrate Escrows)**](https://github.com/psztorc/bips/blob/master/bip-0300.mediawiki) -- "Container UTXOs" that compress 3-6 months of transaction data into a fixed 32-bytes.
2. [**BIP 301 (Blind Merged Mining)**](https://github.com/psztorc/bips/blob/master/bip-0301.mediawiki) -- A technique to replace the act of running a sidechain node with the act of including a single high-fee transaction.


### Selected Recent Podcasts

1. [Van Wirdum Sjorsnado #23](https://twitter.com/BitcoinMagazine/status/1350133309213454340) -- (see my [comments](https://twitter.com/Truthcoin/status/1350183458321141763))
2. [51 Minutes (0:26:00 to 1:17:40)](https://www.youtube.com/embed/VmN6riYe2tI?&rel=0&autoplay=1&start=1605&end=4660) during an [Oct 14 Whalepool Talk on Bitcoin, Drivechain, and Hivemind](https://www.youtube.com/watch?v=VmN6riYe2tI)

Per [learning theory](https://en.wikipedia.org/wiki/Curse_of_knowledge), here is [an explainer written by someone who just learned](https://fiatjaf.alhur.es/drivechain.html) Drivechain (as is the Sjornado #23).


### Key Benefits

*Only* obtainable via Drivechain:

* Three existential threats to BTC are neutralized -- [altcoin-competition](http://www.drivechain.info/faq/#alt-death), [hard fork](http://www.truthcoin.info/blog/against-the-hard-fork/) [campaigns](https://www.coindesk.com/bitcoins-bogeyman-cometh-segwit2x-51-attack), and [extension block](http://www.drivechain.info/faq/#ext-blocks) [campaigns](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-April/014004.html).
* BTC development becomes anti-fragile with respect to CoreDev mistakes.
* BTC maintains [hashrate security in the long run](http://www.truthcoin.info/blog/security-budget/).
* BTC can [scale to credit-card level txn-processing](http://www.truthcoin.info/blog/gigachain/) -- **without changing the [CONOP](http://www.truthcoin.info/blog/measuring-decentralization/) of Bitcoin Core**. These cheap txns have [optimal fungibility](http://www.truthcoin.info/blog/deniability/) and [supply vital pretext](http://www.truthcoin.info/blog/expensive-privacy/#3-applied-to-bitcoin-itself) to the BTC ecosystem. 
* BTC gains [new, experimental abilities](http://www.drivechain.info/projects/index.html), especially [P2P event derivatives](http://bitcoinhivemind.com/).


### Critiques and Controversy

View [the main critiques of Drivechain](http://www.drivechain.info/peer-review/peer-review-new/).

Please [read the FAQ](/faq/index.html)!

Read [Why Drivechain is Hard for Bitcoiners to Understand](https://www.drivechain.info/blog/hard-to-understand/).


### Pro-Drivechain Evidence

* The ever-present **disagreement over consensus rules** (blocksize controversy, rise of Ethereum/Altcoins, BCH/BSV/Amaury split, activation logic disputes). Cultural enforcement of meta-consensus has attracted [sociopath](https://meaningness.com/geeks-mops-sociopaths) "guardians of Bitcoin" who are making everyone miserable.
* The degree of **heterogeneity among people** (some preferring govt-aligned exchanges and custodial wallets, others always running a full node, others preferring Electrum, etc). If BTC caters only to the paranoid, then it can never be mainstream; we must somehow please everyone. 
* The **unwillingness of txn fees to rise** *above* $5 (and to *stay above $5 permanently*), see [here](http://www.truthcoin.info/blog/security-budget/).


### Getting Started

Go [here for a guide on **downloading and using this software**](http://www.drivechain.info/blog/usage-tour/). It has screenshots to help walk you through the process.

Hang out with us by [joining](https://t.me/joinchat/C-POgRCPpB_-ki-csUGE9g) the [Drivechain Telegram Group](http://t.me/DcInsiders).

Check out this [this blockexplorer](https://explorer.drivechain.info/), and this [SideShift (Instant Sidechain Withdrawal Service)](http://sideshift.ai) project, by [@abrkn](https://twitter.com/abrkn).


<!--
  
### The Catch

Drivechain (intentionally) offloads some message-processing to other chains, and doesn't check up on them.

Instead, Drivechain uses incentives and asymmetric processing to guarantee correctness of the side-to-main ("withdrawal") messages:

1. Withdrawals must be publicly announced in advance.
2. They are strongly rate-limited: only a few valid withdrawals per year.
3. They must be willfully and consistently endorsed by a hashrate majority.

Thus, the network will only accept an incorrect withdrawal under one condition: if a hashrate majority *wants* it to be incorrect.

This is justified by observing that, in our pre-sidechain world, miners always want things to be correct. In theory, the [incentives of miners and investors](http://www.truthcoin.info/images/bitcoin-incentives.png) are very strongly aligned: both are compensated most when the exchange rate is highest. And, in practice, we do *not* see large reorganizations (where miners can "steal", by first depositing BTC to major exchanges, then selling that BTC for fiat (which they withdraw), and finally rewriting the last 3 or 4 days of chain history, to un-confirm the original deposits). These reorgs would devastate the exchange rate, as they would cast doubt on the entire Bitcoin experiment. The thesis of Drivechain is that sidechain-theft would also devastate the exchange rate, as it would cast doubt on the entire *sidechain* experiment (which would itself cast doubt on the Bitcoin experiment, given the anti-competitive power of sidechains).

There are also [situations where we'd *want* 51+% hashrate to redirect a sidechain's funds](http://www.truthcoin.info/blog/contracts-oracles-sidechains/). So it is important to ensure that, in these cases, miners actually do direct the refunds (to themselves). More on Drivechain's [security model](http://www.truthcoin.info/blog/drivechain/#drivechains-security).



### The Box Metaphor

Here is a short metaphor for the risks of using a sidechain:

1. When BTC are deposited (from mainchain to sidechain), they are placed into a special account. Miners "own" this account, and can send these funds wherever they like.
2. That might sound like a problem, but it isn't because the box can only be opened infrequently (two or three times a year), and a super-majority of miners must leave a note on the box in advance. This note states exactly where the miners intend to transfer the money. The "correct" note is automatically generated by sidechain software, and is easy to check.
3. So, to steal, miners need to write an invalid note on the box, and leave it there for multiple months. Then, if no one interferes, the sidechain is robbed.

The lengthy multi-month delay might sound prohibitively inconvenient, but it isn't because of instant atomic cross-chain swaps. Investment-banker-types will buy your side-BTC with their main-BTC, at competitive rates. So, in practice, the delay can be avoided by paying a neglibible, market-based fee.

The model is sound because we assume that miners are uninterested in "stealing" (see above).

-->


<!--
  out of date / in-flux; removed temporarily
### BIPs and Code Documentation

Drivechain is so big it actually fits into two BIPs over three files:

1. [drivechain-bips.md](https://github.com/drivechain-project/docs/blob/master/drivechain-bips.md)
2. [bip1-hashrate-escrow.md](https://github.com/drivechain-project/docs/blob/master/bip1-hashrate-escrow.md)
3. [bip2-blind-merged-mining.md](https://github.com/drivechain-project/docs/blob/master/bip2-blind-merged-mining.md)

See also:

* BIP pull requests, [#642]() and [#643](https://github.com/bitcoin/bips/pull/643).
* The ["big diff"](https://github.com/drivechain-project/diff) (our code changes from Bitcoin Core) -- now broken down by [[ignorable] UI changes](/media/mainchainUIDIFF.html) and [[important] non-UI](/media/mainchainBMMDIFF.html).

-->





## Screenshots

![image](/media/shot-6.png)

![image](/media/shot-7.png)

![image](/media/shot-8.png)

![image](/media/shot-9.png)


<!--

![image](/media/screenshots/both.png)

![image](/media/screenshots/mainchain.png)

![image](/media/screenshots/mainchain-2.png)

![image](/media/screenshots/sidechain.png)

![image](/media/screenshots/withdrawals.png)

![image](/media/screenshots/deposits.png)

![image](/media/screenshots/propose.png)


<div class="responsive">
  <div class="gallery">
  
    <a href="">
      <img src="/media/screenshots/both.png" alt="both" width="400" height="200">
    </a>
  
  </div>
</div>

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/screenshots/mainchain.png">
      <img src="/media/screenshots/mainchain.png" alt="mainchain" width="310" height="300">
    </a>
  
  </div>
</div>

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/screenshots/sidechain.png">
      <img src="/media/screenshots/sidechain.png" alt="sidechain" width="310" height="300">
    </a>
  
  </div>
</div>

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/screenshots/deposits.png">
      <img src="/media/screenshots/deposits.png" alt="deposits" width="400" height="200">
    </a>
  
  </div>
</div>

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/screenshots/withdrawals.png">
      <img src="/media/screenshots/withdrawals.png" alt="withdrawals" width="400" height="200">
    </a>
  
  </div>
</div>

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/screenshots/propose.png">
      <img src="/media/screenshots/propose.png" alt="propose" width="310" height="300">
    </a>
  
  </div>
</div>

<div class="clearfix"></div>

-->

## Explainer Memes

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme1.png">
      <img src="/media/meme1.png" alt="meme1" width="200" height="300">
    </a>
  
  </div>
</div>

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme2.png">
      <img src="/media/meme2.png" alt="meme2" width="200" height="300">
    </a>
  
  </div>
</div>

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme3.png">
      <img src="/media/meme3.png" alt="meme3" width="100" height="500">
    </a>
  
  </div>
</div>

<!--
<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme4.png">
      <img src="/media/meme4.png" alt="meme4" width="300" height="200">
    </a>
  
  </div>
</div>



<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme5.png">
      <img src="/media/meme5.png" alt="meme5" width="300" height="200">
    </a>
  
  </div>
</div>

-->

<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme0.png">
      <img src="/media/meme0.png" alt="meme0" width="400" height="200">
    </a>
  
  </div>
</div>



<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme-reqs.png">
      <img src="/media/meme-reqs.png" alt="meme-reqs" width="400" height="200">
    </a>
  
  </div>
</div>


<div class="responsive">
  <div class="gallery">
  
    <a href="/media/meme-vital-few.png">
      <img src="/media/meme-vital-few.png" alt="meme-vtial-few" width="300" height="200">
    </a>
  
  </div>
</div>


<div class="clearfix"></div>

## Even More Info

### Problems With Today's Mono-Chain Setup

* Blockchain technology has **economic tradeoffs**, and [users disagree](https://www.reddit.com/r/btc/comments/4zqd7g/roger_ver_does_your_bitcoin_classic_pool_on/d6yk872/?context=10000) over the optimal tradeoff. But only one group can have their way at a time. Instead we need multiple heterogenous layers ([Satoshi](https://bitcointalk.org/index.php?topic=1790.msg28917#msg28917), [Finney](https://bitcointalk.org/index.php?topic=2500.msg34211#msg34211)).
* Bitcoin [investors](https://bitcointalk.org/index.php?topic=375643.0) must worry about **competition** from other projects (Ethereum, Z-Cash, Ripple).
* Satoshi, creator of Bitcoin, [wanted to support many transaction types](http://satoshi.nakamotoinstitute.org/posts/bitcointalk/126/#selection-21.69-21.214), but knew that his design was **prohibitively inflexible**.
* Bitcoin is supposed to be used as [money](http://nakamotoinstitute.org/shelling-out/), but if it cannot be used on some networks, it is **constrained** as a medium of exchange -- and therefore at a competitive disadvantage.

Instead, sidechains are alt-chains that all use the same Bitcoin token. They start with zero coins; they accept Bitcoin deposits, conduct Bitcoin transfers, and finally dispense Bitcoin withdrawals.


### Main Benefits

1. **Permissionless Innovation**: Anyone can create a new blockchain project, without facing the (near-impossible) task of also bootstrapping a new unit of money.
2. **Eliminates Competition**: Bitcoin will always have the best code, because it can copy any code that exists.
3. **Freedom to Choose**: Satoshi's consensus protocol requires everyone to agree on everything, down to the very last byte. Sidechains allow users to choose which benefits they would like to pay for.

### Other Benefits

1. **Anti-Scam**: SCs filter out get-rich-quick schemes (the 'get rich' part is now impossible). Therefore, good projects can stand out and receive our attention.
2. **Faster Progress**: SCs let us test new features. The tests are safe -- if these features fail, they won't take down the main network. However, the tests are also informative -- real BTC is on the line.

## Contact

<p><u>Email:</u> truthcoin /at/gmail/</p>
<p><u>PGP Key:</u> <a href="https://pgp.mit.edu/pks/lookup?op=get&search=0xAA4B3330F162C410">F162C410</a></p>
<p>I'm usually on <a href="https://twitter.com/Truthcoin">Twitter</a> 8-9 AM and 5-6 PM.</p>

