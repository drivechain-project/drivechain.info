---
title: Spring 2020 Sidechain-Template Contest!
show_author: true
comments: true
date: 2020-04-18 5:00:00
---

### First of Two Announcments

First, *right now*, I will give the **Rules** and Guidelines.

Next, *Monday Apr20 at 5 PM EST*, I will give the specific challenge of *this* contest.

This way, you can examine the rules, decide if you want to participate or not!


## Rules

### Winning $$$ !

Here is a table showing what you can win! Your winnings depend on which date the *first place finisher* finishes (on EASTERN STANDARD TIME -- NYC, NY, USA time). After I confirm that someone has won first place, the contest will end in 36 hours, after which no one can finish!

![contest-table](/media/contest/contest-table.png)

Here are comments on the table:

* Over time, the payouts generally go up.
* * It might be clever (but risky) to wait until just-after-midnight EST, on certain days where the payoff is about to go up suddenly.
* * During the Red Period, the prize for a solo 1st-place finish goes down slightly.
* It is best of all to finish 1st! And worse of all to finish 4th (in which case you get nothing).
* 1st place *really* prefers that other people do not finish. That way they get to keep the biggest prize to themselves. Similarly, if two people finish 1st and 2nd, they are both hoping that no one finishes in 3rd.
* After the table ends, the contest is OVER. Which means that, if nothing is submitted before the last day of the calendar, then no prizes will be awarded at all. :-(


### What's the Goal?

How does one win the race?

The core task is do a "code transplant" from a mystery Altcoin Project [to be revealed Monday] into our **Sidechain Template** (see [here](https://github.com/drivechain-project/sidechains) and [here](https://www.drivechain.info/releases/index.html). And thus "turn an Altcoin into a Sidechain".

![contest-graphic](/media/contest/contest-graphic.png)

But, obviously, this will be much easier said than done!

And it will be much easier for some people than others. Some Altcoins were created by forking an older version of Bitcoin Core. The Sidechain Template was *also* created by forking an older version of Bitcoin Core. Thus, the *original creators* of these Bitcoin-derived Altcoins, would just need to redo something they had already done.

### Details on Deliverables

Here are the details:

1. You must email me at **paul-sc-contest-spring2020@protonmail.com**, with a message that says "I am entering the contest, and I understand that there are no prizes for 4th place and below".
2. You must send a "submission", including:
* Binaries (for fast testing). 
* The Source Code
* Source Code must contain -- a fully "Justified Diff" (see below)

Here are even more details:

1. The email MUST be sent BEFORE sending me any other deliverables.
* * But you can send it at any time.
* * I *might* use this information to announce (publicly), how many people have entered so far. Or I might not.
2. I will test the Binaries on some completely sterile VirtualBox 64-bit Ubuntu 18.04 machine, with nothing else on it. If your software fails, I will reset it back to a snapshot.
* By "test", I mean I will run a bunch of commands on the testchain-cli (you are not required to make any GUI or GUI-changes), to make sure that the sidechain template isn't broken, and that desire Altcoin-features have been faithfully replicated. (see below)
3. After checking the binaries, I will compile the source code.
* * The source code must compile to the binaries!
* * I am skilled enough to compile Bitcoin Core, as well as the sidechain template -- so for your sake I hope your entry is about-that-easy to compile.
4. The "Justified Diff" is the git "diff" between our sidechain template source code, and your sidechain-x source code. Every change that you make, must be "justified". Justification can be done in two ways.
* * The first, easiest, and most-preferred way, is to "cite your source". Ie, use a comment to hyperlink back to the Altcoin code-repository.
* * The second way is to write a comment-block explaining, in English, first: why you could not "cite Altcoin source-code" and second: explaining what the source code is doing. If I cannot make sense of your explanation, your submission will (probably) fail the test. Sorry! (see below)

### How Can I Ensure That My Submission Passes the Test?

* Many of these details will be in the Monday announcement.
* One important guideline is to *not break the Sidechain Template*. The submission must be able to do the things that it did, before you started messing with it, especially:
* * receive coins from the Mainchain,
* * find blocks (and reject invalid blocks, ban bad peers, etc)
* * send coins back from Sidechain to Mainchain back.
* The second guideline is to replicate the altcoin, "warts and all". Whatever "altcoin-cli does", "sidechain-cli" should do.


### Administrative Details

* I plan to check the contest inbox for new submissions, between the hours of noon-7 PM, Eastern Standard Time. And I plan to then test any new ones that have arrived.
* Submissions will be checked in the order they were received. In other words -- in whatever order they arrive in my protonmail inbox.
* As soon as I see a submission, I will tweet publicly (from @truthcoin) to announce it. I will include the time(s) the submission(s) arrived, so that everyone knows what the finish time is (and what "cell" we are all in, for the payouts above).
* If **your software fails**, then you aren't completely disqualified. You can try again.
* * However, you will henceforth be regarded as "low priority" -- so, if *anyone else* has any submission, I will check their submission first, before yours.
* * But if I'm in the middle of checking a submission (for any reason, ever), I won't drop everything and switch to a new one.
* * If you fail twice, then you become "low low priority". And so on. If I, at my sole and absolute discretion, feel that you aren't actual a serious submitter and are just wasting my time with endless nonsense submission, I reserve the right to disqualify you.


### More Commentary

* We are constantly fixing sidechain bugs! So, if something breaks, it *might* not have been your fault. Obviously, this could lead to a horrible mess, but our newest version has no *known* bugs, and it has a GUI that tries to explain very clearly what is going on.
* The "Justified Diff" isn't just for *my* benefit. *Anyone* who runs a sidechain full node will need to make sure that *they* know what it is doing. After all, as a layer-2, SC-nodes must have RPC-access to a full Bitcoin node.

---

#### Stay Tuned

More details will be posted HERE, in 48 hours (Monday 5 PM Eastern time).


---

### Zcash Sidechain! 



Zcash would make a pretty great sidechain of Bitcoin, don't you think?


1. **Much less work** -- Zcash is a code fork of Bitcoin. And so is our Sidechain Template! So, most of the source code already overlaps.
2. **Perfect Compliments** -- Bitcoin prides itself on its transparency and auditability (particularly with respect to the 21 million coin limit, and the validity of individual txns). However, as a result, it has some privacy drawbacks. Zcash is a great compliment -- it has extreme privacy but is a newer, riskier, technology.
3. **Synergy** -- Zcash alone is not "meta-private". But as an optional sidechain, it *is* meta-private. In other words, as a sidechain, you can privately use Zcash-tech, but publicly say "I have never used Zcash, and never will", and no one can prove you wrong. Also, Z-side would allow you to privately cash out Z-coins (to BTC), without interacting with another human being; with Zcash alone, one would need to find a counterparty (and, in practice, probably use a major exchange).

---


### The Task!

#### Summary

The Zcash Github is here: https://github.com/zcash/zcash
Our Sidechain Template (testchain-5.02) is here: http://www.drivechain.info/releases/index.html

You must take from the Zcash GitHub, and add to the Sidechain Template.

Here is [a specific list of all Zcash cli-commands](/media/all-zcash-commands-ordered.txt), that I have sorted and organized. The commands with double-asterisks are the ones you must focus on. The others you can just ignore.

You are NOT responsible for older zk-snarks (ie, you are responsible for sapling, NOT sprout). You are NOT responsible for any of the "deprecated", nor "experimental, disabled by default" features.

In general, these two commands are the main goal:

* z_merge
* z_sendmany

...and their subsidiary functions (ie: z_listaddress, and wallet management).

#### The Evaluation

I will test both softwares, by simply generating some new Zcash keys, and then running the exact same commands through both. I should get the exact same *output* from both!

Then I will try to withdraw some z-side test coin from its sidechain to its mainchain. 

That's it!


#### Helpful Notes (?)

* zcash's t-addresses are NOT exactly similar to our templates s-addresses. You can do whatever you like, but the smart thing is probably to modify the Zcash code to accept our s-addresses.
* You are NOT responsible for ANY of the other eccentricities of Zcash. For example, their Equihash stuff. You are only responsible for the zk-snarks.
* We have produced two pieces of software -- the "mainchain" and the "sidechain template" (called "testchain"). Both of these are Github forks of Bitcoin Core 16.99.
* To find sidechain blocks -- you must "mine regularly" on the mainchain ("setgenerate true" in the console) while enabling BMM on the sidechain. This is because the sidechain template is set up to use blind-merged-mining. (As always), you will need to wait 100 mainchain blocks, before spending any mainchain coins.

### Some References

* Here is a [Zcash explorer](https://explorer.testnet.z.cash/tx/cf4f3da2e434f68b6e361303403344e22a9ff9a8fda9abc180d9520d0ca6527d)
* Here is the Zcash protocol specification is here (although I'm not sure how helpful it will be): https://github.com/zcash/zips/blob/master/protocol/protocol.pdf
* Here are [some technical notes on Blind-Merged-Mining](/media/bmm-notes.txt) (used by the sidechain template).
* Here are the Drivechain BIPs -- [300](https://github.com/bitcoin/bips/blob/master/bip-0300.mediawiki) and [301](https://github.com/bitcoin/bips/blob/master/bip-0301.mediawiki). Ideally you should be able to ignore this completely.

---