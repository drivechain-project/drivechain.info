    Blind Merged Mining (BMM) Econ and Equilibrium Analysis
    Paul Sztorc
    2/19/2018


### Original Question

Is Blind Merged Mining (BMM) at a disadvantage [leading miners to avoid using it]?

### Setup

Let us create a scenario, and compare the base case (today's case) and the BMM case.

* "Mary" is a mainchain miner.
* "Simon A" and "Simon B" are both sidechain full nodes.
* "K" is a block on the sidechain network that is about to be found. It has transaction fees totaling 4 BTC.

### Base Case

In the base case, Mary either runs her own full node, or uses a pool who does this for her. The pool case regresses to the non-pool case (ie, the pool case removes Mary's need to run a node, leaves us with the equivalent question: "Will the pool be running its own sidechain full node, or will it be using BMM?"). BMM is either cheaper than running a node, or else it is not.

So, we designate "c" as "the cost of running the sidechain node". Thus, Mary's revenues are 4, and her profit is 4-c. Simon does nothing in the base case, and his revenues, costs, and profits are all zero.

### BMM Case

The BMM case can be modeled as an auction. Mary is basically auctioning off K to a room full of Simons. And the winning Simon will use K to earn 4 BTC for himself. So BMM is effectively as if Mary is auctioning off "4 BTC" to the highest bidder (she just doesn't realize this, nor does she care).

Aside: ( In practice, the value of the sidechain block will not be a static "4", but will instead be growing. In fact, it will be growing every second, as it should increase whenever a new sidechain txn is broadcast. For this reason, it is important that it be very cheap to increment one's bid. In a regular auction (ie, humans bidding on art), it is impractical to increment the bid by small amounts. But here the bids are negotiated digitally, and off-blockchain. While BMM bidding does not require the Lightning Network, it is LN-compatible. And since the LN is capable of negotiating [sub-satoshi payments](https://en.bitcoin.it/wiki/Lightning_Network), bidding increments should be sufficiently negligible. And so I will continue to assume that we are auctioning off a static K which is worth a static 4 BTC, as this is much simpler. )

As with all auctions, Mary will only take the highest bidder, and the losing Simon(s) walk away empty handed. So [strategic bidders](https://www.youtube.com/watch?v=pyLKkN5HpDY) will bid as closely to 4 BTC as possible. ( And, even if they are not strategic, the final sale price will approach 4 anyway. We only require that the minimum bid increment be very low [see above]. ) Of course, while the bids approach 4 BTC, they cannot reach 4 BTC -- Simon must be compensated for the hassle, and a bid of 4 BTC would leave him with zero surplus. I call the residual value that Simon retains "epsilon".

So in the BMM case, Mary's revenues are 4-e, and her costs are zero, so her profit is 4-e.

To answer the question, then, BMM will be disadvantaged when e > c.

### Paramter "c"

Even for the "lighter" regular mainchain Bitcoin, the parameter "c" is already high enough to [cause anxiety](https://coinjournal.net/adam-back-on-the-overlooked-importance-of-full-nodes-in-bitcoin/) [amongst experts](https://www.youtube.com/embed/TgjrS-BPWDQ?start=8582&rel=8634&autoplay=1), who [often comment](https://www.coindesk.com/jonas-schnelli-wants-run-bitcoin-full-node/) on the need for nodes and problem of declining full node count. This is probably NOT because the cost is so high, but instead because most users find the node to be unnecessary.

Redditors have, from time to time, investigated the cost of their mainchain Bitcoin nodes. One [in July 2014](https://www.reddit.com/r/Bitcoin/comments/29s74m/the_real_cost_of_running_a_bitcoin_node/) used AWS and found that the total cost was $20.43/month (nearly all bandwidth). The second [in Dec 2016](https://www.reddit.com/r/btc/comments/5i5zez/how_much_does_running_a_full_node_actually_cost/) concluded $13.2/month in the cheapest case (one which did not include bandwidth!), and $3.74 per month if only electrical power (!) were included. Both calculations are outdated and misleadingly cheap. Bitcoin.org publishes [minimum requirements](https://bitcoin.org/en/full-node#minimum-requirements) for full nodes, which include an internet connection with 200 GB of *upstream* bandwidth per month. This may itself cost $20-$50 per month. For a sidechain which is ten times the size of Bitcoin Core, the costs would tend to be roughly ten times higher ([we hope](https://www.youtube.com/watch?time_continue=7325&v=TgjrS-BPWDQ)).

For a sidechain which is *unpopular* (perhaps because it contains tech that greatly enhances user's privacy), the cost may be **infinite** because the bandwidth involved will be effectively un-buy-able by miners (in other words, un-buy-able by anyone with a fixed mailing address).

Of course, the more important parameter is "e". Because the lower "e" is, the more powerful BMM becomes in general. If "e" is $0.01 per block, then a sidechain full node can never cost more than [30\*24\*6\*.01]= $43.20 per month. Because if it costs higher, greedy miners (and greedy pools) will stop running the node, and switch to BMM.

### Parameter "e"

Simons compete on "e" -- whichever Simon sets the lowest "e" is the one who wins the auction (and thus, the one who sets the global "e"). Thus, "e" will be determined by the most pessimistic of all the Simons, as this Simon is the one who will bid closest to 4 (and the ultimate winner). So, Simons should be driving "e" down literally to the smallest value possible.

The lower bound of "e" is likely lower than "c", because BMM is trying to reuse sidechain full nodes that already exist. In other words, some users are already running the sidechain node, for their own (BMM-unrelated) purposes. They thus have access to a full node for free -- their own! So, for these users, the fullnode costs were already outweighed by benefits. And a full node already collects new transactions (ie "unconfirmed txns") in realtime. So the only thing for Simon to do (other than run different code, which is negligible), is maintain payment type channels with miners (or pools). With proper engineering, these channels should be very easy to create, and once created they should almost free to maintain. BMM is compatible with LN, but it can operate without LN as it requires even *less* effort (the non-LN version does require an on-chain txn fee, which would be by far the most expensive part of the process -- but this fee also goes to Mary, and so is irrelevant!).

Therefore, as long as at least one Simon refuses to collude, "e" should continue to fall until it is as literally as low as possible. We can be confident that they are not all colluding, because this would obviate their need to use a blockchain network in the first place!

Of course, no one knows what this paramter will fall to, in practice. Or whether or not sidechain full nodes will really be so much *more* cumbersome than mainchain nodes (to the point where it ever makes a difference to anything).

### Stability / Security / Insurance

If "e" were $1.00 per block (a much more "fun" number), this would amount to $4320 per month. This may seem high, but it perhaps is not. Supposedly, Namecoin software was strictly less stable than Bitcoin, and the Namecoin daemon would occasionally crash, bringing the entire mining setup to a halt. Supposedly, if not fixed quickly, this would cause some of the electrical equipment to fill up with excess electricity, and then literally explode.

The value of $4320 per month is overwhelmingly microscopic in the grand scheme of things. The BTC network offers 12.5 BTC per block in subsidy, and 1 BTC per block in fees. Let us imagine that a sidechain also offers 1 BTC per block in fees. This totals [ (12.5+1+1)\*6\*24\*30 ] = 62,640 BTC per month, or 693.4 million dollars in revenue (at 2/19/2018 prices). The "tips" (of $4320) are less then seven thousandths of one percent of that.

For a pool with 10% hashrate, one single 2 minute episode of unwanted downtime (as a result of buggy sidechain software under traditional merged mining) would represent a loss of earnings-potential. The lost revenue would be approximately [ (12.5+1+1) BTC \* 10% \* (2/10) ] = 0.29 BTC (or $3214.65). They can 100% prevent such outages by tipping $1.00 per block -- which for them will be $1 every 100 minutes, or $432 per month.

So the dillema is: 

* Pay $432 per month, no bugs no downtime.
* Pay 'node cost' per month + incur risk of bugs (each bug costs $3215 in downtime).

The breakeven is [3125b=432] = 0.13 bugs per month, or 1.61 bugs per year. If a sidechain has more than two of these "causes-a-2-minute-outage" bugs a year, then BMM is a winner on that basis alone. Or if it prevents a bug that would have caused a four-minute outage. (And this assumes that none of the equipment explodes.)

And, of course, *how can the miners tell* if a piece of sidechains technology is likely to have bugs or not? The only way is by making some effort to assess the project and its codebase. Miners can either put in this effort, or they can simply use BMM.




<!---



The final auction price will be driven ]] by the cost of updating the bid. I usually call this "epsilon", but for now I will call this the "minimum bid increment". In a traditional auction (ie, humans bidding on paintings), this would be some combination of [1] the bidders' cost of raising one's hand (including psychic cost of [re]deciding to bid), [2] the auctioneer's disinclination to increment the bid by very small amounts, and [3] the audience's disinclination to listen to slowly-incrementing bids for hours on end.

For example, imagine that the auctioneer (Mary in this case) requires bids to increase by at least 0.5 BTC. If "Simon A" originally has bid "0 BTC" for K, then the sequence of [naive] bids will be: 0.5 from Simon B, then 1.0 from Simon A again, then 1.5, 2.0, 2.5, 3.0, etc and finally a bid of 3.5 from "Simon B". At this point, "Simon A" has no reason to bid 4.0 (his surplus will be 4-4=0 if he does, and zero if he does not). Thus, the final price is 3.5. If at this point Mary changes her mind, and decides that, henceforth, bids can increase by 0.01, then "Simon A" will now happily bid 3.51 (and Simon B will, of course, reciprocate by bidding 3.52). The final price would be 3.99.

To belabor the point, if instead the minimum bid increment had been 0.8 BTC, the final price would have instead been 3.2, and the sequence of bids would have been 0, 0.8, 1.6, 2.4, 3.2. If the minimum bid increment had been 1.7, the sequence of bids would have been 0, 1.7, 3.4.

 if these agents were [strategically intelligent](https://www.youtube.com/watch?v=pyLKkN5HpDY), both Simons would immediately try to bid




3. To belabor the point, if Mary allows bids to increase by as little as 0.001 BTC, then bidding cannot stop at 3. Whichever of the two Simons is not currently winning

 refuses to allow small bids, or if small bids are too cumbersome for some reason, then the final auction price will be f

We can model BMM as an auction.

Mary, the mainchain miner, is auctioning off $200

--

--With drivechains, some part of the profit margin is kept by the non-mining DC nodes. .. Which means miners who operate these nodes themselves will be able to increase their profit margins, --

-->