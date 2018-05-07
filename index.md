---
layout: page
title: Drivechain
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




Drivechain allows multiple blockchains to all agree to share the same 21,000,000 Bitcoins. These networks are otherwise autonomous.

### Problems With Today's Mono-Chain Setup

* Blockchain technology has **economic tradeoffs**, and [users disagree](https://www.reddit.com/r/btc/comments/4zqd7g/roger_ver_does_your_bitcoin_classic_pool_on/d6yk872/?context=10000) over the optimal tradeoff. But only one group can have their way at a time.
* Bitcoin [investors](https://bitcointalk.org/index.php?topic=375643.0) must worry about **competition** from other projects (Ethereum, Z-Cash, Ripple).
* Satoshi, creator of Bitcoin, [wanted to support many transaction types](http://satoshi.nakamotoinstitute.org/posts/bitcointalk/126/#selection-21.69-21.214), but knew that his design was **prohibitively inflexible**.
* Bitcoin is supposed to be used as [money](http://nakamotoinstitute.org/shelling-out/), but if it cannot be used on some networks, it is **constrained** as a medium of exchange -- and therefore at a competitive disadvantage.

Instead, sidechains are alt-chains that all use the same Bitcoin token. They start with zero coins; they accept Bitcoin deposits, conduct Bitcoin transfers, and finally dispense Bitcoin withdrawals.


### Presentation

<iframe width="560" height="315" src="https://www.youtube.com/embed/gUbGT70wy5k" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


### Memes



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

<div class="clearfix"></div>





### Drawback

Drivechain (intentionally) offloads some message-processing to other chains, and doesn't check up on them.

Instead, Drivechain uses incentives and asymmetric processing to guarantee correctness of the side-to-main ("withdrawal") messages:

1. Withdrawals must be publicly announced in advance.
2. They are strongly rate-limited: only a few valid withdrawals per year.
3. They must be willfully and consistently endorsed by a hashrate majority.

Thus, the network will only accept an incorrect withdrawal under one condition: if a hashrate majority *wants* it to be incorrect.

This is justified by observing that, in our pre-sidechain world, miners always want things to be correct. In theory, the [incentives of miners and investors](http://www.truthcoin.info/images/bitcoin-incentives.png) are very strongly aligned: both are compensated most when the exchange rate is highest. And, in practice, we do *not* see large reorganizations (where miners can "steal", by first depositing BTC to major exchanges, then selling that BTC for fiat (which they withdraw), and finally rewriting the last 3 or 4 days of chain history, to un-confirm the original deposits). These reorgs would devastate the exchange rate, as they would cast doubt on the entire Bitcoin experiment. The thesis of Drivechain is that sidechain-theft would also devastate the exchange rate, as it would cast doubt on the entire *sidechain* experiment (which would itself cast doubt on the Bitcoin experiment, given the anti-competitive power of sidechains).

More on Drivechain's [security model](http://www.truthcoin.info/blog/drivechain/#drivechains-security).

Please [read the FAQ](/faq/index.html)!



### The Box Metaphor

Here is a short metaphor for the risks of using a sidechain:

1. When BTC are deposited (from mainchain to sidechain), they are placed into a special account. Miners "own" this account, and can send these funds wherever they like.
2. That might sound like a problem, but it isn't because the box can only be opened infrequently (two or three times a year), and a super-majority of miners must leave a note on the box in advance. This note states exactly where the miners intend to transfer the money. The "correct" note is automatically generated by sidechain software, and is easy to check.
3. So, to steal, miners need to write an invalid note on the box, and leave it there for multiple months. Then, if no one interferes, the sidechain is robbed.

The lengthy multi-month delay might sound prohibitively inconvenient, but it isn't because of instant atomic cross-chain swaps. Investment-banker-types will buy your side-BTC with their main-BTC, at competitive rates. So, in practice, the delay can be avoided by paying a neglibible, market-based fee.

The model is sound because we assume that miners are uninterested in "stealing" (see above). 

### Bitcoin Improvement Proposals (BIPs)

Drivechain is so big it actually fits into two BIPs over three files:

1. [drivechain-bips.md](https://github.com/drivechain-project/docs/blob/master/drivechain-bips.md)
2. [bip1-hashrate-escrow.md](https://github.com/drivechain-project/docs/blob/master/bip1-hashrate-escrow.md)
3. [bip2-blind-merged-mining.md](https://github.com/drivechain-project/docs/blob/master/bip2-blind-merged-mining.md)

See also:

* BIP pull requests, [#642](https://github.com/bitcoin/bips/pull/642) and [#643](https://github.com/bitcoin/bips/pull/643).
* The ["big diff"](https://github.com/drivechain-project/diff) (our code changes from Bitcoin Core) -- now broken down by [[ignorable] UI changes](/media/mainchainUIDIFF.html) and [[important] non-UI](/media/mainchainBMMDIFF.html).


### Demo Video and Screenshots

View our [Demo Video](https://drive.google.com/file/d/0B0apsclL6jccNEViRy00TThJd2M/view).

Some images of some BTC making a round-trip journey!

Two instances of Bitcoin, at time=0:

![image](/media/shot-1.png)

Mine some mainchain Bitcoin, open the sidechain's "transfer" tab:

![image](/media/shot-2.png)

Make a deposit (from mainchain to sidechain, these happen instantly):

![image](/media/shot-3.png)

Make a withdrawal (from sidechain to mainchain, these are very slow):

![image](/media/shot-4.png)

Time passes. Eventually the withdrawal is confirmed:

![image](/media/shot-5.png)

The roundtrip journey is complete!

Check out the sidebar for more info.


### Main Benefits

1. **Permissionless Innovation**: Anyone can create a new blockchain project, without facing the (near-impossible) task of also bootstrapping a new unit of money.
2. **Eliminates Competition**: Bitcoin will always have the best code, because it can copy any code that exists.
3. **Freedom to Choose**: Satoshi's consensus protocol requires everyone to agree on everything, down to the very last byte. Sidechains allow users to choose which benefits they would like to pay for.

### Other Benefits

1. **Anti-Scam**: SCs filter out get-rich-quick schemes (the 'get rich' part is now impossible). Therefore, good projects can stand out and receive our attention.
2. **Faster Progress**: SCs let us test new features. The tests are safe -- if these features fail, they won't take down the main network. However, the tests are also informative -- real BTC is on the line.

### Contact

<p><u>Email:</u> truthcoin /at/gmail/</p>
<p><u>PGP Key:</u> <a href="https://pgp.mit.edu/pks/lookup?op=get&search=0xAA4B3330F162C410">F162C410</a></p>
<p>I attempt to respond immediately to all <a href="https://twitter.com/Truthcoin">Twitter</a> inquiries.</p>

