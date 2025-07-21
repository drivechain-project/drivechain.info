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
- Some asked about optimizing bandwidth. In the past, bandwidth was the bottleneck (and thus, the most important thing to optimize), but recently the bandwidth problem has basically solved itself. Some envelope math: at maximum size [1600 MB blocks / 10 mins], this comes to [12800 Mb/600 sec] or [21.3 mpbs]. Today's average USA down/up speeds are 200/50, which is already more than enough -- even after accounting for: IBD ("catching up"), jurisdictional arbitrage, queuing theory paradoxes, error, etc. Globally, bandwidth speeds are rising at about 20% per year -- *way higher* than the txn growth rate ([of 6.2%](https://www.truthcoin.info/blog/all-world-txns/)). And even the average is misleading -- phones will be on 5G; servers and desktops (ie, the relevant computer type, for nodes) will be on Gigabit. Today, a single Call of Duty update is now 37.4 GB -- we live in a new era of abundant internet. (Back in 2008, average USA internet down-speed was just 5 Mbps.)
 
---

