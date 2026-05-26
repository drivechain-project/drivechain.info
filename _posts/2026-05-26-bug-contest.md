---
title: Summer 2026 Bug Hunt Hackathon!
show_author: true
comments: true
date: 2026-05-26 1:00:00
---

### Summary

LayerTwoLabs is paying **$100K** in an ongoing hackathon!

$20k per contest. One contest every two weeks. Five contests total.


### Objective

Your goal is to **find bugs** -- especially severe ones.

You compete against other people -- only **the top 3** bug-finders win, per period.

Some **bug-types** are worth more than others:

| Tier | Description                                                      |
|:----:|------------------------------------------------------------------|
|   1  | Network fork, loss of funds, inflation, or theft.                |
|   2  | Network crashes, mining halts, or txns fail to confirm.          |
|   3  | Performance degrades (significantly), software slows.            |
|   4  | Anything else -- strange graphical effects, mysterious behavior. |

...and some **repos** are more mission-critical than others:

| Tier | Description                    |
|:----:|--------------------------------|
|   1  | [Forknet](https://github.com/drivechain-forknet/drivechain-forknet) |
|   2  | [Bip300_301 enforcer](https://github.com/LayerTwo-Labs/bip300301_enforcer) |
|   3  | [Thunder](https://github.com/LayerTwo-Labs/thunder-rust), [zSide](https://github.com/iwakura-rein/thunder-orchard), [BitWindow](https://github.com/LayerTwo-Labs/drivechain-frontends) |
|   4  | [CoinShift](https://github.com/LayerTwo-Labs/coinshift-rs), [BitNames](https://github.com/LayerTwo-Labs/plain-bitnames), [BitAssets](https://github.com/LayerTwo-Labs/plain-bitassets) |
|   5  | [Photon](https://github.com/LayerTwo-Labs/photon), [Truthcoin-DC](https://github.com/LayerTwo-Labs/truthcoin-dc)           |


For more info on the software stack, click [here](https://drivechain.info/dev.txt).

### How to Score

There is a **hierarchy** of REPO-TYPE-QUANTITY.

For example, if you find **one single** Tier 1 bug, in ForkNet, then you will automatically get 1st place. **Unless** another team has also found that same bug (or another Tier 1 bug) -- in which case, you will tie, and the tie will be broken by any other bugs you have found.

Similarly, if no one finds any Tier 1 bugs, in any Tier 2 software -- but you find a Tier 2 bug in Tier 2 software, then you will win 1st place. Even if a rival team finds 300 Tier 3 bugs in Tier 2 software.

Also:

* You will *lose* points for low-quality submissions. If you submit a "bug" -- but upon closer inspection, it is **not** a bug, then you will be awarded *negative* points for that bug. So please only include a bug on your list, if you are certain that it is a true bug.
* We reserve the right to **unilaterally** decide who wins -- to disqualify people -- and to determine which bugs are "real" vs not.


### Prize Money

Money to be awarded as follows:

![image](/media/contest-2026/calendar-1.png)

![image](/media/contest-2026/calendar-2.png)

Let me clarify:

* Colors correspond to contest periods. The contest repeats every two weeks.
* The columns correspond to how many entrants there are.
* * If only one person enters the contest (and qualifies), then they will earn $20,000.
* * If three people enter the contest (and they all qualify), then 1st place gets $9,000, and 2nd and 3rd places each get $4,500.

To Qualify (as a potential winner), you must:

* Present us with **a list** of bugs.
* Include a (short) ReadMe where you explain...
* * ...what the bugs are,
* * ...and why they are bugs.


### More Details

* The submission window ends at **9 AM UTC Time, Wednesday** (5 AM Wednesday). For example, the first oen ends June 10th.
* You must pay a one-time fee of **$20 in telegram stars**, to enter -- (this deters spam entries, sorry). You only need to pay it once, the whole summer.
* Message Paul with your submission, by then! **@psztorc** on Telegram
* The *winner* will be announced by Thursday at 5 PM (NYC time). The bug lists will then be made public.
* You may collect your reward in either BTC, or USD.

### Even More Details

* If you find a bug in one of the rust-based L2s, then it will probably be in **all** of the rust-based L2s. So please **do not** list these out as "multiple" bugs. That is unnecessary.
* Our two previous contests ("zCash sidechain" and "Summer 2025 Performance") were a big success, so I'm optimistic about this one as well!!


## Contact

* @psztorc on Telegram
* @truthcoin on Twitter/X
