---

## Lightning BMM Request

    Paul Sztorc
    2019-07-23


### Summary

It is possible to send a Blind Merged Mining (BMM) Request over the Lightning Network.

( See [Bip301 "BMM Request"](https://github.com/bitcoin/bips/blob/master/bip-0301.mediawiki#bmm-request) for a description of an on-chain BMM Request. )


### Basics

These "Lightning BMMRs" require Simon to have a LN-channel pathway open with at least one Mary.

They consist of the following information:

<pre>  
    4-bytes - Message header (0xD0520C6E)   
    1-byte - sidechain number
    32-bytes  - h* side:merkle hash
    32-bytes  - prevSideBlockHash   
</pre>

### An extra configuration requirement for Mary

With OnChain BMMRs, Simon could reuse the same h\* all he wanted, because only one OnChain BMMR can be included per main:block per sidechain.

In LNs, the BMMRs are invisible. So, instead, Simon will need to ensure that he '''gives each Mary a different h\*'''. Simon can easily do this, as he controls the side:block and can simply increment a side:nonce somewhere. With a unique h\* per Mary (or, more precisely, per channel), and at most 1 h\* making it into a block (per sidechain), Simon can ensure that he is charged, at most, one time.

### An Example

That's probably confusing, so here is an example, in which: Simon starts with 13 BTC, Mary starts with 40 BTC, the side:block's tx-fees currently total 7.1 BTC, and Simon is keeping 0.1 BTC for himself and paying 7 BTC to Mary.

We start with (I):

<pre>
    Simon 13 in, Mary 40 in ; 53 in total
        Simon's version [signed by Mary]
            13 ; to Simon if TimeLock=over; OR to Mary if SimonSig
            40 ; to Mary
        Mary's version [signed by Simon]
            40 ; to me if TimeLock=over; OR to Simon if MarySig
            13 ; to Simon
</pre>


And both parties move, from there to (II):

<pre>
    Simon 13 in, Mary 40 in ; 53 in total
        Simon's version [signed by Mary]
            6 ; to Simon if TimeLock=over; OR to Mary if SimonSig
            40 ; to Mary
            7 ; to Mary if critical data requirements met; OR to Simon if LongTimeLock=over
        Mary's version [signed by Simon]
            40 ; to Mary if TimeLock=over; OR to Simon if MarySig
            6 ; to Simon
            7 ; to Mary if critical data requirements met; OR to Simon if LongTimeLock=over
</pre>


From here, if the h\* side:block in question is BMMed, they can proceed to (III):

<pre>
    Simon 13 in, Mary 40 in ; 53 in total
        Simon's version [signed by Mary]
            6 ; to Simon if TimeLock=over; OR to Mary if SimonSig
            47 ; to Mary
        Mary's version [signed by Simon]
            47 ; to me if TimeLock=over; OR to Simon if MarySig
            6 ; to Simon
</pre>

If Simon proceeds immediately, he removes Mary's incentive to care about blocks being built on this side:block. If Simon's side:block is orphaned, he loses his 7 BTC. Simon can either play it safe, and wait for (for example) 100 side:blocks before moving on (ie, before moving on to the third LN txn, above); or else Simon can take the risk if he feels comfortable with it.

If the h\* side:block is not found, then (II) and (III) are basically equivalent to each other. Simon and Mary could jointly reconstruct (I) and go back there, or they could proceed to a new version of II (with a different h\*, trying again with new side:block in the next main:block).

### Accepting the Request

While LN BMMRs are quite different from on-chain BMMRs, both are Accepted in the exact same way.
