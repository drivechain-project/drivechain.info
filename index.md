---
layout: page
title: Drivechain
---


### Pitch

* Has [*scaling*](https://www.reddit.com/r/btc/comments/4zqd7g/roger_ver_does_your_bitcoin_classic_pool_on/d6yk872/?context=10000) got you down?
* Are your BTC [hodlings](https://bitcointalk.org/index.php?topic=375643.0) threatened by Ethereum, Z-Cash, Ripple, and Other Ethereum?
* Did you want to support every possible transaction type, but can't because core's [design is set in stone for the rest of its lifetime](http://satoshi.nakamotoinstitute.org/posts/bitcointalk/126/#selection-21.69-21.214)?
* Does 'using a separate currency at each individual store' sound like a dumb idea to you, so dumb that it contradicts the very *purpose* of [money](http://nakamotoinstitute.org/shelling-out/)?

If you think that blocks are too small, or too big, or that they should contain more message-types, or fewer message-types, or if you think the CoreDevs should be fired, or if you don't want anyone firing your favorite Devs, then sidechains might be for you!

### What are sidechains?

Sidechains are alternate chains of Bitcoin ("Alt-chains") which do *not* have their own token. To use them, individuals deposit BTC into the sidechain (at a 1:1 rate) which they later redeem (also at a 1:1 rate). Therefore, the total number of BTC currency units remains fixed at 21 million, no matter how many chains are used.

### Benefits of Sidechains

1. **Permissionless Innovation**: Anyone can develop / run their own code, without facing the (near-impossible) task of also bootstrapping a new unit of money.
2. **Anti-Scam**: SCs filter out get-rich-quick schemes (the 'get rich' part is now impossible). Therefore, good projects can stand out and receive our attention.
3. **Eliminates Competition**: Bitcoin will always have the best code, because it can copy any code that exists.
4. **Freedom to Choose**: Satoshi's consensus protocol requires everyone to agree on everything, down to the very last byte. Sidechains allow users to choose which benefits they would like to pay for.
5. **Faster Progress**: SCs let us test new features. The tests are safe -- if these features fail, they won't take down the main network. However, the tests are also informative -- real BTC is on the line.

### Peter Todd / Luke-Jr Told Me That Sidechains Are Insecure

Drivechain's security model is commonly misunderstood (and improved upon Blockstream's original 2014 conception), so here it is, short and simple:

1. When you send your BTC from a mainchain to a sidechain, what you are actually doing is putting it into a special account. Bitcoin miners "own" this account and can send these funds wherever they like.
2. That might sound like a problem, but it isn't because the box can only be opened infrequently (twice or three times a year), and a super-majority of miners must leave a note on the box stating exactly where they intend to transfer the money. Otherwise the money just stays there.
3. The only way anything can go wrong, is if miners leave a note on the box which doesn't match the note that the sidechain full node software auto-generated for them. It is easy to check because the notes are very short. Then, everyone in the Bitcoin community has to do nothing about the error, for *multiple months*.
4. This is unlikely because, if miners wanted to steal some money, they can already do so, much more easily, by [1] depositing BTC to an exchange, [2] selling for fiat (which they withdraw), and [3] rewriting the last 3 or 4 days of chain history, to un-confirm the deposit in step [1]. 

The lengthy delay might sound prohibitively inconvenient, but it isn't because of instant atomic cross-chain swaps. Investment-banker-types will buy your side-BTC with their main-BTC, at competitive rates.

### Demo Video and Screenshots

View our [Demo Video](https://drive.google.com/file/d/0B0apsclL6jccNEViRy00TThJd2M/view).

Two instances of Bitcoin, at time=0:

![shot-1](/media/shot-1.png)

Mine some mainchain Bitcoin, open the sidechain's "transfer" tab:

![shot-2](/media/shot-2.png)

Make a deposit (from mainchain to sidechain, these happen instantly):

![shot-3](/media/shot-3.png)

Make a withdrawal (from sidechain to mainchain, these are very slow):

![shot-4](/media/shot-4.png)

Time passes. Eventually the withdrawal is confirmed:

![shot-5](/media/shot-5.png)

The BTC has completed its round trip journey!

Check out the sidebar for more info.

### Contact

<p><u>Email:</u> truthcoin /at/gmail/</p>
<p><u>PGP Key:</u> <a href="https://pgp.mit.edu/pks/lookup?op=get&search=0xAA4B3330F162C410">F162C410</a></p>
<p>I attempt to respond immediately to all <a href="https://twitter.com/Truthcoin">Twitter</a> inquiries.</p>

