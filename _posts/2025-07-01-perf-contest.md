---
title: Summer 2025 Weekly Hackathon! 
show_author: true
comments: true
date: 2025-07-01 1:00:00
---

### Summary

LayerTwoLabs is paying $60,000 in an ongoing hackathon!

Six weeks, $10k per week!


### Objective

The **fastest time** wins!

1. Visit [thunder-rust](https://github.com/LayerTwo-Labs/thunder-rust/tree/2025-06-12-bench) and fork it (into a private repo).
2. Observe the [sync time](https://github.com/LayerTwo-Labs/thunder-rust/actions/runs/15978565282/job/45067511711) -- automatically calculated via GitHub Actions, which will run [cargo bench](https://github.com/LayerTwo-Labs/thunder-rust/blob/2025-06-12-bench/lib/state/bench.rs) via [check_lint_build.yaml](https://github.com/LayerTwo-Labs/thunder-rust/blob/2025-06-12-bench/.github/workflows/check_lint_build.yaml). (Currently 60.257 seconds, for 5x 160MB blocks).
3. Improve the performance -- and check your new score.
4. Message [Paul on Telegram](https://t.me/psztorc) -- (to deter spam, you must pay 405 stars ($5), sorry) -- saying "I am entering the contest, and I have read the whole announcement" -- and invite/link to your code!


### Prize Money

Money to be awarded as follows:

![image](/media/contest-2025/calendar.png)

Let me clarify:

* Colors correspond to contest periods. The contest repeats every week.
* The very first contest, is 2 weeks long (instead of 1 week).
* The columns correspond to how many entrants there are.
* * If only one person enters the contest (and qualifies), then they will earn $10,000.
* * If three people enter the contest (and they all qualify), then 1st place gets $4,500, and 2nd and 3rd places each get $2,225.
* The final contest, ends Aug 19, 2025 -- but may continue!
* Blocks are currently set to 160 MB -- but we may increase this, up to 800 MB, over the life of the contest.

Also, you only Qualify (as a potential winner) if:

* You improve the published sync time by **at least 5%**.
* Your code includes a (short) ReadMe where you explain...
* * ...what you decided to change,
* * ...and why.
* You did not "cheat" -- (by, for example, just commenting out all the validation code).

Drastic changes -- such as rewriting the codebase in a different language -- are technically allowed, but it will be very difficult for us to evaluate your work. So you may lose (if, for example, we feel we cannot trust the benchmark calculation).


### More Details

* The submission window ends on NOON, Eastern Time (NYC). So, the first submission window ends July 15th, at noon (in New York City).
* Message Paul with your submission, by then!
* The *winner* will be announced by Thursday at 5 PM (NYC time). Their *winning code* will be made public! (It will become the new reference implementation.)
* You may collect your reward in either BTC, or USD.


### Helpful Suggestions

* [Eric Voskuil](https://x.com/evoskuil) improved Bitcoin Core's performance by a staggering 50x (-98%). He obviously has an idea or two. Perhaps you should [study his work](https://github.com/libbitcoin/libbitcoin-system); or ask him for ideas.
* There's some useful information, at [drivechain.info/dev.txt](https://www.drivechain.info/dev.txt).
* (I'll add more suggestions here, if I think of any.)


### Fine Print

* We reserve the right to cancel this whole experiment (at any time) -- if it turns out to be a disaster.
* We also reserve the right to *increase* the prize amounts -- or award extra prizes, if there are many great submissions.


---

## Contest 1 Results! (And updates for Contest 2)

All the entries are **up** -- on [the public repo](https://github.com/LayerTwo-Labs/thunder-rust) as branches "contest1_1, contest1_2, ... contest1_5".

The **winners**, are:

1. 1st place -- "contest1_3"
2. 2nd place -- "contest1_1"
3. 3rd place -- "contest1_2"

Thanks to all who participated!

re: **Next Contest**. It took *longer than expected* for us to put up the new benchmark version. So we shall change the schedule as follows:

* No prize, no contest for July 22nd.
* The July 29th prize will be **doubled** in value. [$20,000 ; $17,600 ; $18,000]

The **[new benchmark software](https://github.com/LayerTwo-Labs/thunder-rust/tree/2025-07-18-bench)** is up, in the new branch "2025-07-18-bench". That's the version you must use, for Contest #2! Stay tuned, as we may still push an update or two, to it!

Notes:
- Some users discussed [*CUDA*](https://developer.nvidia.com/cuda-toolkit), and if it could be used. I say: *yes*. You must stick to hardware offered by Github-actions (I believe they have NVIDIA T4 GPUs). And you will be arbitrarily penalized if we make a CUDA vs CPU apples-to-oranges comparison.
- We had *no merkle tree* before -- but now we have a new, customized one. So that is probably ripe for optimization.
- We *will* increase the blocksize, to 320 Mb, in the next contest.
- Some asked about optimizing bandwidth. In the past, bandwidth was the bottleneck (and thus, the most important thing to optimize), but recently the bandwidth problem has -- more or less -- solved itself[^1].

[^1]: Some envelope math: at maximum size [1600 MB blocks / 10 mins], this comes to [12800 Mb/600 sec] or [21.3 mpbs]. Today's average USA down/up speeds are 200/50, which is already more than enough -- even after accounting for: IBD ("catching up"), jurisdictional arbitrage, queuing theory paradoxes, error, etc. Globally, bandwidth speeds are rising at about 20% per year -- *way higher* than the txn growth rate ([of 6.2%](https://www.truthcoin.info/blog/all-world-txns/)). And even the average is misleading -- phones will be on 5G; servers and desktops (ie, the relevant computer type, for nodes) will be on Gigabit. Today, a single Call of Duty update is now 37.4 GB -- we live in a new era of abundant internet. (Back in 2008, average USA internet down-speed was just 5 Mbps.)
 
---


## Contest 2 Results! (And updates for Contest 3)

Same as before, the [entries are up](https://github.com/LayerTwo-Labs/thunder-rust) as branches "contest2_1, contest2_2, ... ".

Same as before, we will **combine** into a **two-week** contest:

* No prize, no contest for Aug 5th.
* The Aug 12th prize will be **doubled** in value. [$20,000 ; $17,600 ; $18,000]

The **[new benchmark software](https://github.com/LayerTwo-Labs/thunder-rust/tree/2025-08-04-bench)** is "2025-08-04-bench". That's the version you must improve, for Contest #3!

Notes:
- Please do not update UtreeXo at this time. It is no longer part of the benchmark -- we might return to it later.
- We have increased the blocksize from 5x blocks 160 mb , to 10x blocks 320 MB.
- Unsafe code should include comments explaining why it is safe.
- We are now using a paid runner for benchmarks, and may adjust specs, so we advise against optimizing for specific runners.
- We will re-run the baseline, at the submission deadline. This is to account for variation in runners, and give accurate comparisons.

---

## Contest 3 Results!

Same as before, the [entries are up](https://github.com/LayerTwo-Labs/thunder-rust) as branches "2025-18-13-contest3_1, _2, _3, _4".

Same as before, we will **combine** into a **two-week** contest:

* No prize, no contest for Aug 19th.
* A **doubled** prize on Aug 26th.

The **new benchmark** is **[2025-08-19-bench](https://github.com/LayerTwo-Labs/thunder-rust/tree/2025-08-19-bench)** -- it is based on the winner of contest3, but with **960mb** blocks.

Notes:


- We have upgraded our runner, up one size, to 16-core 64 GB RAM.
- What is left to optimize? Probably only these:
- * switching to a thread-safe DB for parallel reads
- * using a GPU for merkle root computation & signature verification
- * switching to a faster elliptic curve/group
- FYI, during contest 3, everyone focused on allocations.

---

## Contest 4 Results!

The final entries [are up](https://github.com/LayerTwo-Labs/thunder-rust) as branches "2025-08-27-contest4_1, \_2, etc".

The winner was **entry 4_1** , who used CUDA / a GPU runner to [get a score](https://github.com/LayerTwo-Labs/thunder-rust/actions/runs/17293562461/workflow) of 303.50:

    *************
    YOUR SCORE:  303.50
    Verified 10x 960mb blocks in 303.50 seconds (mean) / 302.37 seconds (median).
    *************

At a [minimal txn size](https://www.truthcoin.info/blog/small-txns/#part-6-total--conclusion) of 138 bytes per txn, a 960 mB block comes to 6.95 million txns per block. At 600 seconds per block, this comes to a tps rate of 11,594. When we account for [my plan to have 13 cooperating L2s](https://www.truthcoin.info/blog/all-world-txns/#appendix-1--blockspace-napkin-math), the full txn rate is **150,722 transactions per second**.

## Conclusion

Since bandwith is no longer the bottleneck[^1], this means that our software can --today-- process over 50% of [the world's txns](https://www.truthcoin.info/blog/all-world-txns/#appendix-1--blockspace-napkin-math).

Obviously, the software will continue to improve. Obviously, supporting tech (CPUs, GPUs, bandwith, storage, etc) will also continue to improve.

To me, this settles the debate over whether "blockchains can scale". Actually -- they can. They just did! In fact, it is the Lightning Network crew who should probably prove -- to the rest of us -- why end users would want to deal with channel-opening, inbound liquidity, hot wallets, HTLCs, etc.

---

## Appendix 1: Cost

How expensive would these nodes be? Our contest paints a misleading picture, because we had to first *generate* an enormous pile of fake txns. To merely run a full node, would require a machine roughly between to Hetzer's EX44 (about 50 Euros per month) and Akami's G8-dedicated-64x16 ($560 month). We could eyeball it at **$3600 per year**.

In return for our $3600 per year, we are rewarded with a node that can do 11,594 tps. By dividing, we get a ratio of **3.22 tps per annual dollar**. (This ratio allows us to compare our largeblock node against other largeblock-node projects.)

---

### Footnotes

